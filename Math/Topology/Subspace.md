## Definition
Let $X$ be a topological space with topology $\mathcal{T}$
Let $S\subseteq X$
$$
\mathcal{T}_{S}=\{ S\cap U|U\in \mathcal{T} \}
$$
We can also write: 
$$
\mathcal{T}_{S}=\{ U\subseteq S |U=S\cap V \text{ for some }V\subseteq X\}
$$
$\mathcal{T}_{S}$ is the smallest topology such that the map $S\to X$ is continuous

reason:
we want the identity map ${} \iota _{S} :S\to X {}$ to be continuous
Assume we have $U\subseteq X$ to be open
$\implies$ the preimage ${} \iota _{S}^{-1}(U)=U\cap S {}$ must be open ([[Continuous Map (function in topology)#Definition continuous|definition continuous]])
$\implies U\cap S\in \mathcal{T}_{S}$
$\implies \{ U\cap S |U\text{ is open in }X\}\subseteq \mathcal{T}_{S}$
We check this is indeed a topology. ($\varnothing=S\cap \varnothing$ and $S=S\cap X$ and closed under finite intersections, and arbitrary unions)
So we let $\mathcal{T}_{S}=\{ S\cap U|U\in \mathcal{T} \}$, and define this to be a subspace.


## Examples
![[Pasted image 20260205173100.png]]

> [!Warning]
> a subset may be open respect to the subspace topology and closed respect to a larger space


## Propositions
Let $U\subseteq S\subseteq X$
- If $U$ is open (closed) in $X$ , then $U$ is open (closed) in $S$.
	- Proof: $U\subseteq X$ is open, $U=U\cap S$ $\implies$ $U$ is open in $S$.
- If $S$ is open (closed) in $X$ and $U$ open (closed) in $S$, then $U$ is open (closed) in $X$.
	- so if $S$ itself is open in $X$, then the converse of the first proposition holds.
	- Proof: $U\subseteq S$ is open $\implies$ $U=S\cap V$ for some $V\subseteq X$ open in $X$. (by definition)
	- Note that both $S$  and $V$ are open in $X$.
	- $\implies U$ is also open in $X$.
## Characteristic Property

Let $S\subseteq X$ be a subspace.
For any space $Y$, a function $f:Y\to S$ is continuous if and only if ${} \iota_{s}\circ f:Y\to X$ is continuous:
![[Pasted image 20260205175407.png|172]]
### Corollary
Let $X$,$Y$,$Z$ be spaces and $f:X\to Y$ continuous
- If $S\subseteq X$, then $f_{|S}:S\to Y$ is continuous
- If $T\subseteq Y$ and $f(X)\subseteq T$, then $f:X\to T$ continuous.
- If $Y\subseteq Z$, then $f:X\to Z$ is continuous. 

## Inheritance
Subspaces preserves:
- [[Hausdorff spaces#Definition|Hausdorff property]] 
- [[First and second countability#Definition first countable|First countability]]
- [[First and second countability#Definition second countable|Second countability]]