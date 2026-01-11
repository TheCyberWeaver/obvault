Generalization of [[Diagonalizing]]

Let $A\in \mathbb{R}^{m\times n}$
We try to find a basis $V=\begin{bmatrix}	v_{1} & v_{2} & \dots & v_{n}\end{bmatrix}\in \mathbb{R}^{n\times n}$ and $U=\begin{bmatrix}	u_{1} & u_{2} & \dots & u_{n}\end{bmatrix}\in \mathbb{R}^{m\times m}$
$AA^{\top}=U\Lambda U^{\top}$
$A^{\top}A=V\Lambda' V^{\top}$  (the eigenvalues are the same because of [[Symmetric Matrix#Proposition 9.12.15]])

## Definition

> [!NOTE]
> $A=U\Sigma V^{\top}$

$\Sigma _{ij}=0$ for $i\neq j$
$\Sigma _{ij}\geq0\;	\forall{i \in \{ 1,\dots,min\{ m,n \} \}}$
$\Sigma _{11}\geq\Sigma _{22}\geq\dots\geq\Sigma _{kk}$

$V=A^{\top}U\Sigma ^{-1}$ ($V$ can not be chosen freely, it is determined by the chosen eigenvalues and eigenvectors of $A$)
## Theorem 9.3.3

> [!NOTE]
> Every matrix $A\in \mathbb{R}^{m\times n}$ has a singular value decomposition.

> [!Important]
> In other words: **Every** linear transformation is diagonal (only scaling on some axis) when viewed in the bases of the singular vectors.

