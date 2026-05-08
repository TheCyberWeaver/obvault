## Overview
Given an undirected graph $G = (V, E)$ and a non-negative integer $B \in \mathbb{N}_0$, the **Long-Path problem** asks: Does there exist a path in $G$ of length exactly $B$?

### Definitions
- A **path** is a sequence of vertices with no repetitions.
- A path of length $B$ contains $B+1$ distinct vertices.

> [!NOTE]
> The **Long-Path problem** is [[NP-complete]]. It is closely related to the Hamiltonian Path and Hamiltonian Cycle problems. If we can solve the Long-Path problem in $t(n)$ for graph with $n$ nodes, then we can solve the Hamiltonian Path problem in $t(2n-2)+O(n^{2})$


Futhermore:
$$
 G = (V,E) \text{ has a Hamiltonian Cycle}\Longleftrightarrow G' \text{ has path of length n}
$$
![[Long Path - Hamiltonian Cycle Proof.excalidraw]]

> [!NOTE]
> By brute force we can solve the Long-Path problem in $O(n^{B+2})$
> **Goal**: under $O(c^{B})$ where $c$ is a constant

## Randomized Approach: Color Coding

### Key Idea
We randomly color the graph and search for a **colorful path** — a path where all $k$ vertices have distinct colors.

Let $k = B+1$. We seek a path of length $k-1$, using $k$ colors.

For $v \in V$ and $i \in \{0,\dots,k-1\}$ define
$$
P_i(v) :=
\left\{
S \subseteq [k] \;\middle|\; |S| = i+1 \wedge \exists \text{ a colorful path ending in } v \text{ that is colored exactly with } S
\right\}
$$
**Goal:** Compute all sets $P_i(v)$ for every $v \in V$ and every $i \in \{0,1,\dots,k-1\}$
Example:
![[Colorful Path.excalidraw|384]]

$P_{0}(v)=\{ \{ \gamma(v) \} \}$ (color of $v$)
for $i\geq1$ there is:
$\exists\text{a colorful path that ends in } v \text{ that ends in S}$ $\Longleftrightarrow \exists\text{ a neighbor } x\text{ of } v\text{ and a colorful path ending in }x\text{ that is colored with }S\setminus \{ \gamma(v) \}$  

Therefore:
$$
P_{i}(v)=\bigcup _{x \in N(v)}\{ R\cup \{ \gamma(v) \}\;|\; R\in P_{i-1}(x)\wedge \gamma(v)\not\in R \}
$$
Computation of $P_i(v)$ for all $v ∈ V$, given $P_{i-1}(v)$ for all $v ∈ V$

$\textbf{BUNT}(G, i)$
- for all $v \in V$ do  
	- $P_i(v) \leftarrow \varnothing$  
	- for all $x \in N(v)$ do  
	    - for all $R \in P_{i-1}(x)$ with $\gamma(v) \notin R$ do  
		    - $P_i(v) \leftarrow P_i(v) \cup \{ R \cup \{\gamma(v)\} \}$

### Run Time
This algorithm checks for the existence of a colorful path of length $k-1$ in time
$$
O(2^k \cdot k \cdot m)
$$
where $m = |E|$

### Probability That a Path Is Colorful

Suppose the graph contains a path $P$ of length $k-1$.  
Randomly color each vertex independently with a color in $\{1,\dots,k\}$.

There are $k^k$ possible colorings of the $k$ vertices on $P$.

Exactly $k!$ of them assign distinct colors to all vertices on $P$, i.e., make $P$ colorful.

So,
$$
\Pr[P \text{ is colorful}] = \frac{k!}{k^k}
$$
Using Stirling’s approximation:

$$
k! \approx \sqrt{2\pi k}\left(\frac{k}{e}\right)^k
$$
we get

$$
\frac{k!}{k^k}
\approx
\sqrt{2\pi k}\left(\frac{1}{e}\right)^k
$$

Therefore, a lower bound is

$$
\frac{k!}{k^k} \ge \left(\frac{1}{e}\right)^k
= e^{-k}
$$

This means the chance of a particular path becoming colorful under a random coloring is at least $e^{-k}$.

### Summary
> [!Theorem]
> Let $G$ be a graph containing a path of length $k - 1$.
> 
> 1. A random coloring with $k$ colors produces a colorful path of length $k - 1$ with probability 
> $$
> p \approx e^{-k}.
> $$
> 2. For repeated colorings with $k$ colors, the expected number of trials until a colorful path of length $k - 1$ is obtained is  
> $$
> \frac{1}{p} \le e^{k}.
> $$
> (See [[Distributions#Geometric distribution|Geometric distribution]])


## Monte Carlo Algorithm for Long-Path

Let $k = B+1$.

Repeat the following $\lceil \lambda e^k \rceil$ times:

1. Randomly color the vertices of $G$ using $k$ colors.
2. Check whether the graph contains a colorful path of length $k-1$.
3. If such a path is found, return **YES**.

If no colorful path is found in any iteration, return **NO**.

### Correctness

If the algorithm returns **YES**, the graph indeed contains a path of length $B$ (because colorful paths are simple paths by definition).

If the graph contains a path of length $B$, then with probability at least $e^{-k}$, one random coloring will make some such path colorful.

The probability that none of the $\lambda e^k$ trials succeeds is:

$$
(1 - e^{-k})^{\lambda e^k}
\le
e^{-\lambda}
$$

using the inequality

$$
(1-x)^r \le e^{-xr}
$$

So the error probability is at most $e^{-\lambda}$.

This is a **Monte Carlo algorithm**:  
it may return **NO** incorrectly with small probability, but never returns **YES** incorrectly.

### Run Time 
Thus, the total runtime becomes:
$$
O(\lambda \cdot e^k \cdot 2^k \cdot k \cdot m)
=
O(\lambda \cdot (2e)^k \cdot k \cdot m)
$$
This is polynomial in $n$ when $k = O(\log n)$, i.e., when $B = O(\log n)$.




