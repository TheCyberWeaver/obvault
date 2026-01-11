## Definition
Suppose that $A$ has eigenvectors $v_{1},\dots v_{n}\in \mathbb{R}^{n}$ that form a basis of $\mathbb{R}^{n}$. ($n$ linearly independent eigenvectors)
$$
A=V\Lambda V^{-1}
$$
where $V=[v_{1},v_{2},\dots,v_{n}]$  are the eigenvectors
$\Lambda=\begin{bmatrix}	\lambda_{1} & 0 & 0 \\ 0 & \ddots  & 0 \\ 0 & 0 & \lambda _{n}\end{bmatrix}$ are the [[Eigenvalues|eigenvalues]]

**Proof**:
$AV=\begin{bmatrix}	\lambda_{1}v_{1} & \lambda_{2}v_{2} & \dots & \lambda _{n}v_{n} & \end{bmatrix}=\begin{bmatrix}	v_{1} & v_{2} & \dots & v_{n}\end{bmatrix}\begin{bmatrix}	\lambda_{1} & 0 & 0 \\ 0 & \ddots  & 0 \\ 0 & 0 & \lambda _{n}\end{bmatrix}=V\Lambda$

## Requirement
- $A$ is real symmetric $\implies$ $A$ is diagonalizable over $\mathbb{R}$ by an orthogonal matrix
- $A$ is normal ($A^{*}A=A A^{*}$) $\implies$ $A$ is unitary diagonalizable over $\mathbb{C}$
- All eigenvalues are distinct $\implies$ diagonalizable over the [[Field|field]] containing them
### Definition: normal
- over $\mathbb{C}$
	- $A^{*}A=A A^{*}$
- over $\mathbb{R}$
	- $A^{\top}A=A A^{\top}$


## Definition: multiplicity
- **geometric** multiplicity: $dim(\mathbf{N}(A-\lambda I))$
- **algebraic** multiplicity: the number of times $\lambda$ appears as a root of the characteristic polynomial $P_{A}(\lambda)$

We always have:
 $1\leq$ geometric multiplicity $\leq$ algebraic multiplicity

> [!NOTE]
> A matrix is diagonalizable if for **all** $\lambda$ we have geometric multiplicity $=$ algebraic multiplicity

