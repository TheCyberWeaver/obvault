## Overview
A dataset $D = (s_1, s_2, \dots, s_n)$ is a sequence of $n$ elements.
A pair $(i, j)$ with $1 \le i < j \le n$ is called a duplicate in $D$ if $s_i = s_j$.

**Task:** Given a dataset $D$, find all duplicates.
**Example:**
$$
D = (A, C, B, Z, C, B, C)
$$
$$
\begin{array}{ccccccc}
1 & 2 & 3 & 4 & 5 & 6 & 7
\end{array}
$$
Set of duplicates in $D$:
$$
\mathrm{Dupl}(D) = \{(2,5), (2,7), (5,7), (3,6)\}
$$
> [!NOTE] Naive solution
> sort the elements in alphabetic order 


## Hash function
Let the elements in $D$ be drawn from a universe $U$
We use a hash function $h : U \to [m]$ and assume:
- $h$ is efficiently computable.
- $h$ behaves like a random function, i.e.,
$$
\forall u \in U \;\; \forall i \in [m] : 
\Pr[h(u) = i] = \frac{1}{m}
$$
(independently for different $u$)

> [!Important]
> Each $h(s_i)$ is uniformly distributed at random in $[m]$, but
> $$
> s_i = s_j \;\Rightarrow\; h(s_i) = h(s_j).
> $$
> We choose $m$ to be much smaller than $|U|$ (compression).

## Hash-based duplicate detection
Idea: elements that are equal must have the same hash value.
For each position $i$, compute $h(s_i)$ and place $i$ into bucket $h(s_i)$.
For every bucket $b \in [m]$, define
$$
B_b = \{ i \in [n] : h(s_i) = b \}.
$$
If two elements are duplicates, then their indices must appear in the same bucket.
$$
s_i = s_j \Rightarrow h(s_i) = h(s_j)
$$
Therefore, we only need to compare elements inside the same bucket.
## Algorithm
1. Create $m$ empty buckets.
2. For every $i = 1, \dots, n$:
   - compute $b = h(s_i)$
   - insert $i$ into bucket $B_b$
3. For each bucket $B_b$:
   - compare all pairs of indices inside $B_b$
   - if $s_i = s_j$, output $(i,j)$
### Pseudocode
```
Create empty buckets B[1], ..., B[m]
for i = 1 to n:
    b = h(s_i)
    append i to B[b]
Dupl = empty set
for b = 1 to m:
    for each pair (i, j) in B[b] with i < j:
        if s_i = s_j:
            add (i, j) to Dupl
return Dupl
```

