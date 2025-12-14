## Theorem
> [!NOTE]
> Any symmetric matrix $A\in \mathbb{R}^{n\times n}$ has $n$ real [[Eigenvalues|eigenvalues]] and an orthonormal basis of $\mathbb{R}^{n}$ consisting of its eigenvectors.

**Proof** (Induction)
There are $k$ orthonormal eigenvectors von $A$
**Base case**
$k=1$:
if $\lambda \in \mathbb{C}$ an eigenvalue of $A$, then $\lambda \in \mathbb{R}$ (we can normalize this $\lambda$):
Let $v\in \mathbb{C}^{n}$ be an eigenvector of $\lambda$. We have $Av=\lambda v$. 
![[Complex number#Hermitian conjugate]]
Since $A$ is real symmetric we have $A^{*}=A$. Thus,
$\bar{\lambda}\lVert v \rVert^{2}=\bar{\lambda}v^{*}v=(\lambda v)^{*}v=(Av)^{*}v=v^{*}A^{*}v=v^{*}Av=v^{*}\lambda v=\lambda \lVert v \rVert^{2}$
Since $v\neq0$, then $\lambda=\bar{\lambda}$.
$\implies\lambda \in \mathbb{R}$

**Induction steps**
$k\to k+1$
$\exists{k}$ orthonormal eigenvectors $v_{1},\dots,v_{k}$ with real [[Eigenvalues|eigenvalues]] $\lambda_{1},\dots\lambda _{k}$
Let $u_{k+1},\dots ,u_{n}$ a orthonormal basis of $span(v_{1},\dots,v_{k})^{\perp}$ 
Define $V=\begin{bmatrix}	v_{1}  & \dots & v_{k} & u_{k+1} & \dots & u_{n}\end{bmatrix}$
$V$ is orthogonal $\implies V^{\top}V=I\Longleftrightarrow V^{\top}=V^{-1}$
Let $B=V^{\top}AV\in \mathbb{R}^{n\times n}$ ($B$ is symmetric)
![[Pasted image 20251212111658.png|472]]
$B=\begin{bmatrix}	\Lambda _{k} & F \\ G & C\end{bmatrix}$
$G_{ij}=u_{i}^{\top}\lambda _{j}v_{j}=\lambda _{j}u_{i}^{\top}v_{j}=0$
$F_{ij}=$
$C_{ij}=u_{i}^{\top}Au_{j}=u_{i}^{\top}A^{\top}u_{j}=(Au_{i})^{\top}u_{j}=u_{j}^{\top}Au_{i}=C_{ji}$
$C$ is symmetric
$\implies C$ has a real eigenvalue $\lambda _{k+1}$ with eigenvector $y\in \mathbb{R}^{n-k}$
Let $w=\begin{pmatrix}	0 \\ y \end{pmatrix}\in \mathbb{R}^{n}$
$Bw=\begin{bmatrix}	\Lambda _{k} & 0 \\ 0 & C \end{bmatrix}\begin{pmatrix}	0 \\ y  \end{pmatrix}=\begin{pmatrix}	0 \\ Cy\end{pmatrix}=\lambda _{k+1}\begin{pmatrix}	0 \\ y\end{pmatrix}=\lambda _{k+1}w$
$\implies$ $w$ is eigenvector of $\lambda _{k+1}$ (under matrix $B$)

Define $v_{k+1}=Vw\Longleftrightarrow V^{\top}v_{k+1}=w$
$B=V^{\top}AV\Longleftrightarrow A=VBV^{\top}$
$\implies Av_{k+1}=VBV^{\top}v_{k+1}=VBw=\lambda _{k+1}Vw=\lambda _{k+1}v_{k+1}$
$v_{k+1}\in span(u_{k+1},\dots,u_{n})\implies v_{i}^{\top}u_{k+1}=0\;	\forall{i=1\dots k}$
Finally we normalize $v_{k+1}$ such that $\lVert v_{k+1} \rVert=1$
Now we proved that there is always $k+1$ real orthonormal eigenvectors

## Corollary 9.2.2
For any symmetric matrix $A$, there exists an orthogonal matrix $V\in \mathbb{R}^{n\times n}$ such that $A=V\Lambda V^{\top}$

## Proposition 9.2.10 (Rayleigh Quotient)
Given a symmetric matrix $A\in \mathbb{R}^{n\times n}$
the Rayleigh Quotient defined for $x \in \mathbb{R}^{n}\setminus \{ 0 \}$ is
$$
R(x)=\frac{x^{\top}Ax}{A^{\top}x}
$$
There is $\lambda _{min}\leq R(x)\leq\lambda _{max}$

## Lemma 9.2.7
Let $A\in \mathbb{R}^{n\times n}$ be a symmetric matrix and $\lambda_{1}\neq\lambda_{2}\in \mathbb{R}$ be two distinct eigenvalues of $A$ with corresponding eigenvectors $v_{1},v_{2}$. Then $v_{1}$ and $v_{2}$ are orthogonal.