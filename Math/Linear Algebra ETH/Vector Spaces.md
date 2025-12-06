# Generally
![[Section 30 Vector Spaces]]

# In Linear Algebra
## The eight axioms
![[Pasted image 20251029102433.png|517]]

## Some 'obvious' facts

- There is only one zero vector.
**Proof**:
Take two zero vectors $\mathbf{0}$ and $\mathbf{0}'$
$\mathbf{0}'=\mathbf{0}'+\mathbf{0}$ (3. axiom)
$=\mathbf{0}+\mathbf{0}'$ (1. axiom)
$=\mathbf{0}$ (3. axiom)
- Each $\mathbf{v}$ has only one negative vector

## Subspaces
Let $V$ be a vector space.
A nonempty subset $U\subseteq V$ is called a subspace of $V$ if
- $\mathbf{v}+\mathbf{w}\in U$
- $\lambda \mathbf{v}\in U$
and $U$ is also a vector space

### Examples
$U$ is all quadratic polynomials
	$\mathbf{p}=p_{0}+p_{1}x+p_{2}x^{2}$
This subspace is isomorphic to $\mathbb{R}^{3}$
[[Section 13 Homomorphisms#How to show $ phi G rightarrow G'$ is an Isomorphism|Prove isomorphism]]

> [!NOTE]
> a polynomial should have finite terms

- $U$ all matrices of trace $0$ ([[Matrix#Trace|What is trace of a matrix]])

## Lemma 4.16
Ever linear combination of $V$ is again in $V$

> [!Important] Title
> It has to be finite linear combinations


## Examples of Basis

| Vector sapce $V$                                                 | basis $B$                                                                                                                                |
| ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| $\mathbb{R}^{m}$                                                 | $\{ e_{1},e_{2},\dots,e_{m} \}$                                                                                                          |
| $\mathbf{C}(A)$                                                  | independent columns of $A$                                                                                                               |
| $2\times 2$ symmetric matrices (Subspace of $R^{2\times 2}$) | $\{ \begin{bmatrix}1 & 0 \\ 0 & 0\end{bmatrix},\begin{bmatrix}0 & 1 \\ 1 & 0\end{bmatrix},\begin{bmatrix}0 & 0 \\ 0 & 1\end{bmatrix} \}$ |
| $\mathbb{R}[x]$ (polynomials)                                    | $\{ x^{i}:i=0,1,\dots \}$ (infinite set)                                                                                                 |
| $\mathbf{0}$ (smallest vector space)                             | $\varnothing$ (emptyset)                                                                                                                 |

## Definition: finitely generated vector space
A vector space $V$ is called finitely generated if there exists a finite subset $G\subseteq V$ with $\text{Span}(G)=V$

$\mathbb{R}^{m}$ is finitely generated
$\mathbb{R}[x]$ is **not** finitely generated


## Theorem 4.22
let $G\subseteq V$ be a finite subset with $\text{Span}(G)=V$. Then $V$ has a basis $B\subseteq G$



![[Steinitz exchange lemma]]


## Definition: Dimension

> [!definition]
> $\text{dim}(V)$ is the size of an arbitrary basis $B$ of $V$

## Linear transformations between vector spaces


> [!NOTE]
> If a linear transformation $T:V\to W$ is bijective. Then $V$ and $W$ are isomorphic ([[Section 13 Homomorphisms#How to show $ phi G rightarrow G'$ is an Isomorphism|Prove isomorphism]])

Here, isomorphic means the bases and dimension are preserved
See [[Linear Algebra ETH.pdf#page=145&selection=24,0,24,10&color=note|Lemma 4.27]]
### Example
$V=\mathbb{R}^{2\times 2}$, $W=\mathbb{R}^{4}$, $T:\begin{bmatrix}a & b \\ c & d\end{bmatrix}\to \begin{pmatrix}a \\ b \\ c \\ d\end{pmatrix}$
or generally $V=\mathbb{R}^{m\times n}$, $W=\mathbb{R}^{mn}$
This is bijective (invertible)

$V=$ polynomials of degree 2, $W=\mathbb{R}^{3}$, $T: p_{0}+p_{1}x+p_{2}x^{2}\to \begin{pmatrix}p_{0} \\ p_{1} \\ p_{3}\end{pmatrix}$

> [!NOTE]
> All m-dimensional (real) vector spaces are isomorphic


## How to compute the subspaces
[[Computing the three fundamental subspaces]]