## Overview
Algorithm `QUICKSORT(A, l, r)`

If $l < r$ then:
1. $p\leftarrow\text{Uniform}(\{ l,l+1,\dots,r \})$  
2. $t\leftarrow\text{Partition}(A,l,r,p)$
   - Elements $\le A[p]$ are to its left
   - Elements $> A[p]$ are to its right
   - $t$ is the final index of the pivot element, so $A[l \dots t-1] \le A[t]$ and $A[t+1 \dots r] > A[t]$
	   - (this means $t$ is also uniformly distribudted in $\{ l,l+1,\dots,r \}$ )
3. Recursively call:
   - `QUICKSORT(A, l, t-1)`  (Left block)
   - `QUICKSORT(A, t+1, r)`  (Right block)

similar idea to [[Quicksort]]
## Time analysis
We define a random variable:
$$
T_{l,r}:= \text{\# of comparison in Quicksort($A$,$l$,$r$)} 
$$
> [!NOTE] Theorem / Hypothesis
> There is $\mathbb{E}[T_{1,n}]\leq2(n+1)\ln n+O(n)$

### Proof
For $l\geq r$: $T_{l,r}=0$
For $l<r$:
$$
\mathbb{E}[T_{l,r}] =\sum_{i=l}^{r} \Pr[t=i] \cdot \mathbb{E}[T_{l,r}|t=i] =\sum_{i=l}^{r} \frac{1}{r-l+1}\cdot(r-l+\mathbb{E}[T_{l,i-1}] +\mathbb{E}[T_{i+1,r}] )
$$
**Observation**: $\mathbb{E}[T_{l,r}]$ is only dependent on $r-l+1$ (since $t$ is uniformly chosen)

Therefore, we can define 
$$
t_{n}=\begin{cases}
0\;\text{for n $\le$ 1} \\
\frac{1}{n}\sum_{i=0}^{n-1} (n-1+t_{i}+t_{n-i-1})
\end{cases}
$$
with $\mathbb{E}[T_{l,r}]=t_{r-l+1}$

**Goal**: Estimate an upper bound for $\mathbb{E}[T_{1,n}]=t_{n}$

$\forall{n\geq3} :\;$
$$
n\cdot t_{n}=\sum_{i=0}^{n-1} (n-1+t_{i}+t_{n-i-1}) \tag{1}
$$
$$
(n-1)t_{n-1}=\sum_{i=0}^{n-2} (n-2+t_{i}+t_{n-i-2}) \tag{2}
$$
$(1)-(2)$ gives

$$
n\cdot t_{n}-(n-1)t_{n-1}=2(n-1)+2t_{n-1}
$$
$$
t_{n}= \frac{n+1}{n}t_{n-1}+\frac{2(n-1)}{n}\leq \frac{n+1}{n}t_{n-1}+2 \tag{*}
$$
**Claim**:
$$
t_{n}\leq2\sum_{i=3}^{n+1} \frac{n+1}{i}
$$
**Proof by induction**:
For $n=2:\; t_{2}=1\leq2=2\sum_{i=3}^{3} \frac{3}{i}$
For $n\geq3:$ 
$$
2\sum_{i=3}^{n+1} \frac{n+1}{i}=2\sum_{i=1}^{n}  \frac{n+1}{i}+2 \frac{n+1}{n+1}=\frac{n+1}{n}\cdot2\sum_{i=3}^{n} \frac{n}{i}+2
$$
$$
\geq \frac{n+1}{n}\cdot t_{n-1}+2\quad	 \text{(using claim)}
$$
$$
\geq t_{n} \quad	\text{using (*)}
$$

**Finally**

$\mathbb{E}[T_{1,n}]=t_{n}\leq2(n+1)\sum_{i=1}^{n} \frac{1}{i}=2(n+1)\ln(n)+O(n)$ 
Note that $\sum_{i=1}^{n} \frac{1}{i}$ is the $n$-th [[harmonic number]], which gives a bound of $\ln n+O(1)$


## Related
See how to parallelized it [[Parallel Quicksort]]