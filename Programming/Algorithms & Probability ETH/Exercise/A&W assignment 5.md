## T5.1 Sum of Unit Vectors
![[Pasted image 20260506214639.png]]
### a)
by linearity of expected value:
$$
\mathbb{E}[X]=\mathbb{E}\left[ \sum_{i=1}^{n} \sum_{j=1}^{n} s_{i}s_{j}\cdot(v_{i}\cdot v_{j}) \right]=\sum_{i=1}^{n} \sum_{j=1}^{n}\mathbb{E}[s_{i}s_{j}] (v_{i}\cdot v_{j})
$$
case $i=j:$
then $s_{i}=s_{j}\implies s_{i}s_{j}=1\implies \mathbb{E}[s_{i}s_{j}]=1$
$v_{i}\cdot v_{j}=1\implies \mathbb{E}[s_{i}s_{j}](v_{i}\cdot v_{j})=1$

case $i\neq j:$
since $s_{i}$ and $s_{j}$ are chosen independently $\mathbb{E}[s_{i}s_{j}]=\mathbb{E}[s_{i}]\cdot \mathbb{E}[s_{j}]=0\implies \mathbb{E}[s_{i}s_{j}](v_{i}\cdot v_{j})=0$

Therefore: 
$$
\mathbb{E}[X] =\sum_{i=1}^{n} 1=n
$$
### b)
Since $X=\lVert v \rVert^{2}$ and $\mathbb{E}[X]=n$
we know that there exists at least one $v$ such that $\lVert v \rVert^{2}\leq n$
$\implies$ there exists at least one $v$ such that $v\leq \sqrt{ n }$
$\implies$ the minimal possible norm of $v$  $\leq \sqrt{ n }$

### c)
let $Y$ be a random variable with $Y:=\sqrt{ X }$ where $X$ is defined as above
$\Pr[Y\geq2\sqrt{ n }]=\Pr[X\geq4n]$
using Markov inequality:
$\Pr[X\geq4n]\leq \frac{\mathbb{E}[X]}{4n}=\frac{n}{4n}=\frac{1}{4}$
Thus
$$
\Pr[\lVert s_{1}v_{1}+\dots+s_{n}v_{n} \rVert \geq2\sqrt{ n }] \leq \frac{1}{4}
$$

### d)
**Algorithm**:
We choose $s_{1},\dots,s_{n}$ randomly and independently from $\{ -1,1 \}$, then check if $\lVert s_{1}v_{1}+\dots+s_{n}v_{n} \rVert\leq2\sqrt{ n }$.
We repeat this process until we find a valid answer

from c) we get $\Pr[\lVert v \rVert<2\sqrt{ n }]\geq \frac{3}{4}$ ($v$ defined as in b)
So each trial succeeds with probability at least $\frac{3}{4}$

The expected number of trials follows geometric distribution, so the expected number of trials is at most $\frac{1}{\frac{3}{4}}=\frac{4}{3}$

Each trial requires computing $s_{1}\cdot v_{1}+\dots+s_{n}v_{n}$ which costs $O(n^{2})$ time (assume each addition between vectors takes $O(n)$)
Since the expected number of trials is in $O(1)$, the total expected running time is also $O(n^{2})$

