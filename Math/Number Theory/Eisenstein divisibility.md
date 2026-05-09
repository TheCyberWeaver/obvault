The heart of “Eisenstein divisibility” is just the three divisibility checks in Eisenstein’s Criterion for a polynomial

$$f(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0\in \mathbb Z[x]$$
Pick a prime $p$ and verify:

1. **$p$ does _not_ divide the leading coefficient**
 $p\nmid a_n$.
2. **$p$ _does_ divide every other coefficient**
 $p\mid a_{n-1},\,p\mid a_{n-2},\;\dots,\;p\mid a_0$
3. **$p^{2}$ does _not_ divide the constant term**
 $p^2\nmid a_0$

If you can find such a prime $p$, then Eisenstein’s Criterion tells you immediately that $f(x)$ is irreducible over $\Bbb Q$.