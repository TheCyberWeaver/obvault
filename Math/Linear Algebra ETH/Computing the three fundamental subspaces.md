#eth 

**Example**
![[Pasted image 20251031103918.png|365]]
First, compute the RREF of $A$ ([[Gauss-Jordan Elimination#RREF|RREF]])
# Column space
$\subseteq \mathbb{R}^{m}$
> [!NOTE]
> $\text{dim}(\mathbf{C}(A))=\mathbf{rank}(A)=r$

$R$ is in $RREF(1,3)$ so
$B=\{ \begin{pmatrix}1 \\ 2 \\ 3\end{pmatrix},\begin{pmatrix}0 \\ 1 \\ 2\end{pmatrix} \}$
given by the two independent columns 1 and 3

> [!NOTE]
> row operation does not change the position of the linear independent colomn vectors

# Row space
$\subseteq \mathbb{R}^{n}$
> [!NOTE]
> $\text{dim}(\mathbf{R}(A))=r$

$B=\{ \begin{pmatrix}1 \\ 2 \\ 0 \\ 3\end{pmatrix},\begin{pmatrix}0 \\ 0 \\ 1 \\ -2\end{pmatrix} \}$
given by $R$

after row operation the linear independent row vectors is still linear independent.


## Conclusion (Theorem 4.33)
Let $A$ be an $m\times n$ matrix. Then
$\mathbf{rank}(A)=\mathbf{rank}(A^{\top})$

note that:
- $\mathbf{rank}(A^{\top})=\text{dim}(\mathbf{C}(A^{\top}))=\text{dim}(\mathbf{R}(A))=r$
- $\mathbf{rank}(A)=\text{dim}(\mathbf{C}(A))=r$

> [!NOTE]
> The rank is at most the smaller of the two matrix dimensions. $r\leq \text{min}(n,m)$


# Null space
$\subseteq \mathbb{R}^{n}$

$\mathbf{N}(A)=\mathbf{N}(R)=\mathbf{N}(R')$
by definition 
$\mathbf{x} \in \mathbf{N}(R')\Longleftrightarrow R'\mathbf{x}=0$
## example
we separate the linear independent and dependent columns
$$
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}\underbrace{ \begin{pmatrix}
x_{1} \\
x_{3}
\end{pmatrix} }_{ \in \mathbb{R}^{r} }+\begin{bmatrix}
2 & 3 \\
0 & -2
\end{bmatrix}\underbrace{ \begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix} }_{ \in \mathbb{R}^{n-r} }=\mathbf{0}
$$
note that the first matrix is always $I$. Thus we have
$$
\begin{pmatrix}
x_{1} \\
x_{3}
\end{pmatrix}=-\begin{bmatrix}
2 & 3 \\
0 & -2
\end{bmatrix}\begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix}
$$

$\implies \mathbf{N}(R')$ is isomorphic to $\mathbb{R}^{n-r}$ and the dimension is therefore $n-r$

to get  $\mathbf{N}(A)$  we first write the solution in the form of the elements corresponding to the dependent columns
$\begin{pmatrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4}\end{pmatrix}=\begin{pmatrix}-2x_{2}-3x_{4} \\ x_{2} \\ 2x_{4} \\ x_{4}\end{pmatrix},x_{2},x_{4}\in \mathbb{R}$

To get the basis of $\mathbf{N}(A)$ we give $x_{2},x_{4}$ the values $\begin{pmatrix}0 \\ 1 \end{pmatrix}$ and $\begin{pmatrix} 1 \\ 0\end{pmatrix}$
So in this example, we get $\{  \begin{pmatrix}-3 \\ 0 \\ 2 \\ 1\end{pmatrix},\begin{pmatrix}-2 \\ 1 \\ 0 \\ 0\end{pmatrix}\}$

## Null space isomorphism
(still using the previous example)
$$
T: \underbrace{ \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{pmatrix} }_{ \in \mathbf{N}(R') }\to \underbrace{ \begin{pmatrix}
x_{2} \\
x_{4}
\end{pmatrix} }_{ \in \mathbb{R}^{n-r} }
$$
This is a bijective linear transformation. For every $\begin{pmatrix}x_{2} \\ x_{4}\end{pmatrix}$ we can compute the input using the equation we got previously


# Summary
![[Pasted image 20251031111834.png]]
