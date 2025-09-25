
### 1. Fundamental Properties
- **Multilinearity** in rows (or columns): linear in each row separately.  
- **Alternating**: if two rows are equal, $\det=0$.  
- **Normalization**: $\det(I_n) = 1$.  
- **Product rule**:  
  $$
  \det(AB) = \det(A)\,\det(B).
  $$
- **Transpose invariance**:  
  $$
  \det(A^T) = \det(A).
  $$
- **Invertibility criterion**:  
  $$
  A\text{ is invertible}\;\iff\;\det(A)\neq 0.
  $$
### 2. Equivalent Statements to $\det(A)\neq 0$
- **Invertibility**  
  $A$ is invertible (i.e. there exists $A^{-1}$).
- **Full rank**  
  $\mathrm{rank}(A)=n$.
- **Trivial kernel**  
  $\ker(A)=\{0\}$.
- **Homogeneous system**  
  The only solution of $A x=0$ is the trivial one, $x=0$.
- **Unique solvability**  
  For every $b\in\mathbb R^n$, the equation $A x=b$ has exactly one solution.
- **Linear independence of columns**  
  The columns of $A$ form a basis of $\mathbb R^n$.
- **Linear independence of rows**  
  The rows of $A$ form a basis of $\mathbb R^n$.
- **Bijectivity of the associated map**  
  The linear map $T:\mathbb R^n\to\mathbb R^n,\;T(x)=Ax$ is bijective.
- **Eigenvalue condition**  
  $0$ is not an eigenvalue of $A$.
- **Characteristic polynomial**  
  If $p_A(\lambda)=\det(\lambda I - A)$, then $p_A(0)\neq0$.
- **Minimal polynomial**  
  The minimal polynomial of $A$ does not have $0$ as a root.
- **Adjugate formula**  
  $\operatorname{adj}(A)$ exists and  $A^{-1} \;=\;\frac{1}{\det A}\,\operatorname{adj}(A).$

- **LU-decomposition without pivoting**  
  $A$ admits an $LU$ factorization with no row exchanges.

- **Volume interpretation**  
  As the linear map’s oriented-volume scale factor, $\det A$ is nonzero iff the map is volume–nondegenerate.

### 3. Computation Methods
- **Laplace (cofactor) expansion** along any row or column.  
- **Row-reduction** to upper triangular form:  
  $$
  \det(A) = (\text{product of pivots})\times(-1)^{\#\text{swaps}}.
  $$
- **LU decomposition**: if $A=LU$ with unit-lower $L$, then $\det(A)=\prod\mathrm{diag}(U)$.

### 4. Cofactor & Adjugate
- **Cofactor** $C_{ij} = (-1)^{i+j}\det(M_{ij})$.  
- **Adjugate** $\operatorname{adj}(A) = [C_{ji}]$.  
- **Inverse formula** (when $\det(A)\neq0$):  
  $$
  A^{-1} = \frac{1}{\det(A)}\,\operatorname{adj}(A).
  $$

### 5. Cramer’s Rule
For $A\mathbf{x}=\mathbf{b}$,  
$$
x_i = \frac{\det(A_i)}{\det(A)},
$$
where $A_i$ replaces the $i$th column of $A$ with $\mathbf{b}$.

### 6. Effect of Elementary Operations
- **Row swap**: flips sign, $\det\mapsto -\det$.  
- **Scaling a row** by $\alpha$: multiplies $\det$ by $\alpha$.  
- **Adding a multiple** of one row to another: leaves $\det$ unchanged.

### 7. Geometric Interpretation
- $\det(A)$ is the **oriented volume** scaling factor of the linear map $A:\mathbb{R}^n\to\mathbb{R}^n$.  
- $\det(A)>0$ preserves orientation; $\det(A)<0$ reverses it.

