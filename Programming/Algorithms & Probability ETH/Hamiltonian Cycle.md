> [!NOTE]
> A **Hamiltonian cycle** (or **Hamilton cycle**) in a graph is a **simple cycle that visits every vertex exactly once and returns to the start**.
> 

## Theorem: Dirac (1952)

> [!NOTE]
> Every Graph $G=(V,E)$ with $\lvert V \rvert\geq3$ and minimal degree $\delta(G)\geq \frac{\lvert V \rvert}{2}$ has a Hamiltonian cycle

**Proof Structure**:
1. The graph is connected
2. Induction:
	- For $k<n$: $k$-cycle (with $k$ vertices) $\implies$ There exists a $k+1$ long path
	- There is $k$ long path $\implies$ There exists $k+1$ long path or $k$-cycle

**Proof**:
1. Choose any $u,v\in V$
	- If $\{ u,v \}\in E$ then $u,v$ are connected
	- Otherwise, $\lvert N(u) \rvert+ \lvert N(v) \rvert+2=1+\frac{n}{2}+1+\frac{n}{2}=2+n\implies \lvert N(u)\cap N(v) \rvert\geq2$ (by [[Inclusion–exclusion principle|Siebformel]]) $\implies N(u)\cap N(v)\neq \varnothing$ $\implies$ There is a path between $u,v$
 - $N(u)$ is the neighbors of vertex $u$ 
 - $\lvert N(u) \rvert\geq\frac{n}{2}$ because $\delta(G)> \frac{n}{2}$
	- $\implies$ The graph is connected
2. Induction part:
	1. straightforward from the conclusion that $G$ is connected. We can always find a node that is connected to the cycle
	2. Assume there is a $k$ path
 1. Case: $N(v_{1})\not\subseteq \{ v_{2},\dots,v_{k} \}$ or $N(v_{k})\not\subseteq \{ v_{2}\dots v_{k} \}$
 - There is a node $u$ that is not yet in the path, so we can add node $u$ to the path
 2. Case: $N(v_{1})\subseteq \{ v_{2}\dots v_{k} \}$ and $N(v_{k})\subseteq \{ v_{2}\dots v_{k} \}$
 - Define $N^{+}(v_{k})=\{ v_{i+1}:v_{i}\in N(v_{k}) \}$
 - $\lvert N(v_{1})\cap N^{+}(v_{k}) \rvert>1$ 
 - There exists $v_{i}$ such that $(v_{1},v_{i}), (v_{i-1},v_{k})\in E$

## Application: Rotary Encoder

![[Pasted image 20260219131530.png|195]]![[Pasted image 20260219125749.png|462]]
There are $k$ light emitters and light detectors.
We want to arrange the holes on the plate in a certain way such that they encode $2^{k}$ directions.
For $k=2$, we want to have 00, 01, 10, 11. However, we also want the codes of any two neighboring directions to differ in only one bit, because the light detectors are much more precise than the positions of the holes.

We can model this problem as finding a Hamiltonian cycle on a $k$ dimensional hypercube.

Solving this problem is straightforward. Suppose we have a Hamiltonian cycle on $k-1$ dimensional hypercube. We first break it into a Hamiltonian path, then duplicate the hypercube along the $k$-th dimension and finally connect the two paths together to form a new cycle.

How it looks like:
![[Pasted image 20260219131722.png|274]]![[Pasted image 20260219131654.png|239]]

## How to decide if a graph has a Hamiltonian cycle (effizient)
- Brute Force: $O(n!)\approx n^{n}\approx 2^{n\log n}$
- DP: $O(2^{n})$, actually ~$n^{2}2^{n}$ time and ~$n\cdot2^{n}$ memory

Consider a super computer with $10^{25}$ FLOPs ($10^{7}$ EFLOPs)
- Using brute force we can solve graph with ~25 nodes
- Using DP we can solve graph with ~84 node

