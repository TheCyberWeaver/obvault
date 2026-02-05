## Definition
Let $X$ be a topological space with topology $\mathcal{T}$
Let $Y\subseteq X$
$$
\mathcal{T}_{Y}=\{ Y\cap U|U\in \mathcal{T} \}
$$
We can also write: 
$$
\mathcal{T}_{Y}=\{ U\subseteq Y |U=Y\cap V \text{ for some }V\subseteq X\}
$$
$\mathcal{T}_{Y}$ is the smallest topology such that the map $Y\to X$ is continuous

reason:
we want the identity map $f :Y\to X$ to be continuous
Assume we have $U\subseteq X$ to be open
$\implies$ the preimage $f^{-1}(U)=U\cap Y$ must be open ([[Continuous Map (function in topology)#Definition continuous|definition continuous]])
$\implies U\cap Y\in \mathcal{T}_{Y}$
$\implies \{ U\cap Y |U\text{ is open in }X\}\subseteq \mathcal{T}_{Y}$
We check this is indeed a topology. ($\varnothing=Y\cap \varnothing$ and $Y=Y\cap X$ and closed under finite intersections, and arbitrary unions)
So we let $\mathcal{T}_{Y}=\{ Y\cap U|U\in \mathcal{T} \}$, and define this to be a subspace.


## Examples
![[Pasted image 20260205173100.png]]

> [!Warning]
> a subset may be open respect to the subspace topology and closed respect to a larger space


## Propositions
Let ${} Usu {}$