Note: a bridge is a cut edge

## Using DFS

We first run the classical dfs algorithm (red edges and numbers)
![[Pasted image 20260219103637.png]]

Definition: The low number (blue numbers) of a vertex $v$, denoted as $\text{low}[v]$, is the smallest DFS number (the red numbers) reachable from $v$ by following:

- Any number of tree edges downward in the DFS tree (red edges).
- At most one back edge (grey edges).

Formally,
$$
\text{low}[v] =
\min
\begin{cases}
\text{dfs}[v] \\
\min_{(v,w) \in E}
\begin{cases}
\text{dfs}[w] & \text{if } (v,w) \text{ is a back edge} \\
\text{low}[w] & \text{if } (v,w) \text{ is a tree edge}
\end{cases}
\end{cases}
$$

---

### Two Cases for Cut Vertices

#### 1. $v$ is **not** the root of the DFS tree
Vertex $v$ is a cut vertex **if and only if** it has a child $u$ in the DFS tree such that:

$$

\text{low}[u] \ge \text{dfs}[v]

$$
#### 2. $v$ is the **root** of the DFS tree
The root is a cut vertex **if and only if** it has at least **two children** in the DFS tree.
This is because:
- If the root has only one child, removing the root does **not** disconnect the remaining subtree.
- If the root has multiple children, their subtrees become separate connected components when the root is removed.

![[Pasted image 20260219105237.png]]
It's easy to see that if $\text{low}[u]> \text{dfs}[v]$, then there could not exist a back edge from green (the bottom three) to brown vertices. 
If $\text{low}[u]= \text{dfs}[v]$, then there is a back edge from green (the bottom three) to $v$, in which case, $v$ is still a cut vertex.

---
### Bridges
Let $(v, w)$ be a tree edge in the DFS tree, with $v$ being the parent of $w$.
Then $(v, w)$ is a **bridge** if and only if:

$$
\text{low}[w] > \text{dfs}[v]
$$
can easily be checked by the graph above.
