A graph, denoted by $G$, is formally defined as a pair $G=(V,E)$, where:

- $V$: a finite, non-empty set of **vertices** (nodes)
- $E$: a set of **edges** connecting vertices

# Degree of a Vertex

- **Undirected graph**: the degree of a vertex $v$, denoted $deg(v)$, is the number of incident edges.
- **Directed graph**: we distinguish
  - in-degree: number of incoming edges
  - out-degree: number of outgoing edges

## Handshaking Lemma
$$
\sum_{u\in V} deg(u)=2\cdot |E|
$$

# Types of Paths

- **Walk**: vertices/edges may repeat.
- **Path**: no repeated vertices.
- **Closed walk / cycle**: starts and ends at the same vertex.

## Hamiltonian Path
A **Hamiltonian path** visits each **vertex** exactly once.

## Eulerian Path
An **Eulerian path** visits each **edge** exactly once.

## Eulerian Cycle
An **Eulerian cycle** is an Eulerian path that returns to the start.

# Reaching Relation

## Undirected Graph
The reaching relation describes whether one vertex can be reached from another.

It is:
- reflexive
- symmetric
- transitive

So it is an equivalence relation (see [[Relation#Equivalence Relations]]).
Its equivalence classes are the connected components.

> [!NOTE] Connected Graph
> A graph is **connected** if it has exactly one connected component.

# Basic Graph Algorithms
- [[Shortest Path]] problems
- [[Minimum Spanning Tree (MST)]]
- [[Disjoint Set Union]] (used by Kruskal)
