 #exercise 
# 8.1 Party & Beer & Party & Beer
We first model the party as an undirected graph where vertices are people and edges represent “knowing each other.” The problem states that every person knows exactly 7 others. Therefore every vertex has degree 7.
By the Handshaking Lemma $\sum_{u\in V} deg(u)=2\cdot \lvert E \rvert$
The left side equals $7\cdot \lvert V \rvert$, which must be even.
Since $7$ is odd, $\lvert V \rvert$ (or the number of people) must be even. 

# 8.3 Graph connectivity

a) **Claim**: If a vertex v is part of a cycle, then it is not a cut vertex.
![[Pasted image 20251116134239.png]]
The claim is disproved

b)**Claim**: If a vertex v is not a cut vertex, then v must be part of a cycle.
Let a graph contains two vertices $a,b$ that are connected. Both of them are not cut vertices, are they are not in a cycle.
The claim is disproved

c)**Claim**: If an edge e is part of a cycle (i.e. e connects two consecutive vertices in a cycle), then it is not a cut edge.
Let a cycle be $(v_{1},v_{2},\dots v_{k},v_{k+1})$, where $v_{k+1}=v_{1}$.
Let $e=\{ v_{i},v_{i+1} \}$ , If we are to remove $e$, then there still exists a walk $(v_{i+1},\dots v_{k},v_{1},\dots v_{i})$
So the remaining graph is still connected. Therefore, $e$ is not a cut edge.
The claim is proved

d)**Claim**: If an edge e is not a cut edge, then e must be part of a cycle.
Assume $e=\{ v,u \}$ is not a cut edge. Then removing it does not disconnect the graph, so there is still a path between $u$ and $v$.
Now we add back the edge $e$, the path $(u, \dots,v)$ and $(v,u)$ forms together a cycle. Therefore $e$ must lie on a cycle.
The claim is proved.

e)**Claim**: If u and v are two adjacent cut vertices, then the edge e = {u,v} is a cut edge.
![[Pasted image 20251116204057.png|384]]
As shown, u and v are cut vertices but e is not a cut edge.
The claim is disproved.


f)**Claim**: If e = {u,v} is a cut edge, then u and v are cut vertices.
Let a graph contains two vertices $u,v$ that are connected through an edge $e=\{ u,v \}$. $e$ is a cut edge, but $u$ and $v$ are not cut vertices. 
The claim is disproved.
**Claim**: If e = {u,v} is a cut edge and u and v have degree at least 2, then u and v are cut vertices.

Deleting $e$ separates the graph into exactly two components, say $A$ containing $u$ and $B$ containing $v$. 
Since $deg(u)\geq2$, $u$ has at least one neighbor $x$ ($x\neq v$) that lies in component $A$.
But every vertex in $B$ is now disconnected from $x$ when $u$ is removed, because any path from $x$ to a vertex in $B$ must go through $u\to v$ using the edge $e$, and that edge is gone.
Thus removing $u$ disconnects the graph. So $u$ is a cut vertex.
By symmetry, the same argument shows that $v$ is also a cut vertex.
The claim is proved.