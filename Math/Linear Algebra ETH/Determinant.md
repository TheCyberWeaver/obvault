## Define Determinant through axioms
We find a function $\det\{ A\in \mathbb{R}^{n\times n} \}\to \mathbb{R}$ (Note that $A$ must be a square matrix)
with following properties
1. $\det(A)=\det(A^{\top})$
2. $\det(I)=1$
3. $\det(A)=0$ if the columns are linear dependent
4. $\det([a_{1}|\dots|a_{k-1}|a_{k}|\lambda a+\mu b|\dots|a_{k-1}])=\lambda\det([\dots|a_{k-1}|a|\dots])+\mu \det([\dots|a_{k-1}|b|\dots])$

### Simple Example
$\det \begin{bmatrix}	1 & 1 \\ 1 & 1\end{bmatrix}=\det \begin{bmatrix}	\begin{pmatrix}	0 \\ 1  \end{pmatrix}+\begin{pmatrix}	1 \\ 0\end{pmatrix} & \begin{pmatrix}	1 \\ 1\end{pmatrix}\end{bmatrix}=\det \begin{bmatrix}	0 & 1 \\ 1 & 1 \end{bmatrix}+\det \begin{bmatrix}	1 & 1 \\ 0 & 1\end{bmatrix}=0$
$0=\det \begin{bmatrix}	1 & 0 \\ 0 & 1\end{bmatrix}+\det \begin{bmatrix}	0 & 0 \\ 1 & 1\end{bmatrix}+\det \begin{bmatrix}	1 & 1 \\ 0 & 0\end{bmatrix}+\det \begin{bmatrix}	0 & 1 \\ 1 & 0\end{bmatrix}$
$0=1+0+0+\det \begin{bmatrix}	0 & 1 \\ 1 & 0\end{bmatrix}$
$\det \begin{bmatrix}	0 & 1 \\ 1 & 0\end{bmatrix}=-1$

### general example for n=2
$\det \begin{bmatrix}	a & b \\ c & d\end{bmatrix}$
$=\det \begin{bmatrix}	a & 0 \\ 0 & d\end{bmatrix}+\det \begin{bmatrix}	a & b \\ 0 & 0\end{bmatrix}+\det \begin{bmatrix}	0 & 0 \\ c & d\end{bmatrix}+\det \begin{bmatrix}	0 & b \\ c & 0\end{bmatrix}$
$=\det \begin{bmatrix}	a\begin{pmatrix}	1 \\ 0\end{pmatrix} & d\begin{pmatrix}	0 \\ 1\end{pmatrix}\end{bmatrix}+\dots$
$=ad+0+0+(-bc)$
$=ad-bc$

For $n=3$
$\det \begin{bmatrix}	1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0\end{bmatrix}=-\det \begin{bmatrix}	1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}=-1$
the matrix $\begin{bmatrix}	a_{22} & a_{23} \\ a_{32} & a_{33}\end{bmatrix}$ is flipped and thus must multiply $-1$, same principle to [[#Simple Example|example]]
We can see that if we exchange two rows, the determinant must multiply $-1$
## Another Perspective

![[Pasted image 20251126111913.png|459]]
computing the determinant of a $2 × 2$ matrix as the area of the image of the unit square after a linear transformation 

## General case
### Definition 7.2.1
Given a permutation $\pi:\{ 1\dots n \}\to \{ 1\dots n \}$ of n elements
$$
sgn(\pi)=\begin{cases}
1\text{ if } \lvert \{(i,j) |i<j\text{ and }\pi(i)>\pi(j)\} \rvert \text{ is even} \\
-1 \text{ if }  \lvert \{(i,j) |i<j\text{ and }\pi(i)>\pi(j)\} \rvert \text{ is odd}
\end{cases}
$$
#### Example
$\det \begin{bmatrix}	0 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0\end{bmatrix}$
$\pi(1)=3>\pi(2)=1$
$\pi(1)=3>\pi(3)=2$
$\pi(2)=1<\pi(3)=2$
$sgn(\pi)=1$
$\det \begin{bmatrix}	0 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0\end{bmatrix}$ is positive (actually $\det \begin{bmatrix}	0 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0\end{bmatrix}=1$)

### Definition: determinant
$$
\det(A)=\sum_{\sigma \in \prod_{n} }sgn(\sigma)\prod_{i=1}^{n} A_{i,\sigma(i)} 
$$
## Properties
- $\det(A^{\top})=\det(A)$
- $\det(I)=1$
- The columns are linear dependent $\implies \det(A)=0$
- linear
- Let $\pi$ be a permutation, and $P(\pi)$ is the permutation matrix
	- $\det(P(\pi))=sgn(\pi)$
- For a triangular matrix $T$
	- $\det(T)=\prod_{i=1}^{n}T_{_{i}}$
- For a orthogonal matrix $Q$
	- $\det(Q)\in \{ -1,1 \}$
- $\det(AB)=\det(A)\det(B)$
- $\det(A^{-1})=\frac{1}{\det(A)}$
- $A$ invertible $\Longleftrightarrow$ $\det(A)\neq0$
