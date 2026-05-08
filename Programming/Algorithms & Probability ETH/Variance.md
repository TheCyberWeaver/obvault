
> [!NOTE] Definition
> Let $X$ be a [[Random Variable]] with expected value $\mu = \mathbb{E}[X]$.
> The **variance** of $X$ is
> $$
> \operatorname{Var}(X) = \mathbb{E}[(X-\mu)^2].
> $$
> It measures how far $X$ typically deviates from its mean.

## Standard deviation

The **standard deviation** of $X$ is the square root of the variance:
$$
\sigma_X = \sqrt{\operatorname{Var}(X)}.
$$

Unlike the variance, the standard deviation has the same unit as $X$.

## Useful identity

Expanding the square gives

> [!Important]
> $$
> \operatorname{Var}(X) = \mathbb{E}[X^2] - \mathbb{E}[X]^2.
> $$

**Short proof.**
$$
\operatorname{Var}(X)
= \mathbb{E}[(X-\mu)^2]
= \mathbb{E}[X^2 - 2\mu X + \mu^2]
= \mathbb{E}[X^2] - 2\mu \mathbb{E}[X] + \mu^2
= \mathbb{E}[X^2] - \mu^2.
$$
Since $\mu = \mathbb{E}[X]$, this becomes $\operatorname{Var}(X) = \mathbb{E}[X^2] - \mathbb{E}[X]^2$

## Affine transformations

For constants $a,b \in \mathbb{R}$,
$$
\operatorname{Var}(aX+b) = a^2 \operatorname{Var}(X).
$$

So shifting by $b$ does not change the variance, and scaling by $a$ multiplies the variance by $a^2$.

For the standard deviation,
$$
\sigma_{aX+b} = |a|\sigma_X.
$$

## Discrete and continuous forms

If $X$ is discrete, then
$$
\operatorname{Var}(X) = \sum_a (a-\mu)^2 \Pr[X=a].
$$

If $X$ is continuous with density $f_X$, then
$$
\operatorname{Var}(X) = \int_{-\infty}^{\infty} (x-\mu)^2 f_X(x)\,dx.
$$

In both cases, $\mu = \mathbb{E}[X]$.
