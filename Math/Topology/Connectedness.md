---
tags:
  - linker-exclude
---
## Definition: disconnected
A topological $X$ is _disconnected_ if and only if it can be expressed as the disjoint union of two **non-empty open subsets** $U\sqcup V=X$ ($U$ and $V$ are subsets **not** spaces)

## Definition: connected
A space that is not _disconnected_ is _connected_

Whether a space is connected or not depends on its topology
## Example
- disconnected
	- $\mathbb{R}\setminus \{ 0 \}$: can be expressed as $(-\infty,0)\cup(0,\infty)$
	- The disjoint union of two closed disks in $\mathbb{R}^{2}$ is disconnected. (we are talking about the subset topology of those disks (as topology spaces))
	- $\mathbb{Q}^{2}$ is disconnected in $\mathbb{R}^{2}$
- connected
	- Intervals are connected
	- Open (closed) disks are connected
	- $\mathbb{R}^{n}$ is connected

## Lemma

> [!NOTE]
> $X$ is connected $\Longleftrightarrow$ $\varnothing$ and $X$ are the only subsets in $X$ that are both open and closed.

**Proof**: $\implies$
Suppose $U\subseteq X$ is clopen (closed and open), then $U^{c}$ is open. Then $U\sqcup U^{c}=X$, and that would mean $X$ is disconnected.


> [!NOTE]
> $X$ is connected $\Longleftrightarrow$ $X$ is not homeomorphic to a [[Disjoint Union Space|disjoint union]] of some non-empty spaces


## Properties: subspaces
Let $\{ B_{\alpha} \}_{\alpha \in A}$ be a collection of connected subspaces of $X$ with a point in common. Then $\bigcup _{\alpha \in A}B_{\alpha}$ is connected.

Let $p \in \bigcap _{\alpha}B_{\alpha}$
Suppose $\bigcup _{\alpha}B_{\alpha}=U\sqcup V$ with $U,V$ open
Then $p \in U$ or $p \in V$. Assume wlog. that $p \in U$
For each $\alpha$, $B_{\alpha}\subseteq \bigcup _{\alpha}=U\sqcup V$ $\implies B_{\alpha}\subseteq U$ or $B_{\alpha}\subseteq V$ 
Since $p \in B_{\alpha}$ and $p \in U$ $\implies B_{\alpha}\subseteq U$
$\implies$ $\bigcup _{\alpha}B_{\alpha}\subseteq U$ $\implies V=\varnothing$ 
Contradiction
## Properties: real number

> [!NOTE]
> The connected subsets of $\mathbb{R}$ are $\varnothing$,points, and intervals ($J\subseteq \mathbb{R}$ interval $\Longleftrightarrow$ $a,b\in J$ and $a<c<b\implies c\in J$)

## Intermediate value Theorem

> [!NOTE]
> Let $X$ be a connected space and $f:X\to \mathbb{R}$ continuous.
> If $p,q\in X$, then $f$ attains every value between $f(p)$ and $f(q)$


**Proof**:
$X$ connected $\implies$ $f(X)\subseteq \mathbb{R}$ connected $\implies f(X)$ is a singleton or an interval([[#Properties real number]])
Let $p,q\in X$
- If $f(p)=f(q)$, then no points are in between.
- If $f(p)< f(q)$, then $f(p),f(q)\in f(X)$ ($f(X)$ is an interval)
	- $\implies$ $\forall{c}\; f(p)<c<f(q):c\in f(X)$
	- $\implies \exists z\in X:f(z)=c$