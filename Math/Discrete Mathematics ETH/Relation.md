---
tags:
  - linker-exclude
---
#eth 

> [!NOTE]
> A relation is a special [[Set|set]]

## Inverse of Relation
> [!PDF|note] [[Discrete Mathematics ETH.pdf#page=63&selection=188,0,218,9&color=note|Discrete Mathematics ETH, p.53]]
> >  The inverse of a relation $ρ$ from $A$ to $B$ is the relation $\rho$ from $B$ to $A$ defined by
$$
\hat{\rho}\overset{ def }{ = }\{ (b,a)|(a,b)\in \rho \}
$$


## Eigenschaften von Relation
Eigenschaften von Relation $\rho$ auf $A$:
- reflexiv: $\forall a(a\;\rho\; a)$
- symmetrisch: $\forall a,b\;(a\; \rho \; b\leftrightarrow b\; \rho \; a)$
- antisymmetrisch: $\forall a,b\; (a\; \rho\; b\wedge b\; \rho \; a\to a=b)$
- transitiv: $\forall a,b,c\; (a\; \rho \; b\wedge b\; \rho \;c \to a\; \rho \; c)$

## Transitive Closure
$$
\rho ^{*}\overset{ def }{ = }\bigcup P_{\rho} \text{ with }P_{\rho}=\{ \rho,\rho^{2},\rho^{3},\dots \}
$$

# Equivalence Relations
> [!Note] [[Discrete Mathematics ETH.pdf#page=67&selection=254,0,263,26&color=note|Discrete Mathematics ETH, p.57]]
> > An equivalence relation is a relation on a set A that is **reflexive**, **symmetric**, and **transitive**.

### Example
$\equiv _{m}$ is an equivalence relation on $\mathbb{Z}$
$\equiv_{3}$

![[equivalence relation example.excalidraw|273]]
## Equivalence class

 
$$
[a]_{\theta}\overset{ def }{ = }\{ b\in A|b\; \theta \;a \}
$$
each group of elements circled in red is a equivalence class
![[equivalence relation example.excalidraw|185]]
### Example 
The equivalence classes of $\equiv_{3}$
![[Pasted image 20251015145055.png|286]]
## Partition via equivalence relations


$A/\theta\overset{ def }{ = }\{ [a]_{\theta}\;|\; a\in A \}$
The **quotient set** of $A$ by $\theta$, or simply A modulo $\theta$ or $A$ mod $\theta$

This concept is similar to factor group and factor rings
- [[Section 14 Factor Groups]]
- [[Section 26 Homomorphisms and Factor Rings]]

| Context | Relation type                                                        | Quotient object        | Categorical role                   |
| ------- | -------------------------------------------------------------------- | ---------------------- | ---------------------------------- |
| Set     | Equivalence relation                                                 | Partition ( $S/\sim$ ) | [[Coequalizer]] in $\mathbf{Set}$  |
| Group   | Normal subgroup ( $N$ )<br>$a\sim b\Longleftrightarrow a^{-1}b\in N$ | Factor group ( $G/N$ ) | [[Coequalizer]] in $\mathbf{Grp}$  |
| Ring    | Ideal ( $I$ )<br>$a\sim b\Longleftrightarrow a-b\in I$               | Factor ring ( $R/I$ )  | [[Coequalizer]] in $\mathbf{Ring}$ |
|         |                                                                      |                        |                                    |

### Example
Consider $A=\mathbb{Z}\times (\mathbb{Z}\setminus \{ 0 \})$ and define $\sim$ as $(a,b)\sim(c,d)\overset{ def }{ \Longleftrightarrow }ad=bc$
$\sim$ is an equivalence relation
- reflexive: $(a,b)\sim(a,b)\Longleftrightarrow ab=ba\Longleftrightarrow ab=ab$ 
- symmetric: $(a,b)\sim(c,d)\Longleftrightarrow ad=bc\Longleftrightarrow bc=ad\Longleftrightarrow cb=da\Longleftrightarrow(c,d)\sim(a,b)$
- transitive: $(a,b)\sim(c,d),(c,d)\sim(e,f)\implies ad=bc\text{ and } cf=de$
	- If $c=0$
		- then $a=0$ and $e=0$ $\implies af=be\Longleftrightarrow(a,b)\sim(e,f)$ 
	- If $c\neq 0$
		- then $adcf=bcde\implies adf=dbe\implies af=be\Longleftrightarrow(a,b)\sim(e,f)$

And now we can define the set of rational numbers
### Definition of the rational numbers
$$
\mathbb{Q}\overset{ def }{ = }(\mathbb{Z}\times(\mathbb{Z}\setminus \{ 0 \}))/\sim
$$
## Intersection of equivalence relations

> [!PDF|note] [[Discrete Mathematics ETH.pdf#page=68&selection=237,0,238,21&color=note|Discrete Mathematics ETH, p.58]]
> > The intersection of two equivalence relations (on the same set) is an equivalence relation.

### Example
$\equiv_{3}\cap\equiv_{5}\;= \;\equiv _{15}$


