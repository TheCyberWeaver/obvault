$A\in \mathbb{R}^{m\times n}$ invertible then there is $A^{-1}$ and $\forall{b\in \mathbb{R}^{n}}\;$ one can solve $Ax=b$


$Ax\approx b\implies x=A^{\dagger}b$

**Case 1**: $A\in \mathbb{R}^{m\times n}$ has full column rank $n$
**Case 2**: $A\in \mathbb{R}^{m\times n}$ has full row rank $m$
**Case 3**: general case

## Proof
### Case 1: full column rank
- $A^{\top}A$ is invertible
- $Ax=b$ for $b\in \mathbb{R}^{m}$ is not always solvable
However, we can try to solve $Ax=\text{proj}_{C(A)}(b)$
$\Longleftrightarrow A^{\top}A\hat{x}=A^{\top}b$
$\hat{x}=(A^{\top}A)^{-1}A^{\top}b$
#### Definition: Pseudoinverse
Let $A\in \mathbb{R}^{m\times n}$ and $Rank(A)=n$, then
$A^{\dagger}=(A^{\top}A)^{-1}A^{\top}$
**Properties**
$A^{\dagger}A=I$ (Note that $A^{\dagger}$ is here the left inverse)
$AA^{\dagger}=A(A^{\top}A)^{-1}A^{\top}=$ [[Projection|projection]] matrix of $C(A)$

$Ax=b$ might not be solvable, but $A^{\dagger}b$ solves $A^{\top}Ax=A^{\top}b$


### Case 2: full row rank
**Idea**: $A^{\top}$ has full column rank
Let $B=A^{\top}$
We use the definition from case 1 and get
$B^{\dagger}=(B^{\top}B)^{-1}B^{\top}$
#### Definition: Pseudoinverse
Let $A\in \mathbb{R}^{m\times n}$ and $Rank(A^{\top})=m$, then
$A^{\dagger}=(B^{\dagger})^{\top}=((B^{\top}B)^{-1}B^{\top})^{\top}=B(B^{\top}B)^{-1}=A^{\top}(A A^{\top})^{-1}$

**Properties**
$A A^{\dagger}=I$ (Note that $A^{\dagger}$ is only the left inverse)
$A^{\dagger}A=A^{\top}(A A^{\top})^{-1}A$ [[Projection|projection]] matrix of $R(A)$ or $C(A^{\top})$


Since $A$ is full row rank, $\forall{b\in \mathbb{R}^{m}}\;$ there exists $x \in \mathbb{R}^{n}$ such that $Ax=b$, but there might be more than one such vectors. (a natural strategy is to choose the smallest $x$). Therefore, we choose $A^{\dagger}$ such that $A^{\dagger}b$ is the solution from $min\{ \lVert x \rVert|Ax=b, x \in \mathbb{R}^{n} \}$

For $A\in \mathbb{R}^{m\times n}$, $b\in C(A)$
vector $\hat{x}\in C(A^{\top})$ with $A\hat{x}=b$ is the unique solution from $min\{ \lVert x \rVert|Ax=b, x \in \mathbb{R}^{n} \}$ 
**Proof**: 
$\{x \in \mathbb{R}^{n}|Ax=b\}=\hat{x}+N(A)$ where $\hat{x}\in C(A^{\top}),A\hat{x}=b$
Then $\forall{y\in N(A)}\;$: 
$$
\lVert \hat{x}+y \rVert^{2}=\lVert \hat{x}^{2} \rVert +2\hat{x}^{\top}y+\lVert y \rVert ^{2}>\lVert x \rVert ^{2} 
$$
Therefore $\lVert \hat{x} \rVert^{2}$ is the smallest.


Note that $A^{\dagger}$ is precisely the matrix that maps $b$ to $\hat{x}$, meaning $\hat{x}=A^{\dagger}b$
**Proof**:
we need to prove 
- $A A^{\dagger}b=b$ 
	- using $A A^{\dagger}=I$, this is proved
- $A^{\dagger}b\in C(A^{\top})$
	- $A^{\dagger}b=A^{\top}(A A^{\top})^{-1}b\in C(A^{\top})$, proved

### Case 3: general case

$A\in \mathbb{R}^{m\times n}$, $Rank(A)=r$
Idea: $A=C\cdot R$ ([[CR decomposition]]) with $C\in \mathbb{R}^{m\times r},R\in \mathbb{R}^{r\times n}$
Observation:
- $C(A)=\{ Ax|x \in \mathbb{R}^{n} \}=\{ Cy|y\in \mathbb{R}^{r} \}$
- $N(A)=\{ x \in \mathbb{R}^{n}|Ax=0 \}=N(R)$
#### Definition: Pseudoinverse
For $A=C\cdot R$
$A^{\dagger}=R^{\dagger}\cdot C^{\dagger}$
$A^{\dagger}=R^{\top}(R R^{\top})^{-1}(C^{\top}C)^{-1}C^{\top}=R^{\top}(C^{\top}CRR^{\top})^{-1}C^{\top}=R^{\top}(C^{\top}AR^{\top})^{-1}C^{\top}$

> [!Quote] [[Linear Algebra 2 ETH.pdf#page=26&selection=76,0,76,11&color=note|Lemma 6.4.8]]
> Given $A\in \mathbb{R}^{m\times n}$ and $b\in \mathbb{R}^{m}$, the unique solution of $min\{ \lVert x \rVert|x \in \mathbb{R}^{n}, A^{\top}Ax=A^{\top}b \}$ is given by $\hat{x}=A^{\dagger}b$

Let $\hat{x}=A^{\dagger}b$, show $A^{\top}A\hat{x}=A^{\top}b$:
$A^{\top}A\hat{x}=A^{\top}AR^{\top}(C^{\top}AR^{\top})^{-1}C^{\top}b=R^{\top}C^{\top}CRR^{\top}(C^{\top}AR^{\top})^{-1}C^{\top}$
$=R^{\top}(C^{\top}AR^{\top})(C^{\top}AR^{\top})^{-1}C^{\top}b=R^{\top}C^{\top}b=A^{\top}b$

Show that $\hat{x}\in C(A^{\top}A)$
$C(A^{\top}A)=C(A^{\top})=C(R^{\top})$ (see [[Orthogonality#Lemma 5.1.10]])
$\hat{x}=A^{\dagger}b=R^{\top}\underbrace{ [(C^{\top}AR^{\top})^{-1}C^{\top}b] }_{ \text{vector} }$ $\implies x \in C(R^{\top})$

**Conversely**
We can also find two matrices $S\in \mathbb{R}^{m\times r}$ (full column rank) $T\in \mathbb{R}^{r\times n}$ (full row rank)
Then for $A=S\cdot T\in \mathbb{R}^{m\times n}$ 
$A^{\dagger}=T^{\dagger}S^{\dagger}$

> [!NOTE] 
> $C(A)=C(S)$
> $N(A)=N(T)$

## Properties
$AA^{\dagger}A=A$
$A^{\dagger}A A^{\dagger}=A^{\dagger}$
$AA^{\dagger}$ is symmetric and [[Projection|projection]] matrix of $C(A)$
$A^{\top}A$ is symmetric and [[Projection|projection]] matrix of $C(A^{\top})$
$(A^{\top})^{\dagger}=(A^{\dagger})^{\top}$
