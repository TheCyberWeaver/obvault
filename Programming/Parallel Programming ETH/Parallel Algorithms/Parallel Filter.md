> [!Definition]
> A **parallel filter** keeps exactly the elements whose corresponding entry in a filter array is `1`.

- `A = [7, 3, 9, 4]`
- `F = [1, 0, 1, 0]`
- output: `[7, 9]`

## Parallelize it

Use an **exclusive** [[Parallel Prefix-Sum]] on the filter array `F`.

If `P` is that prefix-sum, then `P[i]` tells us how many selected elements appear before index `i`.

So every index can work independently:

- if `F[i] = 1`, write `A[i]` to `output[P[i]]`
- if `F[i] = 0`, write nothing

The final output size is the total number of `1`s in `F`.

> [!Important]
> Parallel filter has `O(n)` work, and with parallel prefix-sum it can achieve `O(log n)` span.
