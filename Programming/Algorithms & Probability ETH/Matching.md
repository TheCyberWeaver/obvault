---
tags:
  - linker-exclude
---
## Definition
Let $G = (V, E)$ be a graph.

**Matching ($M$):** 
A subset of edges $M \subseteq E$ such that no two edges in $M$ are incident to the same vertex. Formally, for any two distinct edges 
$e_1 = \{u_1, v_1\} \in M$ and $e_2 = \{u_2, v_2\} \in M$, we must have

$$
\{u_1, v_1\} \cap \{u_2, v_2\} = \emptyset.
$$

**Perfect Matching:** 
A matching $M$ is called a perfect matching if every vertex in $V$ is covered by $M$. A perfect matching pairs up all vertices in the graph. 
For a perfect matching to exist, the graph must have an even number of vertices, and

$$
|M| = \frac{|V|}{2}.
$$

**Inclusion-Maximal Matching:** 
A matching $M$ is inclusion-maximal if no more edges can be added to $M$ while still maintaining the matching property. In other words, there is no other matching $M'$ with $M\subseteq M'$ and $\lvert M' \rvert>\lvert M \rvert$

**Cardinality-Maximal Matching (Maximum Matching):** 

A matching $M_{max}$ is cardinality-maximal (or simply maximum) if there is no other matching $M'$ with $\lvert M' \rvert>\lvert M_{max} \rvert$

A maximum matching is always inclusion-maximal, but the converse is not necessarily true.

## Greedy Algorithm
Greedy algorithm gives us the inclusion-maximal matching $M_{greedy}$ in $O(\lvert E \rvert)$ with $\lvert M_{greedy} \rvert\geq \left\lvert \frac{M_{max}}{2} \right\rvert$

## M-augmenting path
Given a matching $M$ in a graph $G$, an **$M$-augmenting path** $P$ is a simple path in $G$ with the following properties:

**Alternating Path:** 
The edges of $P$ alternately belong to the matching $M$ and not to the matching $M$. That is, if we traverse the path, the edges appear in the sequence:
$$
\text{not in } M, \ \text{in } M, \ \text{not in } M, \ \text{in } M, \dots
$$
**Starts and Ends at Unmatched Vertices:** 
Both endpoints of the path $P$ are unmatched vertices with respect to $M$. That is, neither endpoint is incident to any edge in $M$.

> [!NOTE] Property
> - Every not cardinality-maximal matching has at least one augmenting path.
> - Every augmenting path provides us a new matching that is bigger.

This means we can exchange the "not in M" edges with "in M" edges, such that we construct $M'=M\oplus P$ (XOR) with $\lvert M' \rvert=\lvert M \rvert+1$

## Hall's Theorem

> [!NOTE]
> A bipartite graph $G=(A\cup B,E)$ has a matching $M$ ($\lvert M \rvert=\lvert A \rvert$) if and only if
> $\forall{X\subseteq A}\;:\; \lvert X \rvert\leq \lvert N(X) \rvert$ ($M$ is perfect matching if $\lvert A \rvert=\lvert B \rvert$)

$\implies$ trivial, proved by contraposition
$\Longleftarrow$ not trivial:
**Proof by induction**: induction on the size $\lvert A \rvert$ on the graph 
let $a=\lvert A \rvert$
_hypothesis_: the theorem holds for all $a'<a$ and $a>1$
_base case_: $a=1$: trivial, just choose an edge
_steps_:
- case 1: $\forall{X,X\neq \varnothing,X\subset A} :\; \lvert X \rvert<\lvert N(X) \rvert$ OR in other words $\lvert N(X) \rvert\geq \lvert X \rvert+1$
	- we can always delete an edge (including the nodes) from $G$ and $X\leq \lvert N(X) \rvert$ still holds, because we deleted at most one neighbor of any $X\subseteq A$.
	- This reduces the problem to $a-1$, which is proved by induction
- case 2: $\exists{X,X\neq \varnothing,X\subset A} :\; \lvert X \rvert=\lvert N(X) \rvert$
	- There is a perfect matching from $X$ to $N(X)$
	- Let $G'=(A\setminus X)\cup (B\setminus N(X))$ not $\varnothing$ and $X'\subseteq(A\setminus X)$
	- $\lvert N(X'\cup X) \rvert\geq \lvert X\cup X' \rvert$
	- $\lvert N_{G'}(X) \rvert\geq \lvert N_{G}(X'\cup X) \rvert-\lvert N(X) \rvert\geq \lvert X\cup X' \rvert-\lvert X \rvert\geq \lvert X' \rvert$
	- There is a perfect matching from


## Corollary
Every $k$-regular bipartite graph contains a perfect matching.

> [!NOTE] Explanation
> A k-regular bipartite graph is one where every vertex in both partitions A and B has a degree of exactly k

These graphs are union from perfect matching

## Finding the perfect matching in bipartite graph

> [!NOTE]
> In $2^{k}$-regular bipartite graph one can find a perfect matching in $O(\lvert E \rvert)$ time

We split the graph into two regular graph with $2^{k-1}$ degrees (for each node)
and split the graph until it is $1$-regular
Find the Euler tour in $O(\lvert E \rvert)$ this $1-$regular graph and delete every second edge. This gives a perfect matching.
Then we can find a perfect matching for $2-$regular graph, $2^{2}-$regular graph and so on.
In the end we have time $\sum_{i=1}^{k} 2^{k}=2^{k+1}-1\approx\lvert E \rvert\implies O(\lvert E \rvert)$
## Berge’s Theorem

> [!NOTE]
> Every matching that is not maximal has a augmenting path ([[#M-augmenting path]]) 
### Simple BFS approach
We can find this (shortest) augmenting path by using BFS
![[Pasted image 20260305101847.png|226]]
### Inefficiency
While the BFS approach works, a naive implementation might perform redundant work in each iteration. Consider that in each iteration, we find only _one_ augmenting path and increase the matching size by just one. We might need to repeat this process many times, potentially up to $\frac{\lvert V \rvert}{2}$ iterations in the worst case. (see perfect matching in this note)
The solution is to use [[Hopcroft-Karp Algorithm|Hopcroft-Karp algorithm]]


## Overview of Matching Algorithms
### For bipartite graphs:

**Hopcroft-Karp Algorithm (Unweighted):**  
Achieves a time complexity of  
$$
O(|V|^{1/2} \cdot |E|)
$$

**More Advanced Algorithms (Weighted):**  
Algorithms exist with complexities close to  
$$
O(|E|^{1+o(1)})
$$  
for weighted bipartite matching, especially with polynomially bounded weights.

### For general graphs (non-bipartite):

**Micali-Vazirani Algorithm (Unweighted):**  
A complex algorithm that achieves a time complexity of  
$$
O(|V|^{1/2} \cdot |E|)
$$  
similar to Hopcroft-Karp for bipartite graphs.  
Gabow-Tarjan algorithm is another algorithm with similar complexity.

**Matrix Multiplication Based Algorithms (Unweighted):**  
Algorithms using fast matrix multiplication have achieved slightly better theoretical complexities like  
$$
O(|V|^{2.373})
$$  
for unweighted maximum matching.

**Gabow’s Algorithms (Weighted):**  
For weighted matching in general graphs, algorithms like Gabow’s algorithms exist, with complexities around  
$$
O(|V|^{3})
$$  
for finding maximum weight or minimum weight perfect matchings.