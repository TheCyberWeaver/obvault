# P2.1 Colorful April

![[Pasted image 20260325211816.png]]

## a
We model this problem as a graph $G=(V,E)$. Each activity is a vertex, and two vertices have an edge if and only if there is a student who requested both activities. The problem now becomes if it is possible to color this graph with at most 30 colors (such that no edge has same color on both ends).
If there is a such coloring strategy, it would mean that we can assign each activity to a corresponding evening in April, such that: if any two activities are requested by the same student, then they must be on two separate evenings, which satisfies the problem.

## b
We choose an arbitrary pair of color ${} \{ a,b \} {}$
wlog. we assume $a<b$
Since the greedy algorithm uses color $b$, there is a first vertex $v$ that receives color $b$. 
When $v$ is colored, greedy chooses the smallest available color, so color $1,2,\dots,b-1$ must all be unavailable for $v$, which means for each color $1,2,\dots,b-1$ there is at least one neighbor of $v$ using that color. In particular, those colors includes $a$. Suppose this neighbor with color $a$ is $u$, then $uv$ is an edge that has both $a,b$ as end-points color.
Therefore, for every pair of color, there is an edge whose end-points have those colors.

## c
In a graph $G$ with chromatic number $\chi(G)$ there exists a coloring strategy with $\chi(G)$ colors, and there exists a greedy coloring algorithm (with specific ordering) that produces this strategy.
Using result from b) we know that every unordered pair of color in $\begin{pmatrix}	[\chi(G)] \\ 2 \end{pmatrix}$ exists in this coloring strategy. Since each edge can only have one pair of colors, there are at least $\begin{pmatrix}	\chi(G) \\ 2\end{pmatrix}$ edges.

## d
Since each student can pick at most two activities, each student can produce at most one edge in the graph. Therefore, graph $G$ has at most 450 edges.
Suppose no strategy can be found, than it would mean $G$ has a chromatic number larger than $30$.
According to c) $G$ must have at least $\begin{pmatrix}	31 \\ 2\end{pmatrix}=465$ edges. However, $G$ has at most 450 edges, which leads to a contradiction. Therefore, $G$ has a chromatic number at most $30$, and a suitable assignment strategy in April must exist.
