
## 20.0 Theorem

> [!NOTE]
> For any field, the nonzero elements form a group under the field multiplication.
> 

For any field $F$, let $F^\times = F \setminus \{0\}$. Then:
1. **Closure**: If $a,b \in F^\times$, then $ab \neq 0$ (since $F$ has no zero divisors), so $ab \in F^\times$.
2. **Associativity**: Multiplication in $F$ is associative.
3. **Identity**: $1 \in F^\times$ and $1 \cdot a = a$ for all $a \in F^\times$.
4. **Inverses**: For each $a \in F^\times$, there exists $a^{-1} \in F$ such that $a \cdot a^{-1} = 1$.
Therefore, $(F^\times, \cdot)$ is a group.

## 20.1 Little Theorem of Fermat

> [!NOTE]
> If $p$ is prime and ${\gcd(a,p)=1}$, then
> $$a^{\,p-1}\equiv1\pmod p.$$
> Equivalently, for any integer $a$,
> $$a^p\equiv a\pmod p.$$

***Proof:***
For a Field $\mathbb F_p$ , the elements $\{1,2,3,...,p-1\}$ form a group of order p-1 under multiplication modulo p: $(\mathbb Z/p\mathbb Z)\times=\{\bar a:1≤a<p,\ gcd(a,p)=1\}$
Since the order of any element in a group divides the order of the group (see [[Section 10 Cosets and The Theorem of Lagrange#The Theorem of Lagrange|The Theorem of Lagrange]]), we see the order of every element in this group divides p-1, meaning $a^{p-1}=1$ for all $a\in (\mathbb Z/p\mathbb Z)\times$  
$\mathbb Z_p$ is isomorphic to $\mathbb Z/p\mathbb Z$ (see [[Section 14 Factor Groups#14.2 Example]], rings follow the similar principle). We see that for any $a\in \mathbb Z$ not in the coset $0+p\mathbb Z$, we have $a^{p-1}\equiv1$ under multiplication modulo p


## 20.6 Theorem 

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=191&selection=170,0,184,1&color=note|p.186]]
> > The set $G_n$ of nonzero elements of $Z_n$ that are not 0 divisors forms a group under multiplication modulo n.

[[Section 19 Integral Domains#19.3 Theorem]]
The elements that are relative prime to n forms a group under multiplication modulo n.
## 20.8 Euler's Theorem
a generalization from Little Theorem of Fermat

define $\phi(n)$ be the number of positive integers $\leq$ n and relatively prime to n
$\phi(12)=4$

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=192&selection=42,0,80,0&color=note|p.187]]
> > If a is an integer relatively prime to n, then $a^{\phi(n)}-1$ is divisible by n, that is, $a^{\phi(n)}\equiv 1\ (mod \ n)$ 

Use [[#20.6 Theorem]] we get a multiplication group of order $\phi(n)$ and the rest of the proof is similar to the proof of [[#20.1 Little Theorem of Fermat]].

## 20.10 Theorem
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=192&selection=340,0,379,1&color=note|p.187]]
> > Let m be a positive integer and let $a \in\mathbb Z_m$ be relatively prime to m. The equation $ax = b$ has a unique solution in $\mathbb Z_m$.

By [[#20.6 Theorem]] a has a multiplication inverse (a is an unit).
We can multiply both sides of the equation on the left by $a^{-1}$
$x=a^{-1}b$, which is the only solution.


