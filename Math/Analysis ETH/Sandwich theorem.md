## Definition: Sandwich theorem
The sandwich theorem (also called squeeze theorem) says that if a [[Sequence|sequence]] is trapped between two other sequences with the same limit, then it has that limit as well.

> [!NOTE] Theorem
> Let $(a_n),(b_n),(c_n)$ be real sequences and assume $a_n\leq b_n\leq c_n$ for all $n\geq N_0$ for some $N_0\in\mathbb{N}$. If
> $$\lim_{n\to\infty} a_n = L \quad\text{and}\quad \lim_{n\to\infty} c_n = L,$$
> then
> $$\lim_{n\to\infty} b_n = L.$$

## Proof idea
Take any $\varepsilon>0$. Since $a_n\to L$, there is $N_1$ such that $|a_n-L|<\varepsilon$ for all $n>N_1$, so $L-\varepsilon<a_n$. Since $c_n\to L$, there is $N_2$ such that $|c_n-L|<\varepsilon$ for all $n>N_2$, so $c_n<L+\varepsilon$. For $n>\max\{N_0,N_1,N_2\}$:
$$L-\varepsilon<a_n\leq b_n\leq c_n<L+\varepsilon,$$
therefore $|b_n-L|<\varepsilon$, which is exactly [[Sequence#Definition Convergence|convergence]].

### Example
Show that $b_n=\frac{\sin n}{n}$ converges to $0$.
Since $-1\leq\sin n\leq 1$, dividing by $n>0$ gives
$$-\frac{1}{n}\leq\frac{\sin n}{n}\leq\frac{1}{n}.$$
Both bounds converge to $0$, so by the sandwich theorem,
$$\lim_{n\to\infty}\frac{\sin n}{n}=0.$$