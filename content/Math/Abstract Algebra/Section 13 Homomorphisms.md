## 13.1 Definition
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=130&selection=123,0,141,8&color=note|p.125]]
> > A map φ of a group G into a group G′ is a homomorphism if the homomorphism property $$\phi (ab) = \phi(a)\phi(b)$$ holds for all $a,b \in G$.


**trivial homomorphism**: $\phi (g)= e'$ for all $g\in G$

> [!tip]
> if G is abelian, then G' must also be abelian:$$a'b'=\phi(a)\phi(b)=\phi(ab)=\phi(ba)=\phi(b)\phi(a)=b'a'$$

Recall: 
- $det(AB)=det(A)det(B)$ on invertible n\*n matrices ([Determinant](Determinant.md))
- matrix A is invertible if and only if det(A) is nonzero.

This means that det is a homomorphism mapping $GL(n,\mathbb{R})$ (the multiplicative group of all invertible n\*n matrices) into the multiplicative group $\mathbb{R}^*$ of non zero real numbers.

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=132&selection=217,0,224,1&color=note|p.127]]
> > Homomorphisms of a group G into itself are often useful for studying the structure of G


## 13.7 Example
One can define multiplication by an integer as a homomorphism of integer addition to itself.
$\phi_r:\mathbb Z\rightarrow \mathbb Z$ $$\phi_r(m+n)=r(m+n)$$
## 13.9 Example
One can also define integral on a certain interval as a homomorphism of function addition to real number addition.
$\sigma: F\rightarrow\mathbb R$ $$\sigma(f)=\int_0^1 f(x)dx $$
## 13.10 Example: Reduction Modulo n
$\gamma: \mathbb Z \rightarrow \mathbb Z_n$ $$\gamma(m)=r\ ,\text{where r is the remainder given by the division when m/n}$$ 
Here, it is a many-to-one map

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=133&selection=286,0,354,18&color=note|p.128]]
> > Composition of group homomorphisms is again a group homomorphism. That is, if φ : G → G′ and γ : G′ → G′′ are both group homomorphisms then their composition (γ ◦ φ) : G → G′′, where (γ ◦ φ)(g) = γ (φ(g)) for g ∈ G, is also a homomorphism. (See Exercise 49.)


# 12.12 Properties of Homomorphisms

let $\phi$ be a homomorphism of a group $G$ into a group $G'$
- If $e$ is the identity element in $G$, then $φ(e)$ is the identity element $e'$ in$G'$.
- If $a ∈ G$, then $φ(a^{-1}) = φ(a)^{-1}$.
- If H is a subgroup of $G$, then $φ[H]$ is a subgroup of $G'$.
- If $K'$ is a subgroup of $G' ∩ φ[G]$, then $φ^{-1}[K']$ is a subgroup of $G$.
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=134&selection=57,0,61,56&color=note|p.129]]
> > Loosely speaking, φ preserves the identity element, inverses, and subgroups.
> 

## 13.11 Definition Im

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=133&selection=395,0,511,1&color=note|p.128]]
> > Let φ be a mapping of a set X into a set Y , and let A ⊆ X and B ⊆ Y . 
> > - The image $φ[A]$ of A in Y under φ is $\{φ(a) | a \in A\}$.  Similar to [[Section 8 Groups of Permutations#8.14 Definition|Definition of Image of group under a function]]
> > - The set φ\[X] is the range of φ. 
> > - The inverse image $φ^{-1}[B]$ of B in X is $\{x \in X | φ(x) \in B\}$. 
> 
> 
## 13.13 Definition $Ker(\phi)$

Let $\phi:G\rightarrow G'$ 
$Ker(\phi)$ is the kernel of $\phi$, $Ker(\phi)=\{x\in G\ |\ \phi(x)=e'\}$ 
In other words: The Elements in G that correspond to the identity element in G'

**Example: Linear Transformation**
Let $\phi:\mathbb{R}^n \rightarrow \mathbb{R}^m$ and A be an $m\times n$ matrix of real numbers: $$\phi(\mathbf v)=A \mathbf v$$ $\phi$ is a homomorphism, because $\phi(v+w)=A(v+w)=Av+Aw=\phi(v)+\phi(w)$ 
This is known as a linear transformation.
$Ker(\phi)$ is known as the *[[Null Space]]* of A. It consists all $\mathbf v\in \mathbb R^n$ such that $A\mathbf v=\mathbf 0$  (the zero vector)

## 13.15 Theorem
let $H=Ker(\phi)$, $a \in G$. Then: $$\phi^{-1}[\{\phi(a)\}]=aH=Ha$$In other words. 
- A [[Section 10 Cosets and The Theorem of Lagrange#10.2 Definition of Cosets|coset]] of $G$ that contains a collapse into an element $\phi(a)$ after the homomorphism.
- For any $a\in G$, the full set of things that share the same image $\phi(a)$ is the coset a$Ker(\phi)$.

This figure shows how the Cosets collapse:
![[Pasted image 20250604224836.png|389]]

## 13.16 Example 
Consider the group homomorphism
$$
\pi: \mathbb{C}^* \to U = \{\,z \in \mathbb{C} : |z| = 1\}, \quad
\pi(z) = \frac{z}{|z|}.
$$

Geometrically, this map projects each nonzero complex number radially onto the unit circle.
## 13.17 Example
- Let D be the additive group of all differentiable functions mapping $\mathbb R$ into $\mathbb R$
- Let F be the additive group of all functions mapping $\mathbb R$ into $\mathbb R$
- $\phi:D\rightarrow F$
- $\phi(f)=f'$
$Ker(\phi)$= all constant functions, which form a subgroup C of F.

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=136&selection=335,0,343,1&color=note|p.131]]
> > Thus Ker(φ) consists of all constant functions, which form a subgroup C of F
> 
> A better way is to say C is a subgroup of D, since $Ker(\phi)$ is normally not defined in $G'$

Let's consider an element of F, $x^2$ and all the elements in D that collapse into $x^2$
we know one element is $\frac{x^3}{3}$ . According to [[#13.15 Theorem]] all such functions form the coset $\frac{x^3}{3}+C$ . which is exactly the integral of $x^2$  
$\phi^{-1}[\{\phi(a)\}]=aH$
$\phi(a)=x^2$
$\phi^{-1}[\{x^2\}]=\frac{x^3}3 + Ker(\phi)$ 


This proves that:
> [!NOTE]
> If two differentiable functions have the same derivative on a connected domain, they differ by a constant (and nothing else).

## 13.18 Corollary of 13.15
> [!NOTE]
> $\phi$ is a one-to-one map if and only if $Ker(\phi)=\{e\}$

## How to show $\phi:G\rightarrow G'$ is an Isomorphism

1. Show $\phi$ is a homomorphism.
2. Show $Ker(\phi)={e}$
3. Show $\phi$ maps G onto G'

| Check            | Criterion                                             |
| ---------------- | ----------------------------------------------------- |
| **Injective?**   | $Ker φ = {e_G}$                                       |
| **Surjective?**  | $Im φ = H$                                            |
| **Isomorphism?** | Both conditions above hold (homomorphism + bijective) |

> [!IMPORTANT]
> Every fiber of a homomorphism is exactly one coset of the kernel

## 13.19 Definition normal

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=137&selection=182,0,210,1&color=note|p.132]]
> > A subgroup H of a group G is normal if its left and right cosets coincide, that is, if g H = Hg for all g ∈ G. 
> 
> all abelian groups are normal. Trivial.

$Ker(\phi)$ is always a normal subgroup of $G$

## Ways to Prove a Subgroup $H$ Is Normal in $G$

A subgroup \(H\) is normal (denoted \(H \triangleleft G\)) if it satisfies any of the following equivalent conditions:

1. **Conjugation Closure**  
   Prove directly that$$\forall\,g\in G,\;\forall\,h\in H:\quad g\,h\,g^{-1}\in H.$$
   - *Proof Outline:*  
     1. Take an arbitrary \($g\in G$\) and \($h\in H$\).  
     2. Compute $g\,h\,g^{-1}$ and use properties of $H$ (e.g., how generators behave) to rewrite it as an element of H.  
     3. Since this holds for all g and h, we conclude $g\,H\,g^{-1} = H$, so H is closed under conjugation by every element of G.

2. **Left and Right Cosets Coincide**  
   Equivalently, $$\forall\,g\in G:\quad gH = Hg.$$
   - *Proof Idea:*  
     - To show $gH \subseteq Hg$, take any element $g\,h\in gH$. If H is conjugation-closed, then $g\,h = (g\,h\,g^{-1})\,g$ with $g\,h\,g^{-1}\in H$, so $g\,h\in Hg$.  
     - The reverse inclusion is similar. Hence $gH = Hg$ for all g, and that’s exactly the condition for normality.

3. **Kernel of a Group Homomorphism**  
   If there exists a group homomorphism $$\varphi: G \;\longrightarrow\; K$$such that $$H = \ker(\varphi),$$
   then automatically $H \triangleleft G$.  
   - *Reason:* Every kernel of a homomorphism is a normal subgroup.
See Summary [[Section 14 Factor Groups#Ways to Prove $H$ is a Normal Subgroup - Summary|Ways to Prove H is a Normal Subgroup - Summary]]
