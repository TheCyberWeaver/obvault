#eth
- Korrektheit (Beweis)
- Laufzeit, hängt ab von 
	- Eingabegröße
	- Computer
	- Implementierung
1. Unit-time random access machine model
2. Asymptotische Notation
# RAM model
![[Unit-cost model.excalidraw|533]]
> [!NOTE]
> Elementare Operationen:
> - lesen/schreiben einer Zahl
> - Arithmetik: +,-,\*,/
> - Vergleiche: $<$,$=$,$\geq$

Laufzeit in RAM Modell= Anzahl elementarer Operationen $\leftrightarrow^?$ Laufzeit in Praxis
Unterschied ist ein ==konstanter Faktor==


# Asymptotische Notation

## Definition

> [!NOTE]
> $N=\{n_{0},n_{0}+1,\dots\}$=Menge möglicher Eingabegröße
> Für $f:N\to \mathbb{R}^+$
> $O(f)=\{g:N\to \mathbb{R}^+|\text{ es gibt } C>0\text{ so dass }g(n)\leq C\cdot f(n)\text{ for all }n\in N\}$ 
> 
> $O(f)$ : Ordnung von f
> $g\in O(f)\leftrightarrow \frac{g(n)}{f(n)}\leq C$ (man kann auch sagen es ist beschränkt)

## Beispiel 1
$f(n)=n^{2}$,$g(n)=4n^{2}$
$f\in O(g)$
	$n^{2}\leq 4n^{2}$  with $C=1$
$g\in O(f)$
	$4n^{2}\leq 4n^{2}$  with $C=4$

**allgemeine**: $a\in \mathbb{R}^+$ konstante 
$$
O(f(n))=O(n\cdot f(n))
$$
## Beispiel 2
$f(n)=100n$, $g(n)=n^{2}$
$f\in O(g):100n\leq100n^{2}$ with $C=100, n\geq 1$

> [!NOTE]
> $O(n^{2})$=Menge aller Funktionen die höchstens quadratisch wachsen
# Nützlicher Werkzeug
- $\lim_{ n \to \infty } \frac{g(n)}{f(n)}=\infty \implies g\not\leq O(f)$
- $\lim_{ n \to \infty }\in \mathbb{R}^+_ \implies g\in O(f)$
## Beispiel 1
$f(n)=n^{1.6}+3n+4\in O(n^{1.6})$
	$\frac{f(n)}{g(n)}=1+3n^{-0.6}+4n^{-1.6}<1+3+4=8$
## Beispiel 2
Sei$a>0$
$f(n)=\ln n\in O(n^a)$
$\lim_{ n \to \infty }\frac{\ln n}{n^a}=\lim_{ n \to \infty }\frac{\frac{1}{n}}{an^{a-1}}=\lim_{ n \to \infty }\frac{1}{an^a}=0$

