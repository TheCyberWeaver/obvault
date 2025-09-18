
## Definition Extension Field

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=270&selection=52,0,70,0&color=note|A First Course in Abstract Algebra, p.265]]
> > A field $E$ is an extension field of a field $F$ if $F \leq E$.

**Example**: A tower of fields
![[Pasted image 20250707162529.png]]
Here $F(x)$ is the field of all polynomials with coefficients in $F$ (with an indeterminate $x$) (see [[Section 22 Rings of Polynomials#Intro]])

## 29.3 Kronecker's Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=271&selection=17,0,59,2&color=note|A First Course in Abstract Algebra, p.266]]
> > Let $F$ be a field and let $f(x)$ be a nonconstant polynomial in $F[x]$. Then there exists an extension field $E$ of $F$ and an $α ∈ E$ such that $f (α) = 0$.

In other words, _every_ polynomial has _some_ root once you allow yourself to enlarge your field

- [ ] Proof🔽 
## Simple Examples of Field Extensions

**Example 1**: Extend $\mathbb R$
- We must firstly find an irreducible polynomial. In this case we use $x^2+1$
- We find $\mathbb C=\mathbb R[x]/\langle x^2+1\rangle$ 
- We force $p(x)=x^2+1=0$, and define an imaginary root $\alpha$ so that $\alpha^2=-1$ (the choice of $\alpha$ depends on the choice of the irreducible polynomial)
- We extend $\mathbb R$ with this new element (normally written as $i$)
- In the end we have $\mathbb C$

It's interesting to know that according to **Frobenius theorem** every 2-dimensional extension of $\mathbb R$ is $\mathbb C$. 
Understanding this is simple:
- suppose we define $j$ as $j^2=-2$ 
- we can always substitute $j$ for $\sqrt(2)i$, and the result is still in the form $a+bi$ 

**Example 2**: Extend $\mathbb Q$
Similar to example 1 we find $\mathbb Q[x]/\langle x^2-2\rangle$ 
The result is $\mathbb Q(\sqrt(2))$, which is just $\mathbb Q + {\sqrt(2)}$

**Summary** 
- Extending $i$ from $\mathbb R$ is just an ordinary procedure. There is nothing special about $i$, we can do the same for $\mathbb Q$
- Note that unlike extending on $\mathbb R$, $\mathbb Q(\sqrt(2))$ is structurally different from $\mathbb Q(\sqrt(3))$

## 29.4 Example: Construct Field Extensions 

An alternative approach of example 1:
we want to find the field $\mathbb E=\mathbb R[x]/\langle x^2+1\rangle$ 

In the factor ring $\mathbb R[x]/\langle x^2+1\rangle$, every element is a coset of $\langle x^2+1\rangle$ , so they are in the form of $$p(x)+\langle x^2+1\rangle$$
If we  project $x$ of $\mathbb R[x]$ (the indeterminate, see [[Section 22 Rings of Polynomials#Intro]]) onto the factor ring, we get $\alpha \;=\; x + \langle x^2+1\rangle$

> [!NOTE]
> Consider the homomorphism: $\pi : \mathbb R[x]\rightarrow \mathbb E$ 
> $$\pi(p(x))=p(x)+\langle x^2+1\rangle$$

If we in insert x into $\pi$ , we get this:$\alpha \;=\; x + \langle x^2+1\rangle$ ($\alpha$ is just for simplicity)

## 29.6 Definition: Algebraic and Transcendental Elements

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=272&selection=567,0,629,1&color=note|A First Course in Abstract Algebra, p.267]]
> > An element α of an extension field $E$ of a field $F$ is **algebraic over** $F$ if $f (α) = 0$ for some nonzero $f (x) ∈ F[x]$. If $α$ is not algebraic over $F$, then $α$ is **transcendental over** $F$. 
> 

 **Examples**: 
 - $\sqrt2$ is an algebraic element over $\mathbb Q$, because $\sqrt 2$ is a zero of $x^2-2$
 - Similarly, $i$ is an algebraic element over $\mathbb Q$
 - $\pi$ and $e$ are transcendental over $\mathbb Q$
 - **BUT** $\pi$ and $e$ are algebraic over $\mathbb R$, for they are zeros of $x-\pi$ and $x-e\in \mathbb R$ respectively. 
## 29.11 Definition: Algebraic and Transcendental Numbers

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=273&selection=235,0,260,1&color=note|A First Course in Abstract Algebra, p.268]]
> > An element of $\mathbb C$ that is algebraic over $\mathbb Q$ is an **algebraic number**. A **transcendental number** is an element of $\mathbb C$ that is transcendental over $\mathbb Q$. 

## 29.12 Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=273&selection=293,0,395,19&color=note|A First Course in Abstract Algebra, p.268]]
> > Let $E$ be an extension field of a field $F$ and let $α ∈ E$. 
> > Let $\phi_\alpha : F[x] → E$ be the evaluation homomorphism of $F[x]$ into $E$.
> > e.g.
> > - $\phi_\alpha(a) = a$ for $a ∈ F$
> > - $\phi_\alpha (x) = \alpha$
> > 
> > Then $\alpha$ is transcendental over $F$ if and only if $\phi_\alpha$ gives an isomorphism of $F[x]$ with a subdomain of $E$, that is, if and only if $\phi_\alpha$ is a one-to-one map

**Proof**:
The element $α$ is transcendental over $F$ if and only if $f (α) \neq 0$ for all nonzero $f (x) ∈ F[x]$, which is true (by definition) if and only if $\phi_\alpha ( f (x)) \neq 0$ for all nonzero $f (x) ∈ F[x]$, which is true if and only if the kernel of $\phi_\alpha$ is $\{0\}$ (remember [[Section 13 Homomorphisms#13.13 Definition Kernel]]), that is, if and only if $\phi_\alpha$ is a one-to-one map. 

**Notes**:
Remember [[Section 14 Factor Groups#The Fundamental Homomorphism Theorem|The Fundamental Homomorphism Theorem]]: $$F[x]/ker\; \phi_\alpha\cong Im(\phi_\alpha)\subseteq E$$
- If $\alpha$ is transcendental -> $ker\; \phi_\alpha =\{0\}$ -> $F[x]\cong Im(\phi_\alpha)$
- If $\alpha$ is algebraic -> $ker\; \phi_\alpha\neq\{0\}$ -> $\phi_\alpha$ is not a one-to-one map

## 29.13 Theorem: Minimal Polynomial

If $\alpha$ is algebraic over $F$ then there’s a “smallest” irreducible polynomial $p(x)$ in $F[x]$ (unique up to scaling) such that $p(α)=0$. Moreover, any other polynomial $f(x)$ in $F[x]$ that vanishes at $\alpha$ must be divisible by this $p(x)$.

**Proof**
- We define firstly $\phi_\alpha$ as the evaluation homomorphism of $F[x]$ into $E$ (see [[Section 22 Rings of Polynomials#22.4 The Evaluation Homomorphisms for Field Theory|homomorphism example]]).
- $ker \; \phi_\alpha$ is an ideal and by [[Section 27 Prime and Maximal Ideals#27.24 Theorem Ideal in polynomial Field]], it must be a principal ideal generated by some $p(x)\in F[x]$  
- we write this ideal as $\langle p(x)\rangle$, every other $f(x)$ with $f(\alpha)=0$ is a multiple of $p(x)$, and there exists a irreducible $p(x)$ of minimal degree
## Definition: monic polynomial

If we multiply a polynomial by a suitable constant so that the coefficient of the highest power of x appearing in $p(x)$ of [[#29.13 Theorem Minimal Polynomial]] is $1$, then this polynomial is called a **monic polynomial**

## Definition: irr() & deg()

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=274&selection=389,0,453,1&color=note|A First Course in Abstract Algebra, p.269]]
> > Let $E$ be an extension field of a field $F$, and let $α ∈ E$ be algebraic over $F$. The unique monic polynomial $p(x)$ having the property described in [[#29.13 Theorem Minimal Polynomial]] is the irreducible polynomial for $α$ over $F$ and will be denoted by $irr(α, F)$. The degree of $irr(α, F)$ is the degree of $α$ over $F$, denoted by $deg(α, F)$. 
> 
> 

**Example**:
$$irr(\sqrt 2,\mathbb Q)=x^2-2$$
It's easy to check that $\alpha=\sqrt{1+\sqrt{3}}$ in $\Bbb R$, meaning that $\alpha$ is also a zero of $x^4-2x^2-2$ in $\Bbb Q$. Using the [[Eisenstein divisibility]] check (where we pick $p=2$), the $x^4-2x^2-2$ is irreducible in $\Bbb Q$
$$irr(\sqrt{1+\sqrt{3}},\mathbb Q)=x^4-2x^2-2$$
Thus, we have $deg(\sqrt{1+\sqrt{3}},\Bbb Q)=4$

> [!Warning]
> We must always specific the field when we are talking about degree or algebraic.
> **Example**:
> $\sqrt 2\in \Bbb R$ is algebraic of degree 2 over $\Bbb Q$ but algebraic of degree 1 over $\Bbb R$, for $irr(\sqrt 2,\Bbb R)=x-\sqrt 2$.

## Two ways of simple extensions
$\phi_\alpha$ is defined as the evaluation homomorphism just as before
### Case I
Suppose $\alpha$ is **algebraic** over $F$. 
Then the kernel of $\phi_\alpha$ is $\langle irr(α, F)\rangle$, which by [[Section 27 Prime and Maximal Ideals#27.25 Theorem]] is a maximal ideal of $F[x]$. Therefore, $F[x]/irr(α, F)$ is a field and is isomorphic to the image $\phi_\alpha[F[x]]$ in $E$. This subfield $\phi_\alpha[F[x]]$ is then the smallest subfield of $E$ containing $F$ and $\alpha$. We shall denote this by $F(\alpha)$

## Case II
Suppose $\alpha$ is **transcendental** over $F$. 
Then $\phi_\alpha$ gives an isomorphism of $F[x]$ with a subdomain of $E$. Thus, $\phi_\alpha[F[x]]$ is ***not*** a field but an integral domain (denoted as $F[\alpha]$)
$E$ contains a field of quotients of $F[\alpha]$ (just like in Case I, it is denoted by $F(\alpha)$), which is thus the smallest subfield of $E$ containing $F$ and $\alpha$. 

## 29.16 Example
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=275&selection=180,1,216,1&color=note|A First Course in Abstract Algebra, p.270]]
> > Since π is transcendental over $\Bbb Q$, the field $\Bbb Q(π)$ is isomorphic to the field $\Bbb Q(π)$ of rational functions over $\Bbb Q$ in the indeterminate $x$. 
> > 
> > Thus from a structural viewpoint, an element that is transcendental over a field $F$ behaves as though it were an indeterminate over $F$.  

It makes sense, because you can construct $\pi^2,\pi^3,\dots$ from $\pi$, which can all be viewed as basis. Therefore, you get an infinite basis.

| Feature                  | **Q(√2)**                                                    | **Q(x)** (or **Q(π)**)                                             |
| ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------------ |
| Type of adjoined element | Algebraic ($\sqrt 2$ satisfies the polynomial $x^2 - 2 = 0$) | Transcendental ($x$ satisfies no nonzero polynomial over $\Bbb Q$) |
| Vector-space dimension   | Finite (2‑dimensional, basis $\{1,\sqrt2\}$)                 | Infinite (basis $\{1,x,x^2,\dots\}$)                               |
| Typical element form     | $a+b\sqrt 2$, with $a,b\in \Bbb Q$                           | $\frac{p(x)}{q(x)}$, with $p,q\in \Bbb Q[x], q\neq 0$              |
| “Size” of the extension  | Small—just one polynomial relation                           | Huge—no polynomial relations, so you get endlessly many powers     |
## 29.17 Definition: simple extension

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=275&selection=221,0,252,0&color=note|A First Course in Abstract Algebra, p.270]]
> > An extension field $E$ of a field $F$ is a simple extension of $F$ if $E = F(α)$ for some $α ∈ E$.
> 

## 29.18 Theorem
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=275&selection=273,0,356,1&color=note|A First Course in Abstract Algebra, p.270]]
> > Let $E$ be a simple extension $F(\alpha)$ of a field $F$, and let $\alpha$ be algebraic over $F$. Let the degree of $irr(\alpha, F)$ be $n \geq 1$. Then every element $\beta$ of $E = F(\alpha)$ can be uniquely expressed in the form $$\beta = b_0 + b_1\alpha + \cdots + b_{n−1}\alpha^{n−1}$$ where the $b_i$ are in $F$.


## 29.19 Example: Field GF(4)

- $\Bbb Z_2[x]$ is a field
- consider $\Bbb Z_2[x]/\langle x^2+x+1\rangle$, we want to find $\Bbb Z_2(\alpha)$
- We know from [[#29.18 Theorem]] $\Bbb Z_2(\alpha)$ has elements 0 + 0α, 1 + 0α, 0 + 1α, and 1 + 1α **OR** 0, 1, α, and 1 + α 
- THIS is a new finite field of four elements!!! called $\Bbb F_4$ or $GF(4)$
- The structure of this field is shown below
![[Pasted image 20250728141250.png]]

For example: $\alpha^2=-\alpha-1=\alpha+1$, (note that in $\Bbb Z_2$ , $-1=1$ and $-\alpha=\alpha$)

We can do the same to $\Bbb R$ and we get $\Bbb C$ as the smallest possible extension field.