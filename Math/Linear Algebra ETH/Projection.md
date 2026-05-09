---
tags:
  - linker-exclude
---
## Definition
Let $S$ be a subspace of $\mathbb{R}^{m}$
$$
proj _{S}(b)=\underset{ p \in S }{ argmin }\lVert b-p \rVert 
$$
> [!Question]
> - Does there always exist a minimum?
> - Is $proj _{S}(b)$ unique?

## One-dimensional case
$S$ is a one dimensional subspace in $\mathbb{R}^{n}$
This means: $S=\{ \lambda a|\lambda \in \mathbb{R} \}=C(a)$ and $a\in \mathbb{R}^{m}$ with $a\neq0$
We know $b\in \mathbb{R}^{m}$
Hypothesis: $proj _{S}(b)=\lambda ^{*}a$ with $\lambda ^{*}\in \mathbb{R}$
$b-proj _{S}(b)$ is orthogonal to $proj _{S}(b)$ 
(See proof below)

### Lemma 5.2.2
$\text{proj}_{C(a)}(b)=\lambda ^{*}a$
$\lambda ^{*}=\frac{a^{\top}b}{\lVert a \rVert^{2}}$ (see the proof below)
$\text{proj}_{S}(b)=\frac{a^{\top}b}{\lVert a \rVert^{2}}a=\frac{a^{\top}b}{a^{\top}a}a=\frac{aa^{\top}}{a^{\top}a}b$

**Proof**: $b-proj _{S}(b)$ is orthogonal to $proj _{S}(b)$
$\Longleftrightarrow a^{\top}\left( b-\frac{a^{\top}b}{a^{\top}a}a \right)=a^{\top}b-\frac{a^{\top}b}{a^{\top}a}a^{\top}a=a^{\top}b-a^{\top}b=0$

**Proof**: Lemma 5.2.2
$\lVert b-p \rVert^{2}=(b-p)^{\top}(b-p)=b^{\top}b-2b^{\top}p+p^{\top}p=b^{\top}b-2b^{\top}\lambda a+\lambda^{2}a^{\top}a=g(\lambda)$ (recall that $a^{\top}b=b^{\top}a$)
$g'(\lambda)=-2a^{\top}b+2\lambda a^{\top}a=0 \Longleftrightarrow \lambda=\frac{a^{\top}b}{a^{\top}a}$

If $S=\{ a\cdot\lambda|\lambda \in \mathbb{R} \}$ and $a\in \mathbb{R}^{m}\setminus \{ 0 \}$, then $\text{proj}_{S}(b)=\frac{1}{\lVert a \rVert^{2}}a\cdot a^{\top}b$

## General case

Consider $S\subseteq \mathbb{R}^{m}$
Let $a_{1},\dots,a_{n}\in \mathbb{R}^{m}$
Let $S=\left\{ \sum_{i=1}^{n}a_{i}\lambda _{i}|\lambda_{1},\dots,\lambda _{n}\in \mathbb{R} \right\}=\{ A\cdot \lambda \}|\lambda \in \mathbb{R}^{n}$
$A=[a_{1}|a_{2}|\dots|a_{n}]$

### Lemma 5.2.3
The projection of $b\in \mathbb{R}^{m}$ on $S=C(A)$ is a vector $A\cdot \hat{x},\hat{x}\in \mathbb{R}^{n}$ with $A^{\top}A\hat{x}=A^{\top}b$

- [ ] Proof

![[Invertible matrices#Lemma 5.2.4]]
Since $A^{\top}A$ is invertible, according to [[#Lemma 5.2.3]], $\text{proj}_{S}(b)=A\hat{x}=A(A^{\top}A)^{-1}A^{\top}b$
### Theorem 5.2.5

$$
\text{proj}_{S}(b)=Pb \text{ with } P=A(A^{\top}A)^{-1}A^{\top}\in \mathbb{R}^{m\times m}
$$
Remark
$PA=A(A^{\top}A)^{-1}A^{\top}A=A(A^{\top}A)^{-1}(A^{\top}A)=A$

## Least Square (Data Fitting)
When $\lVert A\hat{x}-b \rVert^{2}$ is minimal (OR we can write $\lVert b-\text{proj}_{S}(b) \rVert^{2}$)
$\hat{x}$ is the least square solution
$A^{\top}A\hat{x}=A^{\top}b$
$\hat{x}=(A^{\top}A)^{-1}A^{\top}b$
### Application: Linear Regression
![[Pasted image 20251112112741.png|423]]

Data: $(t_{k},b_{k})$ where $k=1,\dots,m$

We want to find $min\left\{ \sum_{k=1}^{m}(b_{k}-\alpha_{0}-\alpha_{1}t_{k})^{2}|\alpha_{0},\alpha_{1}=\mathbb{R} \right\}$
$\underset{ x }{ min }\lVert Ax-b \rVert^{2}$
Solution:
$$
\begin{bmatrix}
\alpha_{0} \\
\alpha_{1} 
\end{bmatrix}=(A^{\top}A)^{-1}A^{\top}b=\begin{bmatrix}
m & \sum_{k=1}^{m} t_{k} \\
\sum_{k=1}^{m} t_{k} & \sum_{k=1}^{m} t^{2}_{k}
\end{bmatrix}^{-1}\begin{bmatrix}
\sum_{k=1}^{m} b_{k} \\
\sum_{k=1}^{m} b_{k}t_{k}
\end{bmatrix}
$$

We can extend this method to cubic, quadratic...
