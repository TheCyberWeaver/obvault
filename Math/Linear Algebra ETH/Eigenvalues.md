## Definition
Find $v\in \mathbb{R}^{n}\setminus \{ 0 \}$ with $Av=\lambda v$
$(\lambda,v)$ is an eigenvalue-eigenvector pair

## Useful fact
Eigenvalues of $\begin{pmatrix}	a & b \\ b & a\end{pmatrix}$ are $a\pm b$
## Example: Fibonacci numbers
$g_{0}=\begin{pmatrix}	1 \\ 0\end{pmatrix}$
$g_{n}=M^{n}g_{0}=\begin{pmatrix}	F_{n+1} \\ F_{n}\end{pmatrix}=\begin{bmatrix}	1 & 1 \\ 1 & 0\end{bmatrix}\begin{pmatrix}	F_{n} \\ F_{n-1}\end{pmatrix}$
We find the eigenvalues of $M$ and the corresponding eigenvectors

$\begin{bmatrix}	M-\lambda I \end{bmatrix}$ has a not trivial null space
$\implies [M-\lambda I]$ not invertible
$\implies \det(M-\lambda I)=0$
$\det \begin{bmatrix}	1-\lambda & 1 \\ 1 & -\lambda\end{bmatrix}=\lambda^{2}-\lambda-1=0$
$\lambda_{1}=\frac{1+\sqrt{ 5 }}{2},\lambda_{2}=\frac{1-\sqrt{ 5 }}{2}$ (Golden ratio)
For $\lambda_{1}$:
$\begin{pmatrix}	0 \\ 0\end{pmatrix}=\begin{bmatrix}	1-\lambda_{1} & 1 \\ 1 & -\lambda_{1}\end{bmatrix}\begin{pmatrix}	(v_{1})_{1} \\ (v_{1})_{2}\end{pmatrix}$
$v_{1}=\begin{pmatrix}	\frac{1+\sqrt{ 5 }}{2} \\ 1\end{pmatrix}$
$v_{2}=\begin{pmatrix}	\frac{1-\sqrt{ 5 }}{2} \\ 1\end{pmatrix}$
$\implies span(v_{1},v_{2})=\mathbb{R}^{2}$
$g_{0}=\begin{pmatrix}	1 \\ 0\end{pmatrix}=\alpha_{1}v_{1}+\alpha_{2}v_{1}$
$\implies \alpha_{1}=\frac{1}{\sqrt{ 5 }},\alpha_{2}=-\frac{1}{\sqrt{ 5 }}$
$g_{n}=M^{n}g_{0}=M^{n}\left( \frac{1}{\sqrt{ 5 }}v_{1}-\frac{1}{\sqrt{ 5 }}v_{2} \right)$
$=\frac{1}{\sqrt{ 5 }}M^{n}v_{1}-\frac{1}{\sqrt{ 5 }}M^{n}v_{2}$
$=\frac{1}{\sqrt{ 5 }}\lambda_{1}^{n}v_{1}=\frac{1}{\sqrt{ 5 }}\lambda_{2}^{n}v_{2}$
$$
F_{n}=\frac{1}{\sqrt{ 5 }}\left( \frac{1+\sqrt{ 5 }}{2} \right)^{n}-\frac{1}{\sqrt{ 5 }}\left( \frac{1-\sqrt{ 5 }}{2} \right)^{n}
$$



## Example: complex Eigenvalue 
$A=\begin{bmatrix}	0 & -1 \\ 1 & 0\end{bmatrix}$
$\det(A-\lambda I)=0$
$\lambda^{2}+1=0$
$\lambda_{1}=i,\lambda_{2}=-i$

Find $v\in \mathbb{C}^{n}$ with $Av=iv$ $(v\neq0)$
$$
Av=iv\Longleftrightarrow v=\begin{pmatrix}
v_{1}\in \mathbb{C} \\
v_{2}\in \mathbb{C}
\end{pmatrix} \text{ gives }
\begin{pmatrix}
-v_{2} \\
v_{1}
\end{pmatrix}=i\begin{pmatrix}
v_{1} \\
v_{2}
\end{pmatrix}
$$
$v_{1}=a+ib, \; v_{2}=x+iy$
$\implies -x-iy=-b+ia\implies x=b,y=-a$
$\implies v=\begin{pmatrix}	a+ib \\ b-ia\end{pmatrix}=(a+ib)\begin{pmatrix}	1 \\ -i\end{pmatrix}$

$\implies \begin{pmatrix}	1 \\ -i\end{pmatrix}$ is an eigenvector of $\lambda_{1}=i$
## Proposition 8.3.1
![[Pasted image 20251205103605.png]]

## Lemma 8.2.8
If $(\lambda,v)$ is an eigenvalue-eigenvector pair, then $(\bar{\lambda},\bar{v})$ is an eigenvalue-eigenvector pair.

![[Pasted image 20251205105147.png|479]]

## Lemma 8.3.6
Let $A\in \mathbb{R}^{n\times n}$ and $\lambda_{1},\dots,\lambda _{n}$ its eigenvalues. ($\lambda$ can be a complex number)
- $\det(A)=\prod_{i=1}^{n}\lambda _{i}$
- $Tr(A)=\sum_{i=1}^{n}\lambda _{i}$

**Proof**
$\det(A-\lambda I)=P(\lambda)=0$ (the characteristic polynomial)
$\det(A-\lambda I)=\sum_{\sigma \in \prod _{n}}sgn(\sigma)\prod_{i=1}^{n}(A-\lambda I)_{i,\sigma(i)}$
$=(a_{11}-\lambda)(a_{22}-\lambda)\dots(a_{nn}-\lambda)+\underbrace{ a_{14}(a_{22}-\lambda)(a_{33}-\lambda)a_{41} }_{ \text{exponent }\leq n-2 }\dots+\dots.$ (If we do not use the identity $\sigma$, then we must have at least two elements not on the diagonal)
$P_{A}(\lambda)=c_{n}\lambda ^{n}+c_{n-1}\lambda ^{n-1}+\dots+c_{0}$
$=(-1)^{n}\lambda ^{n}+(-1)^{n-1}\underbrace{ (a_{11}+a_{22}+\dots+a_{nn}) }_{ \mathrm{Tr}(A) }\lambda ^{n-1}+\dots+\underbrace{ c_{0} }_{ \det (A) }$ (\*)
Note that $P_{A}(0)=c_{0}=\det(A-0I)=\det(A)$
Now consider $P_{A}$ as product of roots
$P_{A}=c_{n}(\lambda-\lambda_{1})(\lambda-\lambda_{2})\dots(\lambda-\lambda _{n})$ 
$P_{A}=(-1)^{n}(\lambda-\lambda_{1})(\lambda-\lambda_{2})\dots(\lambda-\lambda _{n})$ (from \*))
expands:
$P_{A}=(-1)^{n}\lambda ^{n}+(-1)^{n}\lambda ^{n-1}(-\lambda_{1}-\lambda_{2}-\dots -\lambda)+\dots+(-1)^{n}(-1)^{n}(\lambda_{1}\lambda_{2}\dots\lambda _{n})$
$P_{A}=(-1)^{n}\lambda ^{n}+(-1)^{n}\left( -\sum_{i=1}^{n}\lambda _{i} \right)\lambda ^{n-1}+\dots+\prod_{i=1}^{n}\lambda _{i}$
$\implies c_{0}=\prod_{i=1}^{n}\lambda _{i}=\det(A)$
$\implies (-1)\cdot-\sum_{i=1}^{n}\lambda ^{n-1}=\mathrm{Tr}(A)\implies \sum_{i=1}^{n}\lambda _{i}=\mathrm{Tr}(A)$



#math-tools
> [!Important] Method to prove that two matrices are similar
> We set the characteristic equation equal

### Example 1
Prove the eigenvalues of $A$ and $A^{\top}$ are the same
$P_{A^{\top}}(\lambda)=\det(A^{\top}-\lambda I)=\det((A-\lambda I)^{\top})=\det(A-\lambda I)=P_{A}(\lambda)$

### Example 2
Prove $B$ similar to $A$, with $B=S^{-1}AS$
$P_{B}(\lambda)=\det(B-\lambda I)=\det(S^{-1}AS-\lambda S^{-1}S)=\det(S^{-1}(A-\lambda I)S)$
$=\det(S^{-1})\det(A-\lambda I)\det(S)=\det(A-\lambda I)=P_{A}(\lambda)$
