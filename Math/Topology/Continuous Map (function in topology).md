## Definition: continuous
A function $f:X\to Y$ between two topological spaces is called **continuous** if for every open set $V\subseteq Y$, its pre-image $f^{-1}(V)$ is open in $X$
**pre-image**: the set of points in $X$ that are mapped to the set $V$

Note that $f$ does not need to be injective of surjective

For simplicity we normally calls a continuous function as a map
## Property
A function $f:X\to Y$ is continuous $\Longleftrightarrow$ each point of $X$ has a neighborhood on which $f$ is continuous

## Conclusion
Constant maps are continuous (maps to a single point)
Identity maps are continuous

If $f:X\to Y,g:Y\to Z$ are continuous, $g\circ f:X\to Z$ is continuous


## Open Maps
A **continuous** map $f:X\to Y$ is called **open** if for every open $U\subseteq X$, its image $f(u)$ is open in $Y$

> [!Note] 
> The inverse definition of continuous maps 
> 

## Closed Maps
A **continuous** map is call **closed** if it takes closed subsets to closed sets.


> [!Warning] 
> **not** every continuous map is a open map: 
> $f:\mathbb{R}\to \mathbb{R}$ with $y\mapsto 0$ is a closed but not open map


## Proposition
Let $f:X\to Y$ be a continuous map that is open or closed
- If $f$ is bijective, it is a homeomorphism
	- $f$ is a [[Homeomorphism]] $\Longleftrightarrow f$ is open and closed
- If $f$ is injective, it is a topological embedding
	- a topological embedding is a map that is a [[Homeomorphism|homeomorphism]] onto its image
- If $f$ is surjective, it is a [[Quotient Space#Definition|quotient map]]

- continuous maps preserves [[Math/Topology/Connectedness|connectedness]]