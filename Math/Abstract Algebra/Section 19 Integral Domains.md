## 19.2 Definition Zero Divisor
> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=183&selection=250,1,285,1&color=note|p.178]]
> > If a and b are two nonzero elements of a ring R such that ab = 0, then a and b are divisors of 0 (or 0 divisors). 
> 

## 19.3 Theorem
> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=183&selection=304,1,316,1&color=note|p.178]]
> > In the ring $\mathbb Z_n$ , the divisors of 0 are precisely those nonzero elements that are not relatively prime to n.

Let $m\in \mathbb Z_n$, $m\neq 0$ and $d= gcd(n,m)>1$ $$m (\frac n d)=n(\frac m d)$$ $n(\frac m d)$ is 0 because $0\equiv n(\frac m d)\ mod\ n$ , so m is a divisor of 0.

If $gcd(n,m)=1$ then $m\frac n 1=mn=m0=0$ 

## 19.5 Definition Integral Domain

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=184&selection=393,0,407,1&color=note|p.179]]
> > An integral domain D is a commutative ring with unity $1 \neq 0$ and containing no divisors of 0. 

This means we can factorize a polynomial and solve an equation as we do normally. 
There is no other other solutions than $x=r_1$ and $x=r_2$ 
$(x-r_1) (x-r_2)=0$ 

> [!NOTE]
> $\mathbb Z_n$ is an integral domain if and only if $n$ is prime

> [!NOTE]
> A direct product of two nonzero rings $R$ and $S$ cannot be an integral domain,
> because $(r,0)(s,0)=(0,0)$ for $r\in R$ and $s\in S$ 

![[Algebra Structure.excalidraw]]
## 19.9 Theorem
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=185&selection=63,1,68,21&color=note|p.180]]
> > Every field F is an integral domain

## 19.11 Theorem
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=186&selection=7,0,7,38&color=note|p.181]]
> > Every finite integral domain is a field.

- If p is a prime, $\mathbb Z_p$ is a field

## 19.13 Definition The Characteristic of the ring $R$

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=186&selection=326,0,367,1&color=note|p.181]]
> > If for a ring R a positive integer n exists such that n · a = 0 for all a ∈ R, then the least such positive integer is the characteristic of the ring R. If no such positive integer exists, then R is of characteristic 0. 

$\mathbb{Z,Q,R,C}$ all have characteristic 0
$\mathbb Z_n$ is of characteristic n

## 19.15 Theorem
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=187&selection=25,1,81,1&color=note|p.182]]
> > Let R be a ring with unity.
> > - If $n\cdot 1\neq 0$ for all $n\in \mathbb Z^+$, then R has characteristic of 0.
> > - If $n\cdot 1=0$ for some $n\in \mathbb Z^+$, then the smallest such integer n is the characteristic of R.
You can think of the characteristic of a ring $R$ very simply as “how many times you must add $1$ to itself before you get $0$”:

- **Keep adding $1$:**
 1,  1+1,  1+1+1,  …
 - If you never hit $0$, the ring has characteristic $0$ (like $\Bbb Z$). 
 - If the first time you reach $0$ is after $n$ summands, and no smaller positive sum vanishes, then $\operatorname{char}R = n$ (like $\Bbb Z/n\Bbb Z$).
Proof of the second point:
If $n\cdot 1=0$:
$$n · a = a + a + · · · + a = a(1 + 1 + · · · + 1) = a(n · 1) = a0 = 0.$$