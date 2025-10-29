#eth #exercise 
# 1. Matrix multiplication

a) $\mathbf{v}^{\top}\mathbf{w}=n^{2}+n$
b) $\mathbf{v}\mathbf{w}^{\top}=\begin{bmatrix}2 & 2 & 2 & 2 \\ 4 & 4 & 4 & 4  \\ 6 & 6 & 6 & 6  \\ 8 & 8 & 8 & 8\end{bmatrix}$
c) $\mathbf{w}^{\top}(\mathbf{v}\mathbf{w}^{\top})\mathbf{v}=(\mathbf{w}^{\top}\mathbf{v})^{2}=(\mathbf{v}^{\top}\mathbf{w})^{2}=(n^{2}+n)^{2}=n^{4}+2n^{3}+n^{2}$

# 2. Exercise 2.47
a) suppose $r=n$
$C=A$
$R'=I$

b) suppose $r=0$
$C=[\;]$
$R'=[\;]$

# 3. Matrix multiplication and invertibility
a)
$BA=CA$
$\implies BAA^{-1}=CAA^{-1}$
$\implies BI=CI$
$\implies B=C$

b)
It is false.
**Counterexample:**
$A=\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix},B=I,C=\begin{bmatrix}1 & 1 \\ 0 & 1\end{bmatrix}$
$BA=IA=A=\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}=\begin{bmatrix}1 & 1 \\ 0 & 1\end{bmatrix}\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}=CA$

$AB=\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}I=\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}$
$AC=\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}\begin{bmatrix}1 & 1 \\ 0 & 1\end{bmatrix}=\begin{bmatrix}1 & 3 \\ 0 & 0\end{bmatrix}$
$\implies AB\neq AC$

c)
$BA=CA$
$\implies BA-CA=\mathbf{0}$
$\implies (B-C)A=0$
$\implies(B-C)^{-1}(B-C)A=(B-C)^{-1}\mathbf{0}$
$\implies IA=\mathbf{0}$
$\implies A=\mathbf{0}$

# 4. Special matrix inverses
a)
$A^{-1}=\begin{bmatrix}0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0\end{bmatrix}$
b)
$D^{-1}=\begin{bmatrix} \frac{1}{2} & 0 & 0 \\ 0 & \frac{1}{3} & 0 \\ 0 & 0 & \frac{3}{2}\end{bmatrix}$

c)
$B^{-1}=\begin{bmatrix}0 & \frac{1}{3} & 0 \\ 0 & 0 & \frac{3}{2}  \\ \frac{1}{2} & 0 & 0\end{bmatrix}$

# 5. Inverses of matrix powers
a) $(A^{k})^{-1}=(A^{-1})^{k}$
**Proof**:
$A^{k}(A^{-1})^{k}=\underbrace{ AA\dots A }_{ k }\underbrace{ A^{-1}A^{-1}\dots A^{-1} }_{ k }$
$=\underbrace{ AA\dots A }_{ k-1 }(AA^{-1})\underbrace{ A^{-1}A^{-1}\dots A^{-1} }_{ k-1 }$
$=I$

b)
We prove the claim by showing a nilpotent matrix $A$ has an inverse leads to contradiction.
$A^{k}=0$
$A^{k}(A^{-1})^{k}=\mathbf{0}(A^{-1})^{k}$
$I=\mathbf{0}$

c)
$AA^{3}=A^{4}$
$AI=I$
$A=I$

d)
$A=\begin{bmatrix}0 & 1 \\ 1 & 0\end{bmatrix}$
e)
$A=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}$

# 6. Inverse of triangular matrices
a)
$L^{-1}=\begin{bmatrix}1 & 0 \\ -a & 1\end{bmatrix}$

b)
A matrix is invertible
$\Longleftrightarrow A\mathbf{x}=\mathbf{b}$ has an unique solution

$a_{11}x_{1}=b_{1}$
$a_{22}x_{2}+a_{21}x_{1}=b_{2}$
$\vdots$
$a_{kk}x_{k}+\sum_{j=1}^{k-1}a_{kj}x_{j}=b_{k}$
Each step solves uniquely for $x_{k}$​ since $a_{kk}\neq 0$. Hence a unique solution exists for every $b$.

c)

d)
Yes