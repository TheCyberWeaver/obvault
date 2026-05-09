 #exercise 
# 12.1 MST practice
##### a)
After the first step:
$(A,B)$
$(C,H),(D,H),(E,H),(F,I),(G,H),(H,I)$
After the second step:
$(A,B),(C,H),(D,H),(E,H),(F,I),(G,H),(H,I),(B,C)$
##### b)
$(A,B),(D,H),(C,H),(B,C),(H,I),(F,I),(G,H),(E,H)$ 

##### c)
$(G,H),(D,H),(C,H),(B,C),(A,B),(H,I),(F,I),(E,H)$

# 12.3 Uniqueness of MSTs
##### a)
![[not unique MST.excalidraw|261]]
We can get MST $(A,B),(B,C)$ from Kruskal's algorithm, and $(A,C),(B,C)$ from Prim's algorithm
##### b)
Since $T_{2}$ is a spanning tree, adding an extra edge $e\not\in T_{2}$ creates exactly one cycle: Assume $e$ connects $u$ and $v$. There exists a path from $u$ to $v$ through the spanning tree (without using $e$). If we add $e$ to this path, we get a cycle.

We claim this cycle to be $C$. There must be an edge $f\in T_{2}\setminus T_{1}$ on $C$, because otherwise $C$ would be fully contained in $T_{1}$, which contradicts the fact that $T_{1}$ is a spanning tree.
Moreover, $f$ could not be $e$, because $e\in T_{1}\setminus T_{2}$. So $f$ and $e$ are distinct. Since all weights are distinct and $e$ is the minimum weight, we have $w(f)>w(e)$

##### c)
We replace $f$ with $e$ on $T_{2}$.
We first add $e$ to $T_{2}$ and get a cycle $C$, then we remove another edge $f$ on this cycle, such that the remaining structure is still a spanning tree (every vertices are still connected and no more cycles). Now we've reduced the total weight of $T_{2}$ by $w(f)-w(e)$ (not $0$). This leads to a contradiction to our assumption that $T_{2}$ is a minimum spanning tree.
Therefore, the minimum spanning tree of $G$ with weight function $w$ is unique.

##### d)
![[Not unique weight of MST.excalidraw]]
There is one unique minimum spanning tree $(A,B),(B,C)$, however, the weights are not distinct.

# 12.4 Counting Minimum Spanning Trees With Identical Edge Weights
##### a)
Contracting an edge $e\in T$ just “glues together” its two endpoints. Since $T$ is a tree, this operation does not create cycles or disconnect the graph. So the contracted tree $T_{e}$​ is still a spanning tree of the contracted graph $G_{e}$​ . 
Now we show that $T_{e}$ is minimal. Suppose we uncontract $e$ (separate $vw$, and add back the original edges). The total weight increases by exactly $c(e)$ .If there were a spanning tree of $G_{e}$ cheaper than $T_{e}$, then uncontracting it would give a spanning tree $G$ cheaper than $T$, which contradicts the fact that $T$ is minimal.
##### b)
We partition $E$ into weight classes. we define $E_{\alpha}=\{ e\in E|w(e)=\alpha \}$
An edge $f$ is redundant if it lies in a class of size at least $2$. ($e\neq e'\in E$ with $w(e)=w(e')$)
Let $\alpha=w(e)$. In $G_{e}$, the only weight class whose size changes is $E_{\alpha}$, which becomes size $\lvert E_{\alpha} \rvert-1$. 
**Case 1**: $\lvert E_{\alpha} \rvert=2$, then the redundancy drops by 2. $k'=k-2$ because $E_{\alpha}$ now has size of 1 and does not contribute to the overall redundancy.
**Case 2**: $\lvert E_{\alpha} \rvert\geq3$, then the redundancy drops by 1. $k'=k-1$
Therefore, the number of redundant edges in $G_{e}$ is at most $k-1$
Hence, $G_{e}$ is $k'$-redundant for some $k'\leq k-1$
##### c)
We prove by induction
**Claim**:
If $G$ is connected and k-redundant, it has at most $2^{k}$ distinct MSTs.
**Base**:
$k=0$:
If $k=0$, then all edges are pairwise distinct, so MST is distinct (result from 12.3). The number of distinct MST is $1\leq2^{0}=1$

**Step**:
$k\to k+1$
we assume if $G$ is connected and k-redundant, it has at most $2^{k}$ distinct MSTs
Consider a (k+1)-redundant $G$:
we pick a redundant edge $e$
We denote the number of distinct MSTs that contains $e$ with $\#T'$
We denote the number of distinct MSTs that does not contains $e$ with $\#T''$

*case 1* $e\in T$
by (a) the contracted tree $T_{e}$ is an MST of $G_{e}$, so $\#T'\leq \lvert MST(G_{e}) \rvert$
by (b), $G_{e}$ is at most ((k+1)-1)-redundant. So we have $\#T'\leq \lvert MST (G_{e})\rvert\leq2^{(k+1)-1}=2^{k}$
*case 2* $e\not\in T$
Consider $G\setminus e$. Any MST $T$ with $e\not\in T$ is still a spanning tree of $G\setminus e$. Hence we have: $\#T''\leq \lvert MST(G\setminus e) \rvert$
we know deleting a redundant edge decreases the number of redundant edges by at least 1
so $\#T''\leq \lvert MST(G\setminus e) \rvert\leq 2^{k}$
*Conclusion*
the number of distinct MSTs $=\#T'+\#T''\leq2^{k}+2^{k}=2^{k+1}$
We've now shown that there are at most $2^{k+1}$ distinct MSTs.

The claim is proved through induction.
