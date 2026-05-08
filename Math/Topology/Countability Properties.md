A topological space is called **second** countable if it has a [[Cardinality#Theorem 3.17 Countability|countable]] [[Basis|basis]] for its topology.

## Example
Every Euclidean space is second countable.
Recall this definition
![[Basis#1)]]
however, this basis is clearly not countable (real numbers are not countable)

Therefore, we define another basis:
$\mathcal{B}=\{ B_{r}(p)|r\in \mathbb{Q}_{>0},p \in \mathbb{Q}^{n} \}$
This is still a basis, and it's countable
**Proof:** Basis
Consider $U\subseteq \mathbb{R}^{n},x \in U$. There exists some $r\in \mathbb{R}_{>0}$ such that $B_{r}(x)\subseteq U$. There is $q\in \mathbb{Q}_{>0}$ with $q\leq r$. By [[Convergence#Definition dense|denseness]] there $p \in \mathbb{Q}^{n}$ such that $\lVert x-p \rVert< \frac{q}{2}$

