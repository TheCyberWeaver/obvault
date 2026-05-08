 
> [!Important]
> If the interpretation is clear, then a PL formula can be interpreted as a statement.
# Proofs for implications $S\implies T$
## Direct proof (of $S\implies T$)
- assume $S$ is true and prove $T$ under this assumption.
- **simple example**: if $a,b$ are perfect squares, then $a\cdot b$ is a perfect square
	- There exist $u,v$ with $a=u^{2}$ and $b=v^{2}$ (assumption $S$)
	- $\implies ab=(u\cdot u)(v\cdot v)$
	- $\implies ab=u\cdot (u\cdot v)\cdot v$ 
	- $\implies ab=u\cdot(v\cdot u)\cdot v$
	- $\overset{ \cdot }{ \implies } ab=(uv)(uv)$ (associativity of $\cdot$)
	- $\implies$ there exists $w$ with $ab=w\cdot w$ 
	- $\implies$ $a\cdot b$ is a perfect square
## Indirect proof (of $S\implies T$)
- assume $T$ is false, show that $S$ is false
- Reason: $\neg G\to \neg F\models F\to G$ 
- Example: The square root of an irrational number $x>0$ is irrational
	- $S$: $x>0$ irrational
	- $T$: $\sqrt{ x }$ irrational
	- $\sqrt{ x }$ rational ($\neg T$) $\overset{ \cdot }{ \implies }$ there exist $m,n\in \mathbb{Z}$ with $\sqrt{ x }=\frac{m}{n}$
	- $\overset{ \cdot }{ \implies }x= \frac{m^{2}}{n^{2}}$ rational ($\neg S$)
## by transitivity
- Definition: [[Predicate Logic#Allgemein]]
- Example: [[Linear Independence#Equivalent Statements to linear dependence]]
- Reason: $(F\to G)\wedge(G\to H)\models F\to H$
- Variant: find $R_{1},R_{2}$ with $S\implies R_{1}$ and $S\implies R_{2}$ and $R_{1}\text{ and }R_{2}\implies T$
# Proofs for general statements S
## Modus Ponens
![[Propositional Logic#Modus Ponens]]
## Case distinction 
(generalization of Modus Ponens)
- find $R_{1},R_{2},\dots,R_{n}$, prove that $R_{1}$ or $R_{2}$,..., or $R_{n}$ holds, prove that for all $i$, $R_{i}\implies S$
## Proof by contradiction
- find $T$, prove that $T$ is false, prove that $S$ is false $\implies$ $T$ true
- Reason: $(\neg F\to G)\wedge \neg G\models F$
- Example: $\sqrt{ 2 }$ irrational
	- $\sqrt{ 2 } \text{ rational}\implies \sqrt{ 2 }=\frac{m}{n}, gcd(m,n)=1$
	- $\implies 2= \frac{m^{2}}{n^{2}}\implies m^{2}=2n^{2}\implies 2|m^{2}\implies 2|m$
	- $\implies 4|m^{2}\implies 4|2n^{2}\implies 2|n^{2}\implies 2|n$
	- $\implies gcd(m,n)\geq 2$
	- false

## Pigeonhole principle 
![[Pasted image 20251006175542.jpg]]
just write "Pigeonhole principle" to prevent complicated explanations 
# Proofs for statements of the form $\forall n P(n)$ (universe $U=\mathbb{N}$)
1. prove $P(0)$ true
2. prove for all n that $P(n) \text{ true}\implies P(n+1)\text{ true}$
Reason: For $U=\mathbb{N}$ and any predicate $P$, the following holds
$P(0)\wedge \forall n\:(P(n)\to P(n+1))\models\forall n\: P(n)$