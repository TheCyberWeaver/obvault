---
tags:
  - linker-exclude
---
## Definition of a Ring

> [!Quote] [[Discrete Mathematics ETH.pdf#page=120&selection=15,0,15,14&color=note|Definition 5.18]]
> A ring $〈R; +, −, 0, ·, 1〉$ is an algebra for which
> (i) $〈R; +, −, 0〉$ is a commutative group. 
> (ii) $〈R; ·, 1〉$ is a [[Introduction to abstract algebra#Monoid|Monoid]]. 
> (iii) $a(b + c) = (ab) + (ac)$ and $(b + c)a = (ba) + (ca)$ for all $a, b, c ∈ R$ (left and right distributive laws).


> [!Quote] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=172&selection=70,0,210,1&color=note|p.167]]
> > A **ring** $\langle \mathbb{R},+,\cdot \rangle$ is a set $R$ together with two binary operations + and ·, which we call addition and multiplication, defined on $R$ such that the following axioms are satisfied: 
> - R1. $\langle \mathbb{R},+,\cdot \rangle$ is an abelian group. 
> - R2. Multiplication is associative. 
> - R3. For all a, b, c ∈ R, the left distributive law, a · (b + c) = (a · b) + (a · c) and the right distributive law (a + b) · c = (a · c) + (b · c) hold. 

> [!NOTE]
> A ring is called **commutative** if multiplication is commutative (ab = ba)

### Examples of Rings
#### 1) complex numbers
$R'= \langle R\times R;+,-,(0,0),*,(1,0) \rangle$
- $(a,b)+(c,d)\overset{ def }{ = }(a+c,b+d)$
- $(a,b)*(c,d)\overset{ def }{ = }(ac-bd,ad+bc)$

If $R=\mathbb{R}$ then $R'$ is actually $\mathbb{C}$
#### 2) polynomial ring
$R''= \langle R^{*} ; +,-,\varepsilon,*,(1)\rangle$ (Note that $R^{*}$ means here the finite sequence of $R$)
- $(f_{0},\dots,f_{n})+(g_{0},\dots,g_{m})\overset{ def }{ = }(f_{0}+g_{0},f_{1}+g_{1},\dots,f_{n}+g_{n},g_{n+1},\dots,g_{m})$ $(n\leq m)$ (extend the shorter tuple by zeros)
- $(f_{0},\dots,f_{n})*(g_{0},\dots,g_{m})\overset{ def }{ = }(f_{0}g_{0},f_{1}g_{0}+f_{0}g_{1},f_{2}g_{0}+f_{1}g_{1}+f_{0}g_{2},\dots)$

This is the polynomial ring in one indeterminate over $R$: $R''\simeq R[x]$
$(1)$ is the constant polynomial $1$


## Lemma 5.17: Properties of a ring
> [!Quote] [[Discrete Mathematics ETH.pdf#page=120&selection=191,0,191,10&color=note|Lemma 5.17]]
> i) $0\cdot a=a\cdot0=0$
> ii) $(-a)b=-(ab)=a(-b)$
> iii) $(-a)(-b)=ab$
> iv) $\lvert R \rvert=1\Longleftrightarrow1=0$ (If $R$ is non-trivial, then $1\neq0$)

**Proof** iv)
Prove $\Longleftarrow$: trivial
Prove $\implies$:
Let $1=0$, assume $\lvert R \rvert>1$
$a\in R,a\neq0$
$\implies0=a\cdot0=a\cdot1=a\implies$ Contradiction
$\implies|R|=1$

## Definition: Characteristic of a ring
(DE: Charakteristik)
The **characteristic** of a ring is the **order of $1$** in the additive group if it is finite, and otherwise the characteristic is defined to be $0$
Formally:
$$
min\{ i \in \mathbb{N}|i>0\wedge \underset{ i \;	Mal }{ 1+1+\dots+1 }=0 \}\;	\vee\;	 0
$$
[[Section 19 Integral Domains#19.13 Definition The Characteristic of the ring $R$]]
## Definition: Unit
(DE: Einheit)
An element $u$ of a ring $R$ is called a **unit** if $u$ is invertible
That is $uu^{-1}=u^{-1}u=1$ for some $u^{-1}\in R$
The set of units is denoted by $R^{*}$ (must be a group)
### Example
The units of $\mathbb{Z}$ are $-1$ and $1$, $\mathbb{Z}^{*}=\{ -1,1 \}$

## Lemma 5.18: Multiplicative Group of Units
> [!Quote] [[Discrete Mathematics ETH.pdf#page=121&selection=253,0,253,10&color=note|Lemma 5.18]]
> $\langle R^{*},\cdot,(\cdot)^{-1},1 \rangle$ is a group

## Definition: Zero Divisor
$a\in R\setminus \{ 0 \}$ is zero divisor, if there exists $b\in R\setminus \{ 0 \}$ such that $ab=0$


# Applications
- **Error-Correcting Codes:** Rings are used in the construction of error-correcting codes, which are essential for reliable data transmission and storage.
- **Secret Sharing:** Rings play a role in secret sharing schemes, where a secret is divided into multiple shares distributed among participants, and a certain number of shares are required to reconstruct the secret.
- **Privacy Amplification:** Rings are used in privacy amplification techniques, where a partially secret shared value (e.g., a bitstring) can be transformed into a shorter, more secret value. A public function f compresses the bitstring (e.g., from 1000 bits to 800 bits). The specific choice of f is public knowledge, but the way it is applied depends on an additional secret. The remaining 200 bits could function like this key, akin to a one-time pad.