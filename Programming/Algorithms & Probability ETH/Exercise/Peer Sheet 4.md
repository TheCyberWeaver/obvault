# P4.1 Randomized Algorithms
![[Pasted image 20260430104556.png]]

**Algorithm**:
We assign each vertex independently and uniformly one of the $k$ colors and keep only the valid edges (edges that have different colors on the two ends)
We repeat this step until we find a solution such that $\lvert E' \rvert> \frac{k-2}{k}\lvert E \rvert$
**Proof**:
we define event 
$E_{i}:=$ edge $i$ has same colors on both ends
$F_{i}:=$ edge $i$ has different colors on both ends
$\Pr[E_{i}]=\frac{1}{k}$ since the colors of the vertices are chosen indepently and uniformly
$\Pr[F_{i}]=1-\Pr[E_{i}]= \frac{k-1}{k}$

Let $F$ be the number of edges that have different colors on both ends
$\mathbb{E}[\lvert E' \rvert]=\mathbb{E}[F]=\sum_{i=1}^{\lvert E \rvert} \Pr[F_{i}]=\frac{k-1}{k}\lvert E \rvert> \frac{k-2}{k}\lvert E \rvert$

**Time analysis**:
Each trial takes $O(\lvert V \rvert+\lvert E \rvert)$ (we assign each vertex a color and check each edges)
Let $R:=$ the number of repetitions of the trials with $\mathbb{E}[X]=\mathbb{E}[R]\cdot O(\lvert V \rvert+\lvert E \rvert)$
We know each trial succeeds with probability $p>0$
then $R$ is geometric distributed with $\mathbb{E}[R]=\frac{1}{p}$
$\implies \mathbb{E}[X]=\Theta(1)\cdot O(\lvert V \rvert+\lvert E \rvert)=\Theta(\lvert V \rvert+\lvert E \rvert)$


