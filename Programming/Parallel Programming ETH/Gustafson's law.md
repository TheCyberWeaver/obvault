> [!Definition]
> **Gustafson's law** argues that when the problem size scales with the number of processors, the achievable speedup can grow almost linearly.

## Formula

If
- $\alpha$ is the sequential fraction of the runtime on a parallel system
- $1-\alpha$ is the parallel fraction
- $n$ is the number of processors

then the scaled speedup is

$$
S(n) = n - \alpha (n-1)
$$

## Intuition

The key idea is that with more processors, we often solve a **larger problem** in about the same amount of time instead of insisting on a fixed workload.

So the parallel part can grow with `n`, while the sequential overhead stays relatively small.

## Example

Suppose on a 10-processor system, the sequential fraction is $\alpha = 0.1$.

Then

$$
S(10) = 10 - 0.1(10-1) = 10 - 0.9 = 9.1
$$

So the scaled speedup is `9.1`.