Two subspaces $V$ and $W$ are orthogonal if for all $\mathbf{v}\in V$ and $\mathbf{w}\in W$, the vectors $\mathbf{v}$ and $\mathbf{w}$ are orthogonal

[[Linear Algebra 2 ETH.pdf#page=4&selection=218,0,218,11&color=note|Lemma 5.1.2]]
To prove this we only need to prove that the basis of the two subspaces are orthogonal to each other.
The basis are denoted as $v_{1}\dots,v_{k}$ and $w_{1},\dots,w_{l}$ 
In such case the set $\{ v_{1},\dots,v_{k},w_{1},\dots,w_{l} \}$ are linearly independent.

**Proof** 
Consider the linear combination 
$$
\sum_{i=1}^{k} \lambda_{i}v_{i}+\sum_{j=1}^{l} \mu _{j}w_{j}=0
$$
we want to show that $\lambda _{i}=0$ and $\mu _{j}=0$

define
$$
v=\sum_{i=1}^{k} \lambda _{i}v_{i}
$$
then 
$$
v=-\sum_{j=1}^{l} \mu _{j}w_{j}=0
$$
then 
$v^{\top}v=-\sum_{j=1}^{l}\mu _{j}v^{\top}w_{j}=0$
Since $v^{\top}v=||v||$, this means $v=0$

Hence, we get
$$
\begin{cases}
\sum_{i=1}^{k} \lambda _{i}v_{i}=0 \\
\sum_{j=1}^{l} \mu _{j}w_{j}=0
\end{cases}
$$
Since $v_{1},\dots v_{k}$ and $w_{1},\dots,w_{l}$ are linear independent vectors, $\lambda _{i}=0$ and $\mu _{j}=0$ for all $i,j$

This means $\{ v_{1},\dots,v_{k},w_{1},\dots w_{l} \}$ form the basis of a new subspace denoted as $V+W$
and we must have $dim(V)+dim(W)=dim(V+W)$

## Examples
If $v,w\in \mathbb{R}^{n}$ are orthogonal, then 
$||v+w||^{2}=||v||^{2}+||w||^{2}$

### Fact 1
$v,w$ orthogonal
$V,W$ orthogonal subspaces

### Fact 2
$\{ v,w \}$ are linear independent
$\implies v,w$ are basis of $\mathbb{R}^{2}$
and we can decompose $\mathbb{R}^{2}$ as 
$\mathbb{R}^{2}=\{  \lambda v|\lambda \in \mathbb{R} \}+\{ \mu w|\mu \in \mathbb{R} \}$ (MinKonski sum)
## Lemma 5.1.3
![[Pasted image 20251107103221.png]]
# Orthogonal Complement
## Definition: Orthogonal Complement
$V^{\perp}=\{ w\in \mathbb{R}^{n}|w^{\top}v=0 \text{ for all } v\in V \}$

### Theorem 5.1.6

> [!Important]
> $$
> \mathbf{N}(A)=\mathbf{C}(A^{\top})^{\perp}=\mathbf{R}(A)^{\perp}
> $$

of course 
$$
\mathbf{N}(A)^{\perp}=\mathbf{C}(A^{\top})
$$

Show $\mathbf{N}(A)\subseteq \mathbf{C}(A^{\top})^{\perp}$
Let $x \in \mathbf{N}(A)$ (meaning $Ax=0$)
By definition if $x \in \mathbf{C}(A^{\top})^{\perp}$ then $x^{\top}b=0\; \forall b\in \mathbf{C}(A^{\top})$
Lets write $\forall b\in \mathbf{C}(A^{\top})$ as  $b=A^{\top}y$ for all $y\in \mathbb{R}^{m}$ (recall the definition of column space [[Matrix#Column space]])
$b^{\top}x=(A^{\top}y)^{\top}x=y^{\top}Ax=y^{\top} 0=0$ (recall the rules of transpose [[Matrix#Transpose (Transposition)]])


Show $\mathbf{C}(A^{\top})^{\perp}\subseteq \mathbf{N}(A)$
Let $x \in C(A^{\top})^{\perp}$
By definition $x^{\top}b=0 \;\forall b\in \mathbf{C}(A^{\top})$
again we write $b$ as $b=A^{\top}y$ for some $y\in \mathbb{R}^{m}$
Let's choose $y=Ax$ (which is a valid vector in $\mathbb{R}^{m})$:
Then $x^{\top}b=x^{\top}(A^{\top}Ax)=(Ax)^{\top}Ax=\lvert \lvert Ax \rvert \rvert^{2}=0$
$\implies Ax=0$
so $x \in \mathbf{N}(A)$

Hence the theorem is proved

### Example
Find $N(A)^{\perp}$
Just find $C(A^{\top})$ or $R(A)$

### Example 2
Let $V\subseteq \mathbb{R}^{n}$ a subspace
dimension: $n-1$
Theres is $\alpha_{1},\dots,\alpha _{n}\in \mathbb{R}$ with
$V=\left\{  x \in \mathbb{R}^{n}|\; \sum_{i=1}^{n}\alpha _{i}x_{i}=0  \right\}$ 
Therefore, $V=\alpha ^{\perp}$

If we let $A=[\alpha_{1},\alpha_{2},\dots,\alpha _{n}]$ be a $1\times n$ matrix, then
$$
\mathbf{N}(A) =\mathbf{C}(A^{\top})^{\perp}=\mathbf{R}(A)^{\perp}=V
$$

$V$ is the null space of the matrix A, and it is a hyperplane

### Theorem 5.1.7
![[Pasted image 20251107101902.png]]

**Proof**:
	Let $v_{1}\dots v_{k}$ be basis from $V$, and let $w_{1}\dots w_{l}$ be basis from $W$
	$\forall _{i}\in[k],j\in[l]\quad( v_{i}^{\top}w_{j}=0)$
$(i)\to (ii)$
Let $A=\begin{bmatrix}v_{1}^{\top} \\ v_{k}^{\top}\end{bmatrix}\in \mathbb{R}^{k\times n}$
$\mathbf{C}(A^{\top})=V$ 
We know $W=V^{\perp}$
$\implies V^{\perp}=W=\mathbf{N}(A)\implies dim(V)+dim(W)=n$

$(ii)\to (iii)$
... 

$(iii)\to (i)$
$W\subseteq V^{\perp}$ since $W$ is orthogonal to $V$ 
show $V^{\perp}\subseteq W$
...
### Lemma 5.1.8
> [!NOTE]
> $\mathbb{R}^{n}=V+V^{\perp}=V^{\perp}+(V^{\perp})^{\perp}\implies V=(V^{\perp})^{\perp}$

### Lemma 5.1.10

> [!NOTE] Title
> $N(A)=N(A^{\top}A)$ and $C(A^{\top})=C(A^{\top}A)$

**Proof**: 
$N(A)\subseteq N(A^{\top}A)$
$x \in N(A)$ then $Ax=0$
$\implies A^{\top}Ax=A^{\top}0=0$
$\implies x \in N(A^{\top}A)$

$N(A^{\top}A)\subseteq N(A)$
$x \in N(A^{\top}A)$ then $A^{\top}Ax=0$
$x^{\top}A^{\top}Ax=(Ax)^{\top}Ax=\lVert Ax \rVert^{2}=0\implies Ax=0\implies x \in N(A)$

$\implies N(A)=N(A^{\top}A)$

### Example
$A=[1,2]\in \mathbb{R}^{1\times 2}$
$N(A)=\{ x \in \mathbb{R}^{2}|x_{1}+2x_{2}=0 \}$
$A^{\top}A=\begin{bmatrix} 1 & 2 \\ 2 & 4\end{bmatrix}$
$N(A^{\top}A)=\{ x \in \mathbb{R}^{2} | x_{1}+2x_{2}=0,\;2x_{1}+4x_{2}=0 \}=\{ x \in \mathbb{R}^{2}|x_{1}+2x_{2}=0 \}=N(A)$

