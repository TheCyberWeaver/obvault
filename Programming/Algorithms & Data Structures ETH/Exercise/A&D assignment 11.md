#eth #exercise 
# Shortest paths with cheating

##### a)
This algorithm runs the Dijkstra's algorithm for every possible $\gamma$ weight functions

1) For every graph $G(V,E)$ we use, the edges are directed with weight $\gamma(e)$ for all $e\in E$. 
	- We can set at most $k$ edges to $0$. Obviously we should fully use $k$ cheats, because the weights are non-negative. 
	- For each cheat edge, we have $\lvert E \rvert$ choices. By the principle of combination, we have in total $\lvert E \rvert^{k}$ choices. This gives $\lvert E \rvert^{k}$ $\gamma$ weight functions.
2) We apply Dijkstra's algorithm in $O(\lvert V \rvert^{2})$ on each graph from $s$
3) We find the shortest s-to-t-distance among the results of Dijkstra's algorithm from all the graphs. This takes $O(\lvert E^{k} \rvert)$, since there are $\lvert E \rvert^{k}$ graphs.
4) For each iteration we runs Dijkstra's algorithm in $O(\lvert V \rvert^{2})$ and we have $\lvert E \rvert^{k}$ iterations. Plus the time in step 3  we have $O(\lvert E \rvert^{k}\cdot \lvert V \rvert^{2}+\lvert E^{k} \rvert)=O(\lvert E \rvert^{k}\cdot \lvert V \rvert^{2})$

##### b)

1) We construct a new $G'=(V',E')$. $V'$ consists of $k+1$ copies of $V$. Each copy of $V$ are still connected in the same way as $V$ (with the same weight in $E$). We denote each copy as $V'_{i}$ with $i \in[k+1]$. For $i \in[k]$, each vertex in $V'_{i}$ has extra edges pointing to the neighbors of the corresponding vertex in upper layer $V'_{i+1}$. These extra edges all have the weight $0$
2) We apply Dijkstra's algorithm in $O(\lvert V' \rvert^{2})$ on this graph from $s$
3) We extract the result by getting the distance to $t$ from the result of the Dijkstra's algorithm
4) The total runtime costs $O(\lvert V' \rvert^{2})=O((k\lvert V \rvert)^{2})$. We can ignore the cost in step 3 because it takes constant time to extract the result.

# 11.4 Driving from Zurich to Geneva
##### a)
1) We use a directed graph $G(V,E)$ where $V$ is the vertex set representing the cities. $E$ is the edge set representing each highways. Note that each direction of a highway is considered as a distinct edge. The weight of an edge is the cost of the fuel for this part minus (if exists) the money earned by taking a passenger for this part.
2) We apply Bellman-Ford algorithm on this graph from vertex Zurich
3) We extract the result by getting the distance to vertex Geneva.
4) The running time is $O(\lvert V \rvert\cdot\lvert E \rvert)$ (the running time of Bellman-Ford algorithm). The running time in Step 1 and 3 are $O(\lvert V \rvert+\lvert E \rvert)$ and $O(1)$, and therefore can be ignored.

# 11.5 Ancient Kingdom of Macedonia

He does not need to reconsider.

We first model this problem. The kingdom can be treated as a connected graph $G=(V,E)$ with $V$ is the vertex set representing the cities, and $E$ representing the Roman roads. In the first year, the cost of an asphalt edge $e$ is just its length $l_{e}$. and the optimal asphalt network is the minimal spanning tree. Let $S$ be the set of the asphalt edge. This MST has the cost $C_{1}(S)=\sum_{e\in S}l_{e}$.  In the second year the cost of each asphalt node becomes $l_{e}+k$ where $k$ is a constant. The question is if $S$ is still a MST. 
The cost of $S$ is now $C_{2}(S)=\sum_{e\in S}(l_{e}+k)=\sum_{e\in S}l_{e}+k\lvert S \rvert=C_{1}(S)+k\lvert S \rvert$. The number of edges of a spanning tree is always $\lvert S \rvert=\lvert V \rvert-1$. Since the number of cities does no change in year 2, $k\lvert S \rvert$ must be a constant. 
We know that $C_{1}(S)$ is already optimized, so there cannot exist a new $S'$ such that $C_{1}(S')<C_{1}(S)$. Therefore $C_{2}(S)=C_{1}(S)+constant$ must also be optimized. Hence, $S$ is still a MST in year 2.
We now proved that $S$ (the set of asphalt road) does not need to be changed in year 2.
