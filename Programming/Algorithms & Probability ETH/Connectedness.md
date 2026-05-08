> [!Definition] What is this about?
> Determining if a graph is connected (i.e., there is a path between any two vertices).

## u-v-Separator
Let $G=(V,E)$ be a graph.
$u,v\in V$ and $X\subseteq V\setminus \{ u,v \}$
$X$ is u-v-Separator if $u,v$ are in different connected components of $G[V\setminus X]$

$X$ is a set of vertices that separate $u$,$v$ into different connected components.
## k-vertex-connected
$G$ is k-vertex-connected:
- $\lvert V \rvert\geq k+1$ 
- $\forall{u,v\in V}:$ Every u-v-Separator $X$ has size $\lvert X \rvert\geq k$


> [!Definition] Simpler Definition
> The minimum number of vertex whose removal disconnects the graph is **at least** k.

If a graph is $k$-vertex-connected then it is automatically $(k-1)$-vertex-connected
(same for edge-connected)

![[Pasted image 20260217144740.png|332]]
## Menger's Theorem (vertex)

> [!NOTE]
> $G$ is **k-vertex-connected**:
> - $\Longleftrightarrow \forall{u,v\in V}:$ (distinct) there exist at least $k$ _internally vertex-disjoint_ paths between $u$ and v.
> - $\Longleftrightarrow$ $\forall{u,v\in V}:$ Every u-v-Separator $X$ has $\lvert X \rvert\geq k$

It's pretty hard to prove "If every u-v-separator has size at least $k$, then there exist $k$ pairwise internally disjoint s-$t$ paths"

- [ ] Proof

## Menger's Theorem (edge)

> [!NOTE]
> A graph is k-edge-connected if and only if for every pair of distinct vertices, there exist at least k-_edge-disjoint_ paths between them.

Under this definition u-v-separators are now u-v-edge-separators where $X\subseteq E$

## Relationship between Connectivity Measures

There’s a fundamental relationship between vertex connectivity ($\kappa(G)$), edge connectivity ($\lambda(G)$), and the minimum degree of a graph ($\delta(G)$):
$$
\kappa(G) \le \lambda(G) \le \delta(G)
$$
OR: k-vertex-connected $\leq$ k-edge-connected $\leq$ minimal degree

## Structure of Graphs: Blocks

### Equivalence Relation on Edges

We define an equivalence relation, denoted by $\sim$, on the set of edges $E$ of a graph $G = (V, E)$ as follows: For two edges $e, f \in E$, we say $e \sim f$ if and only if either:
- $e = f$ (the edges are the same), **or**
- There exists a cycle in $G$ that contains both $e$ and $f$.

Proof of transitivity:
![[Pasted image 20260217155039.png|303]]
- Assume $e\sim f$ and $f\sim g$
- add vertices $v_{e},v_{f},v_{g}$
- $v_{e},v_{f}$ cannot be separated by removing one edge
- $v_{f},v_{g}$ cannot be separated by removing one edge
- $\implies$ $v_{e},v_{g}$ cannot be separated by removing one edge
- $v_{e},v_{g}$ is 2-edge-connected
- There are two internally disjoint path from $v_{e}$ to $v_{g}$
- There is a cycle between $e,g$
### Blocks
The equivalence classes of this relation $\sim$ are called **blocks**.
A block is a maximal subgraph that is **2-edge-connected**.
A block is a set of edges.

### Block Graph

![[Pasted image 20260217155642.png]]**Theorem:** If G is a connected graph, its block graph is a tree.
**Why is it a tree?**
- **Connected:** The block graph is connected because the original graph G is connected. Every part of G is represented in the block graph.
- **Acyclic:** Assume, for the sake of contradiction, that the block graph contains a cycle. This cycle would have to alternate between block nodes and cut vertex nodes. A cycle implies that there are at least two distinct paths between two nodes in the block graph. This would mean that at least two blocks share two or more vertices. We already have show that this implies that the blocks should be merged, this contradict the blocks. Therefore, the block graph cannot contain a cycle.
#### Application
- Large Road Networks
- Bridges and Tunnels
- Route Planning
- Alternative Roads