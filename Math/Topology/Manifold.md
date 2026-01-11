

## Definition: locally Euclidean
> [!definition] locally Euclidean
> > A space $M$ is locally Euclidean of dimension $n$ if every point $x\in M$ has a neighborhood homeomorphic (to any open subset $U\subseteq \mathbb{R}^{n}$) or (to an open ball $\mathbb{B}^{n}\subseteq \mathbb{R}^{n}$) or (to $\mathbb{R}^{n}$)
> 
> They are all equivalent


## Definition: manifold

> [!Quote]
> An **n-dimensional topological manifold** is a [[First and second countability#Definition second countable|second countable]] [[Hausdorff spaces|hausdorff space]] that is [[#Definition locally Euclidean|locally Euclidean]] of dimension $n$.

### Examples
![[Pasted image 20251231230523.png|768]]

## Definition: Chart and atlas
![[Pasted image 20260102202112.png]]

$\varphi _{x}$ is a [[Homeomorphism|homeomorphism]] to $\mathbb{R}^{n}$
$(U_{x},\varphi _{x})$ is a **coordinate chart**
An **atlas** is the collection of all coordinate charts $\mathcal{A}=\{ (U_{x},\varphi _{x})|x \in M \}$ 


> [!NOTE] 
> This can be imagined as an UV unwrapping process but locally.


## Dimension of manifold

> [!Quote] 
> If $m\neq n$, a nonempty space cannot both be an m-manifold and an n-manifold

We assume there is a nonempty space such that there is a point, whose neighborhood is both $m$ and $n$ dimensional.
This would mean there is a homeomorphism from $m$-dimensional space to $n$-dimensional space, which leads to contradiction

## manifold with boundary (not a manifold)
An n-dimensional manifold with boundary is a second countable hausdorff space in which every point has a neighborhood homeomorphic to an open subset of $\mathbb{R}^{n}$ or $\mathbb{H}^{n}$
#### Definition: upper half-space
The **upper half-space** $\mathbb{H}^{n}\subseteq \mathbb{R}^{n}$ is $\mathbb{H}:=\{ (x_{1},\dots,x_{n}\in\mathbb{R}^{n})|x_{n}\geq0 \}$

### interior point
the point has a neighborhood homeomorphic to $\mathbb{R}^{n}$

### boundary point
the point has a neighborhood homeomorphic to $\mathbb{H}^{n}$ **AND** the image of it must lie on the boundary of $\mathbb{H}^{n}$

> [!Warning] 
> > interior points of a manifold is **NOT** the [[Topology#Definition basic concepts|topological interior]] of the set
> >boundary points of a manifold is **NOT** the [[Topology#Definition basic concepts|topological boundary]] of the set
> 
> I hate semantic pollution !!!

### Theorem

> [!Quote]
> No point of a manifold with boundary is both an interior point and a boundary point.

Assume there is such a point $x$. (same strategy as [[#Dimension of manifold]])
This means this point has a [[Homeomorphism|homeomorphism]] $\varphi$ to an open ball in $\mathbb{R}^{n}$ and a homeomorphism $\psi$ to an open subset in $\mathbb{H}^{n}$.
$\implies$ there is a homeomorphism from $\varphi(x)\to\psi(x)$ 
Then we remove the point $x$ from $\varphi(x)$ and from $\psi(x)$ 
However, then we would have two sets such that one of them has a hole while the other one does not.
There cannot be a homeomorphism between these two sets, which leads to contradiction.
(We need homology to prove there is no such homeomorphism)
![[Pasted image 20260102211849.png]]