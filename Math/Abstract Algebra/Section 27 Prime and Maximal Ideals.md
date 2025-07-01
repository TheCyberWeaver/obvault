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

