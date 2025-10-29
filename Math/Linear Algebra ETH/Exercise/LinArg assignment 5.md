# 1. Interpolation
$P(x)=-\frac{1}{12}x^{3}+\frac{3}{4}x^{2}-\frac{2}{3}x+1$
# 2. Strictly diagonally dominant matrices
Assume $A\mathbf{x}=0$ for some nonzero $\mathbf{x}\in \mathbb{R}^{m}$
Pick the $k$-th row, so that $|x_{k}|$ is the biggest among $|x_{1}|,\dots,|x_{m}|$  
$$
0=\sum_{j=1}^{m} a_{kj}x_{j}
$$
$$
\implies |a_{kk}||x_{k}|=\left\lvert \sum_{j=1,\; j\neq k}^{m}|a_{kj}||x_{j}|  \right\rvert\leq \sum_{j=1,\; j\neq k}^{m}|a_{kj}||x_{j}|\leq |x_{k}|\sum_{j=1,\;j\neq k}^{m} |a_{kj}| 
$$
If $|x_{k}|\neq0$, then we get
$|a_{kk}|\leq \sum_{j=1,\;j\neq k}^{m}|a_{kj}|$
which contradicts strict diagonal dominance.
Hence no nonzero $\mathbf{x}$ satisfies $A\mathbf{x}=\mathbf{0}$. So $A$ is linear independent and thus invertible.