 #exercise 
# 1. Rank of a matrix 

a)
$A_{1}=\begin{bmatrix}2 & 3 \\ 3 & 4\end{bmatrix}$
$A_{2}=\begin{bmatrix}2 & 3 & 4 \\ 3 & 4 & 5 \\ 4 & 5 & 6\end{bmatrix}$
$A_{3}=\begin{bmatrix}2 & 3 & 4 & 5 \\ 3 & 4 & 5 & 6 \\ 4 & 5 & 6 & 7 \\ 5 & 6 & 7 & 8\end{bmatrix}$

b)
$rank(A_{2})=2$
$\begin{pmatrix}2 \\ 3\end{pmatrix}\neq\lambda \begin{pmatrix}3 \\ 4\end{pmatrix}$
$rank(A_{3})=2$
$\begin{pmatrix}4 \\ 5 \\ 6\end{pmatrix}=2\begin{pmatrix}3 \\ 4 \\ 5\end{pmatrix}-\begin{pmatrix}2 \\ 3 \\ 4\end{pmatrix}$
$\begin{pmatrix}3 \\ 4 \\ 5\end{pmatrix}\neq \lambda\begin{pmatrix}2 \\ 3 \\ 4\end{pmatrix}$

$rank(A_{4})=2$
for $3\leq k\leq m$: 
$\mathbf{v}_{k}-\mathbf{v_{1}}=\begin{pmatrix}1+k \\ \vdots \\ m+k\end{pmatrix}-\begin{pmatrix}2 \\ \vdots \\ m+1\end{pmatrix}=(k-1)\begin{pmatrix}1 \\ \vdots \\ 1\end{pmatrix}=(k-1)(\mathbf{v}_{2}-\mathbf{v}_{1})$
$\mathbf{v}_{k}=(k-1)(\mathbf{v}_{2}-\mathbf{v}_{1})+\mathbf{v}_{1}=(2-k)\mathbf{v}_{1}+(k-1)\mathbf{v}_{2}$

# 2. Nullspace as a hyperplane
a) $rank(A)=1$
b)
Let $\boldsymbol{\lambda}=\begin{pmatrix}\lambda_{1} \\ \lambda_{2} \\ \vdots \\ \lambda _{n}\end{pmatrix}$
$A\mathbf{x}=0$
$\begin{bmatrix}\lambda_{1}\mathbf{v} & \lambda_{2}\mathbf{v} & \dots & \lambda _{n}\mathbf{v}\end{bmatrix}\mathbf{x}=\mathbf{0}$
$\sum_{i=1}^{n}x_{i}\lambda _{i}\mathbf{v}=\mathbf{0}$
Since $\mathbf{v}\neq \mathbf{0}$, $\sum_{i=1}^{n}x_{i}\lambda _{i}=0$
This is the equation for the hyperplane. Hence the statement is proved.

# 3. Matrix transformations
a)
rotate the input around y-axis by 45 degree (counter-clockwise)

b)
$\begin{bmatrix}0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & -1\end{bmatrix}$

# 4. Scalar product

a)
$A(\lambda \mathbf{x}+\mu \mathbf{y})=\lambda A(\mathbf{x})+\mu A(\mathbf{y})=\mathbf{0}\lambda+\mathbf{0}\mu=\mathbf{0}$
Let $\mathbf{v}=\lambda \mathbf{x}+\mu \mathbf{y}$
$\implies A\mathbf{v}=0$
$\implies \begin{pmatrix}\mathbf{u}_{1}^{\top}\mathbf{v} \\ \mathbf{u}_{2}^{\top}\mathbf{v} \\ \vdots \\ \mathbf{u}_{m}^{\top}\mathbf{v}\end{pmatrix}=\mathbf{0}$
$\implies \forall i\in[m],\quad\mathbf{u}_{i}^{\top}\mathbf{v}=0$ 
$\implies \lambda \mathbf{x}+\mu \mathbf{y}$ is orthogonal to each of $\mathbf{u}_{1},\mathbf{u}_{2},\dots,u_{m}$

# 5. Rank of matrices
a) $rank(A)=2$
b) $rank(A)=3$

# 6. Skew-symmetric matrices
a)
$\begin{bmatrix}0 & 1 \\ -1 & 0\end{bmatrix}$
b)
$A^{\top}=[a_{ji}]^{n\quad m}_{i=1,j=1}=-A=[-a_{ij}]^{n\quad m}_{i=1,j=1}$
$\implies \forall i\in[m] \quad a_{ii}=-a_{ii}$
$\implies\forall i\in[m] \quad a_{ii}=0$

c)
- $\mathbf{0}$
 $\forall i,j\in [m]\quad a_{ij}=a_{ji}=-a_{ij}$
 $\implies \forall i,j\in [m]\quad a_{ij}=0$
 $\implies A=\mathbf{0}$
 
d)
$A=\begin{bmatrix}0 & a & b \\ -a & 0 & c \\ -b & -c & 0\end{bmatrix}$

$-\frac{c}{a}\mathbf{a}_{1}+\frac{b}{a}\mathbf{a}_{2}=-\frac{c}{a}\begin{pmatrix}0 \\ -a \\ -b\end{pmatrix}+\frac{b}{a}\begin{pmatrix}a \\ 0 \\ -c\end{pmatrix}=\begin{pmatrix}0 \\ c \\ \frac{bc}{a}\end{pmatrix}+\begin{pmatrix}b \\ 0 \\ -\frac{bc}{a}\end{pmatrix}=\begin{pmatrix}b \\ c \\ 0\end{pmatrix}=\mathbf{a}_{3}$
We see $\mathbf{a}_{3}$ is linear dependent on $\mathbf{a}_{1}$ and $\mathbf{a}_{2}$, so the rank muss be less or equal to 2

# 7. Embedding a line in $\mathbb{R}^{m}$

Let $A=[\mathbf{v}]$
$T_{A}(\mathbf{x})=A\mathbf{x}=[\mathbf{v}]\mathbf{x}=\begin{pmatrix}v_{1}x \\ v_{2}x \\ \vdots \\ v_{m}x\end{pmatrix}=x\begin{pmatrix}v_{1} \\ v_{2} \\ \vdots \\ v_{m}\end{pmatrix}=x\mathbf{v}$
Since $x \in \mathbb{R}$
$\{T_{A}(\mathbf{x}):\mathbf{x}\in \mathbb{R}^{1}\}=\{x\mathbf{v}:x \in \mathbb{R}\}=\{\lambda\mathbf{v}:\lambda \in \mathbb{R}\}=L$
The statement is proved.

