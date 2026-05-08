

> [!NOTE] Goal
> Given a number $n \in \mathbb{N}$, decide whether $n$ is prime, i.e., whether it has no divisor in $\{2,\dots,n-1\}$.

Application: Generating large random prime numbers for [[RSA]] cryptography (e.g. 1000 bits).

**Prime Number Theorem**:
$$
\pi(x):=\lvert \{ n\in \mathbb{N}\;|\;n\leq,n \text{ prime }\} \rvert\sim \frac{x}{\ln x} 
$$


## Naive algorithm
For all $a \le \sqrt{n}$, test whether $a$ divides $n$.

This is too slow for $n \approx 2^{1000}$, since then $\sqrt{n} \approx 2^{500}$.

We want an algorithm whose running time is polynomial in $\log n$ (the input size of $n$).


## Euclid Primality Test
Test$(n)$
1. Choose $a \in \{1,\dots,n-1\}$ uniformly at random.
2. If $\gcd(a,n) = 1$, return “prime”. (`gcd(n,m)` can be calculated in $O((\log nm)^{3})$)
3. Otherwise, return “not prime”.

- If $n$ is prime: the output is always correct.
- If $n$ is not prime: the incorrect output “prime” occurs with probability $\frac{|\mathbb{Z}_n^*|}{n-1}= \frac{\phi(n)}{n-1}$ (see [[Euler's Totient Function]])


## Fermat Primality Test
Test$(n)$
1. Choose $a \in \{1,\dots,n-1\}$ uniformly at random.
2. If $a^{\,n-1} \equiv 1 \pmod n$ then return “prime”. (see [[Section 20 Fermat's and Euler's Theorems#20.1 Little Theorem of Fermat|Little Theorem of Fermat]])
3. Otherwise, return “not prime”.

- If $n$ is prime: the output is always correct.

- If $n$ is not prime: the incorrect output “prime” occurs with probability $\le \frac{1}{2}$
  unless $n$ is a [[#Carmichael number|Carmichael number]]. 
	- If $PB_n \ne \mathbb{Z}_n^*$ (i.e. $n$ is not a Carmichael number), then $|PB_n|$ is a proper divisor of $|\mathbb{Z}_n^*|$, hence $|PB_n| \le \frac{\phi(n)}{2}  \le \frac{n-1}{2}$

By repeating the test $k$ times (in the case the result is “prime”), we can reduce the error probability to $\le \left(\frac{1}{2}\right)^k$

### Pseudoprime base
We make an error if $n$ is not prime and
$$
a^{\,n-1} \equiv _{n} 1
$$
Such an $a$ is called a **pseudoprime base** of $n$.
Define
$$
PB_n := \{\, a \in \{1,\dots,n-1\} \mid a^{\,n-1} \equiv _{n} 1 \,\}
$$

Equivalently, $PB_n = \{\, a \in \mathbb{Z}_n^* \mid a^{\,n-1} \equiv _{n} 1 \,\}$

The elements of $PB_n$ are called **pseudoprime bases** of $n$.

> [!NOTE]
> $PB_n$ is a subgroup of $\mathbb{Z}_n^*$ because:
> If $a^{\,n-1} \equiv _{n} 1\quad \wedge \quad b^{\,n-1} \equiv _{n} 1$ then $(ab)^{\,n-1} \equiv _{n} 1$

### Carmichael number
We say that $n$ is a **Carmichael number** if
- $n$ is not prime, and  
- $PB_n = \mathbb{Z}_n^*$

Smallest examples:
$$
561 = 3 \cdot 11 \cdot 17
$$
$$
1105 = 5 \cdot 13 \cdot 17
$$
$$
1729 = 7 \cdot 13 \cdot 19
$$


## The Miller-Rabin Primality Test
The Miller-Rabin test is a stronger randomized variant of the [[#Fermat Primality Test|Fermat primality test]]. It also tests whether $n$ behaves like a prime with respect to modular exponentiation, but it additionally checks the intermediate squarings, so the Carmichael-number problem of the Fermat test no longer occurs.

Write
$$
n-1 = 2^s d
$$
with $d$ odd. ($n$ is always odd)

Test$(n)$
1. Choose $a \in \{2,\dots,n-2\}$ uniformly at random.
2. Compute $x := a^d \bmod n$.
3. If $x \equiv 1 \pmod n$ or $x \equiv -1 \pmod n$, return "prime".
4. Repeat $s-1$ times:
	1. Set $x := x^2 \bmod n$.
	2. If $x \equiv -1 \pmod n$, return "prime".
5. Return "not prime".

- If $n$ is prime: the output is always correct.
- If $n$ is not prime: the incorrect output "prime" occurs with probability at most $\frac{1}{4}$.

By repeating the test $k$ times (in the case the result is "prime"), we can reduce the error probability to at most
$$
\left(\frac{1}{4}\right)^k
$$

### Proof
Assume that $n=p$ is prime and write
$$
p-1=2^s d
$$
with $d$ odd.

Fix a base $a\in\{2,\dots,p-2\}$ and define
$$
x_j:=a^{2^j d}\pmod p,\qquad j=0,1,\dots,s.
$$
Then
$$
x_s=a^{2^s d}=a^{p-1}\equiv 1\pmod p
$$
by Fermat's little theorem.

If $x_0\equiv 1\pmod p$, then the test already returns "prime" in step 3.
So assume $x_0\not\equiv 1\pmod p$.
Since $x_s\equiv 1\pmod p$, there is a smallest index $j\geq1$ such that
$$
x_j\equiv 1\pmod p.
$$
Then
$$
x_{j-1}^2\equiv x_j\equiv 1\pmod p.
$$
Because $\mathbb{Z}_p$ is a field, the congruence
$$
y^2\equiv 1\pmod p
$$
has only the two solutions
$$
y\equiv \pm1\pmod p.
$$
Hence $x_{j-1}\equiv \pm1\pmod p$.
By minimality of $j$, we cannot have $x_{j-1}\equiv 1\pmod p$, so necessarily
$$
x_{j-1}\equiv -1\pmod p.
$$

Therefore one of the following always happens for a prime $p$:
- $a^d\equiv 1\pmod p$, or
- for some $r\in\{0,\dots,s-1\}$ we have $a^{2^r d}\equiv -1\pmod p$.

These are exactly the cases in which the algorithm returns "prime". So every prime passes the Miller-Rabin test.

> [!NOTE]
> If $n$ is composite and the test still returns "prime", then $a$ is called a **strong pseudoprime base** (or **strong liar**) for $n$.
> A standard theorem of Rabin and Monier says that for every odd composite $n$, at most one quarter of the possible bases are strong liars.
> This gives the error bound
> $$
> \Pr[\text{Miller-Rabin outputs "prime" for composite } n]\leq \frac14.
> $$
