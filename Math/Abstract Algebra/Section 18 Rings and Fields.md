
## 18.1 Definition Rings

> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=172&selection=70,0,210,1&color=note|p.167]]
> > A **ring** 〈R, +, ·〉 is a set R together with two binary operations + and ·, which we call addition and multiplication, defined on R such that the following axioms are satisfied: 
> > - R1. 〈R, +〉 is an abelian group. 
> > - R2. Multiplication is associative. 
> > - R3. For all a, b, c ∈ R, the left distributive law, a · (b + c) = (a · b) + (a · c) and the right distributive law (a + b) · c = (a · c) + (b · c) hold. 

For example, $M_n(R)$ ($n\times n$ matrix with real number entries) is a ring

## 18.8 Properties of a ring
> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=175&selection=89,1,158,1&color=note|p.170]]
> > If R is a ring with additive identity 0, then for any a, b ∈ R we have 
> > 1. 0a = a0 = 0, 
> > 2. a(−b) = (−a)b = −(ab), 
> > 3. (−a)(−b) = ab.

## 18.14 Definition Commutative Ring and Unity

> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=177&selection=257,0,270,1&color=note|p.172]]
> > - A ring in which the multiplication is commutative is a commutative ring. 
> > - A ring with a multiplicative identity element is a ring with unity; 
> > - the multiplicative identity element 1 is called “unity.” 


## 18.16 Definition Division Ring and Field
> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=178&selection=187,1,242,1&color=note|p.173]]
> > Let R be a ring with unity $1 \neq 0$. An element u in R is a **unit** of R if it has a multiplicative inverse in R.
> > If every nonzero element of R is a **unit**, then R is a **division ring** (or **skew field**). 

> [!NOTE]
> A unity is always a unit

> [!NOTE]
> A **field** is a commutative division ring. A noncommutative division ring is called a “strictly skew field.” 

> [!question]
> Why can an element on a ring not be divided by $0$

In a ring you can only “divide” by an element if it has a multiplicative inverse. But for every ring
$$0\cdot x = 0$$
for all x. 
If zero had an inverse y, you’d need
$$0\cdot y = 1$$
which is impossible since $0\cdot y$ is always 0, never 1. Hence 0 cannot have an inverse (except in the trivial ring where $0=1$), and so “division by zero” is undefined.


## 18.17 Example
In the Ring $\mathbb Z_{14}$ :
the units are 1,13(-1),3,5,11(-3),9(-5)
(-3)(-5)=3\*5=1

2,4,6,7,8,10 are not units because gcd(m,14)>1