 #exercise 
# Fitting a parabola 

##### a)
To show that $A$ has full column rank, we can prove that the columns of $A$ are linear independent.
Assume $Ax=0$ for some $x=\begin{bmatrix}x_{1} \\ x_{2} \\ x_{3}\end{bmatrix}$ 
Then we must have $x_{1}t_{i}^{2}+x_{2}t_{i}+x_{3}=0$ for every $i \in[m]$
Since $t_{i}$ are all distinct to each other and $m\geq3$, this quadratic equation must have at least three distinct root. Therefore, $x_{1},x_{2},x_{3}$ must all be zero
Since $x$ is the only possible solution to $Ax=0$ ,$A$ must be linear independent.

**Conversely**: Counterexample
Let $A$ be $\begin{bmatrix} 0 & 0 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \\ 4 & 2 & 1\end{bmatrix}$ where $t_{1}=0,t_{2}=1,t_{3}=1,t_{4}=2$
The matrix $A$ has full rank 3 but $t_{2}=t_{3}$, which contradicts the claim

##### b)
$$
\begin{bmatrix} 4 & -2 & 1 \\ 1 & -1 & 1 \\
0 & 0 & 1 \\
1 & 1 & 1 \\
4 & 2 & 1 \end{bmatrix}\begin{bmatrix}
\alpha_{2} \\
\alpha_{1} \\
\alpha_{0}
\end{bmatrix}=\begin{bmatrix}
3 \\
2 \\
1 \\
4 \\
5
\end{bmatrix}
$$
$\begin{bmatrix}\alpha_{2} \\ \alpha_{1} \\ \alpha_{0}\end{bmatrix}=(A^{\top}A)^{-1}A^{\top}b=\begin{bmatrix} \frac{4}{7} \\ \frac{3}{5} \\ \frac{13}{7}\end{bmatrix}$

**Uniqueness**: yes. Because $A$ has full column rank, $A^{\top}A$ is invertible, so it has exactly one result, hence the least-squares minimizer is unique.
