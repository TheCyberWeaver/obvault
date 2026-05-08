- Correctness (proof)
- Running time, depends on:
	- input size
	- computer
	- implementation
1. Unit-time random access machine model
2. Asymptotic notation

# RAM model
![[Unit-cost model.excalidraw|533]]

> [!NOTE]
> Elementary operations:
> - read/write one number
> - arithmetic: `+`, `-`, `*`, `/`
> - comparisons: `$<$`, `$=$`, `$\geq$` 

Running time in the RAM model = number of elementary operations.
This corresponds to practical running time up to a ==constant factor==.

# Asymptotic notation

## Definition

> [!NOTE]
> $N = \{n_0, n_0 + 1, \dots\}$ is the set of possible input sizes.
> For $f: N \to \mathbb{R}^+$,
> $O(f) = \{g: N \to \mathbb{R}^+ \mid \text{there exists } C > 0 \text{ such that } g(n) \leq C \cdot f(n) \text{ for all } n \in N\}$.
>
> $O(f)$: order of $f$.
> $g \in O(f) \leftrightarrow \frac{g(n)}{f(n)} \leq C$ (equivalently: the ratio is bounded).

## Example 1
$f(n) = n^2$, $g(n) = 4n^2$

$f \in O(g)$ because
	$n^2 \leq 4n^2$ with $C = 1$.

$g \in O(f)$ because
	$4n^2 \leq 4n^2$ with $C = 4$.

**In general**, for constant $a \in \mathbb{R}^+$:
$$
O(af(n)) = O(f(n))
$$

## Example 2
$f(n) = 100n$, $g(n) = n^2$

$f \in O(g)$ because
	$100n \leq 100n^2$ with $C = 100$, $n \geq 1$.

> [!NOTE]
> $O(n^2)$ is the set of all functions that grow at most quadratically.

# Useful tools
- $\lim_{n \to \infty} \frac{g(n)}{f(n)} = \infty \implies g \notin O(f)$
- $\lim_{n \to \infty} \frac{g(n)}{f(n)} \in \mathbb{R}^+ \implies g \in O(f)$

## Example 1
$f(n) = n^{1.6} + 3n + 4 \in O(n^{1.6})$

$\frac{f(n)}{n^{1.6}} = 1 + 3n^{-0.6} + 4n^{-1.6} < 1 + 3 + 4 = 8$.

## Example 2
Let $a > 0$.

$f(n) = \ln n \in O(n^a)$, because
$$
\lim_{n \to \infty} \frac{\ln n}{n^a}
= \lim_{n \to \infty} \frac{\frac{1}{n}}{an^{a-1}}
= \lim_{n \to \infty} \frac{1}{an^a}
= 0.
$$
