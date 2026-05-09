## Definition
Let $X$ be a space, $Y$ a set and $q:X\to Y$ a surjective function (the quotient map).
Define the **quotient topology** on $Y$ by setting $U\subseteq Y$ open $\Longleftrightarrow$ $q^{-1}(U)$ open in $X$.

so if a map $q:X\to Y$ is continuous, surjective, and open or closed, then it is a quotient map.

![[Pasted image 20260220223657.png|369]]

The function $q$ is of course always a continuous map.
The quotient topology is also clearly the largest topology we can put on $Y$ such that $q$ is going to be continuous. Since all open sets on $X$ is mapped to the open sets on $Y$, we cannot have an extra set on the quotient topology, otherwise this extra set's preimage will not be open and $q$ will not be continuous.

We can prove that the quotient topology is indeed a topology:
for "Closed under unions":
Let $U_{i}\subseteq Y$ open, $q^{-1}\left( \bigcup _{i}u_{i} \right)=\bigcup _{i}q^{-1}(u_{i})$ by property of preimage. Thus arbitrary union of $U_{i}$ is open. analogously, $q^{-1}\left( \bigcap _{i}u_{i} \right)=\bigcap _{i}q^{-1}(u_{i})$
### Different way to think of a quotient space
![[Pasted image 20260220231959.png|387]]

Similar to [[Section 14 Factor Groups|factor groups]] or factor rings we divide space $X$ into partitions (_[[Fiber|fiber]]s_ or formally $\{ q^{-1}(\{ y \})|y\in Y \}$. $X$ can be viewed as disjoint union of non-empty sets ($X=\coprod_{y\in Y}S_{y}$, with $S_{y}$ being a indexed partition, see [[Disjoint Union Space]]).

We can define such a function $q$ and get the partitions
OR
We can define the partitions $X$ indexed by $Y$ and construct such a function $q$ 
OR
We can define a equivalence relation and view the equivalence classes as partitions

## View from universal property

> [!Note] Lemma
> Let $q:X\to Y$ be a quotient map. For any space $Z$, a map $f:Y\to Z$ is continuous if and only if $f\circ q$ is continuous.

![[Pasted image 20260222010349.png|187]]

Proof $\implies$ is obvious
Proof $\Longleftarrow$ : assume $f\circ q$ is continuous
Let $S\subseteq Z$ open
$\implies$ $(f\circ q)^{-1}(S)$ is open $\implies$ $q^{-1}(f^{-1}(S))$ is open $\implies$ $f^{-1}(S)$ is open ($q$ is continuous)
$\implies$ $f$ is continuous

> [!Important]
> The quotient topology is **unique** with this property
![[Pasted image 20260222011412.png|461]]


### Universal Property:
![[Pasted image 20260222011842.png|182]]
Let $q:X\to Y$ be a quotient map, $f:X\to Z$ continuous such that $q(x)=q(x')\implies f(x)=f(x')$
Then there exists a unique continuous map $\tilde{f}:Y\to Z$ satisfying $f=\tilde{f}\circ q$ (makes graph commute)

### Uniqueness of Quotients

Suppose $q_{1}:X\to Y_{1}$ and $q_{2}:X\to Y_{2}$ are quotient maps satisfying $q_{1}(x)=q_{1}(x')\Longleftrightarrow q_{2}(x)=q_{2}(x')$
Then we must have ${} Y_{1}\cong Y_{2} {}$
![[Pasted image 20260222210217.png|422]]
Then we must have unique $\tilde{q}_{1}$ and $\tilde{q}_{2}$ that makes the graph commute.
$\implies id\circ q_{2}=\tilde{q}_{2}\circ q_{1}=\tilde{q}_{2}\circ \tilde{q}_{1}\circ q_{2}$
$\implies \tilde{q}_{2}\circ \tilde{q}_{1}=\tilde{q}_{1}\circ \tilde{q}_{2}=id$
$\implies Y_{1}\cong Y_{2}$

This relates to the universal property of quotient groups by replacing continuous map by group homomorphism and replacing homeomorphism by group isomorphism.
## Examples
See [[Examples of Quotient Space]]

## Property
> [!Warning]
> Quotient space doe **NOT** preserve the properties like other spaces do ($e$.$g$. [[Product Space#Properties|product space]] or [[Subspace#Inheritance|subspace]]) 

Let $q:X\to Y$ be an _open_ quotient map (For every open set $U\subseteq X$, the image $q(U)\subseteq Y$ is open, see [[Continuous Map (function in topology)#Open Maps|open maps]]), then
$Y$ is hausdorff $\Longleftrightarrow$ $R=\{ (x_{1},x_{2})|q(x_{1})=q(x_{2}) \}$ is closed in $X\times X$
Proof: $\implies$
Take $(x_{1},x_{2})\not\in R$ $\implies$ $q(x_{1}),q(x_{2})$ are distinct
$Y$ is hausdorff, by definition
$\implies \exists{\text{ nbhds}}\; v_{1}\ni q(x_{1}),\;v_{2}\ni q(x_{2}), \; v_{1}\cap v_{2}=\varnothing$
since $q^{-1}(v_{1})$ and $q^{-1}(v_{2})$ are both open in $X$, $q^{-1}(v_{1})\times q^{-1}(v_{2})$ is neighborhood of $(x_{1},x_{2})$
This shows the complement of $R$ is open, so $R$ is closed.
 
It is usually easier to check if $R$ is closed in the [[Product Space|product space]] $X\times X$ than to directly check whether $Y$ is hausdorff
### Other Properties
- Any composition of quotient maps is a quotient map
- An injective quotient map is a [[Homeomorphism|homeomorphism]]
	- an injective quotient map is a bijection
- A subset $K\subseteq Y$ is closed $\Longleftrightarrow$ $q^{-1}(K)$ is closed
- If $U\subseteq X$ is [[Fiber|saturated]] open or closed subset, then $q_{|U}:U\to q(U)$ is a quotient map
- If $\{ q_{\alpha}:X_{\alpha}\to Y_{\alpha} \}$ are a family of quotient maps, then $\tilde{q}:\coprod _{\alpha}X_{\alpha}\to \coprod _{\alpha}Y_{\alpha}$ is a quotient map
- Any quotient of a [[Math/Topology/Connectedness|connected]] space is connected, also works for [[Path Connectedness]]