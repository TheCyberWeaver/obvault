#eth #exercise 
# 10.2 Orthogonal 2 × 2 matrices and rotation matrices
##### a)
$$
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
$$
##### b)
$A$ is orthogonal 
$\implies$ $A^{\top}A =I$
$\implies \begin{bmatrix}	a & c \\ b & d\end{bmatrix}\begin{bmatrix}	a & b \\ c & d\end{bmatrix}=\begin{bmatrix}	1 & 0 \\ 0 & 1\end{bmatrix}$
$\implies \begin{cases} a^{2}+c^{2}=1 \\ ab+cd=0 \\ b^{2}+d^{2}=1\end{cases}$
$\implies (a^{2}+c^{2})(b^{2}+d^{2})-(ab+cd)^{2}=1\cdot1-0\cdot0=1$
$\implies a^{2}b^{2}+a^{2}d^{2}+b^{2}c^{2}+c^{2}d^{2}-a^{2}b^{2}-c^{2}d^{2}-2abcd=1$
$\implies a^{2}d^{2}+b^{2}c^{2}-2abcd=1$
$\implies (ad)^{2}+(bc)^{2}-2(ad)(bc)=1$
$\implies (ad-bc)^{2}=1$
$\implies ad-bc=\pm 1$
$\implies \det(A)=\pm 1$
$\implies$ $\lvert \det(A) \rvert=1$

##### c)
$A=\begin{bmatrix}	1 & 2 \\ 1 & 3\end{bmatrix}$
not orthogonal, but $\lvert \det(A) \rvert=\lvert 1\cdot3-1\cdot2 \rvert=1$
