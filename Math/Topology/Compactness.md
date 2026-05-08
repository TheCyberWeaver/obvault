## Definition: open covers
An **open cover** of a space $X$ is a collection $U$ of open subsets of $X$ whose union is $X$.
A subcover is a subcollection of elements of an open cover $U$ that still covers $X$.


## Definition: compact
A space $X$ is **compact** if every open cover of $X$ has a finite subcover
And a subset $A\subseteq X$ is compact if it is compact as a subspace

A subset of an euclidean space is compact if and only if it is bounded and closed

## Example
 - Every finite space is compact. (since it only has finitely many open sets )
 - Every space with the trivial topology is compact ([[Topology#Simple Examples]])
- A subset of a discrete space is compact $\Longleftrightarrow$ it is finite ([[Topology#Simple Examples]])
	- Suppose $A\subseteq X$ discrete ($\lvert A \rvert=\infty$), then we can find $U:=\{ \{ a \} \}_{a\in A}$ as the union of all singletons in the discrete subset, and we cannot find a finite subcover of $U$ (removing any singleton of $U$ breaks the "coverness")

## Lemma

> [!NOTE]
> A subset $A\subseteq X$ is compact if and only if every collection $\{ U_{\alpha} \}_{\alpha}$ of open subsets of $X$ with $\bigcup _{\alpha}U_{\alpha}\supseteq A$ has a finite subcollection $\{ U_{\alpha _{k}} \}^{n}_{k=1}$ satisfying $\bigcup ^{n}_{k=1}U_{\alpha _{k}}\supseteq A$

This is basically saying the same thing as the definition.
- "every collection $\{ U_{\alpha} \}_{\alpha}$ of open subsets of $X$ with $\bigcup _{\alpha}U_{\alpha}\supseteq A$ " means **every open cover of the subspace $A$**.
- "has a finite subcollection $\{ U_{\alpha _{k}} \}^{n}_{k=1}$ satisfying $\bigcup ^{n}_{k=1}U_{\alpha _{k}}\supseteq A$" means **has a finite subcover that still covers $A$**.


> [!NOTE]
> let $(x_{i})$ be a sequence in a space $X$ that converge to a [[Convergence#Definition Limit points|limit point]] $y$, then the subspace $A=\{ x_{i}:i \in \mathbb{N} \}\cup \{ y \}$ is compact

