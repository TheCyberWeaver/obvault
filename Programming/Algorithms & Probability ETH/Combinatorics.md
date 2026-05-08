## Cheat Sheet
Many [[Probability Space#Laplace Space|Laplace Space]] calculations reduce to counting.

### 1. Ordered selection with replacement
Choose $k$ times from $n$ options, order matters, repetition allowed:
$$
n^k
$$

Example: PIN codes, repeated die rolls.

### 2. Ordered selection without replacement
Choose $k$ distinct objects from $n$, order matters:
$$
n(n-1)\cdots(n-k+1) = \frac{n!}{(n-k)!}
$$

This is the number of $k$-permutations.

### 3. Unordered selection without replacement
Choose $k$ distinct objects from $n$, order does not matter:
$$
\binom{n}{k} = \frac{n!}{k!(n-k)!}
$$

Example: 5-card hands from a deck.

### 4. Unordered selection with replacement
Choose $k$ objects from $n$ types, order does not matter, repetition allowed:
$$
\binom{n+k-1}{k}
$$

This is the **stars and bars** formula.