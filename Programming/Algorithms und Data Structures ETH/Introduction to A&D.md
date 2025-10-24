#eth
# Karatsuba multiplication
![[Karatsuba Multiplikation.excalidraw]]
$$10^n ac+10^{n/2}(ad+bc)+bd$$


> [!NOTE]
> ONLY 3 multiplications needed
> the normal method is to calculate $(10^{n/2}a+b)(10^{n/2}c+d)$ and need 4 multiplications

This is called **Divide and conquer**

## Time Complexity Analysis
$M(n)$: The number of digit multiplications needed to calculate the multiplication of two numbers which have n digits respectively.
- $M(2^0)=1$
- $M(2^k)=3\cdot{} M(2^{k-1})$  //Rekurrenz
- $M(2^k)=3^k$ // kein Beweis, für Beweis braucht man [[Induction]]

$n=2^k\Longrightarrow k=\log_{2}n \Longrightarrow 3^k=3^{\log_{2}n} = n^{\log_{2}3}=n^{1.58}$

# one dimensional goal finding

![[Goal finding on a line.excalidraw|695]]
## Time Complexity Analysis (worst case)
k=distance between start and end
Annahme: $2^{i-1}<k<2^{i}$
- $2\cdot 1+2\cdot 2^1 +2 \cdot 2^2+\dots+2^i+k$
- $=2(2^{i+1}-1)+k$ 
- $2^{i+1}=4\cdot 2^{i-1}<4k$
- $\Longrightarrow 2(2^{i+1}-1)+k <9k$

# Definition des Algorithmus 

> [!NOTE]
> Beschreibung einer Abfolge von elementaren Operationen zur Lösung eines Problems

A typical computer: $10^9$ Ops/sec

# What to learn in A&D
- Entwurf und Analyse von Algorithmen
- algorithmische Denkweise
- wichtige Algorithmen kennenlernen

