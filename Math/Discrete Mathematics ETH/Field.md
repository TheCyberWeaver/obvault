## Definition

> [!Quote] [[Discrete Mathematics ETH.pdf#page=125&selection=199,0,199,14&color=note|Definition 5.26]]
> Commutative [[Ring|ring]] $F$ with $F^{*}=F\setminus \{ 0 \}$ is a field

$\mathbb{Z}_{m}$ is a field $\Longleftrightarrow$ $m$ is prime
$\mathbb{Z}_{m}$ is a field $\implies$ $\mathbb{Z}_{m}$ is a integral domain

![[Section 33 Finite Fields]]

For an irreducible polynomial $m(x)$
$GF(p)[x]_{m(x)}$ is a field. This field is $GF(p^{deg(m)})$
$deg(m)$ is the degree of this polynomial
proof see below

$deg(0)=-\infty$

## Definition: irreducible

> [!Quote] [[Discrete Mathematics ETH.pdf#page=127&selection=396,0,396,14&color=note|Definition 5.28]]
> A polynomial $a(x) ∈ F [x]$ with degree at least $1$ is called irreducible if it is divisible only by constant polynomials and by constant multiples of $a(x)$.

In other words:
$f(x)\in F[x]$ irreducible, if $deg(f(x))\geq1$ and $g(x)|f(x)\to deg(g(x))=0\vee \exists{c\in F^{*}}\; (g(x)=cf(x))$


## Definition: gcd of polynominals

The monic polynomial (leading coefficient is 1) $g(x)$ of largest degree such that $g(x) | a(x)$ and $g(x) | b(x)$ is called the greatest common divisor of $a(x)$ and $b(x)$, denoted $gcd(a(x), b(x))$.
## Theorem 5.25
[[Discrete Mathematics ETH.pdf#page=129&selection=94,0,94,12&color=note|Theorem 5.25]]
![[Pasted image 20251117153850.png]]

## Homomorphismus of rings
![[Section 22 Rings of Polynomials#22.4 The Evaluation Homomorphisms for Field Theory]]


> [!Definition] [[Discrete Mathematics ETH.pdf#page=131&selection=258,0,258,14&color=note|Definition 5.33]]
> $\alpha$ is a root of $a(x)$ $\overset{ def }{ \Longleftrightarrow }$ $a(\alpha)=0$


> [!Quote] [[Discrete Mathematics ETH.pdf#page=131&selection=405,0,405,10&color=note|Lemma 5.29]]
> For a field $F$ , $\alpha \in F$ is a root of $a(x)$ $\Longleftrightarrow$ $(x-\alpha)|a(x)$ 

**Proof**: $\implies$
Let $a(\alpha)=0$ 
then $a(x)=(x-\alpha)q(x)+r(x)$ 
and $deg(r(x))<1$
$a(\alpha)=(\alpha-\alpha)q(\alpha)+r(\alpha)$
$\implies 0=0\cdot q(\alpha)+r\implies r=0$

**Proof**: $\Longleftarrow$
Let $a(x)=(x-\alpha)\cdot b(x)$ 
Evaluation: $a(\alpha)=(\alpha-\alpha)b(\alpha)=0b(\alpha)=0$

## Obeservation
$deg (a(x))=n>-\infty\implies a$ has at most $n$ roots.
### Example
$a(x)=x^{p}-x \in GF(p)[x]$
$\lvert GF(p)^{*} \rvert=p-1$, meaning $\alpha ^{p}=\alpha$ in $GF(p)$ 

Therefore, $x^{p}-x=\prod_{\alpha \in GF(p)}(x-\alpha)=(x-0)(x-1)(x-2)\dots(x-(p-1))$

## Lemma 5.32

> [!Quote] [[Discrete Mathematics ETH.pdf#page=133&selection=4,0,4,10&color=note|Lemma 5.32]]
> A polynomial $a(x) ∈ F [x]$ of degree at most $d$ is uniquely determined by any $d+1$ values of $a(x)$, i.e., by $a(α_{1}), . . . , a(α_{d+1})$ for any distinct $α_{1}, . . . , α_{d+1} ∈ F$ .

> [!NOTE]
> Note that this Theorem does not apply to the example above.
> There are only $p$ elements in $\mathrm{GF}(p)$.  
> If you take $d=p$, then $d+1=p+1$, but you **cannot** find $p+1$ distinct points in $\mathrm{GF}(p)$ (there are only $p$ of them).  
> So the theorem simply does **not apply** to degree $p$ polynomials over $\mathrm{GF}(p)$.

**Proof**
Consider
$$
u_{i}(x)=\frac{\prod_{j\neq i}x-\alpha _{j}}{\prod_{j\neq i}\alpha _{i}-\alpha _{j}}
$$

$u_{i}(\alpha _{j})=0$ if $i\neq j$ and $u_{i}(\alpha _{i})=1$

$$
\tilde{a}=\sum_{i=1}^{d+1}a(\alpha _{i})u_{i}(x)
$$
$a(\alpha _{i})=\tilde{a}(\alpha _{i})$ for all $i$

Therefore, $(a(x)-\tilde{a}(x))\in F[x]$ with $degree\leq d$ , but $d+1$ roots
$\implies a(x)=\tilde{a}(x)$

$F[x]_{m(x)}=\{ a(x)\in F[x]|deg(a(x))<deg (m(x)) \}$, $m(x)$ is irreducible
is a field

**Side note**
$\lvert F[x]_{m(x)} \rvert=\lvert F \rvert^{deg (m(x))}$

### Application: ECC
[[Error-Correcting Codes (ECC)]]
## Example
$m(x)=x^{2}+x+1\in GF(2)[x]$ irreducible
$F[x]_{m(x)}=\{ 0,1,x,1+x \}$
$(x+1)^{2}\equiv _{m(x)}x$
$(x+1)x\equiv _{m(x)}x^{2}+x\equiv _{m(x)}1$

$\mathbb{C}\simeq \mathbb{R}[x]_{x^{2}+1}$ ($x^{2}+1=0\Longleftrightarrow x^{2}=-1$)
