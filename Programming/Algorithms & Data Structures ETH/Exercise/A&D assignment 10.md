#eth #exercise 
# 10.1 Depth-first search
##### a) b) d)
![[dca32467534cd2e7e60b91020c84aa63.jpg|438]]
##### c)
Pre: $ACDEBGHFI$
Post: $BEDHGCFAI$

##### e)
No, we can find a cycle by using a backward edge. Let backward connects $v,u$ , there must exists a path from $u$ to $v$ inside the tree, together with the backward edge, a cycle is formed.
In the example above, a backward edge $(B,A)$ exists, so we can find the cycle $(A,C,D,E,B)$

##### f)
![[cc56a4d11a8fcdc436cdeb07c1ec263e.jpg|681]]
If $I_{u}\subset I_{v}$ then there exists a path from $v$ to $u$ in the DFS-tree

##### g)
If edge $(B,A)$ is removed and $(F,I)$ is added, then:
The new pre/post numbers:
$F:$ 14/17
$I:$ 15/16
$A:$ 1/18

Now the graph has a topological ordering:
AFICGHDEB
If we sort the vertices by pre-number, we do not get a topological sorting

# 10.2 Breadth-First Search
##### a)
$ABDEFCGH$
##### b) c) d)
![[30b311d762df30016e1e0204ec6fdd2f.jpg]]

# 10.5 Strongly connected vertices
Use a DFS. While running DFS, look for a back edge. Any back edge $u\to v$ with $v$ an ancestor of $u$ immediately gives a strongly connected pair $(u,v)$

```
status[1...n]=-1 //-1:unvisited 0:in stack 1:visted

function DFS(u):
    status[u] = 0
    for each v in Adj[u] do
        if status[v] = -1 then
            pair = DFS(v)
            if pair ≠ null then
                return pair
        else if status[v] = 0 then // found back edge v -> u
            return (u, v)      
    status[u] = 1
    return null

// main
for v = 1 to n do
    if status[v] = -1 then
        pair = DFS(v)
        if pair ≠ null then
            output pair
            halt
output "no such pair exists"
```
