# P1.1
a)
![[Pasted image 20260309125954.png]]

We claim that for all $X\subseteq A$ we have $\lvert X \rvert\leq \lvert N(X) \rvert$
**Proof**:
Assume we have an arbitrary subset $X$ of $A$ 
Consider the edge set $E_{X}:=\{ (a,b):a\in X \}$
Because the graph is bipartite, every edge contains exactly one vertex from $X$ and one vertex from $N(X)$
Therefore, we have $\sum_{a\in X} deg(a)=\lvert E_{X} \rvert=\sum_{b\in N(X)}deg(b)$
$\implies k\times \lvert X \rvert=l\times \lvert N(X) \rvert$ (by definition of (k-l)-regular)
$\implies \lvert X \rvert=\frac{l}{k}\lvert N(X) \rvert$
$\implies \lvert X \rvert\leq \lvert N(X) \rvert$ (since $k\geq l$, which means $\frac{l}{k}\leq1$)

By using the Hall's theorem and the claim we just proved, there exists a matching $\lvert M \rvert=\lvert A \rvert$
$q$.$e$.$d$.


b)
![[Pasted image 20260309134519.png]]
**Graph**
We build a graph in the following way:
Each vertex in set A is an unique combination of five cards, and each vertex in set $B$ is an unique permutation of four cards. This means we have $\lvert A \rvert=\begin{pmatrix}	52 \\ 5\end{pmatrix}$ and $\lvert B \rvert=\frac{52!}{48!}$ 
A vertex $a\in A$ is connected to a vertex $b\in B$ with an edge if and only if the permutation of $b$ is fully contained in the combination of $a$.

**Observations**:
Every vertex in $A$ has a degree of $\begin{pmatrix}	5 \\ 4\end{pmatrix}\cdot4! =120$, since any four of the five cards in arbitrary order is a valid vertex in $B$ that is contained in it.
Every vertex in $B$ has a degree of $52-4=48$, since the fifth card can be chosen arbitrarily, and the order does not matter.
This is a (120,48)-regular bipartite graph.
Using the conclusion from part a), there exists a matching of size exactly $\lvert A \rvert$ (since $120>48$)

**Strategy**
Now this matching gives us a strategy to succeed the trick:
- For any 5 cards chosen, the assistant finds the 4-cards-permutation according to the matching, and give those four cards to the magician with the specific order.
- The magician then reverse the process by finding the corresponding 5-cards-combination from any given 4-cards using the same matching. Since the matching covers all vertices in set $B$, it is guaranteed to be able to find such vertex in set $A$. By definition of matching, it is also guaranteed that the 5-cards-combination the magician find must be the original 5 cards the audience member provided
- The magician can then find the fifth card in the 5-cards-combination that is not in the 4-cards-combination, which completes the trick.


