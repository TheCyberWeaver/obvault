# T2.1 Choosing Seminars
![[Pasted image 20260318210906.png]]

a)
We model this problem into a bipartite graph $G=(A+B,E)$
Let each student be a vertex in set $A$, and each seminar be a vertex in set $B$
we now make a new graph $G=(A+B',E)$
where $B'$ contains 13 copies of $B$ (each seminar appears 13 times in $B'$)
There is an edge between $a\in A$ and $b\in B'$ if and only if student $a$ applied for that seminar.
Now the problem becomes "Can we find a matching in graph $G'$ with size $\lvert A \rvert$"
The Hall's Theorem tells us there is such matching if and only if $\forall{X\subseteq A}\;:\; \lvert X \rvert\leq \lvert N(X) \rvert$ under graph $G'$
$\Longleftrightarrow\forall{X\subseteq A}\;:\; \lvert X \rvert\leq 13\lvert N(X) \rvert$ under graph $G$ (since any $\lvert N(X) \rvert$ in $G'$ contains $\frac{\lvert N(X) \rvert}{13}$ seminars)
Now we prove this claim under graph $G$.
For any subset $X\subseteq A$, there are exactly $3\lvert X \rvert$ outgoing edges.
for any $\lvert N(X) \rvert$ we will have at most $40+40+39(\lvert N(X)\rvert-2)=39\lvert N(X) \rvert+2$ edges
So we must have $3\lvert X \rvert\leq39\lvert N(X) \rvert+2$
$\implies \lvert X \rvert\leq13\lvert N(X) \rvert+\frac{2}{3}$
Since we cannot have fractional number of edges, we get
$\implies \lvert X \rvert\leq13\lvert N(X) \rvert$
This proves our claim. Therefore, there must exists such an matching, which gives a possible valid assignment.

b) 
With at most 12 student each seminar it is impossible to always find an assignment.
Counterexample:
suppose we have $4$ seminars ($a$,$b$,$c$,$d$) and  $4*12+1=49$ students
21 students apply for $a,b,c$
10 students apply for $a,b,d$
9 students apply for $a,c,d$
9 students apply for $b,c,d$
then we have $a=21+10+9=40$, $b=21+10+9=40$, $c=21+9+9=39$, $d=10+9+9=28$
This is a valid situation. However, if we choose the entire student set as $X$ then we have $\lvert X \rvert=49>48=12\lvert N(X) \rvert$. By using Hall's theorem, we've shown that there is no matching of size $\lvert A \rvert$ (meaning a valid assignment is not possible)

# T2.2 Augmenting path of length k
![[Pasted image 20260318210926.png]]

a)
