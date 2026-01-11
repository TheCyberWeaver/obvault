## Definition: first countable
> [!definition] First Countable
> >  A collection $\mathcal{B}_{p}$ of *neighborhoods* of $p$ is called a neighborhood basis for $X$ at $p$ if every neighborhood of $p$ contains some $B\in \mathcal{B}_{p}$
> 
> note that this basis is a collection of neighborhoods
> > A space $X$ is called first countable if there is a countable neighborhood basis at each points.

## Definition: second countable
> [!definition] Second Countable
> > A topological space $X$ is called second countable if it has a countable [[Basis|basis]] for its topology
### Example
Every Euclidean space is second countable.
Recall this definition
![[Basis#1)]]
however, this basis is clearly not countable (real numbers are not countable)

Therefore, we define another basis:
$\mathcal{B}=\{ B_{r}(p)|r\in \mathbb{Q}_{>0},p \in \mathbb{Q}^{n} \}$
This is still a basis, and it's countable
**Proof:** Basis
Consider $U\subseteq \mathbb{R}^{n},x \in U$. There exists some $r\in \mathbb{R}_{>0}$ such that $B_{r}(x)\subseteq U$. There is $q\in \mathbb{Q}_{>0}$ with $q\leq r$. By [[Convergence#Definition dense|denseness]] there $p \in \mathbb{Q}^{n}$ such that $\lVert x-p \rVert< \frac{q}{2}$

## Relation between first and second countable
The first countable is a weaker condition comparing to the second countability

we can check: second countable  $\implies$ first countable
let $p \in X$ with $X$ is second countable.
$X$ has countable basis $\mathcal{B}$.  
Consider $\mathcal{B}_{p}\subseteq \mathcal{B}$, $\mathcal{B}_{p}=\{ B\in \mathcal{B} \;	|\;	p \in B\}$
$\implies\lvert \mathcal{B}_{p} \rvert\leq \lvert \mathcal{B} \rvert\implies$ $\mathcal{B}_{p}$ is countable.
By [[Basis#Proposition relation to every neighborhood]] we can easily prove this $\mathcal{B}_{p}$ is indeed a neighborhood basis.

## Propositions
If $X$ is first countable, $A\subseteq X$ and $p \in X$
- $p \in \bar{A}\Longleftrightarrow$ $p$ is a limit of a sequence in $A$.
- $p \in Int (A)\Longleftrightarrow$ every sequence in $X$ converging to $p$ is eventually in $A$.
- $A$ closed $\Longleftrightarrow$ $A$ contains every [[Convergence#Definition Convergence|limit]] of every convergent sequence in $A$
	- note that ($A=\bar{A}\Longleftrightarrow A$ is closed), so this can be shown by the first proposition
- $A$ open $\Longleftrightarrow$ every sequence in $X$ converging to a point of $A$ is eventually in $A$.
	- use the second proposition. ($A=Int(A)$ $\Longleftrightarrow$ $A$ is open)
Explanations to notations: [[Topology#Definition basic concepts]]

