# P3.1 Distributions
## a)
![[Pasted image 20260415135326.png]]
$X$ - the number of bits flipped
$X\sim\text{Bin}(n,p)$
The probability that exactly $k$ bits are flipped is:
$\Pr[X=k]=\begin{pmatrix}	n \\ k \end{pmatrix}p^{k}(1-p)^{n-k}$

## b)
![[Pasted image 20260415135248.png]]

We define one round as "Alice tosses once and if not succeed then Bob tosses once"
A round is not succeed if both of them fail, which has a probability of $\frac{1}{2}(1-p)$

Let $A_{k}$ be the event that Alice wins at round $k$ 
$\Pr[A_{k}]=(\frac{1}{2}(1-p))^{k-1}\cdot \frac{1}{2}$
The total probability that Alice wins ($A$) is:
$$
\Pr[A] =\sum_{k=1}^{\infty} \Pr[A_{k}]=\sum_{k=1}^{\infty}(\frac{1}{2}(1-p))^{k-1}\cdot \frac{1}{2}=\frac{\frac{1}{2}}{1- \frac{1}{2}(1-p)}=\frac{1}{1+p}
$$
In order to make the game fair we must have $\Pr[A]=\frac{1}{2}$
This means $\frac{1}{1+p}=\frac{1}{2}\implies p=1$
However, the biased coin has $p<1$. This leads to a contradiction, which means there is no valid $p$ that makes the game fair.
## c)
![[Pasted image 20260415135309.png]]

### X
We first consider a single plate:
Let random variable $X_{i}$ be the number of caught throws before the plate $i$ breaks.
$X_{i}$ follows geometric distribution, therefore:
$\mathbb{E}[X_{i}]= \frac{1-p}{p}=1$ and $\text{Var}[X_{i}]= \frac{1-p}{p^{2}}=2$

By using the linearity of expected value we have
$$
\mathbb{E}[X]=\mathbb{E}\left[ \sum_{i=1}^{n}X_{i} \right]=\sum_{i=1}^{n}\mathbb{E}[X_{i}]=\sum_{i=1}^{n}1=n\cdot1=n
$$
and by using *Hint* ($X_{i}$ are independent variables)
$$
\text{Var}[X]=Var\left[ \sum_{i=1}^{n} X_{i} \right]=\sum_{i=1}^{n} \text{Var}[X_{i}]=\sum_{i=1}^{n} 2=2n
$$
### Y
Since all plates are going to be thrown until broken. Therefore, the number of throws that are not caught is always $n$
$\mathbb{E}[Y]=n$ 
$\text{Var}[Y]=\mathbb{E}[(Y-\mathbb{E}[Y])]^{2}=\mathbb{E}[(0-0)^{2}]=0$
### X+Y
By using linearity of expected value:
$$
\mathbb{E}[X+Y]=\mathbb{E}[X]+\mathbb{E}[Y]=n+n=2n
$$
Since $Y$ is a constant and adding a constant to a random variable does not change its variance:
$$
\text{Var}[X+Y] =\text{Var}[X+n]=\text{Var}[X]=2n
$$

