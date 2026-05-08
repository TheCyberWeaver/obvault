> [!Definition]
> These are common **discrete probability distributions** that appear frequently in randomized algorithms and probability.

## Bernoulli distribution

A random variable $X$ has a **Bernoulli distribution** with parameter $p$, written
$$
X \sim \operatorname{Bernoulli}(p),
$$
if it has only two outcomes:
- success with probability $p$
- failure with probability $1-p$

Usually,
$$
X \in \{0,1\},
\qquad
\Pr[X=1]=p,
\qquad
\Pr[X=0]=1-p.
$$

So the PMF is
$$
\Pr[X=k] =
\begin{cases}
p, & k=1,\\
1-p, & k=0,\\
0, & \text{otherwise.}
\end{cases}
$$

The [[Expected value|expected value]] is
$$
\mathbb{E}[X]=p,
$$
and the [[Variance|variance]] is
$$
\operatorname{Var}(X)=p(1-p).
$$

An [[Random Variable#Special case: indicator variable|indicator variable]] is Bernoulli-distributed.

## Binomial distribution

A random variable $X$ has a **Binomial distribution** with parameters $n,p$, written
$$
X \sim \operatorname{Bin}(n,p),
$$
if $X$ counts the number of successes in $n$ independent Bernoulli trials with success probability $p$.

Then
$$
\Pr[X=k] = \binom{n}{k} p^k(1-p)^{n-k},
\qquad
k \in \{0,1,\dots,n\}.
$$

Reason:
- choose which $k$ trials are successful: $\binom{n}{k}$ possibilities
- each such pattern has probability $p^k(1-p)^{n-k}$

The expected value is
$$
\mathbb{E}[X]=np,
$$
and the variance is
$$
\operatorname{Var}(X)=np(1-p).
$$

You can think of a binomial variable as a sum of independent Bernoulli variables:
$$
X = X_1+\cdots+X_n.
$$

## Poisson distribution

A random variable $X$ has a **Poisson distribution** with parameter $\lambda > 0$, written
$$
X \sim \operatorname{Po}(\lambda),
$$
if
$$
\Pr[X=k] = \frac{\lambda^k e^{-\lambda}}{k!},
\qquad
k \in \{0,1,2,\dots\}.
$$

Its expected value and variance are both
$$
\mathbb{E}[X]=\lambda,
\qquad
\operatorname{Var}(X)=\lambda.
$$

### Balls and bins view

Throw $n$ balls independently and uniformly at random into $n$ bins, and let $X$ be the number of balls in one fixed bin.
Then
$$
X \sim \operatorname{Bin}(n,1/n),
$$
so
$$
\mathbb{E}[X]=1.
$$

As $n \to \infty$, this binomial distribution converges to
$$
\operatorname{Po}(1).
$$

More generally, if
$$
X \sim \operatorname{Bin}(n,\lambda/n),
$$
then for fixed $\lambda$ and large $n$,
$$
\Pr[X=k] \approx \frac{\lambda^k e^{-\lambda}}{k!}.
$$

So the Poisson distribution is a good model for the number of **rare, independent events** in a fixed time or space interval.

## Geometric distribution

A random variable $X$ has a **Geometric distribution** with parameter $p$, written
$$
X \sim \operatorname{Geo}(p),
$$
if $X$ is the number of independent Bernoulli trials until the **first success**.

Here the support is
$$
X \in \{1,2,3,\dots\}.
$$

To have the first success on trial $k$, we need:
- $k-1$ failures first
- then one success

So
$$
\Pr[X=k] = (1-p)^{k-1}p,
\qquad
k \ge 1.
$$

The expected value is
$$
\mathbb{E}[X]=\frac{1}{p},
$$
and the variance is
$$
\operatorname{Var}(X)=\frac{1-p}{p^2}.
$$

> [!Important]
> The geometric distribution is **memoryless**:
> $$
> \Pr[X>s+t \mid X>s] = \Pr[X>t].
> $$

So after a long wait without success, the remaining waiting time has the same distribution as at the start.

## Negative binomial distribution

A random variable $X$ has a **Negative Binomial distribution** with parameters $r,p$ if $X$ is the number of independent Bernoulli trials until the **$r$-th success**.

This generalizes the geometric distribution, which is the special case $r=1$.

The support is
$$
X \in \{r,r+1,r+2,\dots\}.
$$

To have the $r$-th success on trial $k$:
- the $k$-th trial must be a success
- among the first $k-1$ trials, exactly $r-1$ must be successes

Therefore
$$
\Pr[X=k]
=
\binom{k-1}{r-1} p^r (1-p)^{k-r},
\qquad
k \ge r.
$$

The expected value is
$$
\mathbb{E}[X]=\frac{r}{p},
$$
and the variance is
$$
\operatorname{Var}(X)=\frac{r(1-p)}{p^2}.
$$

## Relationship

- **Bernoulli**: one success/failure experiment
- **Binomial**: number of successes in $n$ Bernoulli trials
- **Poisson**: approximation for rare-event counts
- **Geometric**: waiting time until the first success
- **Negative Binomial**: waiting time until the $r$-th success
