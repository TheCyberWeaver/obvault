#eth 

# Equivalent Statement to Invertible
Let $A$ be an invertible $m\times m$ matrix:
1. $T_{A}:\mathbb{R}^{m}\to \mathbb{R}^{m}$  is [[Set#Bijective (undoable)|bijective]]
2. There is an $m\times m$ matrix $B$ such that $BA=I$
3. The columns of $A$ are linearly independent

**Proof** $S_{2}\implies S_{3}$
Assume $A\mathbf{x}=\mathbf{0}$
$\mathbf{x}=(BA)\mathbf{x}=B(A\mathbf{x})=B\mathbf{0}=\mathbf{0}$
Since $A\mathbf{x}=\mathbf{0}$ has only the trivial solution $\mathbf{x}=0$, the **columns of** $A$ are **linearly independent**
(See [[Linear Independence#Equivalent Statements to linear independence]] Statement 2)

> [!NOTE]
> If $A$ is not invertible, it is called **singular**

## Lemma 2.54
Let $A,B$ be $m\times m$ matrices such that $BA=I$. Then also $AB=I$
According to $S_{1}$ in [[#Equivalent Statement to Invertible]], we know $T_{A}$ is bijective. So for every $\mathbf{y}$ we have some $\mathbf{x}$ with $A\mathbf{x}=\mathbf{y}$ 
$AB\mathbf{y}=AB(A\mathbf{x})=A(BA)\mathbf{x}=A\mathbf{x}=\mathbf{y}$
Thus, we must have $AB=I$

## Observation 2.56
$A$ is invertible if and only if there is an $B$ satisfying one of the following conditions (and therefore all):
i)$AB=I$
ii)$BA=I$
iii)$AB=BA=I$
Proof of uniqueness of $B$
$$
B=IB\overset{ (ii) }{ = }(B'A)B=B'(AB)\overset{ i }{ = }B'I=B'
$$
## Example
$$
A=\begin{bmatrix}
a
\end{bmatrix}\implies A^{-1}=\begin{bmatrix}
\frac{1}{a}
\end{bmatrix}
$$
$$
A=\begin{bmatrix}a & b \\ c & d\end{bmatrix}\implies A^{-1}=\frac{1}{ad-bc}\begin{bmatrix}d & -b \\ -c & a\end{bmatrix}
$$
