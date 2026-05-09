 
### Operation notations
$\odot_{3}$ is multiplication under modulo 3
$\oplus$ is addition under modulo 3
$\langle \mathbb{Z}_{2}\times \mathbb{Z}_{2}, \oplus_{2} \times \oplus_{2}\rangle\simeq V_{4}$ (isomorphism of groups)
$\mathbb{Z}_{m}$ for $\langle \mathbb{Z}_{m},\oplus _{m},\ominus _{m},0\rangle$
$\mathbb{Z}_{m}^{*}$ for $\langle \{ x \in \mathbb{Z}_{m}|gcd(x,m)=1 \},\odot _{m},mod. Inv., 1\rangle$
- $\mathbb{Z}_{6}= \langle \{ 1,5 \},\odot_{6},mod. Inv.,1 \rangle$
## Uniqueness of the Neutral Element
If $e$ is left neutral element and $e'$ is right neutral element, then $e=e'$

**Proof:**
1. Since e′ is a right neutral element, e∗e′=e.
2. Since e is a left neutral element, e∗e′=e′.
## Monoid
### Definition
A **monoid** is an algebraic structure consisting of a set M, a binary operation ∗, and a neutral element e, satisfying the following properties:
1. **Associativity:** For all $x,y,z∈M$, $(x∗y)∗z=x∗(y∗z)$.
2. **Neutral Element:** There exists an element $e∈M$ such that for all $x∈M$, $e∗x=x∗e=x$.
3. **Closed** 
We denote a monoid as $⟨M;∗,e⟩$.
### Example: Monoid of Bitstrings

Consider the set of all finite bitstrings, denoted by $\{0,1\}^{*}$, along with the concatenation operation $∥$, and the empty bitstring ϵ. This forms a monoid: $⟨{0,1}∗;∥,ϵ⟩$

- **Associativity:** Concatenation is associative. For example, $(01∥10)∥01=0110∥01=011001$ is the same as $01∥(10∥01)=01∥1001=011001$.
- **Neutral Element:** The empty bitstring ϵ acts as the neutral element for concatenation. For any bitstring $x∈\{0,1\}^{*}$, $ϵ∥x=x∥ϵ=x$.
### Overview
![[Algebra Structure.excalidraw|403]]

## Inverse
The algebra we work on must have an neutral element at first
- **Left Inverse:** An element $b∈S$ is a left inverse of a if $b∗a=e$, where $e$ is the neutral element.
- **Right Inverse:** An element $c∈S$ is a right inverse of a if $a∗c=e$.

[[Discrete Mathematics ETH.pdf#page=106&selection=308,0,308,9&color=note|Lemma 5.2]]
If an element $a$ has both a left inverse $b$ and a right inverse $c$, and the operation $∗$ is **associative**, then $b$ and $c$ must be the same.

**Proof**:
$b=b*e$ (neutral element)
$=b*(a*c)$ (c is the right inverse)
$=(b*a)*c$ (associativity)
$=e*c$ (b is the left inverse)
$=c$ (neutral element)


## Groups
### Definition
A group is an algebra $\langle G; *,\hat{}, e \rangle$, if $\langle G; *,e \rangle$ is a monoid and every $x \in G$ has an inverse $\hat{a}$
### Other definitions
![[Section 4 Groups#Definition Group - normal definition]]

#### Formalized
- associativity: $\forall x\forall y\forall z\; (x*y)*z=x*(y*z)$
- identity element: $\forall x\; x*e=e*x=x$
	- $\forall x\; x*e=x$ (simplified)
- inverse: $\forall x\; x*\hat{x}=\hat{x}*x=e$
	- $\forall x\; x*\hat{x}=e$ (simplified)

**Proof**: prove that the simplified version is still sufficient
$\hat{x}*x=(\hat{x}*x)*e=(\hat{x}*x)*(\hat{x}*\hat{\hat{x}})=\hat{x}*((x*\hat{x})*\hat{\hat{x}})=\hat{x}*(e*\hat{\hat{x}})$
$=(\hat{x}*e)*\hat{\hat{x}}=\hat{x}*\hat{\hat{x}}=e$

### Examples
$\langle \mathbb{Z}_{3}; \oplus_{3},\ominus_{3},0 \rangle$
$\langle \mathbb{Z}; +,-,0 \rangle$
$\langle \mathbb{Z}_{m}\setminus \{ 0 \},\odot_{m},\text{ mod Inv. },1 \rangle$ when $m$ is prime (see [[Number Theory#Multiplicative Inverses]])
![[Number Theory#Multiplicative Inverses#Example]]

### Lemma 5.3
![[Pasted image 20251103155053.png]]

### An Important example: Permutation Groups

$S_{n}$: the set of $n!$ permutations of $n$ elements OR the set of bijections $\{ 1\dots n \}\to \{ 1\dots n \}$


## Applications
- [[RSA]] Public Key Encryption