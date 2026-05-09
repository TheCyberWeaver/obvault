 
## Notations
$A=\begin{bmatrix}\mathbf{v}_{1} & \mathbf{v}_{2} & \dots & \mathbf{v}_{n}\end{bmatrix}$
$$
b=A\mathbf{x}
$$
$$
b=\sum_{j=1}^{n} x_{j}\mathbf{v}_{j}
$$
$A=\begin{bmatrix}\mathbf{u}^{\top}_{1} \\ \mathbf{u}_{2}^{\top} \\ \vdots \\ \mathbf{u}_{m}^{\top}\end{bmatrix}$
$$
b_{i}=\mathbf{u}_{i}^{\top}\mathbf{x}
$$


## Method: Gauss elimination
![[Pasted image 20251017113825.png]]![[Pasted image 20251017113949.png]]

Gaus elimination succeeds $\leftrightarrow$ The columns of $A$ are linearly independent

## Method: [[Gauss-Jordan Elimination]] 
[[Gauss-Jordan Elimination]]

# All solutions of $A\mathbf{x}=\mathbf{b}$
## Definition: The solution space 
$\mathbf{Sol}(A,b)\overset{ def }{ = }\{ \mathbf{x}\in \mathbb{R}^{n}:A\mathbf{x}=\mathbf{b} \}\subseteq \mathbb{R}^{n}$

It's obvious that $\mathbf{Sol}(A,\mathbf{0})=\mathbf{N}(A)$ (see [[Computing the three fundamental subspaces#Null space|How to compute null space]])
and $\mathbf{Sol}(A,\mathbf{b})$ is just a shifted [[Null Space (Kernel of a Matrix)|null space]]
**visualization of a shifted null space**
![[Pasted image 20251031114540.png|532]]
Thus,
$$
\mathbf{Sol}(A,\mathbf{b})=\{ \mathbf{s}+\mathbf{x}: \mathbf{x}\in \mathbf{N}(A) \}
$$

To solve $\mathbf{Sol}(A,\mathbf{b})$, we just compute one solution using [[Gauss-Jordan Elimination]] and a basis $B=\{ \mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n-r} \}$ from $\mathbf{N}(A)$. 
Then 
$$
\mathbf{Sol}(A,\mathbf{b})=\left\{ s+\sum_{i=1}^{n-r}\lambda _{i}\mathbf{v}_{i}:\; \lambda _{i}\in \mathbb{R} \text{ for } i\in[n-r] \right\}
$$
Generally, a shifted copy of a subspace in a vector space is called an **affine subspace**
## Theorem 6.2.2
> [!QUOTE] [[Linear Algebra 2 ETH.pdf#page=16&selection=314,0,314,13&color=note|Theorem 6.2.2]]
> Suppose $\mathbf{Sol}(A,b)$ is not empty
> $\mathbf{Sol}(A,b)=x_{1}+N(A)$ where $x_{1}\in \mathbf{R}(A)$ is unique such that $Ax_{1}=b$

Now we know that we can find a unique vector that can represent $\mathbf{Sol}(A,b)$
The vector $x_{1}$ is **orthogonal** to the $N(A)$ (the shortest position vector)

- [ ] Proof

### Edge case
> [!Question]
> What if $\mathbf{Sol}(A,b)$ is empty?

Let $A=[a_{1}|a_{2}|\dots|a_{n}]$
Consider the equation $\sum_{i=1}^{n}\lambda _{i}a_{i}+\mu\cdot b=0$ 
$b$ is linear independent from $\{ a_{1},\dots,a_{n} \}$
The equation has a solution if $\mu=0$ 
$\Longleftrightarrow b=-\sum_{i=1}^{n}\frac{\lambda _{i}a_{i}}{u}$

$\mathbf{Sol}(A,b)=\varnothing\Longleftrightarrow\{ z\in \mathbb{R}^{m}|A^{\top}z=0,b^{\top}z=1 \}\neq \varnothing$

Let $P=\mathbf{Sol}(A,b)$, $D=\{ z\in \mathbb{R}^{m}|A^{\top}z=0,b^{\top}z=1 \}$
**Proof**: $P$ and $D$ can have a same solution
$z\in D$ and $x \in P$
$0=0^{\top}x=z^{\top}Ax=z^{\top}b=1$
$\implies Contradiction$

**Proof**: $P= \varnothing\implies D\neq \varnothing$
$P=\varnothing\implies b\not\in C(A)\Longleftrightarrow b-\text{proj}_{C(A)}(b)\neq0$
$b=\text{proj}_{C(A)}(b)+q$ with $q\in C(A)^{\perp}=N(A^{\top})$
This means $q\neq0$ 
Let $z=\frac{1}{q^{\top}q}q$

$z\in N(A^{\top})\implies A^{\top}z=0$
$b^{\top}z=\frac{1}{q^{\top}q}b^{\top}q=\frac{1}{q^{\top}q}(p+q)^{\top}q=\frac{1}{q^{\top}q}\underbrace{ p^{\top}q }_{ 0 }+\frac{1}{q^{\top}q}q^{\top}q=1$

### Application: Row Independent Equation Systems

If $A\in \mathbb{R}^{m\times n}$ and the rows are linear independent:
$\{ x \in \mathbb{R}^{n}|Ax=b \}$ is solvable for all $b\in \mathbb{R}^{m}$
**Proof**:
$z^{\top}A=0\implies x=0\implies z^{\top}b=0\neq1\implies D=\varnothing$

### Application: [[Projection]] System
$A^{\top}Ax=A^{\top}b$ is always solvable for all $b\in \mathbb{R}^{m}$
**Proof**:
$z^{\top}A^{\top}A=0\Longleftrightarrow z\in N(A^{\top}A)=N(A)$ (See [[Orthogonality#Lemma 5.1.10]])
$\implies Az=0\implies z^{\top}A^{\top}b=(Az)^{\top}b=0\neq1\implies D=\varnothing$


## Dimension of the solution space
> [!QUOTE] [[Linear Algebra ETH.pdf#page=157&selection=104,0,104,12&color=note|Theorem 4.39]]
> If $A\mathbf{x}=\mathbf{b}$ has a solution, then $\mathbf{Sol}(A,\mathbf{b})$ has dimension $n-r$, since $\text{dim}(\mathbf{Sol}(A,\mathbf{b}))=\text{dim}(\mathbf{N}(A))$

## Lemma 6.2.1
> [!Quote] [[Linear Algebra 2 ETH.pdf#page=16&selection=98,0,98,11&color=note|Lemma 6.2.1]]
> Let $A\in \mathbb{R}^{m\times n}$. Let $x,y\in \mathbf{C}(A^{\top})$. We have$$
Ax=Ay\Longleftrightarrow x=y 
$$

**Proof**:
$x \in C(A^{\top}), y\in C(A^{\top}) \implies x-y\in C(A^{\top})$
$Ax=Ay\implies A(x-y)=0\implies x-y\in N(A)\implies x-y \in C(A^{\top})^{\perp}$
$(x-y\in C(A^{\top}))\wedge (x-y\in C(A^{\top})^{\perp})\implies x-y=0\implies x=y$


## Certificate
$A\in \mathbb{R}^{m\times n},b\in \mathbb{R}^{m},A=\begin{bmatrix}a_{1}^{\top} \\ a_{2}^{\top} \\ \vdots \\ a^{\top}_{m}\end{bmatrix}$
$a_{i}^{\top}\in \mathbb{R}^{n}$, consider $P=\{ x \in \mathbb{R}^{n}|a_{i}^{\top}x\leq b_{i}, \;i \in[m]\}=\{ x \in \mathbb{R}^{n}|Ax\leq b\}$
### Theorem: Farkas
$P=\{ x \in \mathbb{R}^{n}|Ax\leq b\}=\varnothing\Longleftrightarrow \{ z\in \mathbb{R}^{m}|A^{\top}z=0,b^{\top}z=-1,z\geq0 \}$


OR formally
![[Pasted image 20251114115652.png]]