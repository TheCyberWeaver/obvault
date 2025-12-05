#eth #exercise 
# 10.3 Characteristic of a field
##### 1)
By definition of characteristic, $q\times1_{F}=0$
$q\times a=\underbrace{ a+a+\dots a }_{ q\text{ times} }$ 
$=\underbrace{ (1_{F}\star a)+(1_{F}\star a)+\dots+(1_{F}\star a) }_{ q \text{ times} }$
$=(\underbrace{ 1_{F}+1_{F}+\dots+1_{F} }_{ q \text{ times} })\star a$
$=(q\times 1_{F})\star a$
$=0_{F}\star a$
$=0_{F}$
##### 2)
By using the binomial theorem
$(a+b)^{q}=\sum_{k=0}^{q}\begin{bmatrix}	\begin{pmatrix}	q \\ k\end{pmatrix}\times(a^{k}\star b^{q-k})\end{bmatrix}$
So
$(a+b)^{q}=\begin{pmatrix}	q \\ 0\end{pmatrix}a^{q}b^{0}+\begin{pmatrix}	q \\ q\end{pmatrix}a^{0}b^{q}+\sum_{k=1}^{q-1}\begin{bmatrix}	\begin{pmatrix}	q \\ k\end{pmatrix}\times(a^{k}\star b^{q-k})\end{bmatrix}$
$=a^{q}+b^{q}+\sum_{k=1}^{q-1}\begin{bmatrix}	\begin{pmatrix}	q \\ k\end{pmatrix}\times(a^{k}\star b^{q-k})\end{bmatrix}$

We prove that the equation $(a+b)^{q}=a^{q}+b^{q}$ holds by showing $\sum_{k=1}^{q-1}\begin{bmatrix}	\begin{pmatrix}	q \\ k\end{pmatrix}\times(a^{k}\star b^{q-k})\end{bmatrix}=0_{F}$ 
Consider  $\begin{pmatrix}	q \\ k \end{pmatrix}$ for all $1\leq k\leq q-1$

$\begin{pmatrix}	q \\ k\end{pmatrix}=\frac{q(q-1)\cdots(q-k+1)}{k(k-1)\cdots 2\cdot1}$
For all $l\in \{ 1,\dots,k \}$, $gcd(l,q)=1$, because $k$ is smaller than $q$ (so $l<q$), and $q$ is prime.
$\implies$ so the factor $q$ remains, making $\begin{pmatrix}	q \\ k\end{pmatrix}$ a multiple of $q$

If an integer is divisible by $q$ in $\mathbb{Z}$, its image in $F$ is $0_{F}$ (the kernel of the ring homomorphism $\mathbb{Z}\to F$ is $(q)$)
$\implies\begin{pmatrix}	q \\ k\end{pmatrix}=0_{F}$ in $F$
$\sum_{k=1}^{q-1}\begin{bmatrix}	\begin{pmatrix}	q \\ k\end{pmatrix}\times(a^{k}\star b^{q-k})\end{bmatrix}=\sum_{k=1}^{q-1}\begin{bmatrix}	0_{F} \star(a^{k}\star b^{q-k})\end{bmatrix}$ 
$=\sum_{k=1}^{q-1}0_{F}$
$=0_{F}$
Therefore, the $(a+b)^{q}=a^{q}+b^{q}+0_{F}=a^{q}+b^{q}$
The claim is proved.

##### 3)
Let $S_{k}=\sum_{i=1}^{k}a_{i}$ where $k\in \mathbb{N}$, and for all $i \in[k]$, $a_{i}\in F$,
**Claim** (statement P): For all $k\geq1$ and for all $a_{1},\dots,a_{k}\in F$
$$
S_{k}^{q}=\sum_{i=1}^{k} a_{i}^{q}
$$
**Base**: $k=1$
$S_{1}^{q}=\left( \sum_{i=1}^{1}a_{i} \right)^{q}=(a_{1})^{q}=a_{1}^{q}$

**Induction Steps**: $k\to k+1$
$S_{k+1}^{q}=\left( \sum_{i=1}^{k+1}a_{i} \right)^{q}=\left( \sum_{i=1}^{k} a_{i}+a_{k+1}\right)^{q}=\left( S_{k}+a_{k+1} \right)^{q}$
$=S_{k}^{q}+a_{k+1}^{q}$ (using the result from question 2)
$=\left( \sum_{i=1}^{k}a_{i}^{q} \right)+a^{q}_{k+1}$
$=\sum_{i=1}^{k+1}a_{i}^{q}$

Thus, by induction, the claim holds for all $k\in \mathbb{N}$

##### 4)
Let $a$ be  $m\times1_{q}$ where $m\in \mathbb{N}$
$a^{q}=(m\times1_{q})^{q}=\left( \sum_{i=1}^{q} 1_{q} \right)^{q}=\sum_{i=1}^{q} 1_{q}^{q}=\sum_{i=1}^{q} 1_{q}=m\times 1_{q}=a$
The claim is proved.