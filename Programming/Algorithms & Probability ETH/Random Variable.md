a> [!NOTE] Definition
> A **random variable** on a probability space $\Omega$ is a function
> $$
> X : \Omega \to \mathbb{R}.
> $$
> It assigns a real number $X(\omega)$ to each outcome $\omega \in \Omega$.

So a random variable is not itself an event. It is a numerical quantity defined on the outcomes of a [[Probability Space]].

## Events defined by a random variable

From a random variable $X$, we get events such as
$$
\{X = a\}, \qquad \{X \le a\}, \qquad \{X \in S\}.
$$

For a discrete random variable, its distribution is given by
$$
\Pr[X = a] = \Pr(\{\omega \in \Omega : X(\omega) = a\}).
$$

### Special case: indicator variable

An **indicator variable** of an event $A$ is the random variable
$$
\mathbf{1}_A(\omega) =
\begin{cases}
1, & \omega \in A, \\
0, & \omega \notin A.
\end{cases}
$$
Its expected value is just: $\mathbb{E}[\mathbf{1}_A] = \Pr[A]$

## Density and cumulative distribution function

- **probability density function (PDF)**: a function $f_X$ such that probabilities are obtained by integration
- **cumulative distribution function (CDF)** : $F_X(x) = \Pr[X \le x].$

If $X$ is continuous and has density $f_X$, then
$$
\Pr[a \le X \le b] = \int_a^b f_X(x)\,dx
$$
and
$$
F_X(x) = \int_{-\infty}^x f_X(t)\,dt.
$$

When $F_X$ is differentiable, the density is its derivative:
$$
f_X(x) = F_X'(x).
$$

Further properties such as [[Expected value]], conditional expectation, linearity of expectation, and moments are collected in [[Expected value]].
