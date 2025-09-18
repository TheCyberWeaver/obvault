## 27.1 Example
According to [[Section 19 Integral Domains#19.11 Theorem]]  $\mathbb Z_p$ is a field, if p is a prime. $\mathbb Z_p$ is isomorphic to $\mathbb Z/p\mathbb Z$. 
Thus a factor ring of an integral domain may be a field.

## 27.3 Example 
The subset $N=\{0,3\}$ of $\mathbb Z_6$ (not a integral domain) is easily seen to be an ideal of $\mathbb Z_6$ 
$\mathbb Z_6/N\subseteq \mathbb Z_3$ has three elements: $0+N$, $1+N$, $2+N$

Remember
[[Section 19 Integral Domains#19.5 Definition Integral Domain]]
and
[[Section 19 Integral Domains#19.11 Theorem]]

> [!NOTE]
>  if R is not even an integral domain, that is, if R has zero divisors, it is still possible for $R/N$ to be a field.

## Definition: improper ideal and trivial ideal
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=251&selection=254,0,271,1&color=note|A First Course in Abstract Algebra, p.246]]
> > Every nonzero ring $R$ has at least two ideals, the **improper ideal** $R$ and the **trivial ideal**$\{0\}$

## 27.5 Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=251&selection=329,1,348,1&color=note|A First Course in Abstract Algebra, p.246]]
> > If R is a ring with unity, and N is an ideal ([[Section 26 Homomorphisms and Factor Rings#26.10 Definition Ideal|Definition of Ideal]]) of R containing a unit ([[Section 18 Rings and Fields#18.16 Definition Division Ring and Field|Definition of unit]]), then N = R

Or we can say: no element in N can have a multiplicative inverse
***Proof***:
Let $u\in N$ for an unit in $N$
$rN\subseteq N$ with $r\in R$ implies that if we take $r=u^{-1}$, we find that $1$ must be inside $N$
If $1\in N$, then $r1\subseteq N$ and $r1=r$, meaning that every element in $R$ is in $N$.
## 27.6 Corollary

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=251&selection=472,0,472,44&color=note|A First Course in Abstract Algebra, p.246]]
> > A field contains no proper nontrivial ideals.
> 

## 27.7 Definition: maximal ideal

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=252&selection=7,0,34,0&color=note|A First Course in Abstract Algebra, p.247]]
> > A maximal ideal of a ring R is an ideal M different from R such that there is no proper ideal N of R properly containing M.

So we can also say (just like the [[Section 15 Factor-Group Computations and Simple Groups#15.18 Theorem|maximal normal subgroup]] in group theory): 
> [!NOTE]
> $M$ is a maximal ideal of $R$ if and only if $R/M$ is a field.

## 27.10 Example

p is a prime
Since $\mathbb Z/p\mathbb Z$ is isomorphic to $\mathbb Z_p$ (a field, according to [[Section 19 Integral Domains#19.11 Theorem]]). We see that the maximal ideals of $Z$ are precisely the ideals $p\mathbb Z$ 

> [!Tip]
> Most rings have multiple maximal ideals. Only local rings have exactly one maximal idea.

## 27.11 Corollary

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=252&selection=532,0,532,90&color=note|A First Course in Abstract Algebra, p.247]]
> > A commutative ring with unity is a field if and only if it has no proper nontrivial ideals.
> 

Extension to [[#27.6 Corollary]]
***Proof***:
 If a commutative ring R with unity has no proper nontrivial ideals, then {0} is a maximal ideal and R/{0}, which is isomorphic to R, is a field by the Note in [[#27.7 Definition maximal ideal]]

## Factor Ring and Integral Domain

The factor ring $R/N$ will be an integral domain if and only if:
$$(a + N)(b + N) = N \Longrightarrow a+N=N \ or \ b+N=N$$
Note that $a+N$ and $b+N$ are two elements in the factor ring $R/N$.
This is the same as the definition of an integral domain (no 0 divisor [[Section 19 Integral Domains#19.5 Definition Integral Domain|Definition of Integral Domain]]) $ab=0\Longrightarrow a=0\ or\ b=0$

Remember:
- $\mathbb Z_n$ is an integral domain if and only if $n$ is prime
- If $p$ is a prime, $\mathbb Z_p$ is a field
## 27.13 Definition: prime ideal
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=253&selection=179,0,232,0&color=note|A First Course in Abstract Algebra, p.248]]
> > An ideal $N \neq R$ in a commutative ring $R$ is a prime ideal if:
> >  $ab \in N$ implies that either $a \in N$ or $b \in N$ for $a, b \in R$.

 So we cannot have two elements outside of $N$, whose product is in the ideal $N$.
 And of course $\{0\}$ is a prime ideal in any integral domain, because of no 0 divisor.

Example: $\mathbb Z\times \{0\}$ is a prime ideal of $\mathbb Z \times \mathbb Z$ 

## Characteristics of a commutative ring R with unity

For a commutative ring $R$ with unity: 
1. An ideal $M$ of $R$ is maximal if and only if $R/M$ is a field. 
2. An ideal $N$ of $R$ is prime if and only if $R/N$ is an integral domain. 
3. Every maximal ideal of $R$ is a prime ideal.

## 27.17 Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=254&selection=102,0,150,1&color=note|A First Course in Abstract Algebra, p.249]]
> > If R is a ring with unity 1, then the map $φ : Z → R$ given by $φ(n) = n · 1$ for $n ∈ Z$ is a homomorphism of $Z$ into $R$.
> 
> 

## 27.20 Definition Prime Fields

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=255&selection=45,0,57,1&color=note|A First Course in Abstract Algebra, p.250]]
> > The fields $Z_p$ and $Q$ are prime fields. 

## 27.21 Definition Principal Ideal

In a ring with unity $R$, the ideal $\{ra|r\in R\}$ is **the principal ideal generated by a**, denoted as $\langle a \rangle$. 
- An ideal is a principal ideal if such a exists. 

**Example:**
Considering the ring $\mathbb Z$, the ideals $n\mathbb Z$ are generated by n
(Note that every ideal of $\mathbb Z$ is of the form $n\mathbb Z$)

## 27.24 Theorem: Ideal in polynomial Field

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=255&selection=255,1,265,15&color=note|A First Course in Abstract Algebra, p.250]]
> > If $F$ is a field, every ideal in $F[x]$ is principal.

***Proof:***
Let $N$ be an ideal of field $F[x]$ 
- If $N=\{0\}$, then it's trivial, $\{0\}$ is generated be $\langle 0 \rangle$
- If $N\neq \{0\}$ and the degree of a minimal degree element $g(x)$ is 0 (in other words g(x) is constant), then $N=F[x]=\langle 1 \rangle$ according to [[#27.5 Theorem]], because elements in $N$ are units.

> [!Question]
> Why is constant g(x) here an unit?
- [ ] ⏫ Answer:
If $N\neq \{0\}$ and the degree of a minimal degree element $g(x)$ is greater than 0, then:
- consider $f(x)=g(x)q(x)+r(x)$:
- $f(x)\in N$ and $g(x)\in N$, then we have $f(x)-g(x)q(x)=r(x)\in N$ according to the [[Section 26 Homomorphisms and Factor Rings#26.10 Definition Ideal|definition of an ideal]]. 
- and since $g(x)$ is a nonzero element of minimal degree in N, we must have $r(x)=0$
- Thus, every $f(x)=g(x)q(x)$, meaning that $N=\langle g(x)\rangle$


> [!Tip]
> In $F[x]$, $f(x)=g(x)q(x)+r(x)$. then $r(x)$ is either 0 or (degree r(x)) < (degree g(x))

## 27.25 Theorem 
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=256&selection=7,0,34,1&color=note|A First Course in Abstract Algebra, p.251]]
> > An ideal $\langle p(x)\rangle \neq \{0\}$ of $F[x]$ is maximal if and only if $p(x)$ is irreducible over F.

irreducible: cannot be fatorized

***Proof:***
- Let $p(x)=f(x)g(x)$
- $\langle p(x)\rangle$ is a maximal ideal $\longrightarrow$ $\langle p(x)\rangle$ is a prime ideal (see [[#Characteristics of a commutative ring R with unity]])
- either $f(x)\in \langle p(x)\rangle$ or $g(x)\in \langle p(x)\rangle$
- meaning that either $f(x)$ or $g(x)$ has $p(x)$ as a factor. 
- But then the degrees of $f(x)$ and $g(x)$ cannot both be less than the degree of $p(x)$.
- p is irreducible over F
***Proof conversely***:
- [ ] proof⏫ 

**Example**:
Show that $f(x)=x^3+3x+2$ in $\mathbb Z_5[x]$ is irreducible over $\mathbb Z_5$.
- We need to firstly find a term in form $x-a$ for some $a\in \mathbb Z_5$, so that $f(a)=0$.
- Iterate through $f(a)$ for $a\in\mathbb Z_5$, we find that such a doesn't exist, showing that $f(x)$ has no zeros in $\mathbb Z_5$.
- $f(x)$ is irreducible over $\mathbb Z_5$
- $\langle x^3+3x+2 \rangle$ is a maximal ideal
- $\mathbb Z_5[x]/\langle x^3+3x+2 \rangle$ is a field (see [[#27.7 Definition maximal ideal]])

Similarly, $x^2-2$ is irreducible in $\mathbb Q[x]$, so $\mathbb Q[x]/\langle x^2-2\rangle$ is a field.

## 27.27 Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=256&selection=551,0,613,2&color=note|A First Course in Abstract Algebra, p.251]]
> > Let p(x) be an irreducible polynomial in F[x]. If p(x) divides r(x)s(x) for r(x), s(x) ∈ F[x], then either p(x) divides r(x) or p(x) divides s(x).
> 

***Proof***:
- Suppose p(x) is irreducible and divides r(x)s(x)
- $\langle p(x)\rangle$ is a maximal ideal (see [[#27.25 Theorem]]) 
- $\langle p(x)\rangle$ is a prime ideal (see [[#Characteristics of a commutative ring R with unity]])
- $r(x)s(x)\in \langle p(x)\rangle$ implies either $r(x)\in \langle p(x)\rangle$ or $s(x)\in \langle p(x)\rangle$ (see [[#27.13 Definition prime ideal]])
- Hence, $p(x)$ divides $r(x)$ or $p(x)$ divides $s(x)$ (see [[#27.21 Definition Principal Ideal]])
$q.e.d.$