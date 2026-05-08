## Discrete Probability Space
A discrete probability space consists of:
- a sample space $\Omega$ of countable elementary outcomes
- a probability assignment $p(\omega)$ for every $\omega \in \Omega$

with
$$
p(\omega) \ge 0
\qquad\text{and}\qquad
\sum_{\omega \in \Omega} p(\omega) = 1.
$$

An **event** is any subset $A \subseteq \Omega$, and its probability is
$$
\Pr[A] = \sum_{\omega \in A} p(\omega).
$$

The complement of $A$ is $\overline{A} = \Omega \setminus A$.

## Basic Properties
For events $A,B \subseteq \Omega$:

$$
\Pr[\varnothing] = 0,\qquad \Pr[\Omega] = 1
$$

$$
0 \le \Pr[A] \le 1
$$

$$
\Pr[\overline{A}] = 1 - \Pr[A]
$$

If $A \subseteq B$, then
$$
\Pr[A] \le \Pr[B].
$$

If $A_1, A_2, \dots$ are pairwise disjoint, then (Addition Principle)
$$
\Pr\left[\bigcup_i A_i\right] = \sum_i \Pr[A_i].
$$

### Union Bound
For arbitrary events $A_1,\dots,A_n$:
$$
\Pr\left[\bigcup_{i=1}^n A_i\right] \le \sum_{i=1}^n \Pr[A_i].
$$

This is Boole's inequality, also called the **union bound**.

### Inclusion-Exclusion
To compute the union exactly, use [[Inclusion–exclusion principle]]:
$$
\Pr\left[\bigcup_{i=1}^n A_i\right]
=
\sum_i \Pr[A_i]
- \sum_{i<j} \Pr[A_i \cap A_j]
+ \sum_{i<j<k} \Pr[A_i \cap A_j \cap A_k]
- \cdots
$$

Idea: first sum all events, then correct the overcounting by subtracting intersections, then add back intersections that were subtracted too often, and so on.

## Laplace Space
A **Laplace space** is a finite probability space in which all elementary outcomes are equally likely.

If $|\Omega| = n$, then every outcome has probability
$$
\frac{1}{n}.
$$

So for any event $A$:
$$
\Pr[A] = \frac{|A|}{|\Omega|}.
$$

This is the standard
$$
\frac{\text{favorable outcomes}}{\text{all outcomes}}
$$
rule.

> [!NOTE]
> Choosing the Right Sample Space:
> The key modeling lesson is: choose the sample space so that the elementary outcomes are truly equally likely.

### Example: Two Dice
If we only look at the possible sums $\{2,\dots,12\}$, this is **not** a Laplace space, because sums do not occur equally often.

The correct Laplace space is
$$
\Omega = \{1,\dots,6\} \times \{1,\dots,6\},
$$
where each ordered pair has probability $\frac{1}{36}$.

Then:
- sum $2$ has probability $\frac{1}{36}$
- sum $7$ has probability $\frac{6}{36}$
- sum $10$ has probability $\frac{3}{36}$
