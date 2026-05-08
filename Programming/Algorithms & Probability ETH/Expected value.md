> [!NOTE] Definition
> The **expected value** (or **mean**) of a random variable $X$ describes its average value.

If $X$ is discrete:
$$
\mathbb{E}[X] = \sum_{\alpha \in W_X} \alpha \Pr[X = \alpha]
=
\sum_{\omega \in \Omega} X(\omega)\Pr[\omega].
$$

If $X$ is continuous:
$$
\mathbb{E}[X] = \int_{-\infty}^{\infty} x f_X(x)\,dx.
$$

More generally, for a function $g$:

discrete case:
$$
\mathbb{E}[g(X)] = \sum_a g(a)\Pr[X = a]
$$

continuous case:
$$
\mathbb{E}[g(X)] = \int_{-\infty}^{\infty} g(x) f_X(x)\,dx
$$

## Conditional expectation on an event

If $A$ is an event with $\Pr[A] > 0$, then the conditional expectation of $X$ given $A$ is
$$
\mathbb{E}[X \mid A]
=
\sum_x x \Pr[X = x \mid A]
$$
in the discrete case.

It is the expected value of $X$ under the condition that the event $A$ has occurred.

## Law of total expectation for a partition

Let $A_1,\dots,A_n$ be pairwise disjoint events such that
$$
A_1 \cup \cdots \cup A_n = \Omega
\qquad\text{and}\qquad
\Pr[A_i] > 0 \text{ for all } i.
$$
Then
$$
\mathbb{E}[X]
=
\sum_{i=1}^{n} \mathbb{E}[X \mid A_i]\Pr[A_i].
$$

This is the expectation analogue of the law of total probability: split the sample space into cases, compute the conditional expectation in each case, and weight by the probability of the case.

### Example

Suppose:
- with probability $\frac12$, we choose a fair coin and let $X$ be the number of heads in one toss
- with probability $\frac12$, we choose a fair die and let $X$ be the number shown

Let:
- $A_1$ = "coin was chosen"
- $A_2$ = "die was chosen"

Then
$$
\mathbb{E}[X \mid A_1] = \frac12,
\qquad
\mathbb{E}[X \mid A_2] = 3.5
$$
and therefore
$$
\mathbb{E}[X]
=
\mathbb{E}[X \mid A_1]\Pr[A_1] + \mathbb{E}[X \mid A_2]\Pr[A_2]
=
\frac12 \cdot \frac12 + 3.5 \cdot \frac12
=
2.
$$

> [!NOTE]
> If $X$ is non-negative and integer-valued, then
> $$
> \mathbb{E}[X] = \sum_{i=1}^{\infty}\Pr[X \ge i].
> $$
>
> **Short proof.**
> Since $X$ is integer-valued,
> $$
> \mathbb{E}[X] = \sum_{j=1}^{\infty} j \Pr[X = j].
> $$
> Now write each $j$ as $\sum_{i=1}^{j} 1$, so
> $$
> \mathbb{E}[X]
> = \sum_{j=1}^{\infty} \sum_{i=1}^{j} \Pr[X = j].
> $$
> Exchanging the order of summation gives
> $$
> \mathbb{E}[X]
> = \sum_{i=1}^{\infty} \sum_{j=i}^{\infty} \Pr[X = j]
> = \sum_{i=1}^{\infty} \Pr[X \ge i].
> $$

## Linearity of expectation

Expected value is linear. For random variables $X_1,\dots,X_n$ and constants $a_1,\dots,a_n,b$,
$$
\mathbb{E}\!\left[a_1X_1 + \cdots + a_nX_n + b\right]
= a_1\mathbb{E}[X_1] + \cdots + a_n\mathbb{E}[X_n] + b.
$$

**Short proof.** In the discrete case,
$$
\mathbb{E}\!\left[a_1X_1 + \cdots + a_nX_n + b\right]
= \sum_{\omega \in \Omega} \left(a_1X_1(\omega) + \cdots + a_nX_n(\omega) + b\right)\Pr[\omega].
$$
Distributing the sum gives
$$
= a_1 \sum_{\omega \in \Omega} X_1(\omega)\Pr[\omega]
+ \cdots
+ a_n \sum_{\omega \in \Omega} X_n(\omega)\Pr[\omega]
+ b \sum_{\omega \in \Omega} \Pr[\omega]
$$
$$
= a_1\mathbb{E}[X_1] + \cdots + a_n\mathbb{E}[X_n] + b.
$$
This does **not** require the random variables to be independent.

## Moments

The **$k$-th moment** of a random variable $X$ is
$$
\mathbb{E}[X^k],
$$
provided the expectation exists.

- The **first moment** is $\mathbb{E}[X]$, the mean.
- The **second moment** is $\mathbb{E}[X^2]$.

Often one also uses **centered moments**, defined by
$$
\mathbb{E}[(X-\mathbb{E}[X])^k].
$$

The most important centered moment is the second one:
$$
\mathbb{E}[(X-\mathbb{E}[X])^2] = \operatorname{Var}(X).
$$

So moments describe the shape of a distribution:

- the first moment gives its location,
- the second centered moment gives its spread,
- higher moments capture finer properties such as asymmetry and tail behavior.
