---
aliases:
 - Siebformel
---
## General form

> [!THEOREM]
> For finite sets $A_1,\dots,A_n$,
> $$
> \left|\bigcup_{i=1}^n A_i\right|
> =
> \sum_{\emptyset \neq I \subseteq \{1,\dots,n\}} (-1)^{|I|+1}\left|\bigcap_{i\in I} A_i\right|.
> $$

Equivalently,
$$
\left|\bigcup_{i=1}^n A_i\right|
=
\sum_i |A_i|
- \sum_{i<j} |A_i\cap A_j|
+ \sum_{i<j<k} |A_i\cap A_j\cap A_k|
- \cdots
+ (-1)^{n+1}|A_1\cap \cdots \cap A_n|.
$$

For $n=2$
$\lvert A_{1}\cup A_{2} \rvert=\lvert A_{1} \rvert+\lvert A_{2} \rvert-\lvert A_{1}\cap A_{2} \rvert$

For $n=3$: 
$\lvert A_{1}\cup A_{2}\cup A_{3} \rvert=\lvert A_{1} \rvert+\lvert A_{2} \rvert+\lvert A_{3} \rvert-\lvert A_{1}\cap A_{2} \rvert-\lvert A_{2}\cap A_{3} \rvert-\lvert A_{1}\cap A_{3} \rvert+\lvert A_{1}\cap A_{2}\cap A_{3} \rvert$
![[Pasted image 20260224142506.png|214]]

## Proof

Pick an element $x$ and suppose it lies in exactly $r$ of the sets $A_1,\dots,A_n$.

Then on the right-hand side:
- $x$ is counted in exactly $\binom{r}{1}$ single sets,
- subtracted in exactly $\binom{r}{2}$ pairwise intersections,
- added in exactly $\binom{r}{3}$ triple intersections,
- and so on.

So the total contribution of $x$ to the right-hand side is
$$
\binom{r}{1}-\binom{r}{2}+\binom{r}{3}-\cdots+(-1)^{r+1}\binom{r}{r}.
$$

Using
$$
\sum_{k=0}^r (-1)^k\binom{r}{k}=(1-1)^r=0,
$$
we get
$$
\binom{r}{1}-\binom{r}{2}+\binom{r}{3}-\cdots+(-1)^{r+1}\binom{r}{r}=1.
$$

So every element in the union is counted exactly once. An element outside the union has $r=0$, so it contributes $0$ on both sides. Therefore both sides count exactly the same elements with the same multiplicity, which proves the formula.

## Enumerating the subsets in code

In programming problems, the sets in the inclusion-exclusion formula are usually traversed with a **bitmask**.

For `n` sets, every integer `mask` from `1` to `(1 << n) - 1` represents one non-empty subset of $\{1,\dots,n\}$:

- bit `i` is `1` if and only if the subset contains the `i`-th set
- `Integer.bitCount(mask)` gives the size of the subset
- odd subset size means **add** the intersection term
- even subset size means **subtract** the intersection term

For divisibility problems, if $A_i$ is the set of numbers divisible by `a[i]`, then for a chosen subset the intersection size is often computed with the `lcm`:
$$
\left|\bigcap_{i \in I} A_i\right| = \left\lfloor \frac{N}{\mathrm{lcm}(a_i : i \in I)} \right\rfloor.
$$

Example:

```java
public static void testCase() {
    int n = In.readInt();
    long[] a = new long[n];
    for (int i = 0; i < n; i++) {
        a[i] = In.readInt();
    }

    long N = (long) Math.pow(10, 10), res = N;

    for (int mask = 1; mask < (1 << n); mask++) {
        long lcm = 1;
        int bits = Integer.bitCount(mask);

        for (int i = 0; i < n; i++) {
            if ((mask & (1 << i)) != 0) {
                lcm = (lcm * a[i]) / gcd(lcm, a[i]);
            }
        }

        res = bits % 2 == 1 ? res - N / lcm : res + N / lcm;
    }

    Out.println(res);
}

public static long gcd(long a, long b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

Here:

- the loop over `mask` enumerates all non-empty subsets
- `bits` is the subset size
- `lcm` represents the intersection of the chosen divisibility sets
- `N / lcm` is the number of integers in `1..N` divisible by all chosen numbers
- since `res` starts as `N`, this code computes how many integers in `1..N` are divisible by **none** of the numbers in `a`
