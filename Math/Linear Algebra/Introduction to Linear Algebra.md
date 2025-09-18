---
email: anguhl@ethz.ch
---

## Linear combination

Let $\mathbf{v},\mathbf{w}\in \mathbb{R}^{m}$
$\lambda \mathbf{v} + \mu \mathbf{w}\in \mathbb{R}^m$

> [!PDF|note] [[Linear Algebra ETH.pdf#page=17&selection=339,0,344,42&color=note|Linear Algebra ETH, p.16]]
> > Every vector in $\mathbb{R}^{2}$ is a linear combination of the two vectors $\mathbf{v}=\begin{pmatrix}2 \\ 3\end{pmatrix},\mathbf{u}=\begin{pmatrix}3 \\ -1\end{pmatrix}$
> 
> 

***Proof***
trivial,
$\lambda \begin{pmatrix}2 \\ 3\end{pmatrix}+\mu \begin{pmatrix}3 \\ -1\end{pmatrix}=\begin{pmatrix}u_{1} \\ u_{2}\end{pmatrix}$
Both $\lambda$ and $\mu$ can be solved in terms of $u_{1}$ and $u_{2}$


### special linear combination

- affine: $\lambda_{1}+\lambda_{2}+\dots+\lambda_{n}=1$
	- $\lambda+\mu=1$
	- $\lambda \mathbf{v} + \mu \mathbf{w}$
	- $\lambda \mathbf{v}+\mathbf{w}-\lambda \mathbf{w}$
	- $\mathbf{w}+\lambda (\mathbf{v}-\mathbf{w})$
- conic: $\lambda\geq 0$ for $j=1,2,\dots ,n$
- convex: if it is both a affine and a conic combination ![[Pasted image 20250918090441.png]]