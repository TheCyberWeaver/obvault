## Definition
$\mathbb{Z}^{*}_{m}\overset{ def }{ = }\{ a\in \mathbb{Z}_{m}|gcd(a,m)=1 \}$
$\phi (m)=\lvert \mathbb{Z}^{*}_{m} \rvert$

## general formula
$$  
\phi(m) = m \prod_{p \mid m} \left(1 - \frac{1}{p}\right)  
$$
## when calulating by hand
If
$$
m = p_1^{k_1} p_2^{k_2} \cdots p_r^{k_r}
$$
is the prime factorization of $m$, then
$$
\phi(m)
= p_1^{k_1-1}(p_1-1)
  \cdot
  p_2^{k_2-1}(p_2-1)
  \cdots
  p_r^{k_r-1}(p_r-1)
$$

So the rule is:

- Factor $m$ into primes  
- For each prime $p_i^{k_i}$:
  - keep $p_i^{k_i-1}$
  - replace one $p_i$ by $(p_i-1)$
- Multiply everything together

## Example
$$
m = 18 = 2 \cdot 3^2
$$

$$
\phi(18)
= 2^{1-1}(2-1)\cdot 3^{2-1}(3-1)
= 1\cdot 1 \cdot 3 \cdot 2
= 6
$$
