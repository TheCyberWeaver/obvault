## Goal
Compute a maximum [[Matching|matching]] in a bipartite graph $G=(A\cup B,E)$ faster than augmenting one path at a time.

> [!NOTE]
> Main idea: in each round, augment along a **maximal set of vertex-disjoint shortest augmenting paths**.

## One Iteration
1. **BFS phase**: start from all unmatched vertices in $A$, build alternating layers, and get shortest augmenting-path length $k$.
2. **DFS phase**: find a maximal set $S$ of vertex-disjoint augmenting paths, each of length $k$.
3. **Augmentation**: augment along all paths in $S$ simultaneously.

`maximal` means inclusion-maximal: no additional shortest augmenting path can be added while preserving vertex-disjointness.

## Key Proof Ideas

### Claim 1: Shortest augmenting-path length increases
If the shortest augmenting-path length in round $i$ is $k$, then in round $i+1$ it is at least $k+2$.

Reason:
- If an augmenting path $P$ is disjoint from all paths in $S$ and has length $k$, then $P$ should have been in $S$ (contradiction to maximality).
- If $P$ intersects some path in $S$, symmetric-difference reasoning gives $|P|>k$.
- Augmenting paths in bipartite graphs have odd length, so the next possible shortest length is at least $k+2$.

### Claim 2: Bound on distance to optimum
Let $M$ be current matching, $M^*$ a maximum matching, and $k$ the shortest $M$-augmenting-path length.
From $M\oplus M^*$, there are $|M^*|-|M|$ vertex-disjoint $M$-augmenting paths.
Each has at least $k+1$ vertices, so:

$$
(|M^*|-|M|)(k+1)\le |V|
$$

Hence:

$$
|M^*|-|M|\le \frac{|V|}{k+1}
$$

> [!IMPORTANT]
> When $k$ is large, the remaining matching gap $|M^*|-|M|$ is small.

## Why the Number of Iterations is $O(\sqrt{|V|})$
Split into two phases:

1. **Short-path phase** ($k<\sqrt{|V|}$):
   By Claim 1, $k$ increases by at least $2$ per round, so this phase has $O(\sqrt{|V|})$ rounds.
2. **Long-path phase** ($k\ge \sqrt{|V|}$):
   By Claim 2:

$$
|M^*|-|M|\le \frac{|V|}{k+1}\le O(\sqrt{|V|})
$$

Each round increases $|M|$ by at least $1$, so at most $O(\sqrt{|V|})$ rounds remain.

Total rounds: $O(\sqrt{|V|})$.

### Where does $\sqrt{|V|}$ come from exactly?
Use a generic threshold $T$ instead of fixing $T=\sqrt{|V|}$ first.

- Phase 1 ($k<T$): because $k$ increases by at least $2$ per round, this costs $O(T)$ rounds.
- Phase 2 ($k\ge T$): by Claim 2,

$$
|M^*|-|M|\le \frac{|V|}{k+1}\le \frac{|V|}{T+1}=O\left(\frac{|V|}{T}\right)
$$

so at most $O(|V|/T)$ rounds remain.

So total rounds are:

$$
O(T)+O\left(\frac{|V|}{T}\right)
$$

Balance both terms by choosing $T$ such that:

$$
T\approx \frac{|V|}{T}\Rightarrow T^2\approx |V|\Rightarrow T\approx \sqrt{|V|}
$$

Substitute back to get total rounds $O(\sqrt{|V|})$.

## Runtime
Each round (BFS + DFS on layered graph) costs $O(|E|)$.
Therefore total runtime is:

$$
O(|E|\sqrt{|V|})
$$
