## Definition: Spanner

Let $G=(V,E,w)$ be a weighted graph and let $t\geq 1$.

A subgraph $H=(V,E_H,w)$ is called a **$t$-spanner** of $G$ if for all vertices $u,v\in V$,
$$
\operatorname{dist}_H(u,v)\leq t\cdot \operatorname{dist}_G(u,v).
$$

So $H$ approximately preserves all shortest-path distances while using fewer edges.

## Greedy spanner algorithm

The **greedy spanner** constructs a sparse $t$-spanner as follows:

1. Sort all edges in nondecreasing order by weight.
2. Start with $H=(V,\emptyset)$.
3. For each edge $e=(u,v)\in E$ in that order:
   - if the current graph $H$ already contains a path from $u$ to $v$ of length at most $t\cdot w(e)$, do not add $e$;
   - otherwise add $e$ to $H$.

Intuition:
- short edges are considered first;
- a later edge is only kept if the current graph does not already provide a sufficiently short detour;
- therefore many edges are discarded, and the final graph is much sparser.

## Why the result is a $t$-spanner

Consider any edge $e=(u,v)$ of the original graph $G$.

When the algorithm processes $e$, one of two things happens:
- either $e$ is inserted into $H$;
- or there is already a path in the current graph from $u$ to $v$ of length at most $t\cdot w(e)$.

Hence after the algorithm finishes, every original edge has a replacement path in $H$ whose length is at most $t$ times the edge length.

Now take any two vertices $x,y$ and a shortest path
$$
x=v_0,v_1,\dots,v_k=y
$$
in $G$. Replacing each edge $(v_i,v_{i+1})$ by its corresponding path in $H$ gives a walk from $x$ to $y$ in $H$ of length at most
$$
\sum_{i=0}^{k-1} t\cdot w(v_i,v_{i+1})
=
t\cdot \operatorname{dist}_G(x,y).
$$

Therefore
$$
\operatorname{dist}_H(x,y)\leq t\cdot \operatorname{dist}_G(x,y),
$$
so $H$ is indeed a $t$-spanner.

## Dynamic graphs

The classical greedy spanner algorithm is usually presented for a **static** graph.

Still, the greedy criterion is useful in **dynamic graphs** as well:
- when edges are inserted or deleted, one can try to update the spanner locally instead of rebuilding it from scratch;
- many dynamic spanner data structures are inspired by the same idea: keep an edge only if it is needed to maintain short approximate paths.

So the main characteristic is:

> [!NOTE] Dynamic viewpoint
> Greedy spanner ideas extend naturally to dynamic settings, because edge decisions are based on whether a sufficiently short replacement path already exists.

## Remarks
- Greedy spanners are usually sparse.
- In geometric and network settings, they are a standard tool for reducing graph size while approximately preserving distances.
