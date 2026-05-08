
## Definition: Chromatic Number

The **chromatic number** (*die chromatische Zahl*) $\chi(G)$ of a graph is the minimum number of colors needed to color its vertices so that adjacent vertices have different colors.

> [!NOTE] Equivalence
> $\chi(G)\leq k\Longleftrightarrow G$ is $k$-partite

![[Pasted image 20260310143710.png|184]]
## The Coloring Problem

> [!Question] A [[NP-complete|NP-hard]] question
> Given a graph $G=(V,E)$, is $\chi(G)\leq k$ ?
### Approximation

Approximating the chromatic number is also hard:
- For every $\varepsilon>0$, approximating $\chi(G)$ within a factor of $n^{1-\varepsilon}$ is **NP-hard**.
- Even for the promise version with $k=3$ (that is, when the graph is known to be 3-colorable), finding an optimal coloring is hard.
- However, for 3-colorable graphs, there is an algorithm that uses $O(\sqrt{ n })$ colors within time $O(\lvert V \rvert+\lvert E \rvert)$

## Greedy Algorithm

1. Choose an order of the vertices.
2. Go through the vertices one by one.
3. Assign each vertex the smallest color that is not already used by its colored neighbors.

> [!NOTE] Degree bound
> For any graph $G$, greedy coloring uses at most $\Delta(G)+1$ colors, where $\Delta(G)$ is the maximum degree of $G$.

Time: $O(\lvert E \rvert)$

One common heuristic is:
1. Repeatedly delete a vertex of smallest current degree.
2. Store the deleted vertices in a stack.
3. Reinsert them in reverse order and rcolor each vertex greedily.
This is the **smallest-degree-last ordering**. we start with the vertex that has the highest degree (**NOT** in any order from highest to lowest). 
An counter example would be :
![[Counter example coloring order.excalidraw]]

So the algorithm is less likely to introduce a new color, and it yields a coloring with at most $d+1$ colors, where $d$ is the degeneracy of the graph.
The **degeneracy** of a graph is the smallest number d such that every subgraph has a vertex of degree at most d.

## Brook's theorem
> [!THEOREM] Brooks' theorem
> If $G$ is connected and is neither a complete graph nor an odd cycle, then
> $$\chi(G)\leq \Delta(G).$$

Time: $O(\lvert E \rvert)$
### Proof idea                                         
 The ordinary greedy bound gives $\chi(G)\leq \Delta(G)+1$.  
 Brooks' theorem improves this by forcing two neighbors of one vertex to receive the same color, which frees one color for that vertex at the end.

## Coloring by blocks

> [!THEOREM] Coloring by blocks
> Let $G$ be a graph. If every [[Programming/Algorithms & Probability ETH/Connectedness#Blocks|block]] of $G$ can be colored with $k$ colors, then $G$ itself can be colored with $k$ colors.


## Examples
### Interference Graph Example

In [[Register|register]] allocation, two variables interfere if they are live at the same time, so they cannot use the same register.

```c
t1 = a + b
t2 = t1 * c
t3 = t1 - d
return t2 + t3
```

Here `t2` and `t3` are both needed at the `return`, so they are live at the same time. Also, `t1` interferes with `t2` and `t3` while those values are being computed.

Interference graph:

```text
t1 -- t2
 |     
 t3

t2 -- t3
```

So the graph is a triangle. A triangle needs 3 colors, which means this code needs 3 different registers if we want to keep all three temporaries in registers at once.

### Example: 4-color Theorem

In map coloring, each region is a vertex, and two vertices are connected if the regions share a border. A graph is **planar** if it can be drawn in the plane without any edges crossing.

> [!THEOREM] 4 Color Theorem
> Every planar graph can be colored with at most 4 colors.
> Equivalently, if $G$ is planar, then $\chi(G)\leq 4$.

> [!NOTE] Degree bound for planar graphs
> Every planar graph has at least one vertex of degree at most $5$.

