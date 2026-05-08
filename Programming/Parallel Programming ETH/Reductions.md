> [!Definition]
> A **reduction** computes a single result from a collection by combining elements with an **associative** operator.

one of the two most important and common patterns in parallel programming (the other one is [[Maps]])
## Core idea

Reductions are useful in parallel programming because we can compute partial results independently and then combine them afterward.

Reduction always achieve `O(log n)` parallel time
## Examples

- `sum`
- `product`
- `max`
- `count`
- histogram of test results, which can be seen as a variant of summing bucket counts

## Non-examples

- median
- subtraction
- exponentiation

These are not reductions in the same sense because they are not naturally based on an associative combine step.

## Sequential limits

Some computations are inherently sequential.

If processing `arr[i]` depends on the result of processing `arr[i - 1]`, then we cannot freely split the work and combine partial answers afterward.

> [!Important]
> Reductions parallelize well when the combine operator is **associative**. Strong step-by-step dependencies usually prevent that.
