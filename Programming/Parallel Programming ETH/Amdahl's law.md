> [!Definition]
> **Amdahl's law** gives the theoretical upper bound on the speedup of a program when only part of it can be parallelized.

## Formula

If
- $p$ is the parallelizable fraction of the program
- $1-p$ is the inherently sequential fraction
- $n$ is the number of processors

then the maximum speedup is

$$
S(n) = \frac{1}{(1-p) + \frac{p}{n}}
$$

As $n \to \infty$,

$$
S(\infty) = \frac{1}{1-p}
$$

So the sequential part becomes the bottleneck.

## Intuition

Even if we add infinitely many processors, the part of the program that must run sequentially cannot be accelerated. This means small sequential fractions can still severely limit total speedup.

## Example

Suppose 90% of a program can be parallelized, so $p = 0.9$.

With 10 processors:

$$
S(10) = \frac{1}{0.1 + \frac{0.9}{10}} = \frac{1}{0.19} \approx 5.26
$$

With infinitely many processors:

$$
S(\infty) = \frac{1}{0.1} = 10
$$

So even with unlimited processors, the program can never become more than 10 times faster.

> [!Important]
> Amdahl's law shows that optimizing or reducing the sequential part is often more important than adding more cores.

For the scaled-workload view, see [[Gustafson's law]]. For a direct comparison, see [[Amdahl's law vs Gustafson's law]].
