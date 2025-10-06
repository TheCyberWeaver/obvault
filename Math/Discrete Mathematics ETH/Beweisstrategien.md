
> [!Important]
> Wenn Interpretation klar, dann kann PL-Formel als Aussage interpretiert werden
# Beweise für Implikationen $S\implies T$
## Direkter Beweis (von $S\implies T$)
- nimm $S$ als wahr und beweise $T$ unter dieser Annahme.
- **einfaches Beispiel**: wenn $a,b$ Quadratzahl sind, dann ist $a\cdot b$ Quadratzahl
	- Es existiert $u,v$ mit $a=u^{2}$ und $b=v^{2}$ (Annahme $S$)
	- $\implies ab=(u\cdot u)(v\cdot v)$
	- $\implies ab=u\cdot (u\cdot v)\cdot v$ 
	- $\implies ab=u\cdot(v\cdot u)\cdot v$
	- $\overset{ \cdot }{ \implies } ab=(uv)(uv)$ (Assoziativität $\cdot$)
	- $\implies$ es existiert $w$ mit $ab=w\cdot w$ 
	- $\implies$ $a\cdot b$ ist eine Quadratzahl
## Indirekter Beweis (von $S\implies T$)
- nimm $T$ als falsch an, zeige, dass  falsch ist
- Begründung: $\neg G\to \neg F\models F\to G$ 
- Beispiel: Die Wurzel einer irrationalen Zahl $x>0$ ist irrational
	- $S$: $x>0$ irrational
	- $T$: $\sqrt{ x }$ irrational
	- $\sqrt{ x }$ rational ($\neg T$) $\overset{ \cdot }{ \implies }$ es existiert $m,n\in \mathbb{Z}$ mit $\sqrt{ x }=\frac{m}{n}$
	- $\overset{ \cdot }{ \implies }x= \frac{m^{2}}{n^{2}}$ rational ($\neg S$)
## durch Transitivität
- Definition: [[Prädikatenlogik#Beispiel#Allgemein]]
- Beispiel: [[Linear Independence#Equivalent Statements to linear dependence]]
- Begründung: $(F\to G)\wedge(G\to H)\models F\to H$
- Variante: finde $R_{1},R_{2}$ mit $S\implies R_{1}$ und $S\implies R_{2}$ und $R_{1}\text{ und }R_{2}\implies T$
# Beweise für allgemeine Aussagen S
## Modus Ponens
![[Aussagenlogik#Modus Ponens]]
## Fallunterscheidung 
(Verallgemeinerung von Modus Ponens)
- finde $R_{1},R_{2},\dots,R_{n}$, beweise, dass $R_{1}$ oder $R_{2}$,..., oder $R_{n}$ gilt, beweise, dass für alle $i$ gilt $R_{i}\implies S$
## Beweise durch Widerspruch
- finde $T$, beweise, dass $T$ falsch, beweise dass $S$ falsch $\implies$ $T$ wahr
- Begründung: $(\neg F\to G)\wedge \neg G\models F$
- Beispiel: $\sqrt{ 2 }$ irrational
	- $\sqrt{ 2 } \text{ rational}\implies \sqrt{ 2 }=\frac{m}{n}, gcd(m,n)=1$
	- $\implies 2= \frac{m^{2}}{n^{2}}\implies m^{2}=2n^{2}\implies 2|m^{2}\implies 2|m$
	- $\implies 4|m^{2}\implies 4|2n^{2}\implies 2|n^{2}\implies 2|n$
	- $\implies gcd(m,n)\geq 2$
	- falsch

# Beweise für Aussagen der Form $\forall n P(n)$ (Universum $U=\mathbb{N}$)
1. beweise $P(0)$ wahr
2. beweise für alle n, dass $P(n) \text{ wahr}\implies P(n+1)\text{ wahr}$
Begründung: Für $U=\mathbb{N}$ und beliebige Prädikat $P$ gilt
$P(0)\wedge \forall n\:(P(n)\to P(n+1))\models\forall n\: P(n)$
