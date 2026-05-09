 #exercise 
# 2. Nullspace and column space 

##### a)
$A^{2}=(\mathbf{v}\mathbf{v}^{\top})(\mathbf{v}\mathbf{v}^{\top})=\mathbf{v}(\mathbf{v}^{\top}\mathbf{v})\mathbf{v}^{\top}=\mathbf{v}\lVert \mathbf{v} \rVert^{2}\mathbf{v}^{\top}=\mathbf{v}\mathbf{v}^{\top}=A$
$P^{2}=(I_{3}-A)(I_{3}-A)=I_{3}^{2}-2I_{3}A+A^{2}=I_{3}-2A+A=I_{3}-A=P$
##### b)
$\mathbf{w} \text{ is orthogonal to }\mathbf{v}\implies\mathbf{v}^{\top}\mathbf{w}=0\implies \mathbf{v}\mathbf{v}^{\top}\mathbf{w}=\mathbf{v} 0=0\implies A\mathbf{w}=0$
##### c)
$A\mathbf{w}=0\implies \mathbf{v}\mathbf{v}^{\top}\mathbf{w}=0\implies \mathbf{v}^{\top}\mathbf{v}\mathbf{v}^{\top}\mathbf{w}=\mathbf{v}^{\top}0=0\implies \lVert \mathbf{v} \rVert^{2}\mathbf{v}^{\top}\mathbf{w}=0\implies \mathbf{v}^{\top}\mathbf{w}=0$
$\implies \mathbf{v}\cdot\mathbf{w}=0\implies \mathbf{w}\cdot \mathbf{v}=0$
##### d)
$\mathbf{N}(A)=\{ \mathbf{w}\in \mathbb{R}^{3}| \mathbf{v}^{\top}\mathbf{w}=0 \}$

##### e)
the rank of $A$ is 1
$A$ is not invertible

##### f)
$C(A)=\{ A\mathbf{w}|\mathbf{w}\in \mathbb{R}^{3} \}=\{ \mathbf{v}\mathbf{v}^{\top}\mathbf{w}|\mathbf{w}\in \mathbb{R}^{3} \}=\{ (\mathbf{v}^{\top}\mathbf{w})\mathbf{v}|\mathbf{w}\in \mathbb{R}^{3} \}=\{ \alpha \mathbf{v}|\alpha \in \mathbb{R} \}=span(\mathbf{v})$
##### g)
Let $\mathbf{y}\in \mathbf{C}(A)$ 
$\mathbf{y}=A\mathbf{x}$ for some $\mathbf{x}\in \mathbb{R}^{3}$ 
$\implies A\mathbf{y}=A^{2}\mathbf{x}\implies A\mathbf{y}=A\mathbf{x}=\mathbf{y}$
$\mathbf{y}\in \{ \mathbf{w}\in \mathbb{R}^{3}|A\mathbf{w}=\mathbf{w} \}$

Conversely,
Let $A\mathbf{w}=\mathbf{w}$, then $\mathbf{w}=A\mathbf{w}\in \mathbf{C}(A)$
Thus $\mathbf{C}(A)=\{ \mathbf{w}\in \mathbb{R}^{3}|A\mathbf{w}=\mathbf{w} \}$
##### h)
Let $\mathbf{w}\in \mathbf{N}(P)$
$\Longleftrightarrow P\mathbf{w}=0$
$\Longleftrightarrow (I_{3}-A)\mathbf{w}=0$
$\Longleftrightarrow I_{3}\mathbf{w}-A\mathbf{w}=0$
$\Longleftrightarrow \mathbf{w}-A\mathbf{w}=0$
$\Longleftrightarrow \mathbf{w}=A\mathbf{w}$
$\implies \mathbf{N}(P)=\{ \mathbf{w} \in \mathbb{R}^{3}| A\mathbf{w}=\mathbf{w}\}=C(A)$
##### i)
First we prove $\mathbf{C}(P)\subseteq \mathbf{N}(A)$
Let $\mathbf{w}\in \mathbf{C}(P)$
$\implies\mathbf{w}=P\mathbf{x}$ for some $\mathbf{x}\in \mathbb{R}^{3}$
$\implies \mathbf{w}=(I_{3}-A)\mathbf{x}$
$\implies A\mathbf{w}=A(I_{3}-A)\mathbf{x}=(A-A^{2})\mathbf{x}=(A-A)\mathbf{x}=0\mathbf{x}=0$
Thus $\mathbf{w}\in \mathbf{N}(A)$

Then we prove $\mathbf{N}(A)\subseteq \mathbf{C}(P)$
Let $\mathbf{w}\in \mathbf{N}(A)$
$\implies A\mathbf{w}=0$
$\implies P\mathbf{w}=(I_{3}-A)\mathbf{w}=\mathbf{w}-A\mathbf{w}=\mathbf{w}-0=\mathbf{w}$
$\implies \mathbf{w}\in \mathbf{C}(P)$

Since $\mathbf{C}(P)\subseteq \mathbf{N}(A)$ and $\mathbf{N}(A)\subseteq \mathbf{C}(P)$, $\mathbf{C}(P)=\mathbf{N}(A)$