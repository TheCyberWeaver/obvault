---
level: "1"
---
#exercise #eth 

# 1. Linear combinations of vectors
## a
![[Pasted image 20250918221011.png]]
Proof:
Consider any vector $\mathbf{u}\in \mathbb{R}^{2}$
$$
\mathbf{u}=\lambda \mathbf{v}+\mu \mathbf{w}
$$
$$
\begin{pmatrix}
u_{1} \\
u_{2}
\end{pmatrix}=\lambda \begin{pmatrix}
1 \\
1
\end{pmatrix} + \mu \begin{pmatrix}
-1 \\
1
\end{pmatrix}
$$
$$
\lambda = \frac{u_{1}+u_{2}}{2},\mu=\frac{u_{2}-u_{1}}{2}
$$
we see $\lambda$ and $\mu$ can always be solved in terms of $u_{1}$ and $u_{2}$
q.e.d.
## b
![[Pasted image 20250918221048.png]]
$$
\mathbf{u}=\begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix}
$$
suppose $\mathbf{u}=\lambda \mathbf{v}+\mu \mathbf{w}$, $\lambda$ must be 1 because of $u_{1}$ , but then $\mu$ can never be adjusted so that $u_{2}$ and $u_{3}$ are both 0

# 2. The perfect long drink
## a
![[Pasted image 20250921215456.png]]
$$
x \begin{pmatrix}
15 \\
85
\end{pmatrix}+(1-x) \begin{pmatrix}
35 \\
65
\end{pmatrix}=\begin{pmatrix}
23 \\
77
\end{pmatrix}
$$
$$
x=\frac{3}{5}, \quad y=1-x=\frac{2}{5}
$$
## b
![[Pasted image 20250921215443.png]]
$$
\hat{D}:=\{\begin{pmatrix}
g \\
t
\end{pmatrix}\in \mathbb{R}^{2}:g+t=100,g\geq0,t\geq 0,15\leq g\leq 35,65\leq t\leq 85
\}
$$
This set is a segment.
## c
![[Pasted image 20250921215434.png]]
a triangle

# 3. Geometry of linear combinations
![[Pasted image 20250921215515.png]]
## a
![[Pasted image 20250921215536.png|285]]
## b
![[Pasted image 20250921215552.png|290]]
## c
![[Pasted image 20250921215620.png|283]]