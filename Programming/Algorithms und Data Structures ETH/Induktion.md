#eth 
# Allgemein

Beweise $A(k)$ für alle $k\in \mathbb{N}$
- Induktionshypothese (IH): $A(k)$
- Induktionsanfang (IA): zeige $A(1)$
- Induktionsschritt (IS): zeige dass $A(k+1)$ gilt, falls $A(k)$ gilt

# Example

> [!NOTE]
> $S_{k}=1+2+2^2+..+2^{k-1}=2^k-1$ for all $k\in \mathbb{N}$

***Proof:***
- Induktionsanfang: $s_{1}=1$
- Induktionsschritt: 
	- $k\to k+1$
	- $S_{k+1}=S_{k}+2^k$
	- $=2^{k-1}+2^k=2^k-1$

# Example: Bernoulli Ungleichung
Für alle $x\geq-1$ und $u\in \mathbb{N}$
$$
(1+x)^n\geq1+nx
$$
**IA**: n=1: $(1+x)\geq 1+x$
**IS**: $n\to n+1$
- $(1+x)^{n+1}=(1+x)^n(1+x)$
- $(1+x)^{n+1}\geq (1+nx)(1+x)$
- $= 1+x(n+1)+nx^2\geq 1+x(n+1)$

# Example: Star Suche
Finde einen Star unter n Personen $p_{1},\dots p_{n}$ 
**Definition**: $p_{s}$ ist ein Star wenn alle $p_{s}$ kennen, und $p_{s}$ niemand kennt
**Operation**: Frage $p_{i}$ über  $p_{j}$ 
## Idee 1
Finde Lösung für $n$ basierend auf einer Lösung von $n-1$ Personen
- Schicke einen raus (z.B. $p_{n}$)
- Finde Star $p_{s}$ unter $p_{1}\dots p_{n-1}$ 
	- Time: $F(n-1)$
- Ist $p_{s}$ auch Star unter $p_{1}\dots p_{n}$
	- Time: $2$
- Ist $p_{n}$ Star unter $p_{1}\dots p_{n}$
	- Time: $2(n-1)$
### Time Complexity Analysis (best case)
- $F(n)=F(n-1)+2$
- $F(2)=2$
$\implies F(n)=2(n-1)$

### Time Complexity Analysis (worst case)
- $F(n)=F(n-1)+2(n-1)$
- $F(n)=n(n-1)=n^{2}-1$ 
## Idee 2
Stelle sicher keinen Star rauszuschicken 
- Neues Schritt 0: Schicke einen aus: $p_{i}\to^? p_{j}$
	ja: $p_{i}$ kein Star
	nein: $p_{j}$ kein Star
	- Time: $1$
- Finde Star $p_{s}$ unter $p_{1}\dots p_{n-1}$ 
	- Time: $F(n-1)$
- Ist $p_{s}$ auch Star unter $p_{1}\dots p_{n}$
	- Time: $2$
### Time Complexity Analysis (worst case)
- $F(n)=F(n-1)+3$
- $F(n)=3n-4$ 
==deutlich besser==

