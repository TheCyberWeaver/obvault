> [!NOTE]
> The Traveling Salesman Problem (TSP) is an optimization problem where, given a set of cities and the distances between each pair of cities, the goal is to find the shortest possible route that visits each city exactly once and returns to the starting city.

The Traveling Salesman Problem is [[NP-complete]]. This can be shown by reducing the [[Hamiltonian Cycle|Hamiltonian cycle]] problem to TSP.

Given a graph $G = ([n], E)$, we construct the complete graph $K_n$ and define the edge lengths

$$
\ell(\{x,y\}) =
\begin{cases}
0 & \text{if } \{x,y\} \in E, \\
1 & \text{otherwise}.
\end{cases}
$$

Then $G$ has a Hamiltonian cycle if and only if the optimal TSP tour in $K_n$ with length function $\ell$ has total length $0$.
So if we can solve TSP, then we can solve the Hamiltonian cycle problem


## Metric TSP
Suppose we work on a complete graph
### Triangle Inequality
In the Metric TSP, the distance function $l$ is required to satisfy the triangle inequality: for any three cities $x, y, z \in [n]$, the following holds:

$$
l(x, z) \le l(x, y) + l(y, z)
$$

### 2-approximation

- Compute [[Minimum Spanning Tree (MST)]]
	- $l(T)\leq\text{opt}(K_{n},l)$
- Double the edges
	- $2l(T)\leq2\text{opt}(K_{n},l)$
- Find the Eulerian Tour $W$
	- $l(W)=2l(T)\leq2\text{opt}(K_{n},l)$
- Short cut the Eulerian Tour and find Hamiltonian cycle $C$ 
	- This works because of the triangle inequality
	- $l(C)\leq l(W)=2l(T)\leq2\text{opt}(K_{n,l})$
	- The result is smaller or equal to $2\text{opt}(K_{n},l)$

**Time Complexity**: $O(m\log n)$

### 1.5-approximation
This is the **Christofides(-Serdyukov) algorithm** for Metric TSP.

- Compute [[Minimum Spanning Tree (MST)]] $T$
	- $l(T)\leq \text{opt}(K_{n},l)$
- Let $X:=$ vertices of **odd degree** in $T$
	
- $\lvert X\rvert$ is even (handshaking lemma)
- Compute a **minimum-weight perfect [[Matching|matching]]** $M$ on $X$
	- (See [[Matching#Overview of Matching Algorithms]] for perfect matchings / algorithms.)

	- **Key bound:** $l(M)\leq \frac{1}{2}\text{opt}(K_{n},l)$

- Let $C^{*}$ be an optimal TSP tour. Consider the order in which $C^{*}$ visits the vertices in $X$.
- Taking every second edge along this induced cycle on $X$ gives a perfect matching $M'$ on $X$ with $l(M')\le \frac{1}{2}l(C^{*})=\frac{1}{2}\text{opt}(K_{n},l)$.
- Since $M$ is minimum-weight, $l(M)\le l(M')$.
- Add the edges: $H := T \cup M$
- Every vertex has even degree in $H$ $\Rightarrow$ $H$ is Eulerian

- Find an Eulerian tour $W$ in $H$
	- $l(W)=l(T)+l(M)\leq \text{opt}(K_{n},l)+\frac{1}{2}\text{opt}(K_{n},l)=\frac{3}{2}\text{opt}(K_{n},l)$
- Short cut the Eulerian tour and find a Hamiltonian cycle $C$
	- This works because of the triangle inequality
	- $l(C)\leq l(W)\leq\frac{3}{2}\text{opt}(K_{n},l)$

**Time Complexity**: dominated by the matching step (minimum-weight perfect matching on $X$, polynomial-time; typically $\tilde O(n^3)$ for general graphs), plus MST and Euler tour.