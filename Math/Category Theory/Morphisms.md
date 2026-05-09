---
tags:
  - linker-exclude
---
## Definition Isomorphisms

> [!NOTE]
> A morphism $f\in Hom_C(A,B)$ is an isomorphism if it has an inverse under composition: 
> There exists a morphism $g\in Hom_C(B,A)$ so that: $$gf=1_A,\quad fg=1_B$$

Note that in $gf=1_A$ f is calculated first. so we have $A\rightarrow B \rightarrow A$

If $f$ is an isomorphism, then $f^{-1}$ is an isomorphism and $(f^{-1})^{-1}=f$

### Examples

the isomorphisms in the category Set are precisely the bijections
see [[Section 13 Homomorphisms#How to show $ phi G rightarrow G'$ is an Isomorphism|Ways to prove Isomorphism]] in group theory which is the isomorphism in the category **Grp**
**Grp** has the morphism: Homomorphism (see [[Section 13 Homomorphisms]])
## Definition Endomorphisms
A morphism of an object A of a category C to itself is called an endomorphism 
In **Grp** It is defined as: [[Section 24 Noncommutative Examples#Rings of Endomorphisms]]

## Definition Groupoid

> [!NOTE]
> A category, in which every morphism is an isomorphism, is called ***groupoid***. 

- [[Category Theory Intro#What is a Category]]
- [[Category Theory Intro#Difference between Morphism and Function]]
- [[#Definition Isomorphisms]]
## Definition: Automorphism
An Automorphism of an object A of category C is an isomorphism from A to itself.

> [!PDF|note] [[Algebra Chapter 0.pdf#page=51&selection=9,0,44,10&color=note|Algebra Chapter 0, p.51]]
> > If a morphism is a endomorphism and an isomorphism at the same time, it is a **automorphism**
> 

The set of automorphisms of A is denoted $Aut_C(A)$
- Every element $f\in Aut_C(A)$ has an inverse $f^{-1}\in Aut_C(A)$
- $Aut_C(A)$ contains the element $1_A$
- composition is associative
- the composition of two elements $f,g$ in this set is again an element $gf\in Aut_C(A)$

> [!Tip]
> This Definition seems familiar, doesn't it? See [[Section 4 Groups]]

See how Automorphism is defined in Group Theory: [[Section 14 Factor Groups#14.15 Definition: Automorphism]]
## Difference between Automorphism and endomorphism

| Property | Endomorphism | Automorphism |
| ----------------------- | ------------------------------------------ | ----------------------------------------------------------- |
| **Definition** | A morphism $f: A \to A$ in a category. | An invertible endomorphism $f: A \to A$. |
| **Hom-set** | $f \in \mathrm{Hom}(A,A)$. | $f \in \mathrm{Hom}(A,A)$ **and** $f^{-1}$ exists. |
| **Invertibility** | Not required. | Required: there exists gg with $g f = 1_A$ and $f g = 1_A$. |
| **Algebraic structure** | Monoids under composition. | Groups under composition. |
| **Role** | “Self-map” preserving structure. | “Symmetry” or “automagic move” of A. |
| **Examples** | Any linear map $V\to V$ (e.g. projection). | Any invertible linear map (e.g. rotation). |
Note that $Aut_C(A)\subseteq End_C(A)$
Automorphism is a stricter morphism.


## Definition Monomorphism 

> [!NOTE]
> Let C be a category. A morphism $f\in Hom_C(A,B)$ is a monomorphism if:
> 
> for all objects Z of C and all morphisms $\alpha'$ $\alpha''$ $\in Hom_C(Z,A)$
> $$f\circ \alpha'=f\circ \alpha''\Longrightarrow\alpha'=\alpha''$$ 

Or we can write it in this way:
$f(\alpha')=f(\alpha'')\Longrightarrow \alpha'=\alpha''$ Similar to the definition of [[Set#Injective|injective functions in the Set Theory]]

In the category **Set** the monomorphisms are precisely the injective functions (one-to-one) 
## Definition Epimorphism

> [!NOTE]
> Let C be a category. A morphism $f\in Hom_C(A,B)$ is a Epimorphism if:
> 
> for all objects Z of C and all morphisms $\alpha'$ $\alpha''$ $\in Hom_C(A,Z)$
> $$\alpha'\circ f= \alpha''\circ f\Longrightarrow\alpha'=\alpha''$$

In the category **Set** the monomorphisms are precisely the [[Set#Surjective|surjective functions]] (onto) 

Difference between monomorphism and Epimorphism is just left composition and right composition.



