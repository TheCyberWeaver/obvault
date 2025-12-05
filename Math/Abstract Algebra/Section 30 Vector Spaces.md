
## 30.1 Definition: Vector Space
$\langle V,+,\cdot \rangle$ is a **vector space over $F$** if:
for all $a, b \in F$ and $\alpha,\beta \in V$
![[Pasted image 20250730195539.png|246]]
- $+: V\times V\to V$ a function (addition)
- $\cdot: \mathbb{R}\times V\to V$ a function (scalar multiplication)
**Example**:
$\langle\Bbb R^{n},+,\cdot\rangle$
- $\mathbb{R}^{n}=\underbrace{ \mathbb{R}\times \mathbb{R}\times\dots \times \mathbb{R} }_{ n }$

## 30.6 Definition: Span

If all vectors in the vector space can be expressed as a linear combination of a set of vectors in the vector space, this vector set span (or generate ) this vector space. If this is a minimal subset, it is a basis.

### Basis
$B$ is a basis if $B$ is linearly independent and $\mathbf{Span}(B)=V$

## 30.9 Definition: finite dimensional

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=282&selection=224,0,244,1&color=note|A First Course in Abstract Algebra, p.277]]
> > A vector space $V$ over a field $F$ is finite dimensional if there is a finite subset of $V$ whose vectors span $V$. 

## 30.11 Example
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=282&selection=278,0,307,1&color=note|A First Course in Abstract Algebra, p.277]]
> > If $F ≤ E$ and $α ∈ E$ is algebraic over the field $F$, then $F(α)$ is a finite-dimensional vector space over $F$. 

By [[Section 29 Introduction to Extension Fields#29.18 Theorem|29.18 Theorem]] $F(\alpha)$ is spanned by the vectors in $\{1,\alpha,\cdots,\alpha^{n-1}\}$, where $n=deg(\alpha,F)$. See $Q(\sqrt 2)$ in [[Section 29 Introduction to Extension Fields#29.16 Example|29.16 Example]]

If $n=deg(\alpha,F)$, then every vector can be uniquely expressed by $\{1,\alpha,\cdots,\alpha^{n-1}\}$

## 30.21 Definition: Dimension

If $V$ is a finite-dimensional vector space over a field $F$, the number of elements in a basis  is the **dimension** of $V$ over $F$. 

## 30.22 Example

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=285&selection=184,1,230,0&color=note|A First Course in Abstract Algebra, p.280]]
> > Let $E$ be an extension field of a field $F$, and let $α ∈ E$. 
If $α$ is algebraic over $F$ and $deg(α, F) = n$, then the dimension of $F(α)$ as a vector space over $F$ is $n$.


