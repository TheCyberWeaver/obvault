#eth 
# Covector

$\mathbf{v}= \begin{pmatrix}1 \\ 2\end{pmatrix}$, then $\mathbf{v}^{\top}=\begin{pmatrix}1 & 2\end{pmatrix}$.

$$
\mathbf{v}^{\top}\mathbf{w}=\sum^m_{i=1}v_{i}w_{i} =\mathbf{v}\cdot \mathbf{w};\in \mathbb{R}
$$

# Definition 1.21

> [!PDF|note] [[Linear Algebra ETH.pdf#page=37&selection=20,0,102,1&color=note|Linear Algebra ETH, p.36]]
> > Vectors $\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n}\in \mathbb{R}^m$ are linearly dependent if at least one of them is a linear combination of the others, i.e. there is an index $k \in [n]$ and scalars $\lambda_{j}$ such that $$\mathbf{v}_{k}=\sum^{n}_{j=1,j\neq k}\lambda_{j}\mathbf{v}_{j}$$ . Otherwise, $\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n}$ are linearly independent

Drei Vektoren im $\mathbb{R}^{2}$ sind immer linear abhängig: 
	entweder sind zwei bereits kollinear, oder der dritte ist eine Linearkombination der beiden ersten


> [!Special Cases]
>  linear abhängig: 
>- $\mathbf{v}=\mathbf{0}$ 
>- $\dots,\mathbf{0},\dots$
>- $\dots,\mathbf{\mathbf{v}\dots,\mathbf{\mathbf{v}\dots}}$
>
> linear unabhängig:
> - $\mathbf{v}\neq \mathbf{0}$
> - empty sequence: $()$ 
> 	Es gibt kein $k\in[n]$, deswegen linear independent according to the definition above


# Equivalent Statements to linear dependence

1. ==At least one== of the vectors is a linear combination of the other ones. (see [[#Definition 1.21]])
2. ==There are scalars== $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ besides $0, 0, . . . , 0$ such that $\sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}=\mathbf{0}$. We also say that $\mathbf{0}$ is a nontrivial linear combination of the vectors. 
3. ==At least one== of the vectors is a linear combination of the previous ones.

***Proof***
idea to proof: $S_{1}\implies S_{2}\implies S_{3}\implies S_{1}$

$S_{1}\implies S_{2}$
Sei $\mathbf{v}_{k}=\sum^n_{j=1,j\neq k}\lambda_{j}\mathbf{v}_{j}$, setze $\lambda_{k}=-1$.
Dann $\sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}=0$ und $\lambda_{k}\neq 0$, also gilt $S_{2}$

$S_{2}\implies S_{3}$
Sei $k$ der größte Index mit $\lambda_{k}\neq 0$ : Dann $\sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}=0$ 
$\implies \mathbf{v}_{k}=\sum^{k-1}_{j=0}\left( -\frac{\lambda_{j}}{\lambda_{k}} \right)\mathbf{v_{j}}\implies S_{3}$

$S_{3}\implies S_{1}$ Eine Linearkombination der vorherigen ist auch eine Linearkombination der anderen.

# Equivalent Statements to linear independence
1. ==None of the vectors== is a linear combination of the other ones. (see [[#Definition 1.21]])
2. ==There are no scalars== $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ besides $0, 0, . . . , 0$ such that $\sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}=\mathbf{0}$. We also say that $\mathbf{0}$ can only be written as a trivial linear combination of the vectors.
3. ==None of the vectors== is a linear combination of the previous ones.

Note that: a linear combination of linearly independent vectors can be written as a linear combination ==in only one way==


# Span of vectors

Spann von Vektoren: Menge aller Linearkombinationen
## Definition 1.25
Let $\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n}\in \mathbb{R}^m$. Their span is the set of all linear combinations.
## Example
![[Pasted image 20250924115325.png|583]]
$\mathbf{Span}(\mathbf{v}_{1},\mathbf{v}_{2},\dots,\mathbf{v}_{n}):=\left\{ \sum^n_{j=1}\lambda_{j}\mathbf{v}_{j}:\lambda_{j}\in \mathbb{R}, \forall j\in[n] \right\}$

## Lemma 1.26
Let $\mathbf{v_{1},v_{2},\dots,v_{n}}\in \mathbb{R}^m$, and let $\mathbf{v}\in \mathbb{R}^m$be a linear combination of $\mathbf{v_{1},v_{2},\dots,v_{n}}$
The ...