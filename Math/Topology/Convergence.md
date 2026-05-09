---
tags:
  - linker-exclude
---
## Definition: Limit points
Let $X$ be a space and set $A\subseteq X$
A point $p \in X$ is a **limit point of A** if every neighborhood of $p$ contains a point of $A$ other than $p$
OR _accumulation point

$A'$ denotes the set of limit points.

For any topology space we have
$\bar{A}=A\cup A'$ [[Topology by James Munkres.pdf#page=99&selection=350,0,350,12&color=note|Topology by James Munkres, p.99]]
$\implies$ $A'\subseteq \bar{A}$
> [!NOTE]
> In any topological space, if a subset $A$ has no isolated points, then its set of limit points is exactly equal to its [[Topology#closure|closure]].

![[Pasted image 20251205235448.png|373]]
In this case, $p$ and $b$ are limit points
## Definition: Isolated points
A point $p \in A$ is an **isolated point of A** if $p$ has a neighborhood $U$ in $X$ with $U\cap A=\{ p \}$
![[Pasted image 20251205235411.png|324]]
In this case, $a$ is a isolated point

## Definition: dense
A subset $A$ of $X$ is dense if $\bar{A}=X$
A subset $A$ is dense in $X$ $\Longleftrightarrow$ every non-empty open $B\subseteq X$ contains a point of $A$
### Example
$\mathbb{Q}$ is **dense** in $\mathbb{R}$

## Definition: Convergence

$(x_{i})^{\infty}_{i=1}$ is a sequence of points in $X$, and $x \in X$, we say the sequence converges to the limit $x$, if for every neighborhood $U$ of $x$ there is $N\in \mathbb{N}$ such that $x_{i}\in U$ for all $i\geq N$

we also say $x$ is a **limit point** of this sequence

> [!NOTE] In other word
> For any neighborhood $U$ of $x$, there exists all the elements in the sequence from a certain index.


![[Pasted image 20251206193941.png|273]]similar to definition of [[Sequence#Definition Convergence|convergence]] in Euclidean space
In $\mathbb{R}^{2}$, we take a ball of $x$ instead of an arbitrary neighborhood

If $x_{i}\to x$ then $x \in \bar{A}$ (limits lies in [[Topology#closure|closure]])