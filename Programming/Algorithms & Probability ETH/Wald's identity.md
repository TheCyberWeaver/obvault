> [!Definition]
> **Wald's identity** states that for i.i.d. (independent and identically distributed) random variables $X_1, X_2, \dots$ with finite expectation and an integer-valued random variable $N$ with $\mathbb{E}[N] < \infty$,
> $$
> \mathbb{E}\left[\sum_{i=1}^{N} X_i\right] = \mathbb{E}[N] \cdot \mathbb{E}[X_1]
> $$
> provided the usual independence / stopping-time assumptions are satisfied.

## Intuitive Interpretation

If each step has average value $\mathbb{E}[X_1]$, and we take on average $\mathbb{E}[N]$ steps, then the expected total is just
$$
\text{expected number of steps} \times \text{expected contribution per step}.
$$
## Short proof

Let
$$
Z := \sum_{i=1}^{N} X_i.
$$
Use the [[Expected value#Law of total expectation for a partition|law of total expectation for a partition]] with the disjoint events
$$
A_n := \{N=n\}, \qquad n \ge 0.
$$
$$
\mathbb{E}[Z]
=
\sum_{n \ge 0} \mathbb{E}[Z \mid N=n]\Pr[N=n].
$$
So by linearity of expectation,
$$
\mathbb{E}[Z \mid N=n]
=
\mathbb{E}\left[\sum_{i=1}^{n} X_i \,\middle|\, N=n\right]
=
\sum_{i=1}^{n} \mathbb{E}[X_i \mid N=n]
= n\,\mathbb{E}[X_1].
$$
Therefore
$$
\mathbb{E}[Z]
=
\sum_{n \ge 0} n\,\mathbb{E}[X_1]\Pr[N=n]
=
\mathbb{E}[X_1]\sum_{n \ge 0} n\Pr[N=n]
=
\mathbb{E}[X_1]\mathbb{E}[N].
$$
So
$$
\mathbb{E}[Z] = \mathbb{E}[N]\cdot\mathbb{E}[X_1].
$$

## Typical assumptions

- $X_1, X_2, \dots$ are i.i.d.
- $\mathbb{E}[|X_1|] < \infty$
- $N$ is a nonnegative integer-valued random variable with $\mathbb{E}[N] < \infty$
- Usually, $N$ is a [[Random Variable#Definition|random variable]] that does not look into the future, e.g. a stopping time

## Example

Let $X_i$ be the outcome of the $i$-th roll of a fair die, so
$$
\mathbb{E}[X_i] = \frac{1+2+3+4+5+6}{6} = 3.5
$$

Suppose we roll the die a random number $N$ of times, and $\mathbb{E}[N] = 10$.
Then
$$
\mathbb{E}\left[\sum_{i=1}^{N} X_i\right] = 10 \cdot 3.5 = 35.
$$


## Important remark

> [!Important]
> Wald's identity is **not** true for arbitrary dependence between $N$ and the variables $X_i$. The assumptions matter.

It is especially useful when the stopping rule is random, but each increment still has the same expected value.
