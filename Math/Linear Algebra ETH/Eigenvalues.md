## Definition
Suche $v\in \mathbb{R}^{n}\setminus \{ 0 \}$ with $Av=\lambda v$
$(\lambda,v)$ is an eigenvalue-eigenvector pair


## Example: Fibonacci numbers
$g_{0}=\begin{pmatrix}	1 \\ 0\end{pmatrix}$
$g_{n}=M^{n}g_{0}=\begin{pmatrix}	F_{n+1} \\ F_{n}\end{pmatrix}=\begin{bmatrix}	1 & 1 \\ 1 & 0\end{bmatrix}\begin{pmatrix}	F_{n} \\ F_{n-1}\end{pmatrix}$
We find the eigenvalues of $M$ and the corresponding eigenvectors

$\begin{bmatrix}	M-\lambda I \end{bmatrix}$ has a not trivial null space
$\implies [M-\lambda I]$ not invertible
$\implies \det(M-\lambda I)=0$
$\det \begin{bmatrix}	1-\lambda & 1 \\ 1 & -\lambda\end{bmatrix}=\lambda^{2}-\lambda-1=0$
$\lambda_{1}=\frac{1+\sqrt{ 5 }}{2},\lambda_{2}=\frac{1-\sqrt{ 5 }}{2}$  (Golden ratio)
For $\lambda_{1}$:
$\begin{pmatrix}	0 \\ 0\end{pmatrix}=\begin{bmatrix}	1-\lambda_{1} & 1 \\ 1 & -\lambda_{1}\end{bmatrix}\begin{pmatrix}	(v_{1})_{1} \\ (v_{1})_{2}\end{pmatrix}$
$v_{1}=\begin{pmatrix}	\frac{1+\sqrt{ 5 }}{2}  \\ 1\end{pmatrix}$
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
$\implies v=\begin{pmatrix}	a+ib  \\ b-ia\end{pmatrix}=(a+ib)\begin{pmatrix}	1 \\ -i\end{pmatrix}$

$\implies \begin{pmatrix}	1 \\ -i\end{pmatrix}$ is an eigenvector of $\lambda_{1}=i$
## Proposition 8.3.1
![[Pasted image 20251205103605.png]]

## Lemma 8.2.8
If $(\lambda,v)$ is an eigenvalue-eigenvector pair, then $(\bar{\lambda},\bar{v})$ is an eigenvalue-eigenvector pair.

![[Pasted image 20251205105147.png|479]]

