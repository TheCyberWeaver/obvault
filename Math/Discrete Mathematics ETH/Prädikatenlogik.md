#eth 
# Bausteine
- Universum $U$ : $U=\mathbb R, U=\{0,1\}…$
- Konstanten aus $U$ : $0,1,\pi…$
- Prädikate $P$,$Q$ : $prime(x), less(x)…$
- Funktionen: $f,g$ : $square(x),add(x)…$
- Operatoren: $\neg,\wedge,\vee,\to, \leftrightarrow$ similar to [[Aussagenlogik]]
- Quantoren: $\forall x$, $\exists x$

## Beispiel
Spezielle Interpretation
$U=\mathbb N$
- $\forall x (0\leq x)$ wahr
- $(\exists x(x\leq 2)) \wedge (\exists x(3\leq x))$ wahr
$prime(x)\overset{ def }{ \Longleftrightarrow }(x>1)\wedge(\forall y\:(y|x)\to(y=1\vee y=x))$
$y|x\overset{ def }{ \Longleftrightarrow }(y> 0)\wedge(\exists k \: (y\cdot k=x))$
### Allgemein
- $\exists x (F\wedge G) \models (\exists x\: F)\wedge(\exists x\: G)$
- $\forall x(F\wedge G)\equiv(\forall x \:F)\wedge(\forall x\:G)$
- $\neg \forall x\:F\equiv \exists x\:\neg F$
- $\neg \exists x\:F\equiv \forall x\:\neg F$
- $\forall x\:\forall y\:\forall z \:((P(x,y)\wedge P(y,z))\to P(x,z))$ ==Transitivität==
- $\forall x\:\forall y(P(x,y)\to P(y,x))$ ==Symmetrie==
- $\forall x(P(x)\to Q(x))\models(\forall x\: P(x))\to(\forall x\:Q(x))$
Was können wir über $\forall x(P(x)\to \neg P(x))$ sagen?



### Beispiel: Verwandtschaftsbeziehung 
$U=$Menschen (idealisiert)
$par(x,y)$
$child(x,y)\overset{ def }{ \Longleftrightarrow } par(y,x)$
$sibl(x,y)\overset{ def }{ \Longleftrightarrow }\exists k(par(k,x)\wedge par(k,y)\wedge x\neq y)$
$grandpar(x,y)\overset{ def }{ \Longleftrightarrow }\exists k\: (child(k,x)\wedge par(k,y))$
$ancestor(x,y)$ ==definition nicht möglich==

### Beispiel: exists only 1 
$$
\exists_{1} x\: F\overset{ def }{ \Longleftrightarrow }\exists \tilde{x}\:\forall x(x=\tilde{x}\leftrightarrow F)
$$




