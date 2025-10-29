  #eth #exercise 
# 1. Linear functional

a)
$T$ is linear functional if $T(\lambda_{1}\mathbf{u}+\lambda_{2}\mathbf{v})=\lambda_{1}T(\mathbf{u})+\lambda_{2}T(\mathbf{v})$
$$
T(\lambda_{1}\mathbf{u}+\lambda_{2}\mathbf{v})=\sum_{k=1}^{n} k(\lambda_{1}u_{k}+\lambda_{2}v_{k})=\sum_{k=1}^{n} k\lambda_{1}u_{k}+\sum_{k=1}^{n} k\lambda_{2}v_{k}
$$
$$
=\lambda_{1}\sum_{k=1}^{n} ku_{k}+\lambda_{2}\sum_{k=1}^{n} kv_{k}=\lambda_{1}T(\mathbf{u})+\lambda_{2}T(\mathbf{v})
$$
The statement is proved

b)
$$
T(\lambda_{1}\mathbf{u}+\lambda_{2}\mathbf{v})=\sum_{k=1}^{n} (\lambda_{1}u_{k}+\lambda_{2}v_{k})^{k}
$$
$$
\lambda_{1}T(\mathbf{u})+\lambda_{2}T(\mathbf{v})=\lambda_{1}\sum_{k=1}^{n} (u_{k})^{k}+\lambda_{2}\sum_{k=1}^{n} (v_{k})^{k}=\sum_{k=1}^{n} (\lambda_{1}(u_{k})^{k}+\lambda_{2}(v_{k})^{k})
$$
$$
\sum_{k=1}^{n} (\lambda_{1}u_{k}+\lambda_{2}v_{k})^{k}\neq\sum_{k=1}^{n} (\lambda_{1}(u_{k})^{k}+\lambda_{2}(v_{k})^{k})\quad \text{when }n\geq2
$$
Thus, $T$ is not linear functional
# 2. Matrix powers 

IH: $A^{k}=\begin{bmatrix}1+k & k \\ -k & 1-k\end{bmatrix}$ for any $k\geq0$
Base: $k=0$
$A^{0}=\begin{bmatrix}1+0 & 0 \\ -0 & 1-0\end{bmatrix}=\begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix}=I$

IS: $k\to k+1$
$A^{k+1}=AA^{k}\overset{ IH }{ = }A\begin{bmatrix}1+k & k \\ -k & 1-k \end{bmatrix}=\begin{bmatrix}2 & 1 \\ -1 & 0\end{bmatrix}\begin{bmatrix}1+k & k \\ -k & 1-k\end{bmatrix}$
$=\begin{bmatrix}2(1+k)-k & 2k+(1-k) \\ -(1+k) & -k\end{bmatrix}=\begin{bmatrix}k+2 & k+1 \\ -k-1 & -k\end{bmatrix}=\begin{bmatrix}1+(k+1) & k+1 \\ -(k+1) & 1-(k+1)\end{bmatrix}$


By the principle of mathematical induction, $A^{k}=\begin{bmatrix}1+k & k \\ -k & 1-k\end{bmatrix}$ is true for any $k\geq0$

# 3. Reconstruct a linear transformation
a)
$T\begin{pmatrix}\begin{pmatrix}x \\ y\end{pmatrix}\end{pmatrix}=\begin{pmatrix}x+y \\x+2y \\ 2x \end{pmatrix}$
b)
$A=\begin{bmatrix}1 & 1 \\ 1 & 2 \\ 2 & 0 \end{bmatrix}$


# 4. Linear transformation
$T(\mathbf{x})=A\begin{pmatrix}\mathbf{x} \\ 1\end{pmatrix}=\mathbf{v}_{n+1}\cdot1+\sum_{i=1}^{n}\mathbf{v}_{i}x_{i}=\mathbf{v}_{n+1}+\sum_{i=1}^{n}\mathbf{v}_{i}x_{i}$
**Necessity**
$T$ is linear when $T(0)=0$
$T(0)=A\begin{pmatrix}\mathbf{0} \\ 1\end{pmatrix}=\mathbf{v}_{n+1}\cdot1=\mathbf{v}_{n+1}$
meaning that $\mathbf{v}_{n+1}=\mathbf{0}$

**Sufficiency**
if $\mathbf{v}_{n+1}=\mathbf{0}$, then $T=\sum_{i=1}^{n}\mathbf{v}_{i}x_{i}$  which is a matrix transformation and therefore a linear transformation

# 5. Matrix multiplication
$$
\begin{bmatrix}
1 & 0 & 3 \\
3 & 1 & 9 \\
0 & 3 & 1
\end{bmatrix}
+x\begin{bmatrix}
0 & 1 & 0 \\
0 & 3 & 1 \\
1 & 0 & 3
\end{bmatrix}
+y\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 3 \\
0 & 1 & 0
\end{bmatrix}
+z\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
=\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$

Observing numbers at position $(1,1)$
$1+z=0$
$z=-1$
Observing numbers at position $(1,2)$
$x=0$
Observing numbers at position $(1,3)$
$3+y=0$
$y=-3$

Verification:
$$
\begin{bmatrix}
1 & 0 & 3 \\
3 & 1 & 9 \\
0 & 3 & 1
\end{bmatrix}
-3\begin{bmatrix}
0 & 0 & 1 \\
1 & 0 & 3 \\
0 & 1 & 0
\end{bmatrix}
-\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
=\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$
$$
\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}=\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$
The verification holds. The solutions are $x=0,y=-3,z=-1$

b)
$(AB)^{k}=\underbrace{ (AB)(AB)\dots(AB) }_{ \text{k times} }=\underbrace{ AA\dots A }_{ \text{k times} }\underbrace{ B\dots BB }_{ \text{k times} }=A^{k}B^{k}$
c)
$(AB)^{k}=A^{k}B^{k}=\mathbf{0}B^{k}=\mathbf{0}$
$AB$ is nilpotent, the nilpotent degree of is less or equal than $\mathbf{0}$

d)
$(I-A)(I+A+\dots+A^{k-1})$
$=I(I+A+\dots+A^{k-1})-A(I+A+\dots+A^{k-1})$
$=(I+A+\dots+A^{k-1})-(A+A^{2}+\dots+A^{k})$
$=I-A^{k}=I-\mathbf{0}=I$
The equation is proved.

e)


# 6. Rotation matrices
a)
Let $\phi=\frac{\pi}{2}$
$A=Q\left( \frac{\pi}{2} \right)=\begin{bmatrix}\cos\left( \frac{\pi}{2} \right) & \sin\left( \frac{\pi}{2}\right) \\ \sin\left( \frac{\pi}{2} \right) & \cos\left( \frac{\pi}{2} \right) \end{bmatrix}=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}$
b)
$Q(\phi_{3})=Q(\phi_{1})Q(\phi_{2})=\begin{bmatrix}\cos(\phi_{1}) & -\sin(\phi_{1}) \\ \sin(\phi_{1}) & \cos(\phi_{1})\end{bmatrix}\begin{bmatrix}\cos(\phi_{2}) & -\sin(\phi_{2}) \\ \sin(\phi_{2}) & \cos(\phi_{2})\end{bmatrix}$
$=\begin{bmatrix}\cos(\phi_{1})\cos(\phi_{2})-\sin(\phi_{1})\sin(\phi_{2}) & -\cos(\phi_{1})\sin(\phi_{2})-\sin(\phi_{1})\cos(\phi_{2}) \\ \sin(\phi_{1})\cos(\phi_{2})+\cos(\phi_{1})\sin(\phi_{2}) & \cos(\phi_{1})\cos(\phi_{2})-\sin(\phi_{1})\sin(\phi_{2})\end{bmatrix}$
$=\begin{bmatrix}\cos(\phi_{1}+\phi_{2}) & -\sin(\phi_{1}+\phi_{2}) \\ \sin(\phi_{1}+\phi_{2}) & \cos(\phi_{1}+\phi_{2})\end{bmatrix}$
$=Q(\phi_{1}+\phi_{2})$

c)
Let $A=Q(\phi)$
and let $B=Q(2\pi-\phi)$
$AB=Q(\phi)Q(2\pi-\phi)=Q(\phi+2\pi-\phi)=Q(2\pi)=\begin{bmatrix}1 & 0 \\ 0 & 1 \end{bmatrix}=I$
$BA=Q(2\pi-\phi)Q(\phi)=Q(2\pi-\phi+\phi)=Q(2\pi)=\begin{bmatrix}1 & 0 \\ 0 & 1 \end{bmatrix}=I$



