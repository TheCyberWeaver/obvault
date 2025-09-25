#eth #exercise 

# 1. Lines in $\mathbb{R}^m$
![[Pasted image 20250924130937.png]]
a)
Since $\mathbf{u}\in L$, $\mathbf{u}=\lambda_{2} \mathbf{w}$ for some $\lambda_{2} \in \mathbb{R}$
$\mathbf{w}=\frac{\mathbf{u}}{\lambda_{2}}$
$L=\{\lambda_{1} \mathbf{w}:\lambda_{1}\in \mathbb{R}\}=\left\{ \frac{\lambda_{1}}{\lambda_{2}} \mathbf{u}:\lambda_{1}\in \mathbb{R},\lambda_{2}\in \mathbb{R} \right\}=\{\lambda \mathbf{u}:\lambda\in \mathbb{R}\}$

b)
$L_{1}=\{\lambda_{1} \mathbf{v}:\lambda_{1}\in \mathbb{R}\}$
$L_{2}=\{\lambda_{2} \mathbf{w}:\lambda_{2}\in \mathbb{R}\}$

$L_{1}=L_{2}$
$\lambda_{1}\mathbf{v}=\lambda_{2}\mathbf{w}$
either $\lambda_{1}=0,\lambda_{2}=0$ meaning that $L_{1}\cap L_{2}=\{0\}$
or
$\mathbf{v}=\lambda \mathbf{w}, \lambda \in \mathbb{R}$ meaning that $\mathbf{w}$ is a element of $L_{1}$, and according to question a, they must be the same line.

c)
$\mathbf{v}\cdot \mathbf{w}=0$
$\begin{pmatrix}v_{1} \\ v_{2}\end{pmatrix} \begin{pmatrix}d_{1} \\ d_{2}\end{pmatrix}=0$
$v_{1}d_{1}+v_{2}d_{2}=0$
$v_{1}=- \frac{d_{2}}{d_{1}}v_{2}$
$v_{1}=- \frac{d_{2}}{d_{1}}\lambda,\quad v_{2}=\lambda,\quad\lambda \in \mathbb{R}$
$\mathbf{v=}\begin{pmatrix}v_{1} \\ v_{2}\end{pmatrix}=\lambda \begin{pmatrix}- \frac{d_{2}}{d_{1}} \\ 1\end{pmatrix},\lambda \in \mathbb{R}$
$L=\{\lambda \begin{pmatrix}- \frac{d_{2}}{d_{1}} \\ 1\end{pmatrix}:\lambda \in \mathbb{R}\}$
and this is a line

# 2. Orthogonality and Linear independence
![[Pasted image 20250924130914.png|648]]
a)
$\mathbf{v}\cdot \mathbf{w}=0$
$s+6+2s=0$
$s=-2$

b)
$t=0$

c)
$\mathbf{v}\cdot \mathbf{w}=0$
suppose $\mathbf{v},\mathbf{w}$ are linearly dependent: $\mathbf{w}=\lambda \mathbf{v}$
$\mathbf{v}\cdot\lambda \mathbf{v}=0$
$\lambda (\mathbf{v}\cdot \mathbf{v})=0$
$\mathbf{v}\cdot \mathbf{v}=0$
$\sum^n_{i=1}v_{i}^{2}=0$
There is no nonzero solution to this equation, so $\mathbf{v}$ and $\mathbf{w}$ must be linearly independent

# 3. [[Cauchy-Schwarz inequality]]
![[Pasted image 20250924131014.png|389]]
$$
\sum^m_{i=1}v_{i}=\begin{pmatrix}
1 \\
1 \\
\vdots \\
1
\end{pmatrix}\cdot \mathbf{v}\leq \| 1 \| \| \mathbf{v} \| = \|\mathbf{v}\|\leq \sqrt{ m }\|\mathbf{v}\|
$$
 
![[Pasted image 20250924131023.png|387]]
$$
\sum^m_{i=1}\sqrt{ i }v_{i}=\begin{pmatrix}
\sqrt{ 1 } \\
\sqrt{ 2 } \\
\vdots \\
\sqrt{ m }
\end{pmatrix}\cdot \mathbf{v}\leq \left\| \begin{pmatrix}
\sqrt{ 1 } \\
\sqrt{ 2 } \\
\vdots \\
\sqrt{ m }
\end{pmatrix} \right\| \| \mathbf{v} \| = \sqrt{ 1+2+\dots+m }\|\mathbf{v}\|= \sqrt{ \frac{m^{2}+m}{2} }\|\mathbf{v}\|
$$

- [ ] proof
# 4. [[Linear Independence]]
![[Pasted image 20250925081800.png]]
a)
$$
\mathbf{v}_{m}=\sum^m_{j=1}(-1)^{j+1}\mathbf{v}_{j}=\begin{pmatrix}
1+0+\dots+0 \\
1+(-1)+0+\dots+0 \\
0+(-1)+1+0+\dots+0 \\
\vdots \\
0+\dots+0+1
\end{pmatrix}=\begin{pmatrix}
1 \\
0 \\
0 \\
\vdots  \\
0 \\
1
\end{pmatrix}
$$
b)
$$\sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}=\mathbf{0}$$
- [ ] Proof

# 5. Angle between vectors
![[Pasted image 20250925093448.png]]
$$\cos(\alpha)=\frac{\mathbf{v}\cdot \mathbf{w}}{\|\mathbf{v\|\|\mathbf{w\|}}}=\frac{xz+xy+zy}{(\sqrt{ x^{2}+y^{2}+z^{2} })^{2}}=\frac{xz+xy+zy}{x^{2}+y^{2}+z^{2}}$$
$x+y+z=0$
$(x+y+z)^{2}=0$
$x^{2}+y^{2}+z^{2}+2xy+2xz+2yz=0$
$xy+xz+yz=-\frac{1}{2}(x^{2}+y^{2}+z^{2})$
$$
\cos(\alpha)=-\frac{1}{2}\frac{x^{2}+y^{2}+z^{2}}{x^{2}+y^{2}+z^{2}}=-\frac{1}{2}
$$

# 6. Challenge 1.6
![[Pasted image 20250925095322.png]]
