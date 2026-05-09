Vector $q_{1},\dots,q_{n}\in \mathbb{R}^{m}$ are **orthonormal** (orthogonal and normalized) if: 
- $\lVert q_{1} \rVert=1\;	\;	\forall{i=1\dots n}$
- $q_{i}^{\top}q_{j}=0\;	\;	\forall{{i\neq j}}\;$

Let the columns of $Q$ be $q_{1},\dots,q_{n}$:
$Q^{\top}Q$ matrix with entries $\delta_{ij}=q_{i}^{\top}q_{j}$ (the Kronecker delta)
 $Q^{\top}Q=I$
 
> [!NOTE] Title
> Note that $Q$ may not be a square matrix. Hence, it is not necessarily the case that $Q Q^{\top}=I$

$q_{1},\dots,q_{n}$ are orthogonal $\implies$ $q_{1},\dots,q_{n}$ are linearly independent
(see [[Orthogonality#Fact 2]])
### Example
Let $Q=\begin{bmatrix} 1 & 0 \\ 0 & \frac{1}{3} \\ 0 & \frac{2}{3} \\ 0 & \frac{2}{3}\end{bmatrix}$
$Q^{\top}Q=\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}$

## Definition: Orthogonal matrix
A square matrix $Q\in \mathbb{R}^{n\times n}$ is orthogonal if $Q^{\top}Q=I$
$\implies Q^{\top}=Q^{-1}$ and $Q Q^{\top}=I$
the columns of $Q$ form an orthonormal basis for $\mathbb{R}^{n}$.
### Properties
> [!Quote] [[Linear Algebra 2 ETH.pdf#page=20&selection=253,0,253,17&color=note|Proposition 6.3.6]]
> Orthogonal matrices preserve norm and inner product of vectors

This means
$$
\lVert Qx \rVert =\lVert x \rVert \quad \forall x \in \mathbb{R}^{n}
$$
$$
(Qx)^{\top}(Qy)=x^{\top}y\quad	\forall{x,y\in \mathbb{R}^{n}}
$$
Let $S$ be a subspace of $\mathbb{R}^{m}$ and $q_{1},\dots,q_{n}$ form an orthonormal basis of $S$ 
Then,
- $S=span(q_{1},\dots q_{n})=\left\{ \sum_{i=1}^{n}\lambda _{i}q_{i}|\forall{i}\;	\lambda _{i}\in \mathbb{R} \right\}$
- The [[Projection#Theorem 5.2.5|projection matrix]] $P$ to $S$ is given by $Q Q^{\top}$
	- $P=Q(Q^{\top}Q)^{-1}Q^{\top}=Q Q^{\top}$

# Construction of [[Orthonormal Bases]]

> [!task]
> Given $a_{1},\dots ,a_{n}\in \mathbb{R}^{m}$ are basis of a subspace $S_{n}=span(a_{1},\dots,a_{n})$
> Find a orthonormal basis of $S_{n}$
## Gram-Schmidt Process
### Idea
![[Pasted image 20251121113951.png|265]]
- $q_{1}=\frac{a_{1}}{\lVert a_{1} \rVert}$
- $q_{2}$ is $a_{2}$ subtract $a_{2}$ [[Projection|projection]] onto $C(a_{1})$
- For $k\geq3$
	- $a_{k}$ subtract $a_{k}$ [[Projection|projection]] onto $span(q_{1},\dots,q_{k-1})$
### Algorithm
- $q_{1}=\frac{a_{1}}{\lVert a_{1} \rVert}$
- For $k\geq2$:
	- $q_{k}'=a_{k}-\sum_{j=1}^{k-1}(a_{k}^{\top}q_{j})q_{i}$
	- $q_{k}=\frac{q'_{k}}{\lVert q_{k}' \rVert}$

### Proof of correctness
