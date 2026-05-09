 #exercise 
# 2. Determinant of block matrix 

> [!recall] Definition 7.2.3
> $$ \det(A)=\sum_{\sigma \in \prod_{n} }sgn(\sigma)\prod_{i=1}^{n} A_{i,\sigma(i)}$$


##### a)

Using the definition 7.2.3 
$\det M=\sum_{\sigma \in \prod_{n} }sgn(\sigma)\prod_{i=1}^{n} M_{i,\sigma(i)}$

Because the lower-left block is zero, any term with some $i>m$ and $\sigma(i)\leq m$ contains a factor $M_{i,\sigma(i)}=0$ and vanishes. Hence the only permutations that contribute satisfy

$i \in \{ m+1\dots n \}\implies \sigma(i)\in \{ m+1\dots n \}$ and $i \in \{ 1\dots m\}\implies \sigma(i)\in \{ 1\dots m \}$ (since $\sigma$ is bijective)
This means we can split $\sigma$ into $\sigma_{1}$ and $\sigma_{2}$ where $\sigma_{1}$ maps $\{ 1\dots m \}\to \{ 1\dots m \}$ and $\sigma_{2}$ maps $\{ m+1\dots n \}\to \{ m+1\dots n \}$ with $\sigma=\sigma_{1}\circ\sigma_{2}$ and $sgn(\sigma)=sgn(\sigma_{1})sgn(\sigma_{2})$
The product splits:
$$
\prod_{i=1}^{n} M_{i,\sigma(i)}=\left( \prod_{i=1}^{m} A_{i,\sigma_{1}(i)}\right)\left( \prod_{i=m+1}^{n} C_{i-m,\sigma_{2}(i)-m} \right)
$$
Therefore,
$\det M=\sum_{\sigma_{1}\in \prod _{m} }\sum_{\sigma_{2}\in \prod_{n=m}}sgn(\sigma_{1})sgn(\sigma_{2})\left( \prod_{i=1}^{m} A_{i,\sigma_{1}(i)}\right)\left( \prod_{i=m+1}^{n} C_{i-m,\sigma_{2}(i)-m} \right)=\det A\cdot \det C$



##### b)
$M=\begin{bmatrix}	2 & 0 & 0 & 4 & 0 & 7 \\ 9 & 0 & 0 & 0 & 0 & 4 \\ 1 & 0 & 0 & 0 & 0 & 0 \\ 3 & 2 & 0 & 5 & 0 & 7 \\ 2 & 3 & 1 & 5 & 0 & 2 \\ 8 & 8 & 7 & 3 & 2 & 1\end{bmatrix}$
$\det(M)=\det(M^{\top})=\det(\begin{bmatrix}	2 & 9 & 1 & 3 & 2 & 8 \\ 0 & 0 & 0 & 2 & 3 & 8 \\ 0 & 0 & 0 & 0 & 1 & 7 \\ 4 & 0 & 0 & 5 & 5 & 3 \\ 0 & 0 & 0 & 0 & 0 & 2 \\ 7 & 4 & 0 & 7 & 2 & 1\end{bmatrix})$
swap row 2 with row 6, swap row 3 with row 4 (swap twice makes determinant unchanged)
$=\det(\begin{bmatrix}2 & 9 & 1 & 3 & 2 & 8 \\ 7 & 4 & 0 & 7 & 2 & 1\\ 4 & 0 & 0 & 5 & 5 & 3 \\ 0 & 0 & 0 & 0 & 1 & 7 \\ 0 & 0 & 0 & 0 & 0 & 2 \\ 0 & 0 & 0 & 2 & 3 & 8 \end{bmatrix})$
Let $A=\begin{bmatrix}	2 & 9 & 1 \\ 7 & 4 & 0 \\ 4 & 0 & 0\end{bmatrix},B=\begin{bmatrix}	3 & 2 & 8 \\ 7 & 2 & 1 \\ 5 & 5 & 3\end{bmatrix},C=\begin{bmatrix}	0 & 1 & 7 \\ 0 & 0 & 2 \\ 2 & 3 & 8\end{bmatrix}$
$\det(M)=\det(\begin{bmatrix}	A & B \\ 0 & C \end{bmatrix})=\det(A)\det(C)$ (result from previous subtask)
$\det(A)=-16,\det(C)=4$
$\det(M)=-16\cdot4=-64$


