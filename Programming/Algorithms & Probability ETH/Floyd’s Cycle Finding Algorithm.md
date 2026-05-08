---
aliases:
  - Hase-Igel-Algorithmus
  - Tortoise and Hare Algorithm
---
If we constraint the input of [[Finding Duplicates]] to:

> [!NOTE]
> input array $a[1,...,n]$ with $a[i]\in \{ 1,\dots,n-1 \}$

then we can use a better algorithm with $O(n)$ time and $O(1)$ memory
## Overview
The idea is to start with the **two pointers slow** and **fast**, both starting at the **head** of the linked list.
- While traversing the List:
    - **slow** pointer will move one step at a time.
	- **fast** pointer moves two steps at a time.
    - If there's a **cycle**, the fast pointer will eventually catch up with the slow pointer within the cycle because it's moving faster.
    - If there's **no cycle**, the fast pointer will reach the end of the list (i.e., it will become **NULL**).
- When the slow and fast pointers meet, a **cycle** or **loop** exists

## Application
**Given**: Array $a[1,...,n]$ with $a[i]\in \{ 1,\dots,n-1 \}$
**Goal**: Find two indices $i\neq j$ with $a[i]=a[j]$
**Constraints**: time $O(n)$, memory $O(1)$
We observe the graph $D=(V,A)$ with
$V=[1,\dots,n]$
$A=\{ (i,a[i])|1\leq i\leq n \}$
![[floyd's cycle finding example.excalidraw|256]]
We observe the subgraph $D_{n}$ (nodes and edges that are reachable from $n$)
![[floyd's cycle finding example Dn.excalidraw|256]]
We define
$x_{0}=n$
$x_{t}=a[t_{t-1}]$
**Claim**: There is $t\leq n$ such that $x_{t}=x_{2t}$
**Proof**: 
Let $r=\left\lceil  \frac{k}{l}  \right\rceil\cdot l-k\geq0$
so $k+r=\left\lceil  \frac{k}{l}  \right\rceil l\implies x_{k+r}=x_{2(k+r)}$
and $t:=k+r=\left\lceil  \frac{k}{l}  \right\rceil l<\left( \frac{k}{l}+1 \right)l=k+l\leq n$

Now we can use the two pointers to solve the task.

Find $t$
```
slow=a[n]
fast=a[a[n]]
t=1
while(slow!=fast)
	slow=a[slow]
	fast=a[a[fast]]
	t=t+1
```

**Claim**: Let $t\leq n$ with $x_{t}=x_{2t}$ then $x_{t+k}=x_{k}$
**Proof**:
$x_{t}=x_{2t}\implies2t=t+p\cdot l$ for some $p \in \mathbb{N}$
$\implies t=p\cdot l$ for some $p \in \mathbb{N}$
$\implies x_{k+t}=x_{k}$


find $i,j$ with $a[i]=a[j]$
```
fast=n
while(slow!=fast)
	i=slow
	j=fast
	slow=a[slow]
	fast=a[fast]
return i,j
```