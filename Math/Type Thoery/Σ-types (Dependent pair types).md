## Definition - "there exists"
A dependent pair type is the “pair” analogue of a dependent function type: the type of pairs where the type of the second component depends on the first component.

Given a type $A:\mathcal{U}$ and a [[Type Family|type family]] $B:A\to \mathcal{U}$
we construct a type of dependent pair: $\sum_{(x:A)}B(x):\mathcal{U}$

A term $p:\sum_{(x:A)}B(x)$ consists of 
-  a first component $a:A$
- a second component $b:B(a)$

so it is a pair $(a,b)$ where the second entry’s type is allowed to depend on the first.

if $B$ is constant then $\sum_{(x:A)}B:\mathcal{U}\simeq A\times B$


## Projections
if $p:\sum_{(x:A)}B(x)$, then
- $\text{pr}_{1}(p):A$
- $\text{pr}_{2}(p):B(\text{pr}_{1}(p))$

## Example
let $A$ be $\mathbb{N}$ and $B(n)$ be the type "vectors of length n", then:
$\sum_{(n:\mathbb{N})}B(n)$ is the type of "a length together with a vector of that length" 
an example term would be $(3,[1,2,3])$

## Example: Magma
We often use dependent pair types to define types of mathematical structures

$$
\text{Magma}:\equiv \sum_{A:\mathcal{U}}(A\to A\to A)
$$
this means the _type of magmas_ is a pair $(A,m)$ where $m$ is a binary operation and has type $A\to A\to A$


## Further example: axiom of choice
![[Pasted image 20260202205945.png]]

> [!Note] read as
> if for all x : A there is a y : B such that R(x, y), then there is a function f : A → B such that for all x : A we have R(x, f (x))
> OR
> $\forall{x}\exists{y}\; P(x,y)\to \exists{f}\forall{x}\; P(x,f(x))$
> >(set theory version: [[Axiom of Choice]])

