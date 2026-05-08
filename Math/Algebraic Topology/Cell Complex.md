## Notation
$e^{n}$ is an n cell, homeomorphic to the open n disk $D^{n}-\partial D^{n}$ or $D^{n}-S^{n-1}$ or $Int(D^{n})$
## Construction
- We start from a discrete set $X^{0}$ (0-cells)
-  form the **n-skeleton** $X^{n}$ from $X^{n-1}$ by attaching $n$-cells $e^{n}$ via the *attaching map* 
$$
	\varphi _{\alpha}:S^{n-1}\to X^{n-1}
$$
For example we construct $X^{1}$ from $X^{0}$ by adding edges ($1$-cells) between discrete points. Each attaching map is $\varphi _{\alpha}:S^{0}\to X^{0}$ (remember that $S^{0}$ is two points). Here $S^{0}$ is the boundary of the $1$-cells that will be attached
We now have the new space
$$
X^{n}=X^{n-1}\coprod _{\alpha}e^{n}_{\alpha} \; \text{, for each }   \alpha
$$
or more formally 
$$
X^{n}=(X^{n-1}\sqcup \coprod _{\alpha} D^{n}_{\alpha})/\sim \;,\; x\sim\varphi _{\alpha}(x) \text{ with } x \in D^{n}_{\alpha}
$$
In the end we get $X^{0}\subset X^{1}\subset X^{2}\subset\dots \subset X$
## Example
a 1-dimensional cell complex $X=X^{1}$ is a **graph**
![[Pasted image 20260422235453.png|465]]
A 2-dimensional cell complex $X=X^{2}$
![[Pasted image 20260422235418.png|488]]

## characteristic map
$$
\Phi _{\alpha}:D^{n}_{\alpha}\to X
$$
This can be seen as a composition of maps
$$
D^{n}_{\alpha}\hookrightarrow X^{n-1}\coprod _{\alpha}D^{n}_{\alpha}\to X^{n}\hookrightarrow X^{n}
$$
the middle map is the quotient map defining $X^{n}$

## Subcomplex
A **subcomplex** of a CW complex $X$ is a subspace $A$ formed by a collection of cells of $X$ such that it is still a complex. This means once you include a cell, you must also include all lower-dimensional cells on which its boundary is attached.

We call $(X,A)$ a *CW pair*
## Operations
### Products
If $X$ and $Y$ are cell complexes, then $X \times Y$ is also a cell complex, whose cells are exactly the products $e_\alpha^m \times e_\beta^n$, where $e_\alpha^m$ is a cell of $X$ and $e_\beta^n$ is a cell of $Y$.
> [!Warning]
> The topology on $X\times Y$ as a cell complex could be finer than the product topology. The two topology coincide if either $X$ or $Y$ has finitely many cells, or both $X$ and $Y$ have countably many cells. We could ignore the difference in most of the cases.

### Quotients
Let $(X,A)$ be a CW pair
$X/A$ means collapsing the subcomplex $A$ into a single point (a $0$-cell)
This single point is also the image of $A$ in $X/A$ 

### Others
The **suspension** of $X$ is obtained by stretching $X$ between two new points: a north pole and a south pole. Or stretching $X$ into a cylinder and then collapsing both end faces to points.
Formally,
$$
\Sigma X = (X \times I) / (X \times \{0\} \sim \ast_S,\; X \times \{1\} \sim \ast_N).
$$
![[Pasted image 20260507220141.png|164]]
The **join** $X * Y$ connects every point of $X$ to every point of $Y$ by a line segment. Formally,
$$
X * Y = (X \times Y \times I)/\sim,
$$
where $(x,y_1,0) \sim (x,y_2,0), \quad (x_1,y,1) \sim (x_2,y,1).$
![[Pasted image 20260507220101.png|240]]
The **wedge sum** glues two based spaces together at their basepoints:
$$
X \vee Y = (X \sqcup Y)/(\ast_X \sim \ast_Y).
$$
![[Pasted image 20260507220250.png|326]]
The **smash product** is like the product $X \times Y$, but we collapse the parts where one coordinate is the basepoint:
$$
X \wedge Y = (X \times Y)/(X \vee Y).
$$
![[Visualization_of_the_smash_product_of_two_circles.gif|243]]