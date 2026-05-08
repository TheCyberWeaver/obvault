## Overview

`Quickselect(A,l,r,k)` (find the $k$-th smallest element in $\{ A[l],\dots ,A[r] \}$)
$p\leftarrow\text{Uniform}(\{ l,l+1,\dots,r \})$  
$t\leftarrow\text{Partition}(A,l,r,p)$
If $t=l+k-1$ then return $A[t]$
else if $t>l+k-1$ then return `Quickselect(A,l,t-1,k)` (Left block)
else then return `Quickselect(A,t+1,r,k-t)` (Right block)

## Time Analysis
**Goal**: Las Vegas Algorithm with expected run time $O(n)$

We define 
$T=$ # of comparisons
$N_{j}=$ # of calls of `Quickselect` on $m$ elements with $\left( \frac{3}{4} \right)^{j}n<m\leq\left( \frac{3}{4} \right)^{j-1}n$

$$
T \leq \sum_{j=1}^{\infty} N_{j}
\underbrace{
\left( \frac{3}{4} \right)^{j-1} n
}_{\substack{\text{upper bound of} \\ \text{comparisons in}\\ \text{the partition}}}
$$
$$
\implies \mathbb{E}[T] \leq n\cdot \sum_{j=1}^{\infty} \mathbb{E}[N_{j}] \left( \frac{3}{4} \right)^{j-1}
$$

**Observation**
If we choose the middle half of the elements as pivot element, then the search room is reduced by factor at most $\frac{3}{4}$ 
$\implies$ The search room will be reduced by factor $\leq\frac{3}{4}$ with probability of $\geq\frac{1}{2}$

**Claim**: $\mathbb{E}[N_{j}]\leq2\quad	\forall{j>1}$
Then $\mathbb{E}[T]\leq \sum_{j=1}^{\infty}2\cdot\left( \frac{3}{4} \right)^{j-1}n=8n$ (geometric serie $S=\frac{a_{1}}{1-p}$)
**Proof**
We also see that the pivot element is one of the middle $\frac{m_{i}}{2}$ elements with probability of $\geq\frac{1}{2}$
$\implies m_{i+1}\leq \frac{3}{4}m_{i}$
$\implies \mathbb{E}[N_{j}]\leq2$
