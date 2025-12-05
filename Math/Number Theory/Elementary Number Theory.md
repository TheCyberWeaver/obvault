# Problem 1
**Problem**
Find all $n\in \mathbb{N}\setminus \{ 0 \}$ such that $(n+1)|(n^{2}+1)$
**Solution**
$\overset{ def }{ \implies } \exists x\; (x(n+1)=n^{2}+1)$
There are three obvious cases:
$$
\begin{cases}
x\leq n-1\implies x(n+1)\leq n^{2}-1<n^{2}+1 \text{ contradiction} \\
x=n \implies x(n+1)=n^{2}+n=n^{2}+1\implies n=1\\
x\geq n+1\implies x(n+1)\geq n^{2}+2n+1>n^{2}+1 \text{ contradiction}
\end{cases}
$$
This technique can be used in finding many integer equation systems (Diophantine equations).


