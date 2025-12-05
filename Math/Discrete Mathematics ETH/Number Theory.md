## Theorem Euclid

> [!NOTE]
> For all integers $a$ and $d\neq0$ there exist  unique integers $q$ and $r$ satisfying 
> $$
> a=dq+r \text{ and } 0\leq r<|d|
> $$
- $a$ is the dividend
- $d$ is the divisor
- $q$ is the quotient
- $r$ is the remainder

$r$ or the remainder is denoted as $R_{d}(a)$

For $a,b$ with $a\neq0$ or $b\neq0$ is a g.g.T. an element $d$ with $(d|a)\wedge(d|b)\wedge(\forall c\; (c|a)\wedge(c|b)\to(c|d))$  
$gcd(a,b)$ is the unique positive g.g.T. from $a$ and $b$

> [!NOTE]
> $gcd(m,R_{m}(n))=gcd(m,,n)$

# Ideal
### Definition
$(a,d)\overset{ def }{ = }\{ ua+vb\;|\; u,v\in \mathbb{Z} \}$
$(a)\overset{ def }{ = }\{ ua\; |\; u\in \mathbb{Z} \}$
## Lemma 4.3

For $a,b\in \mathbb{Z}$ , $a$ and $b$ are not both 0, then $(a,b)=(gcd(a,b))$
**Proof**:
$(a,b)\subseteq(d)$
![[Ideal-generator.excalidraw]]
Sei $a,b$ so, dass $a\neq0$ oder $b\neq0$, und $d\in(a,b)$ das kleinste positive Element in $(a,b)$. Dann $d=u^{*}a+v^{*}b$
$d|a$ und $d|b$ (wenn z. B. )
- for all $c$ with $c|a$ and $c|b$

$(d)\subseteq(a,b)$
- [ ] finish the proof
## Corollary 4.5
> [!NOTE]
> For $a,b\in \mathbb{Z}$, there exist  $u,v\in \mathbb{Z}$ such that 
> $gcd(a,b)=ua+vb$

## Theorem 4.6 prime factorization
> [!PDF|note] [[Discrete Mathematics ETH.pdf#page=90&selection=31,0,33,2&color=note|Discrete Mathematics ETH, p.80]]
> > Every positive integer can be written uniquely (up to the order in which factors are listed) as the product of primes.

## Example 
$x^{3}+x^{2}=y^{4}+y+1$
left side is always even, right is always odd
The equation hat no solution in $\mathbb{Z}$
$x^{3}-x=y^{2}+1$
left side divisible by 3, the right side cannot be divisible by 3


## Modular Arithmetic
$a\equiv _{m}b\overset{ def }{ \Longleftrightarrow } m|(a-b)$ 
- $a=b\implies a\equiv _{m}b$
- $\Longleftrightarrow R_{m}(a)=R_{m}(b)$


Define $\mathbb{Z}_{m}=\{ 0,\dots,m-1 \}$

### Example
$2^{20}\equiv _{15}(2^{4})^{5}\equiv _{15}1^{5}\equiv _{15}1$

## Multiplicative Inverses
$ax\equiv _{m}1$
The equation has a solution $x \in \mathbb{Z}_{m}$ if and only if $\text{gcd}(a,m)=1$. The solution is unique

This unique solution $x \in \mathbb{Z}_{m}$ is called the multiplicative inverse of $a$ modulo $m$
### Example
$5^{-1}\equiv _{13}8$
because $5\cdot8\equiv _{13}1$
## CRT
![[Chinese Remainder Theorem (CRT)]]
