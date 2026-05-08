---
tags:
  - linker-exclude
---
## Single-Source Shortest Path (SSSP)

Given a source vertex $s$, compute shortest distances $dist(v)$ from $s$ to every vertex $v$.

### Pick the Right Algorithm

#### Unweighted graph
- Use BFS.
- Time: $O(|V|+|E|)$.

#### Nonnegative edge weights
- Use [[Dijkstra]].
- Time: $O(|E|\log |V|)$ with binary heap.

#### Negative edge weights allowed
- Use [[Bellman-Ford]].
- Time: $O(|V||E|)$.
- Also detects reachable negative cycles.

#### DAG
- Topological-order DP.
- Time: $O(|V|+|E|)$.

### Relaxation Principle
For an edge $(u,v,w)$, try:
$$
dist(v) = \min(dist(v),\; dist(u)+w)
$$

All shortest-path algorithms differ mainly in the order and number of relaxations.

### Output Variants
- Distance only
- Distance + predecessor array (`parent`) to reconstruct actual shortest paths

## Multi-Source Shortest Path

Compute shortest distance from a set of sources $S=\{s_1,\dots,s_k\}$ to every vertex.

Equivalent definition:
$$
dist(v)=\min_{s\in S} dist(s,v)
$$

### Core Trick: Super Source
Add a new node $s^*$ and connect it to each source $s\in S$ with edge weight $0$.
Then run a single-source algorithm from $s^*$.

### Cases

#### Unweighted graph
- Initialize BFS queue with all sources at distance $0$.
- Time: $O(|V|+|E|)$.

#### Nonnegative weighted graph
- Initialize priority queue with all sources at distance $0$ (or use super source + [[Dijkstra]]).
- Time: $O(|E|\log |V|)$.

#### Negative edges
- Use super source + [[Bellman-Ford]].

### Relation to All-Pairs Shortest Paths (APSP)
- Multi-source: one run for a source set $S$.
- APSP: run SSSP from every vertex (or use Floyd-Warshall).

> [!TIP]
> If you need distances to the **nearest facility** (hospital, station, server), multi-source shortest path is usually the right model.