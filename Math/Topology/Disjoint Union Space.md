**Disjoint union of spaces** $A \sqcup B$ is the **coproduct** in topology.
See coproduct in Type theory: [[Type (Type Theory)#Example Coproduct type A+B]]

## Definition
Let $(X_{\alpha})_{\alpha \in A}$ be an indexed family of spaces, and let $\coprod_{\alpha \in A}X_{\alpha}$ denote their disjoint union.
Then a subset $\mathcal{U}\subseteq \coprod_{\alpha \in A}X_{\alpha}$ is open in the disjoint union topology if $\mathcal{U}\cap X_{\alpha}$ is open for each $\alpha \in A$ 

$$
\coprod_{\alpha \in A}x_{\alpha}:=\{ (x,a)|x \in X_{\alpha} \}
$$
Since we want $\iota _{\alpha}:X_{\alpha}\hookrightarrow \coprod_{\alpha \in A}X_{\alpha}$ to be continuous, for every open $\mathcal{U}\subseteq\coprod_{\alpha \in A}X_{\alpha}$ we must have $\iota ^{-1}_{\alpha}(\mathcal{U})$ is open. $\iota ^{-1}_{\alpha}(\mathcal{U})=\{ x \in X_{\alpha}|(x,\alpha)\in \mathcal{U} \}= X_{\alpha}\times \{ \alpha \}\cap \mathcal{U}=X_{a}\cap \mathcal{U}$ 
Note that $X_{\alpha}\times \{ \alpha \}\cong X_{\alpha}$

![[Pasted image 20260220195209.png]]

In simpler words: a open subset of the disjoint union spaces is a union of open subset of each space.

### Notation
$\hookrightarrow$ means inclusion map
a map $\iota:A\hookrightarrow X$ indicates $A\subseteq X$ and elements are mapped to themselves
## Characteristic Property
Let $Y$ be any space. A function $f:\coprod_{\alpha \in A}X_{\alpha}\to Y$ is continuous $\Longleftrightarrow$ $f_{|X_{\alpha}}:X_{\alpha}\to Y$ is continuous for all $\alpha \in A$.

![[Pasted image 20260220204002.png|323]]

We try to prove the $\Longleftarrow$ direction
### Proof using universal property
![[Pasted image 20260220205633.png|222]]
By universal property of the category of topological spaces we know that there exists a unique continuous map $\mathcal{U}$ that makes this graph commute.

> [!Warning] Title
> Note that $\mathcal{U}$ is unique among continuous maps, **NOT** among all functions. Thus, we need to prove $f$ is $\mathcal{U}$

That is $\mathcal{U}\circ\iota _{\alpha}=f_{|X_{\alpha}}=f\circ\iota _{\alpha}$

$f$ satisfies the universal property for disjoint union viewed as a set, because $f$ makes the graph commute. This gives $\mathcal{U}=f$ as functions $\implies$ $f$ is also continuous

Note that this argument is almost the same as the arguments in [[Product Space#Universal properties of Product space]]. Only the directions of the arrows are reversed
### Proof using definitions
Let $U\subseteq Y$ open
we need to prove $f^{-1}(U)$ is open
Consider $f^{-1}(U)\cap X_{\alpha}$
$f^{-1}(U)\cap X_{\alpha}=\{ x \in \coprod X_{\alpha}\;|\; f(x)\in U\; \wedge\; x \in X_{\alpha} \}$
$=\{ x \in X_{\alpha} \;|\; f(x)\in U\}=f^{-1}_{|X_{\alpha}}(U)$ 
Since $f_{|X_{\alpha}}$ is continuous, $f^{-1}_{|X_{\alpha}}(U)$ is open 
$\implies f^{-1}(U)\cap X_{\alpha}$ is open for all $\alpha \in A$
$\implies f^{-1}(U)$ is open (by definition of coproduct)

## Properties
- $C\subseteq \coprod _{\alpha \in A}X_{\alpha}$ is closed $\Longleftrightarrow$ $C\cap X_{\alpha}$ is closed for all $\alpha \in A$
- Each injection $\iota _{\alpha}:X_{\alpha}\to \coprod X_{\alpha}$ is an embedding
	- a topological embedding means a map is a [[Homeomorphism|homeomorphism]] onto its image
	- $X_{\alpha}$ is homeomorphic to $\iota _{\alpha}(X_{\alpha})$
	- This is straightforward, because $x\mapsto(x,\alpha)$
- Taking disjoint unions preserves:
	- [[Hausdorff spaces#Definition|Hausdorff property]] 
	- [[First and second countability#Definition first countable|First countability]]
	- [[First and second countability#Definition second countable|Second countability]], provided $A$ is countable