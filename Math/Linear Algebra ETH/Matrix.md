---
tags:
  - linker-exclude
---
#eth 
Vectors in form of matrix: 
$$
\begin{pmatrix}
\begin{pmatrix}
1 \\
3 \\
5
\end{pmatrix},\begin{pmatrix}
2 \\
4 \\
6
\end{pmatrix}
\end{pmatrix}
\to
\begin{bmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{bmatrix}
$$

> [!NOTE]
> A $m\times n$ matrix is a table with $m$ rows and $n$ columns
> also noted as $A=[a_{ij}]^{m\quad n}_{i=1,j=1}\in \mathbb{R}^{m\times n}$
> OR
> we can treat a matrix as a function:
> $A:[m]\times[n]\to \mathbb{R}$
> $A(i,j)=A_{ij}$

**other notation form**
$A=\begin{bmatrix}\mathbf{v}_{1},\dots \mathbf{v}_{n}\end{bmatrix}$
$A=\begin{bmatrix}\mathbf{u^\top_{1}} \\ \vdots \\ \mathbf{u}^\top_{m}\end{bmatrix}$
$\mathbf{0}$ : The zero matrix

![[Pasted image 20250926112317.png]]
Identische matrix $I$
$a_{ij}=\delta_{ij}$ with Kronecker-Delta $\delta_{ij}=1$ falls $i=j$ und $0$ sonst 

> [!NOTE]
> Die Spalten von $A$ sind linear unabhängig $x=0$ ist der einzige Vektor mit $Ax=0$
[[Linear Independence#Equivalent Statements to linear independence|Other equivalent statements]]

# Column space

> [!Definition]
>  $\mathbf{C}(A):=\{Ax:x \in\mathbb{R}^{n}\}\subseteq \mathbb{R}^{m}$

$$
 \mathbf{C}(\begin{bmatrix}
2 & 3 \\
3 & -1
\end{bmatrix})=Span\left(\begin{pmatrix}
2 \\
3
\end{pmatrix},\begin{pmatrix}
3 \\
-1
\end{pmatrix}\right)=\mathbb{R}^{2}
$$
![[Linear Independence#Span of vectors#Definition of Span 1.25]]

# Rank
$rank(A)=n$ : linear unabhängige Spalten

if $rank(A)=0$ : Nullmatrix

**Example**
$rank(\begin{bmatrix}1 & 2 \\ 2 & 4\end{bmatrix})=1$

# Lemma 2.11
![[Pasted image 20251001103647.png]]


# Transpose (Transposition)

$A^{\top}=[a_{ji}]^{n\quad m}_{i=1,j=1}$

**Example**
$$
A=\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}
\leftrightarrow 
A^{\top}=\begin{bmatrix}
1 & 4 \\
2 & 5 \\
3 & 6
\end{bmatrix}
$$
$$
(A^{\top})^{\top}=A
$$
$$
(A+B)^{\top}=A^{\top}+B^{\top}
$$
$$
(AB)^{\top}=B^{\top}A^{\top}
$$
# Row Space

$\mathbf{R}(A):=\mathbf{C(A^{\top})}$

Note that 
- $\mathbf{R}(A)\subseteq \mathbb{R}^{n}$
- $\mathbf{C(A)}\subseteq \mathbb{R}^{m}$
# Null Space
![[Pasted image 20251001112601.png]]

$\mathbf{0}\in N(A)$ 

$N(A)=\{\mathbf{0}\}\Longleftrightarrow$ Spalten von A sind linear unabhängig 
$N(A)=\mathbb{R}^{n}\Longleftrightarrow A=\mathbf{0}$



> [!Important]
> If the **columns of a matrix are linearly independent**, then the **null space contains only the zero vector**.
> consider $A\mathbf{x}=x_{1}\mathbf{a}_{1}+x_{2}\mathbf{a}_{2}+\dots+x_{n}\mathbf{a}_{n}$

## Properties
![[Orthogonality#Lemma 5.1.10]]
# Trace
The trace of a matrix is the sum of its diagonal elements.
$$
\text{tr}(A)=\sum_{i=1}^{n} a_{ii}
$$
Let $A$ be a square matrix and let $\lambda_{1},\lambda_{2},\dots,\lambda _{n}$ be its [[Eigenvalues|eigenvalues]], then:
$\mathrm{Tr}(A)=\sum_{i=1}^{n}\lambda _{i}$
$\det(A)=\prod_{i=1}^{n}\lambda _{i}$
