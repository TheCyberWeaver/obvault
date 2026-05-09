---
tags:
  - linker-exclude
---
 
### Naive Verständnis
- The empty set: $\varnothing$ or $\{\}$
- $A=\{ 1,1 \}=\{ 1 \}$
- $A=\{ x \in \mathbb{R}|x\geq2 \}$
- $A=\{ M \;\text{Menge} | \;|M|\geq3\}$
	- $A\in A$
	- formal ist das kein problem
**However:**
> [!Question]
> $A=\{ M \text{ Menge}|M \not\in M \}$
> $A\in A$?
> A Paradox:
> - $A\in A\implies A\not\in A$
> - $A\not\in A\implies A\in A$

**Solution:**
Existenz und Konstruktion von Mengen reglementieren
# Definition of Set
Neuanfang mit Universum:

> [!definition]
> gleiche enthaltene Elemente ($\forall x((x \in A)\leftrightarrow(x \in B))$)
> $\implies$ gleiche Mengen ($A=B$)
> **Axiom**:
> Menge, die nur aus eine Element $x$ besteht, existiert $\forall y((x \in A)\leftrightarrow(x=y))$
> **Schreibweise**
> $\{ x \}$ analog für $\{ x_{1},x_{2},\dots,x_{n} \}$


> [!PDF|note] Lemma 3.1 [[Discrete Mathematics ETH.pdf#page=54&selection=161,0,188,1&color=note|Discrete Mathematics ETH, p.44]]
> > For any (sets) a and b, $\{a\} = \{b\}\implies a = b$.

**Proof**:
$\neg(a=b)\implies \neg(\{ a \}\neq \{ b \})$

> [!NOTE]
> Schreibe $A\subseteq B$, falls $\forall x((x \in A)\to(x \in B))$ wahr


> [!PDF|note] Lemma 3.2 [[Discrete Mathematics ETH.pdf#page=55&selection=283,0,307,1&color=note|Discrete Mathematics ETH, p.45]]
> > $A=B\Longleftrightarrow(A\subseteq B)\wedge(B\subseteq A)$
>

**Proof**:
$(A\subseteq B)\wedge(B\subseteq A)\overset{ \cdot }{ \implies }(\forall x((x \in A)\to(x \in B)))\wedge(\forall x((x \in B)\to(x \in A)))$ Definition $\subseteq$
 $\overset{ \cdot }{ \implies }\forall x(x \in A\leftrightarrow x \in B)$ [[Propositional Logic]]
$\overset{ \cdot }{ \implies } A=B$ Definition $=$


# Empty set

Leere Menge $\varnothing$ ist Menge mit $\forall x(x\not\in \varnothing)$ wahr

> [!Important]
> $\varnothing$ ist eindeutig bestimmt
> $\forall A(\varnothing\subseteq A)$

> [!Warning]
> This does not mean $\forall A \;(\varnothing\in A)$

### Example
- $A=\{ \{ \varnothing \} \}$
- $B=\{ \{ \varnothing \},\{ \varnothing,\varnothing \} \}$
- $C=\{ \varnothing,\{ \varnothing \} \}$
- $D=\{ \varnothing,\{ \varnothing,\{ \varnothing \} \} \}$

Observations:
$A=B$
$C\in D$
$A\subseteq C$

> [!definition] Tuple
> $(a,b)\overset{ def }{ = }\{ a,\{ a,b \} \}$

> [!PDF|note] [[Discrete Mathematics ETH.pdf#page=57&selection=184,0,184,11&color=note|Discrete Mathematics ETH, p.47]]
> > Theorem 3.4
> 
> ![[Pasted image 20251008145442.png]]

# Alphabet 

> [!NOTE]
> set of all finite binary strings
> $\{ 0,1 \}^{*}\overset{ def }{ = }\{ \varepsilon,0,1,00,01,10,11,000,\dots \}$ 
$|x|\overset{ def }{ = }$ length of $x$


# Power Set
$$
\mathcal P(A)\overset{ def }{ = }\{ S|S\subseteq A \}
$$
**Example**: $\mathcal{P}(\{ a,b \})=\{ \varnothing,\{ a \},\{ b \},\{ a,b \} \}$
For a finite set with cardinality $k$, the power set has cardinality $2^{k}$


# Cartesian Product

> [!definition]
> The Cartesian product $A \times B$ of two sets $A$ and $B$ is the set of all ordered pairs with the first component from $A$ and the second component from $B$
> $A\times B=\{ (a,b)|a\in A\wedge b\in B \}$

**Example**:
- $\varnothing\times A=\varnothing$
- $A\times B=B\times A$
$$
\bigtimes^{k}_{i=1}A_{i}=\{ (a_{1},\dots,a_{k})|\; a _{i}\in A_{i}\;\text{for } 1\leq i\leq k \}
$$

# Relations types
![[Pasted image 20251020154640.png]]
## Injective
> [!PDF|note] [[Linear Algebra ETH.pdf#page=87&selection=56,2,56,58&color=note|Linear Algebra ETH, p.86]]
> > For every possible output, at most one input leads to it

$$
\forall a,a'((f(a)=f(a'))\to(a=a')) 
$$
## Surjective
> [!PDF|note] [[Linear Algebra ETH.pdf#page=87&selection=91,2,91,59&color=note|Linear Algebra ETH, p.86]]
> > For every possible output, at least one input leads to it

$$
\forall b\in B\; \exists a\in A(f(a)=b)
$$

## Bijective (undoable)
> [!PDF|note] [[Linear Algebra ETH.pdf#page=87&selection=105,2,105,58&color=note|Linear Algebra ETH, p.86]]
> > For every possible output, exactly one input leads to it (There always exists an inverse)
> 
> = Injective + Surjective
$$
f\circ f^{-1}=\text{id}
$$


