
> [!NOTE]
> See detailed quicksort algorithm and its time analysis in [[Quicksort]]

## Core idea
Like ordinary quicksort:
1. choose a pivot
2. partition the array into elements smaller than the pivot, equal to the pivot, and greater than the pivot
3. recursively sort the left and right parts

The parallelism comes from sorting the two recursive subproblems concurrently.

## Parallel partitioning

The hard part is the partition step.
A simple in-place partition is mostly sequential, so a common parallel version uses [[Parallel Filter]]:

- build a `0/1` flag array for elements `< pivot`
- build a `0/1` flag array for elements `== pivot`
- build a `0/1` flag array for elements `> pivot`
- use parallel filter / prefix-sum to pack each group into the output

Then recursively sort the `< pivot` and `> pivot` parts in parallel.

## Complexity

Expected work is still `O(n log n)`.

If partitioning is parallel and the splits are reasonably balanced, the span can be about `O(log^2 n)`. 

> [!Important]
> Parallel quicksort is a divide-and-conquer algorithm, but its performance depends heavily on the pivot quality and on whether partitioning is parallelized well.
