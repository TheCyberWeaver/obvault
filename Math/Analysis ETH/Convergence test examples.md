## Example
Consider
$$
\sum_{n=2}^{\infty} \frac{3n+\sin(n)}{n^{3}-n^{2}}
$$

We compare with the p-series $\sum \frac{1}{n^2}$.

Since $|\sin(n)|\le 1$,
$$
|3n+\sin(n)|\le 3n+1\le 4n \qquad (n\ge1)
$$

Also,
$$
n^3-n^2=n^3\left(1-\frac{1}{n}\right)
$$
For $n\ge2$,
$$
1-\frac{1}{n}\ge 1-\frac{1}{2}=\frac{1}{2}
$$
so we can take $c=\frac{1}{2}$ and get
$$
n^3-n^2\ge \frac{1}{2}n^3 \qquad (n\ge2)
$$

Hence for $n\ge2$,
$$
\left|\frac{3n+\sin(n)}{n^3-n^2}\right|
\le \frac{4n}{\frac{1}{2}n^3}
= \frac{8}{n^2}
$$

Since $\sum_{n=2}^{\infty}\frac{8}{n^2}$ converges by the [[Series convergence#p-Series Test|p-series test]], the comparison test gives
$$
\sum_{n=2}^{\infty} \frac{3n+\sin(n)}{n^{3}-n^{2}}
$$
converges absolutely.
