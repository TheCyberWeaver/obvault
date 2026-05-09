 #exercise 
# 9.3 Number of paths in DAGs
##### a)
We prove the existence of a topological sorting by providing a constructive method.
Let's first remove $v_{1},v_{n}$ and all the edges connect to them from $G$. Removing nodes and edges in DAG does not create cycles, so the new graph is still a DAG, and therefore has a topological sorting. Let this topological sorting be $(u_{1},\dots,u_{n-2})$. Now we construct a new topological sorting for $G$: $(v_{1},u_{1},\dots,u_{n-2},v_{n})$. We claim this sequence to be a topological sorting:
- All the relative orders in $(u_{1},\dots,u_{n-2})$ remains the same.
- Since $v_{1}$ is a source, there is no edge pointing to $v_{1}$. Then $v_{1}$ is before all other vertices, so it can be placed at position $1$
- Since $v_{n}$ is a sink, there is no edge pointing from $v_{n}$. Then $v_{n}$ is behind all other vertices, so it can be placed at position $n$ 

This proves the claim.
##### b)
Take any edge from the $v_{1}$-$v_{n}$-path $(v_{i_{j}},v_{i_{j+1}})$, we have $i_{j}<i_{j+1}$ according to the property of topological order. Therefore, if we apply this property to every consecutive pair in $v_{1}$-$v_{n}$-path, we get $i_{0}<i_{1}<\dots<i_{l}$

##### c)
1. **Dimensions**: The table is one dimensional and has a size of $\lvert V \rvert+1$
2. **Subproblems**: the entry `dp[i]` is the number of possible paths from $v_{1}$ to $v_{i}$
3. **Recursion**:
	1. Base Case: `dp[1]` is $1$
	2. Normal Case: the entry `dp[i]` is the sum of `dp[j]` where node $v_{j}$ point to node $v_{i}$
 - Justification: 
 1. We assume $dp[1]$ to $dp[k-1]$ are correctly calculated.
 2. Every path to $v_{k}$ must go through one of the nodes that point to $v_{k}$.
 3. To calculate the number of possible paths to $v_{k}$, we can add up all the paths that leads to each nodes that point to $v_{k}$
 4. Since $(v_{1},\dots,v_{n})$ is in topological order, all the nodes we need to calculate $v_{k}$ must have been calculated.
4. **Calculation order**: iterate through the topological order.
``` pseudocode
countPaths(n, Adj):
 dp[1] = 1
 for i = 1 to n:
 for each j in Adj[i]: 
 dp[j] = dp[j] + dp[i] 
 return dp[n]
```
1. **Extracting the solution**: take the value in `dp[n]`
2. **Running time**: $O(\lvert E \rvert+\lvert V \rvert)$
##### d)
Yes it is still possible
we just need to change the initialization process
$dp[v_{1}]=1$
the transition process is same as before, and we get the answer from $dp[v_{n}]$
# 9.4 Bipartite graphs, Eulerian graphs and painting rooms
![[Pasted image 20251123195323.png]]
##### b)
1.
We prove the claim by contraposition
Assume $G$ has odd number of edges.
Assume $G$ is bipartite.
If there exists a closed walk in $G$ it must alternates between two sets $V_{1}$ and $V_{2}$. To return back to the starting node, the walk must have even number of steps, meaning every closed walk has even number of edges.
If $G$ is Eulerian, the closed Eulerian walk must have odd number of edges.
This contradicts to the assumption we made.

2.
$G$ is Eulerian and has an even number of vertices means there exists a closed Eulerian walk that contains even number of vertices. To connected this cycle we need exactly same number of edges to the vertices. Since the Eulerian walk travels each edge in $G$ exactly once, the number of edges in $G$ must also be even.

##### c)
No, it is not possible
We model the floor plan as a graph, where each room is a node and a door between two rooms means there is an edge between these two rooms. The task is to check if this graph is bipartite (room is red means this node is in set $V_{1}$ , purple means in set $V_{2}$). Using Theorem 1, a graph is bipartite, only if it does not contains any cycle of odd length. However the sequence (Best friend's room -> Bar -> Hallway -> Kitchen -> Your room -> Best friend's room) forms a cycle of length 5. Therefore this graph is not bipartite, which means such a coloring plan does not exists.



