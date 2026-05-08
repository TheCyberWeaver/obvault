> [!Definition]
> The **Fork/Join Framework** is a Java framework for parallelizing **divide-and-conquer** algorithms using a pool of worker threads and **work stealing**.

## Core idea

The basic pattern is:

1. split a large task into smaller subtasks (`fork`)
2. solve subtasks in parallel
3. combine the results (`join`)

This is especially useful when a problem can be solved recursively.

## Main classes

- `ForkJoinPool`: the thread pool that runs fork/join tasks
- `ForkJoinTask<V>`: base abstraction for tasks
- `RecursiveTask<V>`: a task that returns a result
- `RecursiveAction`: a task with no return value

Java also provides a **common pool**, which is often used by parallel streams and some other concurrency utilities.

## Work stealing

The framework uses **work stealing** for load balancing.
- each worker thread keeps a deque of tasks
- when a worker becomes idle, it steals work from another worker
- this helps keep all processors busy
![[Pasted image 20260323111359.png]]
This is one of the main reasons fork/join works well for irregular recursive workloads.
## Example

```java
import java.util.concurrent.*;

class SumTask extends RecursiveTask<Long> {
    private static final int THRESHOLD = 1000;
    private final int[] arr;
    private final int left;
    private final int right;

    SumTask(int[] arr, int left, int right) {
        this.arr = arr;
        this.left = left;
        this.right = right;
    }

    @Override
    protected Long compute() {
        if (right - left <= THRESHOLD) {
            long sum = 0;
            for (int i = left; i < right; i++) {
                sum += arr[i];
            }
            return sum;
        }

        int mid = (left + right) / 2;
        SumTask leftTask = new SumTask(arr, left, mid);
        SumTask rightTask = new SumTask(arr, mid, right);

        leftTask.fork();
        long rightResult = rightTask.compute();
        long leftResult = leftTask.join();

        return leftResult + rightResult;
    }
}

ForkJoinPool pool = new ForkJoinPool();
long result = pool.invoke(new SumTask(array, 0, array.length));
```

## Why compute one side directly?

A common idiom is:

- `fork()` one subtask
- `compute()` the other subtask in the current thread
- `join()` the forked subtask

This often reduces scheduling overhead compared with forking both sides immediately.

## When it is useful

- divide-and-conquer algorithms such as merge sort or quicksort
- tree and graph traversal with mostly independent subtasks
- large array or matrix computations
- CPU-bound tasks that can be split recursively

## When it is not ideal

- blocking I/O tasks
- tasks with too much shared mutable state
- extremely small tasks, where scheduling overhead dominates the useful work

If tasks block frequently, worker threads may sit idle and the framework becomes less effective.

> [!Important]
> Fork/Join is best for **CPU-bound**, **recursive**, and **mostly independent** tasks. It is not mainly a replacement for all multithreading in Java.
