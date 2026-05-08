## T4.1 Recursive dice
![[Pasted image 20260422200842.png]]
### a)

$\Pr[X=x,Y=y]=\Pr[X=x]\cdot\Pr[Y=y|X=x]=\frac{1}{6}\cdot \frac{1}{x}$ (for $1\leq y\leq x$)
so
$$
p_{X,Y}(x,y)=\begin{cases}
\frac{1}{6x}, \;1\leq y\leq x\leq6 \\
0,\;\text{otherwise}
\end{cases}
$$

### b)
Since $x\geq y$, we must have
$$
\Pr[Y=y]=\sum_{x=y}^{6} \Pr[X=x,Y=y] =\sum_{x=y}^{6} \frac{1}{6x}
$$
Therefore,
$$
p_{Y}(y)=\begin{cases}
\frac{1}{6}\sum_{x=y}^{6} \frac{1}{x}, \; y=1,\dots,6 \\
0, \; \text{otherwise}
\end{cases}
$$
### c)
calculate the expected value:
$\mathbb{E}[X]=\frac{1+2+3+4+5+6}{6}=\frac{7}{2}$
$\mathbb{E}[Y]=\mathbb{E}[\mathbb{E}[Y|X]]=\mathbb{E}\left[ \frac{X+1}{2} \right]=\frac{\mathbb{E}[X]+1}{2}=\frac{\frac{7}{2}+1}{2}=\frac{9}{4}$ (using linearity of the expected value)

calculate the variance:

Since $Y|X=x$ is uniform on $\{ 1,\dots,x \}$ we have
$$
\mathbb{E}[Y^{2}|X=x]=\frac{1^{2}+2^{2}+\dots+x^{2}}{x}=\frac{x(x+1)(2x+1)}{6x}=\frac{(x+1)(2x+1)}{6}
$$
$$
\mathbb{E}[Y^{2}]=\mathbb{E}[\mathbb{E}[Y^{2}|X]]=\frac{1}{6}\sum_{x=1}^{6}\frac{(x+1)(2x+1)}{6}=\frac{1}{36}\cdot \sum_{x=1}^{6} 2x^{2}+3x+1
$$
$$
=\frac{1}{36}\left( 2\sum_{x=1}^{6} x^{2} +3\sum_{x=1}^{6} x+6\right)=\frac{1}{36}(2\cdot91+3\cdot21+6)=\frac{251}{36}
$$
$$
\text{Var}[Y]=\mathbb{E}[Y^{2}]-\mathbb{E}[Y]^{2}=\frac{251}{36}-\left( \frac{9}{4} \right)^{2}=\frac{275}{144}
$$
