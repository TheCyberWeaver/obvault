---
tags:
  - linker-exclude
---
> [!Definition]
> A **map** applies a function independently to each element of a collection, producing an output collection of the same size.

one of the two most important and common patterns in parallel programming (the other one is [[Reductions]])

Map achieves `O(log n)` with Divide & Conquer


> [!Important] 
> Don't implement maps on Linked Lists. They require $O(n)$ time to access an arbitrary element, making divide-and-conquer less effective.

## Standard map

The usual form of map takes one input collection and a unary function.
If `A` is the input and `f` is the function, then:
$$
B[i] = f(A[i])
$$
Unlike [[Reductions]], a map keeps the number of elements the same.

## Zip map

If the function takes multiple inputs, we can extend the idea to a **zip map** or **element-wise map**. This applies a function to corresponding elements from multiple collections.

The output still has the same size as the input collections.

Example:
- element-wise addition of two arrays
$$
C[i] = A[i] + B[i]
$$

## Stencil

A **stencil** is closely related to a map, but each output element depends on a small neighborhood around the input position rather than just one corresponding element.

> [!NOTE]
> a stencil computation is often implemented by a kernel, but it doesn't have to be a kernel

Example:
- smoothing an array where `B[i]` depends on `A[i - 1]`, `A[i]`, and `A[i + 1]`


> [!Important]
> Maps parallelize well when each output element can be computed independently from the others.
