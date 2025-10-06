#eth 
# Matrix transformation

$$
T_{A}:\mathbf{x}\mapsto A\mathbf{x}
$$
![[Pasted image 20251001113607.png|345]]

$$
A(\mathbf{x})=\{Ax:x \in \mathbf{X}\}
$$
$\mathbf{x}$ is the set of input

![[Pasted image 20251001114154.png|512]]
![[Pasted image 20251001114216.png|515]]


$$
A(\lambda_{1}\mathbf{x}_{1}+\lambda_{2}\mathbf{x}_{2})=\lambda_{1}A\mathbf{x}_{1}+\lambda_{2}A\mathbf{x}_{2}
$$
commutative diagram
![[Pasted image 20251001115421.png]]

Other example of commutative diagram in group theory:
![[Pasted image 20250605122136.png|284]]


## Axiom: Linear transformation
***Linearity***

> [!NOTE]
> 
> A function $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$ is called a linear transformation if the following linearity axiom holds for all $\mathbf{x}_{1},\mathbf{x}_{2}\in \mathbb{R}^{n}$ and all $\lambda_{1},\lambda_{2}\in \mathbb{R}$
> $$
> T(\lambda_{1}\mathbf{x}_{1}+\lambda_{2}\mathbf{x}_{2})=\lambda_{1}T(\mathbf{x}_{1})+\lambda_{2}T(\mathbf{x}_{2})
> $$
> 

OR 
- $T(\mathbf{x}+\mathbf{x}')=T(\mathbf{x})+T(\mathbf{x}')$
- $T(\lambda \mathbf{x})=\lambda T(\mathbf{x})$

### linear functional
a special case of linear transformation where $m=1$
So $T:\mathbb{R}^{n}\to \mathbb{R}$
## What is axiom

> [!NOTE]
> An axiom is a defining property of a class of mathematical objects. Exactly the objects satisfying the property belong to the class.

> [!Warning]
> - In **axiomatic mathematics**, “class” = collection of all objects satisfying certain axioms.
> 	- The class of groups is defined by the group axioms.
>	- The class of vector spaces is defined by the vector space axioms.
>     
> - In [[Category Theory Intro|category theory]], “class” = a size notion (collection of objects or morphisms), not the same as “axiomatically defined class.”
> 	- “a possibly proper class of objects,” i.e. too large to be a set
> 	- [[Category Theory Intro#What is a class]]

