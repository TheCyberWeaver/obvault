---
tags:
  - linker-exclude
---
## Definition
Let $X$ be a topological space. A collection $\mathcal{B}$ of subsets of $X$ is called a basis for $X$ if 
1. Every $B\in \mathcal{B}$ is open
2. Every open subset of $X$ is the union of elements in $\mathcal{B}$

## Examples
### 1)
> [!Example] 
> Open balls form a basis of the topology on a metric space $M$.

defines open balls:
$B_{r}(x)=\{ y|d(x,y)<r \}$
defines the basis formed by open balls:
$\mathcal{B}=\{ B_{r}(x)|r\in \mathbb{R}_{>0},x \in M \}$
**Proof**:
this is how a topology on a metric space is defined, see [[Topology#Metric Topology]]
### 2)

> [!Example] 
> The collection of all singletons is a basis for the discrete topology.

$U=\bigcup _{y\in U}\{ y \}$

## Proposition: continuity
Let $X,Y$ be spaces with $\mathcal{B}$ a basis for $Y$.
A function $f:X\to Y$ is [[Continuous Map (function in topology)#Definition continuous|continuous]] $\Longleftrightarrow$ $f^{-1}(B)$ is open for each $B\in \mathcal{B}$

So we do not acquire to check that every subset is open, we only need to check the elements of the basis are open.

## Proposition: generation of basis
$\mathcal{B}$ is a basis for a unique topology on $X$ if and only if:
- $\bigcup _{B\in \mathcal{B}}=X$
- If $B_{1},B_{2}\in \mathcal{B}$ and $x \in B_{1}\cap B_{2}$, then there is $B_{3}\in \mathcal{B}$ such that $x \in B_{3}\subseteq B_{1}\cap B_{2}$

#math-tools 
## Proposition: relation to every neighborhood
Let $\mathcal{B}$ be a basis of topological space $X$
$N$ is a neighborhood of $p$ $\implies \exists{B\in \mathcal{B}}\; (p \in B\subseteq N)$

## Basis in Vector space
![[Section 30 Vector Spaces#30.6 Definition Span]]

