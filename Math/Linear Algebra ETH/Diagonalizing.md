$$
A=V\Lambda V^{-1}
$$
where $V=[v_{1},v_{2},\dots,v_{n}]$  are the eigenvectors
$\Lambda=\begin{bmatrix}	\lambda_{1} & 0 & 0 \\ 0 & \ddots  & 0 \\ 0 & 0 & \lambda _{n}\end{bmatrix}$ are the [[Eigenvalues|eigenvalues]]

**Proof**:
$AV=\begin{bmatrix}	\lambda_{1}v_{1} & \lambda_{2}v_{2} & \dots & \lambda _{n}v_{n} & \end{bmatrix}=\begin{bmatrix}	v_{1} & v_{2} & \dots & v_{n}\end{bmatrix}\begin{bmatrix}	\lambda_{1} & 0 & 0 \\ 0 & \ddots  & 0 \\ 0 & 0 & \lambda _{n}\end{bmatrix}=V\Lambda$
## Definition: multiplicity
- **geometric** multiplicity: $dim(\mathbf{N}(A-\lambda I))$
- **algebraic** multiplicity: the number of times $\lambda$ appears as a root of the characteristic polynomial $P_{A}(\lambda)$

We always have:
 $1\leq$ geometric multiplicity $\leq$ algebraic multiplicity

> [!NOTE]
> A matrix is diagonalizable if for **all** $\lambda$ we have geometric multiplicity $=$ algebraic multiplicity

