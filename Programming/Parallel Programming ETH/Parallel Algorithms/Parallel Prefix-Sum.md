> [!Definition]
> **Parallel prefix-sum** computes an output array where `output[i] = input[0] + input[1] + ... + input[i]`.

## Core idea

The lecture uses two passes over a recursion tree:

1. **Up pass**: split the array recursively and compute the sum of every segment
2. **Down pass**: propagate a value called `fromLeft` from the root to the leaves
3. At each leaf, do a small sequential scan starting from `fromLeft`

The key rule in the down pass is:
- left child gets the parent's `fromLeft`
- right child gets the parent's `fromLeft + left.sum`
So the right subtree already knows the sum of everything that appears before it.

The usual sequential loop has `O(n)` work and `O(n)` span, but a tree-based parallel algorithm achieves `O(n)` work and `O(log n)` span. (This means the longest chain of dependencies is logarithmic)
## Example

For input
`[6, 4, 16, 10, 16, 14, 2, 8]`
the inclusive prefix-sum is
`[6, 10, 26, 36, 52, 66, 68, 76]`

During the up pass, the algorithm computes segment sums such as:
- left half `[0,4)` has sum `36`
- right half `[4,8)` has sum `40`
- whole array `[0,8)` has sum `76`

During the down pass:
- the root starts with `fromLeft = 0`
- the left half also gets `0`
- the right half gets `36`, because `36` is the sum of everything to its left

Each subtree repeats the same rule until it reaches a small chunk, where the final prefix values are written.
## Java Fork/Join example

The implementation below fits naturally with the [[Fork-Join Framework]].

```java
import java.util.concurrent.ForkJoinPool;
import java.util.concurrent.RecursiveAction;
import java.util.concurrent.RecursiveTask;

public class ParallelPrefixSum {
    private static final int THRESHOLD = 1_024;

    private static final class Node {
        final int lo;
        final int hi;
        int sum;
        Node left;
        Node right;

        Node(int lo, int hi) {
            this.lo = lo;
            this.hi = hi;
        }

        boolean isLeaf() {
            return hi - lo <= THRESHOLD;
        }
    }

    private static final class UpTask extends RecursiveTask<Node> {
        private final int[] input;
        private final int lo;
        private final int hi;

        UpTask(int[] input, int lo, int hi) {
            this.input = input;
            this.lo = lo;
            this.hi = hi;
        }

        @Override
        protected Node compute() {
            Node node = new Node(lo, hi);

            if (node.isLeaf()) {
                int total = 0;
                for (int i = lo; i < hi; i++) {
                    total += input[i];
                }
                node.sum = total;
                return node;
            }

            int mid = (lo + hi) >>> 1;
            UpTask leftTask = new UpTask(input, lo, mid);
            UpTask rightTask = new UpTask(input, mid, hi);

            leftTask.fork();
            Node right = rightTask.compute();
            Node left = leftTask.join();

            node.left = left;
            node.right = right;
            node.sum = left.sum + right.sum;
            return node;
        }
    }

    private static final class DownTask extends RecursiveAction {
        private final Node node;
        private final int fromLeft;
        private final int[] input;
        private final int[] output;

        DownTask(Node node, int fromLeft, int[] input, int[] output) {
            this.node = node;
            this.fromLeft = fromLeft;
            this.input = input;
            this.output = output;
        }

        @Override
        protected void compute() {
            if (node.isLeaf()) {
                int running = fromLeft;
                for (int i = node.lo; i < node.hi; i++) {
                    running += input[i];
                    output[i] = running;
                }
                return;
            }

            DownTask leftTask = new DownTask(node.left, fromLeft, input, output);
            DownTask rightTask = new DownTask(
                node.right,
                fromLeft + node.left.sum,
                input,
                output
            );

            leftTask.fork();
            rightTask.compute();
            leftTask.join();
        }
    }

    public static int[] compute(int[] input) {
        if (input.length == 0) {
            return new int[0];
        }

        int[] output = new int[input.length];
        ForkJoinPool pool = ForkJoinPool.commonPool();

        Node root = pool.invoke(new UpTask(input, 0, input.length));
        pool.invoke(new DownTask(root, 0, input, output));

        return output;
    }
}
```

For an **exclusive** prefix-sum, the down pass is the same, but the leaf scan writes the current `running` value before adding `input[i]`.

> [!Important]
> Prefix-sum is not just about addition. The same pattern works for other associative operations (see [[Reductions]]), which is why it appears in many parallel algorithms such as filtering, packing, and counting.
