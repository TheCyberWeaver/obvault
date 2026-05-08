> [!Definition]
> **Bounding probabilities** means deriving upper bounds or lower bounds for probabilities when the full distribution is unknown, using only coarse information such as the mean or variance.

## Markov inequality

Let $X \ge 0$ be a nonnegative random variable and let $t > 0$. Then
$$
\Pr[X \ge t] \le \frac{\mathbb{E}[X]}{t}.
$$
This is useful when you only know the [[Expected value]] of a nonnegative random variable.

### Proof

Since $X \ge t$ implies $X/t \ge 1$, we have
$$
X \ge t \mathbf{1}_{\{X \ge t\}}.
$$
Taking expectations gives
$$
\mathbb{E}[X] \ge t \Pr[X \ge t]\implies\Pr[X \ge t] \le \frac{\mathbb{E}[X]}{t}.
$$

## Chebyshev inequality

Let $X$ be a random variable with mean $\mu = \mathbb{E}[X]$ and finite variance $\operatorname{Var}(X)$. Then for every $t > 0$,
$$
\Pr[|X-\mu| \ge t] \le \frac{\operatorname{Var}(X)}{t^2}.
$$
### Proof (Derivation from Markov)

Apply Markov's inequality to the nonnegative random variable
$$
Y := (X-\mu)^2.
$$
Then
$$
\Pr[|X-\mu| \ge t]
=
\Pr[(X-\mu)^2 \ge t^2]
\le
\frac{\mathbb{E}[(X-\mu)^2]}{t^2}
=
\frac{\operatorname{Var}(X)}{t^2}.
$$

### Example

If $\mathbb{E}[X] = 10$ and $\operatorname{Var}(X) = 9$, then
$$
\Pr[|X-10| \ge 6] \le \frac{9}{36} = \frac14.
$$

## Chernoff bounds

Chernoff bounds are much sharper concentration bounds for sums of **independent Bernoulli random variables**. (see [[Distributions#Bernoulli distribution]])

Let $X = X_1 + \cdots + X_n$ where the $X_i$ are independent and $X_i \in \{0,1\}$ let $\mu = \mathbb{E}[X]$

1. $\Pr[X \ge (1+\delta)\mu] \le e^{-\mu \delta^2/3}$
2. $\Pr[X \le (1-\delta)\mu] \le e^{-\mu \delta^2/2}$
3. $\Pr[X\geq t]\leq2^{-t}$ for all $t\geq2e\mathbb{E}[X]$
### Proof of 3
Apply [[#Markov inequality]] to $Y:=4^{X}$
There is $X\geq t\Longleftrightarrow 4^{X}\geq4^{t}$
So 
$$
\Pr[X\geq t]=\Pr[4^{X}\geq4^{t}]\leq \frac{\mathbb{E}[4^{X}]}{4^{t}}
$$

$X_{1},X_{2},\dots,X_{n}$ are independent $\implies 4^{X_{1}},\dots,4^{X_{n}}$ are independent
$$
\mathbb{E}[4^{X}]=\mathbb{E}\left[ 4^{\sum_{i=1}^{n}X_{i}} \right]=\mathbb{E}\left[ \prod_{i=1}^{n} 4^{X_{i}} \right] =\prod_{i=1}^{n} \mathbb{E}[4^{X_{i}}] 
$$
$X_{i}\sim\text{Bernoulli}(p_{i})\implies \mathbb{E}[4^{X_{i}}]=4^{1}\cdot p_{i}+4^{0}\cdot(1-p_{i})=1+3p_{i}\leq e^{3p_{i}}$ (using $1+x\leq e^{x}$)
$\mathbb{E}[4^{X}]\leq \prod_{i=1}^{n}e^{3p_{i}}=e^{3\sum_{i=1}^{n}p_{i}}=e^{3\mathbb{E}[X]}\leq e^{\frac{3t}{2e}}\leq2^{t}$ (note that $e^{\frac{3}{2e}}\leq2$)
$\Pr[X\geq t]\leq \frac{2^{t}}{4^{t}}=2^{-t}$
> [!NOTE]
> To prove 1 and 2, apply Markov's inequality to $Y:=(1+\delta)^{X}\geq0$ and $Y:=(1-\delta)^{X}\geq0$

### Example
Let $X \sim \operatorname{Bin}(1000, 1/2)$. Then $\mu = \mathbb{E}[X] = 500.$
Take $\delta = 0.2$. Then
$$
\Pr[X \ge 600]
=
\Pr[X \ge (1+0.2)\mu]
\le
e^{-500 \cdot 0.2^2 / 3}
=
e^{-20/3}.
$$
So the probability of being at least $20\%$ above the mean is already very small.

