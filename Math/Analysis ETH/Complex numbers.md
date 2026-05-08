## Fundamental theorem of algebra

> [!NOTE]
> a polynomial of degree $n\geq1$ has exactly $n$ complex roots.

This implies that complex numbers form an algebraically closed field
## Conjugate
$\overline{(a+ib)}=a-ib$ 
$v^{*}=\bar{v}^{\top}$
$z^{-1}=\frac{\bar{z}}{\lvert z \rvert^{2}}=\frac{a-bi}{a^{2}+b^{2}}$
useful identity: $i^{-1}=-i$

## Example equation
$$
z^{n}=1
$$
${} z_{j}=\cos\left( \frac{2\pi}{n} j \right)+i\sin\left( \frac{2\pi}{n}j \right)=e^{i\cdot2\pi\cdot (j/n)} {}$

## Vector
$v\in \mathbb{C}^{n}\implies v=\begin{pmatrix}	v_{1} \\ v_{2} \\ \vdots \\ v_{n}\end{pmatrix}$ with $v_{i}\in \mathbb{C}$
### Scalar product
$\langle v,w \rangle=w^{*}v=\overline{v^{*}w}$

### Matrix
For $A\in \mathbb{C}^{m\times n}$
#### Hermitian conjugate
Let $A^{*}=\bar{A}^{\top}$ with $\bar{A}=\begin{bmatrix}	\bar{A}_{i,j}\forall_{i,j}\end{bmatrix}\in \mathbb{C}^{m\times n}$

$(AB)^{*}=B^{*}A^{*}$