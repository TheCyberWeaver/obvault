---
tags:
  - linker-exclude
---
## Definition

Relation $f\subseteq A\times B$ is a function $f:A\to B$ if:
- $\forall a\in A\; \exists b\in B\quad (a\; f\; b)$ (without this condition, $f$ is a **partial function**)
- $\forall a\in A\quad\; \forall b,b'\in B \;(a\; f\; b\wedge a \; f \; b'\to b=b')$ (assure **right-uniqueness**)
	- one input maps to at most one output.

$f(A)=\{ f(a)|a\in A \}$

> [!NOTE]
> A function is a special [[Relation|relation]]

$B^{A}$ is the set of all functions $f:A\to B$

## Transitivity of injectivity and surjectivity

$f,g$ injective/surjective $\implies$ $g\circ f$ injective/surjective 
Proof for injectivity
$a\neq a'\implies f(a)\neq f(a')$
$\implies g(f(a))\neq g(f(a'))$
$\implies(g\circ f)(a)\neq(g\circ f)(a')$


