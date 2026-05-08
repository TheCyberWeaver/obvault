Given a connected, undirected, weighted graph $G=(V,E)$, a **minimum spanning tree** is a spanning tree with minimum total edge weight.

## Key Properties
- A spanning tree has exactly $|V|-1$ edges.
- No cycles.
- If edge weights are distinct, the MST is unique.

## Main Algorithms

### Kruskal
1. Sort edges by nondecreasing weight.
2. Add an edge if it connects two different components.
3. Stop after adding $|V|-1$ edges.

- Typical implementation: [[Disjoint Set Union]].
- Time: $O(|E|\log |E|)$ (sorting dominates).

### Prim
1. Start from any vertex.
2. Repeatedly add the minimum-weight edge crossing from visited to unvisited.

- Binary heap implementation: $O(|E|\log |V|)$.
- Dense graph version (array): $O(|V|^2)$.

### Boruvka
Repeat until only one component remains:
1. Treat each vertex/component as a separate component.
2. For each component, choose its cheapest outgoing edge.
3. Add all chosen edges to the MST (ignore duplicates/cycles via DSU).
4. Merge components.

- Each phase reduces the number of components by at least a factor of $2$.
- Number of phases: $O(\log |V|)$.
- Typical total time: $O(|E|\log |V|)$.

> [!TIP]
> Boruvka is naturally parallelizable because each component picks its cheapest outgoing edge independently.

## Correctness Intuition (Cut Property)
> [!NOTE]
> For any cut $(S, V\setminus S)$, the lightest edge crossing the cut is safe: it belongs to some MST.

Kruskal, Prim, and Boruvka are correct because each step picks safe edges.

## Typical Use Cases
- Network design (roads, cables, pipelines)
- Clustering (single-link hierarchical clustering)
- Approximation building block (e.g., TSP heuristics)
