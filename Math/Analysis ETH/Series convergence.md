A series is studied through its sequence of partial sums
$$
s_n=\sum_{k=0}^{n} a_k
$$
so series convergence is a special case of [[Sequence|sequence convergence]].

For worked examples, see [[Convergence test examples]].

For a series $\sum_{n=0}^{\infty} a_n$:
- it is **absolutely convergent** if $\sum_{n=0}^{\infty} |a_n|$ converges
- it is **conditionally convergent** if $\sum_{n=0}^{\infty} a_n$ converges, but $\sum_{n=0}^{\infty} |a_n|$ does not

### Riemann Rearrangement Theorem
If a real series is conditionally convergent, then for every $L \in \mathbb{R}$ there is a bijection $\varphi:\mathbb{N}_0 \to \mathbb{N}_0$ such that
$$
\sum_{n=0}^{\infty} a_{\varphi(n)} = L
$$
So a conditionally convergent series can be rearranged to converge to any prescribed real value. In contrast, absolutely convergent series keep the same sum under every rearrangement.

### Leibniz Criterion
If $(a_n)_{n\in\mathbb{N}_0}$ is a monotone decreasing sequence of non-negative real numbers and $a_n \to 0$, then the alternating series
$$
\sum_{n=0}^{\infty} (-1)^n a_n
$$
converges.

### Cauchy Criterion
The series $\sum_{n=0}^{\infty} a_n$ converges if and only if for every $\varepsilon > 0$ there exists $N \in \mathbb{N}_0$ such that for all $n \ge m \ge N$,
$$
\left| \sum_{k=m+1}^{n} a_k \right| < \varepsilon
$$
So the tails of the series must become arbitrarily small.

### p-Series Test
The series
$$
\sum_{n=1}^{\infty} \frac{1}{n^p}
$$
converges if and only if $p>1$.

**Proof**:

If $p>1$, split the series into dyadic blocks:
$$
\sum_{n=1}^{\infty} \frac{1}{n^p}
= 1 + \sum_{m=0}^{\infty}\sum_{n=2^m}^{2^{m+1}-1}\frac{1}{n^p}
$$
For $2^m \le n < 2^{m+1}$, we have
$$
\frac{1}{n^p} \le \frac{1}{(2^m)^p}
$$
and there are $2^m$ terms in this block. Hence
$$
\sum_{n=2^m}^{2^{m+1}-1}\frac{1}{n^p}
\le 2^m \cdot \frac{1}{(2^m)^p}
= 2^{-m(p-1)}
$$
Therefore
$$
\sum_{n=1}^{\infty} \frac{1}{n^p}
\le 1 + \sum_{m=0}^{\infty} 2^{-m(p-1)}
$$
and the right-hand side is a convergent geometric series because $p-1>0$.

If $p=1$, then for $2^m \le n < 2^{m+1}$ we have
$$
\frac{1}{n} \ge \frac{1}{2^{m+1}}
$$
so
$$
\sum_{n=2^m}^{2^{m+1}-1}\frac{1}{n}
\ge 2^m \cdot \frac{1}{2^{m+1}}
= \frac{1}{2}
$$
Thus each dyadic block contributes at least $\frac{1}{2}$, so the harmonic series diverges.

If $0<p<1$, then $n^p \le n$ for all $n\ge1$, hence
$$
\frac{1}{n^p} \ge \frac{1}{n}
$$
Since the harmonic series diverges, $\sum_{n=1}^{\infty}\frac{1}{n^p}$ also diverges by comparison.

If $p\le0$, then
$$
\frac{1}{n^p}=n^{-p}
$$
does not converge to $0$, so the series cannot converge.

### Limit Comparison Test
Let $a_n,b_n>0$ for all sufficiently large $n$. Assume
$$
\lim_{n\to\infty}\frac{a_n}{b_n}=c
$$

- If $0<c<\infty$, then $a_n$ and $b_n$ have the same size for large $n$.
  In this case, $\sum a_n$ and $\sum b_n$ either both converge or both diverge.

- If $c=0$, then $a_n$ is asymptotically smaller than $b_n$ for large $n$.
  If $\sum b_n$ converges, then $\sum a_n$ also converges.

- If $c=\infty$, then $a_n$ is asymptotically larger than $b_n$ for large $n$.
  If $\sum b_n$ diverges, then $\sum a_n$ also diverges.

This is the same asymptotic idea used in [[Algorithm Runtime Analysis]].

### Root Test
Let
$$
\rho = \limsup_{n\to\infty} |a_n|^{1/n}
$$
Then:
- if $\rho < 1$, the series $\sum_{n=0}^{\infty} a_n$ converges absolutely
- if $\rho > 1$, the series diverges

### Ratio Test
If $a_n \neq 0$ for all $n$ and
$$
\rho = \lim_{n\to\infty} \left| \frac{a_{n+1}}{a_n} \right|
$$
then:
- if $\rho < 1$, the series $\sum_{n=0}^{\infty} a_n$ converges absolutely
- if $\rho > 1$, the series diverges

### Cauchy Product
If $\sum_{n=0}^{\infty} a_n$ and $\sum_{n=0}^{\infty} b_n$ are absolutely convergent, then
$$
\left( \sum_{n=0}^{\infty} a_n \right)\left( \sum_{n=0}^{\infty} b_n \right)
= \sum_{n=0}^{\infty} \left( \sum_{k=0}^{n} a_{n-k} b_k \right)
$$
and the series on the right also converges absolutely.

### Power Series
A power series centered at $a$ has the form
$$
\sum_{k=0}^{\infty} c_k (x-a)^k
$$
It has a radius of convergence $R$ such that:
- it converges for $|x-a| < R$
- it diverges for $|x-a| > R$

The interval $(a-R, a+R)$ is called the interval of convergence. If
$$
\rho = \limsup_{n\to\infty} |c_n|^{1/n}
$$
then
$$
R =
\begin{cases}
0, & \rho = \infty \\
\rho^{-1}, & 0 < \rho < \infty \\
\infty, & \rho = 0
\end{cases}
$$
when using root test on power series: $a_{k}=c_{k}(x-a)^{k}\Longleftrightarrow \frac{a_{k}}{c_{k}}=(x-a)^{k}$

#### Example
Consider
$$
\sum_{n=1}^{\infty} (-1)^{n+1}\frac{1}{n}x^n
$$
This is a power series centered at $a=0$ with coefficients
$$
c_n = (-1)^{n+1}\frac{1}{n}
$$
Hence
$$
|c_n|^{1/n} = \left(\frac{1}{n}\right)^{1/n} \to 1
$$
so
$$
\rho = \limsup_{n\to\infty} |c_n|^{1/n} = 1
$$
and therefore
$$
R = \rho^{-1} = 1
$$

For the terms
$$
a_n(x) = (-1)^{n+1}\frac{1}{n}x^n
$$
the root test gives
$$
\limsup_{n\to\infty} |a_n(x)|^{1/n}
= \limsup_{n\to\infty} \left(\frac{1}{n}|x|^n\right)^{1/n}
= |x|
$$
Therefore:
- if $|x| < 1$, the series converges absolutely
- if $|x| > 1$, the series diverges
- if $|x| = 1$, the root test is inconclusive

Check the endpoints separately:
- at $x=1$, we get $\sum_{n=1}^{\infty} (-1)^{n+1}\frac{1}{n}$, which converges by the [[#Leibniz Criterion]]
- at $x=-1$, we get $-\sum_{n=1}^{\infty} \frac{1}{n}$, which diverges

So the interval of convergence is
$$
(-1,1]
$$

$$\sum_{n=1}^{\infty}c_{n}x^{n},c_{n}=\begin{cases}
\frac{1}{2^{n}} \text{n is even} \\
\frac{-1}{3^{n}} \text{n is odd}
\end{cases}
$$