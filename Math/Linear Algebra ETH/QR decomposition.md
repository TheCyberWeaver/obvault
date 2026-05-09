Let $A$ be an $m × n$ matrix with linearly independent columns. ($rank(A)=n$)
$$
A=QR
$$
$Q$ is $m\times n$ matrix with orthonormal columns, output of [[Orthonormal Bases#Gram-Schmidt Process| Gram-Schmidt Process]]
$R$ is given by $Q^{\top}A\in \mathbb{R}^{n\times n}$

> [!Quote] [[Linear Algebra 2 ETH.pdf#page=22&selection=504,0,504,12&color=note|Lemma 6.3.11]]
> $R$ is upper triangular and invertible
> $QQ^{\top}A=A$


**Proof**:
$R_{ki}=0\;	\forall{k\in \{ 2\dots n \},i<k}\;$
We know $q_{k}^{\top}q_{i}=0$ $\forall{i<k}$
Since the subspace $S_{k-1}=span(q_{1}\dots q_{k-1})=span(a_{1},\dots,a_{k-1})$ we get $q_{k}^{\top}a_{i}=0$ for all $i=1,\dots,k-1$. Hence $R_{ki}=0\;	\forall{k\in \{ 2\dots n \},i<k}$ (note that $R=Q^{\top}A$)

Moreover,
$Q Q^{\top}$ is [[Projection|projection]] matrix onto $C(A)$
The least squares solution $\hat{x}$ to $Ax = b$ can be calculated by:
$A^{\top}A\hat{x}=A^{\top}b$ (see [[Projection#Least Square (Data Fitting)]])
$R^{\top}Q^{\top}QR\hat{x}=R^{\top}Q^{\top}b$
$R^{\top}R\hat{x}=R^{\top}Q^{\top}b$ 
$R\hat{x}=Q^{\top}b$ ($R^{\top}$ is invertible)


> [!NOTE] R is invertible
> $N(A)=\{ 0 \}$
> $\implies N(R)=\{ 0 \}$
> $\implies R$ is invertible
> $\implies R^{\top}$ is invertible

## Properties
- $A^{\top}A=R^{\top}R$
- $(A^{\top}A)^{-1}=R^{-1}(R^{\top})^{-1}$
- $A^{\dagger}=R^{-1}Q^{\top}$
- $P=QQ^{\top}$
- $Q^{\top}PQ=I$