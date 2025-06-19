
## Definition Group - normal definition

A group $\langle G,*\rangle$ is a set $G$, with a operation $*$, such that the following axioms are satisfied:
- The set is *closed* under $*$
- associativity of $*$
- identity element e for $*$
- Every element in $G$ is invertible 

Group is a algebra structure: ![[Algebra Structure.excalidraw]]

## Definition Group - from the view of Category Theory

> [!PDF|note] [[Algebra Chapter 0.pdf#page=63&selection=217,0,236,1&color=note|Algebra Chapter 0, p.63]]
> > Definition: A group is a groupoid with a single object. 
> 

see [[Special Morphisms#Definition Groupoid|Definition of Groupoid]]

We consider this groupoid G:
- objects: $\{*\}$
- Morphisms: This single object has only endomorphisms (an object to itself). Moreover, they are automorphisms, because morphisms in groupoids are isomorphisms. (see [[Special Morphisms#Definition Automorphism]]). Thus the only hom-set is $Hom_G(*,*)$ or $Aut_G(*)$

> [!NOTE]
> The set $Aut_G(*)$ and the morphism composition forms a group.

We check the criterions:
- **all** morphisms are invertible (because of isomorphism)
- for $f,g\in Aut_G(*)$, $g\circ f$ is again an automorphism of G
- By Definition of category, the morphism composition fulfills the associativity law. (see [[Category Theory Intro#What is a Category|Definition of Category]])
- By Definition of category, there is an identity automorphism. (see [[Category Theory Intro#What is a Category|Definition of Category]])

Thus, we can also say

> [!Important]
> The hom-set of a single-object groupoid forms a group under composition.

We can conclude that:
$$Grp\cong Gpd_*$$
### Example: $\langle\mathbb Z,+\rangle$

A groupoid G defined as $(\{*\},Hom_G(*,*)=\mathbb Z)$:
The morphisms in this set are $f_n:*\to *$ 
- $f_n$ here is purely a symbol, representing a morphism.
We define a composition: $\circ: Hom_G(*,*)\times Hom_G(*,*)\to Hom_G(*,*)$
- $\circ$ is defined as: For any $m,n\in\mathbb Z$: $f_n\circ f_m=f_{n+m}$
$id_*=f_0$
and the inverse is defined as $(f_n)^{-1}=f_{-n}$






