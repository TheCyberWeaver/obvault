## 1. Subspaces of function spaces and $\mathbb{R}^{m\times m}$
##### a)
- Non-empty: all constant function $f\in U$
- closed under addition: $f,g\in U$, arbitrary $x \in[0,1]$
	- $(f+g)(x)=f(x)+g(x)=f(1-x)+g(1-x)=(f+g)(1-x)$
- closed under scalar multiplication: $f,g\in U$, $\alpha \in \mathbb{R}$, arbitrary $x \in[0,1]$
	- $(\alpha f)(x)=\alpha f(x)=\alpha f(1-x)=(\alpha f)(1-x)$
$\implies U$ is a subspace

##### b)
$\text{dim} (\mathcal{D}_{m})=m$
**Proof**:
For $i\in[m]$ let $E_{ii}$ be the $m\times m$ matrix with 1 at $(i,i)$ and 0 elsewhere
We try to prove that $\{ E_{ii}|i\in[m] \}$ is the basis of $\mathcal{D}_{m}$
- Spanning: Any diagonal matrix can be expressed as $\sum_{i=1}^{n}c_{i}E_{ii}$ for $c_{i}\in \mathbb{R}$
- Linear independence: Consider the equation $\sum_{i=1}^{n}d_{i}E_{ii}=\mathbf{0}=\begin{bmatrix}d_{1} & 0 & \dots & 0 \\ 0 & d_{2} & \dots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \dots & d_{n}\end{bmatrix}$. 
	- $d_{i}$ must be zero, which shows the linear independence of 
$\implies$ $\{ E_{ii}|i\in[m] \}$ is the basis of $\mathcal{D}_{m}$
Since the dimension is the cardinality of a basis. $\text{dim} (\mathcal{D}_{m})=|\{ E_{ii}|i\in[m] \}|=m$

#eth #exercise 
## 2. Skew-symmetric matrices as a subspace
![[Pasted image 20251104223621.png]]

##### a)
we prove the claim by showing the following statements (using the definition of Subspaces)
- for all $A,B\in S_{m}$ we have $A+B\in S_{m}$ 
	- $A+B\overset{ def }{ = }-A^{\top}+(-B^{\top})$
	- $\implies A+B=-(A^{\top}+B^{\top})$ 
	- $\implies A+B=-(A+B)^{\top}$ 
	- $\implies A+B$ is a skew-symmetric matrix and thus $A+B\in S_{m}$ 
- for all $A\in S_{m}$ and $\lambda \in \mathbb{R}$ we have $\lambda A\in S_{m}$
	- $\lambda A=\lambda(-A^{\top})=-\lambda A^{\top}=-(\lambda A^{\top})=-(\lambda A)^{\top}$
	- $\implies \lambda A$ is a skew-symmetric matrix and thus $\lambda A\in S_{m}$
Hence, $S_{m}$ is a subspace of $\mathbb{R}^{m\times m}$

##### b)
The dimension of $S_{m}$ is $\frac{m^{2}-m}{2}$

We define:
$$
A_{xy}=[a_{ij}]_{m\times m},\quad a_{ij}=\begin{cases}
1,\; \text{if }i=x \text{ and } j=y, \\
0, \; \text{otherwise} \\
-1, \; \text{if } i=y \text{ and }j=x 
\end{cases}
$$
We prove the set $A=\{A_{xy} \;|\; x,y\in[m], y>x\}$ is a basis of $S_{m}$
- This set spans $S_{m}$
	- For any matrix $B$ in $S_{m}$ we can write $B$ as a linear combination of the matrices $A_{ij}$ 
	- $$ B=\sum_{1\leq i<j\leq m}  b_{ij}A_{ij} $$
	- so the $(i,j)$-th entry is $b_{ij}$ ($i<j$), and the $(j,i)$-th entry is $-b_{ij}$, matching the structure of $B$
	- Therefore $A$ spans $S_{m}$
- This set $A$ is linear independent
Assume 
$$
\sum_{1\leq x<y\leq m}c_{xy}A_{xy}=0 
$$
Consider the $i,j$-entry with $i<j$. 
Since only $A_{ij}$ has a nonzero  element in that position, we obtain $c_{ij}=0$
This holds for all $i<j$
Hence all coefficient $c_{ij}$ are zero, and the set $A$ is linear independent.
**Conclusion**
Now we have a basis of $S_{m}$
The size of this basis is the number of elements on top of the diagonal of a matrix in $\mathbb{R}^{m\times m}$, which can be calculated by $\frac{m(m-1)}{2}=\frac{m^{2}-m}{2}$
