#eth 
A graph, denoted by $G$, is formally defined as a pair $G=(V,E)$, where:

- $V$: A finite, non-empty set of _vertices_ (also called nodes). Vertices represent the individual entities within the network.
- $E$: A set of _edges_. Each edge represents a connection between two vertices.

# Degree of a Vertex

- **Undirected Graph:** The degree of a vertex v, denoted as deg(v), is the number of edges incident to v.
- **Directed Graph:** We distinguish between _in-degree_ (number of edges coming into v) and _out-degree_ (number of edges going out of v).

## Handshaking Lemma
$$
\sum_{u\in V} deg(u)=2\cdot \lvert E \rvert  
$$

# Types of Paths

- **Walk:** Most general, allows repetition of vertices and edges.
- **Path:** No vertex repetition allowed, each vertex visited exactly once.
- **Closed Walk/Cycle:** Starts and ends at the same vertex, allowing repetition of vertices but not edges (except for the first and last edge, which are the same).
### Hamiltonian Path
A **Hamiltonian path** is a path in a graph that visits each _vertex_ exactly once.

### Eulerian Paths
An **Eulerian path** is a path in a graph that visits every **edge** of the graph exactly once. It can start and end at different vertices.

### Eulerian Cycle
An **Eulerian cycle**, also known as an Eulerian circuit, is a closed Eulerian path. This means it’s a trail that traverses every edge of a graph exactly once and **returns to the starting vertex**.
# The Reaching relation
## Undirected graph
The _reaching relation_ in a graph 
describes the ability to get from one vertex to another.

Symmetric, Reflexive, Transitive
$\implies$ This is an equivalence relation (see [[Relation#Equivalence Relations]])
The equivalence classes are called connected components or (Zusammenhangskomponenten, ZHK)

> [!NOTE] Connected Graph
> A graph is **connected** if the graph has exactly one connected component

