---
tags:
  - linker-exclude
---
## Definitions
- $A\preccurlyeq B$, if [[Set#Injective|injective]] function $f:A\to B$ exists
	- reflexive, transitive, **not** antisymmetric (so not a partial order relation)
	- $A\subseteq B\implies A\preccurlyeq B$
- $A\sim B$, if [[Set#Bijective (undoable)|bijective]] function $f:A\to B$ exists
	- equivalence relation
	- $A\preccurlyeq B\wedge B\preccurlyeq A\implies A\sim B$
- $|A|=n$ if $A\sim n$ (n is a natural number defined using a set)
- $A$ countable, if $A\preccurlyeq \mathbb{N}$
	- or if $A\sim \mathbb{N}$ or $A\sim n$ for a $n\in \mathbb{N}$ (See [[#Theorem 3.17 Countability]])

### Example
$|\{ 1,2,5 \}|=3$
- The number of elements
$\mathbb{Z}\sim \mathbb{N}$
- $f:\mathbb{N}\to \mathbb{Z}$ with $f(n)=(-1)^{n}\left\lceil \frac{n}{2} \right\rceil$ a bijective function
Interval $(0,1)\sim \mathbb{R}$ 
- $f:\mathbb{R}\to(0,1)$ with $f(x)=\frac{1}{e^{x}+1}$

## Theorem 3.17 Countability

> [!NOTE]
> A set $A$ is countable ($A\preccurlyeq B$) if and only if it is finite or if $A\sim N$

**Proof**:
The important step is to show if $A$ is infinite $A\preccurlyeq B$ then $A\sim N$: 

If $A\preccurlyeq \mathbb{N}$, then according to the [[#Definitions|definitions]], a injective function $f:A\to \mathbb{N}$ exists. Let $C\subseteq \mathbb{N}$ be the image of $f$ (also infinite), meaning $f:A\to C$ is bijective.
According to the *well-ordering principle* of $\mathbb{N}$, every subset of $\mathbb{N}$ has a least element.
So we define a function $g:C\to \mathbb{N}$ with
$g(c_{0})=0$
$g(c_{1})=1$
$\vdots$
> [!NOTE] definitions of $c_{0},c_{1},\dots$
> $c_{0}$ is the least element in $C$
> $c_{1}$ is the least element in $C_{1}$ with $C_{1}=C\setminus \{ c_{0} \}$
> $\vdots$

And this process can be continued, and shows $g:C\to \mathbb{N}$ is bijective. 
Using [[Function#Transitivity of injectivity and surjectivity]] we know $g\circ f$ is a bijection $A\to \mathbb{N}$, which proves $A\sim \mathbb{N}$

### A shorter proof (Overkill)
using [[Axiom of Choice]] (well-ordering principle), which assumes $A$ has a least element. Therefore, we can skip the construction of $C$ an show directly $A\sim \mathbb{N}$

# Important Examples
### Example 1
![[Set#Alphabet]]

$\{ 0,1 \}^{*}\sim \mathbb{N}$
**Proof**:
Define $f:\{ 0,1 \}^{*}\to \mathbb{N}$ with $f(x)=\text{toRationalNumber}(\text{"1"}+x)-1$


### Example 2
$\mathbb{N}\times \mathbb{N}\sim \mathbb{N}$

### Example 3
$A$ countable $\implies$ $A^{*}$ countable
Encode the finite sequence $(a_{1},\dots ,a_{n})$ with an unique bit string
and let it be $f:A\to \{ 0,1 \}^{*}$ showing $A\sim \{ 0,1 \}^{*}$
...

### Example 4
$\{ 0,1 \}^{\infty}$ (the set of semi-infinite binary sequences) is uncountable
$\{ 0,1 \}^{\infty}\sim \mathbb{R}$
or denoted as $\{ 0,1 \}^{\mathbb{N}}$ (see [[Function#Notation of the set of all functions]])
The set of all functions from $\mathbb{N}$ to $\{ 0,1 \}$ is uncountable
## Bemerkung 1

The set of all programs $\sim \mathbb{N}$, 
jedes Program

Es existiert Funktionen, die von keinem Programm berechnet werden.

## Bemerkung 2
$\mathbb{N}\prec \mathcal P(\mathbb{N})\prec \mathcal P(\mathcal P(\mathbb{N}))$

## Continuum hypothesis

> [!NOTE]
> There is no set whose cardinality is strictly between that of the integers and the real numbers.

Cannot be proven under ZFC.