#eth #exercise 
# 2.  Characterizing solvability via null spaces
![[Pasted image 20251125192201.png]]

> [!Quote] Theorem 6.2.4
> $$
> \{ x \in \mathbb{R}^{n}|Ax=b \}=\varnothing\Longleftrightarrow\{ z\in \mathbb{R}^{m}|A^{\top}z=0,b^{\top}z=1 \}\neq \varnothing
> $$

$EQ$ has a solution for every $c$ $\implies$ $N(A^{\top})\cap N(B^{\top})=\{ 0 \}$

Let $M=\begin{bmatrix}	A & B\end{bmatrix}\in \mathbb{R}^{m\times(n_{1}+n_{2})}$ and $u=\begin{pmatrix}	x \\ y\end{pmatrix}\in \mathbb{R}^{n_{1}+n_{2}}$
we can write EQ as $Mu=c$
Assume for every $c$ there exists a $u$, then for every c:
$\{ u|Mu=c \}\neq \varnothing$
$\implies \{ z\in \mathbb{R}^{m}|M^{\top}z=0,c^{\top}z=1 \}=\varnothing$ (Theorem 6.2.4)
We show this by using contradiction
Suppose there exists a nonzero $z_{0}$ with $A^{\top}z_{0}=0$ and $B^{\top}z_{0}=0$
then $M^{\top}z_{0}=\begin{pmatrix}	A^{\top} \\ B^{\top}\end{pmatrix}z_{0}=0$
so $z_{0}\in N(M^{\top})$
Since $z_{0}\neq0$ then we can choose some $c$ such that $c^{\top}z_{0}=1$, which means $z_{0}\in\{ z\in \mathbb{R}^{m}|M^{\top}z=0,c^{\top}z=1 \}$. This is a contradiction to $\{ z\in \mathbb{R}^{m}|M^{\top}z=0,c^{\top}z=1 \}=\varnothing$
Therefore $N(M^{\top})=\{ 0 \}$ 
note that, for every $z$, $M^{\top}z=0\Longleftrightarrow\begin{pmatrix}	A^{\top}z \\ B^{\top}z\end{pmatrix}=0\Longleftrightarrow A^{\top}z=0\wedge B^{\top}z=0$
So $N(M^{\top})=N(A^{\top})\cap N(B^{\top})$
Together with $N(M^{\top})=\{ 0 \}$ we get $N(A^{\top})\cap N(B^{\top})=\{ 0 \}$

$N(A^{\top})\cap N(B^{\top})=\{ 0 \}\implies$ $EQ$ has a solution for every $c$ 

we define $M$ and $u$ just like in the last section.
we know from last part $N(A^{\top})\cap N(B^{\top})=\{ 0 \}\implies N(M^{\top})=\{ 0 \}$ 
we also know that $\{ u|Mu=c \}= \varnothing\Longleftrightarrow \implies \{ z\in \mathbb{R}^{m}|M^{\top}z=0,c^{\top}z=1 \}\neq\varnothing$ (Theorem 6.2.4)
Let $c$ be an arbitrary vector in $\mathbb{R}^{m}$:
Assume $Mu=c$ has no solution, then there must exist at least one $z$ such that $M^{\top}z=0$ and $c^{\top}z=1$.
But $M^{\top}z=0$ means $z\in N(M^{\top})$, so $z=0$
However, $c^{\top}0=0$ contradicts our assumption, which means $Mu=c$ must have at least a solution.
Equivalently there exists $x,y$ such that $Ax+By=c$ for every $c$

**Conclusion**
We proved the claim in both direction, so the claim holds.