---
tags:
  - linker-exclude
---
A function $f:D\to \mathbb{R}$ with $D\subseteq \mathbb{R}$ is **continuous at a point** $x_{0}\in D$ if small changes in the input lead to arbitrarily small changes in the output.

> [!NOTE] Definition
> Let $f:D\to \mathbb{R}$ and $x_{0}\in D$. Then $f$ is continuous at $x_{0}$ if
> $$
> \forall{\varepsilon>0}\; \exists{\delta>0}\; \forall{x\in D}:\; |x-x_{0}|<\delta \Rightarrow |f(x)-f(x_{0})|<\varepsilon
> $$

This means that for every prescribed output tolerance $\varepsilon$, we can choose an input tolerance $\delta$ such that all points $x$ sufficiently close to $x_{0}$ are mapped to values sufficiently close to $f(x_{0})$

> [!NOTE] Definition
> Let $f:D\to \mathbb{R}$. Then $f$ is continuous on $D$ if
> $$
> \forall{x_{0}\in D}\; \forall{\varepsilon>0}\; \exists{\delta>0}\; \forall{x\in D}:\; |x-x_{0}|<\delta \Rightarrow |f(x)-f(x_{0})|<\varepsilon
> $$

## Sequential characterization
The function $f:D\to \mathbb{R}$ is continuous at $x_{0}\in D$ if and only if for every sequence $(x_{n})_{n\geq1}$ in $D$ with $x_{n}\to x_{0}$, we have
$$
f(x_{n})\to f(x_{0}).
$$

The definition of [[Sequence#Definition Convergence|convergence of sequences]] has the same logical structure: the index $n$ plays the role of the input variable, and $n\to\infty$ is the discrete analogue of a function limit. In this sense, sequence convergence is a special case of the general idea of limits.
## Limits
### Limit at $+\infty$
We write
$$
\lim_{x\to+\infty}f(x)=L
$$
if
$$
\forall{\varepsilon>0}\; \exists{R>0}:\; \forall{x\in D}:\; x>R \implies |f(x)-L|<\varepsilon
$$

### Right-hand limit
We write
$$
\lim_{x\to x_{0}^{+}}f(x)=L
$$
if
$$
\forall{\varepsilon>0}\; \exists{\delta>0}:\; \forall{x\in D\cap(x_{0},x_{0}+\delta)}:\; |f(x)-L|<\varepsilon
$$

Here $x$ approaches $x_{0}$ only from the right.
