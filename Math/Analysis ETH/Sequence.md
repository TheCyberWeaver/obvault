A **sequence** of [[Real numbers|real numbers]] is a function $f:\mathbb{N}\to \mathbb{R}$
we denote it as $(a_{n})_{n\geq0}$ with $a_{n}=a(n)$ 
we can define a sequence either recursive or exclusive

## Operations
Let $(a_{n}),(b_{n})$ be two convergent sequence with $\lim_{ n \to \infty }a_{n}=a$ and $\lim_{ n \to \infty }b_{n}=b$
Then:
- $\lim_{ n \to \infty }(a_{n}\pm b_{n})=a\pm b$
- $\lim_{ n \to \infty }(a_{n}b_{n})=ab$
- If $b_{n}\neq 0\forall{n\geq0}\; \wedge b\neq0$ then $\lim_{ n \to \infty }\left( \frac{a_{n}}{b_{n}} \right)=\frac{a}{b}$
- If there is $K>1$ such that $a_{n}>b_{n}\forall{n\geq K}\;$ then $a>b$

## Definition: Convergence 
A sequence $(a_{n})_{n\geq1}$ converges to a limit $l\in \mathbb{R}$ if for any arbitrarily small distance $\varepsilon$, we can find a point in the sequence beyond which all subsequent terms are within that distance of the limit. 

> [!NOTE] Theorem
> A sequence $(a_{n})_{n\geq1}$ converges to a limit $l\in \mathbb{R}$ if $\forall{\varepsilon>0}\; \exists{N\in \mathbb{N}}\; \forall{n>N}\; (\lvert a_{n}-l \rvert<\varepsilon)$

The limit of a convergent sequence is unique, can be prove by contradiction

We can find similarities to the definition of [[Convergence#Definition Convergence|convergence]] in a topology space

Every convergent sequence is a [[Cauchy sequence]]. In [[Real numbers]], the converse also holds because of completeness.

## How to prove convergence
To prove a convergence property, we usually focus on finding a suitable $N$ for a given $\varepsilon$ without explicitly dealing with the set of indices
### Example
$a_{n}=\frac{n}{n+1}$ and we try to prove $\lim_{ n \to \infty }a_{n}=1$
$\lvert a_{n}-1 \rvert=\left\lvert \frac{n}{n+1}-1 \right\rvert=\left\lvert -\frac{1}{n+1} \right\rvert=\frac{1}{n+1}\implies\varepsilon> \frac{1}{N+1}$
Given $\varepsilon>0$ there exists $N$ such that $N> \frac{1}{\varepsilon}-1$ (by [[Real numbers#Corollary Archimedean Principle|Archimedean principle]]). Then for all $n>N$, we have $n+1>N+1> \frac{1}{\varepsilon}$, so $\frac{1}{n+1}<\varepsilon$. Thus $\lvert a_{n}-1 \rvert<\varepsilon$ for all $n>N$. This proves that $a_{n}$ converges to $1$

## Divergence
- positive: $\forall{M>0}\; \exists{N>0}\; \forall{n>N}:a_{n}>M$
- negative: $\forall{M>0}\; \exists{N>0}\; \forall{n>N}:a_{n}<-M$
