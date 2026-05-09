---
tags:
  - linker-exclude
---
## Formal Definition
A **Homotopy** is a continuous deformation between two [[Continuous Map (function in topology)|continuous maps]].

Let $f,g:X\to Y$ be [[Continuous Map (function in topology)|continuous maps]]. We say that $f$ and $g$ are **homotopic**, written
$$
f\simeq g,
$$
if there is a family of maps $h_t:X\to Y$ for $t\in I=[0,1]$ such that:
- $h_0=f$ and $h_1=g$,
- the map $H:X\times I\to Y$ defined by $H(x,t)=h_t(x)$ is continuous.

The map $H$ is called a **homotopy** from $f$ to $g$. The continuity of $H$ implies in particular that each individual map $h_t:X\to Y$ is continuous. 
**homotopy** is an equivalence relation on maps $X\to Y$

### nullhomotopic
A *constant map* is a $c_{x_{0}}:X\to X, x\mapsto x_{0}$
A map $f:X\to Y$ is **nullhomotopic** if it is homotopic to a *constant map*, meaning that there exists a homotopy $H:X\times I\to X$ such that $H(x,0)=f(x)$ and $H(x,1)=x_{0}$
## Homotopy Equivalence

A map $f:X\to Y$ is a **homotopy equivalence** if there exists a map $g:Y\to X$ such that
$$
g\circ f\simeq 1_X
\qquad\text{and}\qquad
f\circ g\simeq 1_Y.
$$

In this case, $X$ and $Y$ are called **homotopy equivalent**, or said to have the same **homotopy type**.

Homotopy type is an [[Relation#Equivalence Relations|equivalence relation]]:

- **Reflexive:** $1_X:X\to X$ is a homotopy equivalence.
- **Symmetric:** if $f:X\to Y$ is a homotopy equivalence with inverse up to homotopy $g:Y\to X$, then $g$ is also a homotopy equivalence.
- **Transitive:** the composition of homotopy equivalences is again a homotopy equivalence.

### Homotopy Class
The [[Relation#Equivalence class|equivalence class]] of $f:X\to Y$ is called its **homotopy class** and denoted $[f]$

The set of homotopy classes between two spaces $X$ and $Y$ is usually written as $[X,Y]$
Its elements are not spaces, but equivalence classes of maps $f:X\to Y$, where two maps are considered the same if they are homotopic.
## Contractible Spaces

A space $X$ is **contractible** if it has the homotopy type of a point.
$$
X\text{ is contractible}
\iff
1_X\text{ is nullhomotopic}.
$$
note that $1_{X}$ is the identity map of a space to it self: $1_{X}:X\to X$ with $x\mapsto x$
### Example: $\mathbb{R}^n$

The Euclidean space $\mathbb{R}^n$ is homotopy equivalent to the one-point space $\{\ast\}$

Let $f:\mathbb{R}^n\to\{\ast\}$ be the unique map, and let $g:\{\ast\}\to\mathbb{R}^n$ send $\ast$ to the origin. 
We want to show that $f\circ g\simeq 1_{\{ * \}}$ and $g\circ f\simeq1_{\mathbb{R}^{n}}$ 
We know $f\circ g=1_{\{\ast\}}\implies f\circ g\simeq 1_{\{ * \}}$
$g\circ f:\mathbb{R}^n\to\mathbb{R}^n$ is the constant map sending every point to $0$. The homotopy
$$
H:\mathbb{R}^n\times I\to\mathbb{R}^n,\qquad H(x,t)=tx
$$
deforms the *constant map* $H(x,0)=0$ to the *identity map* $H(x,1)=x$. Hence
$$
g\circ f\simeq 1_{\mathbb{R}^n},
$$
so $\mathbb{R}^n$ is contractible.



## Deformation Retractions

A **deformation retraction** of $X$ onto a subspace $A\subset X$ is a homotopy $f_t:X\to X$ such that:

- $f_0=1_X$,
- $f_t|_A=1_A$ for all $t\in I$,
- $f_1(X)=A$.

Thus every point of $X$ is continuously moved into $A$, while every point of $A$ stays fixed throughout the homotopy.

In this case, $f_1:X\to A$ is a homotopy equivalence with homotopy inverse given by the inclusion
$$
A\hookrightarrow X.
$$

Therefore, if $A$ is a deformation retract of $X$, then $X$ and $A$ have the same homotopy type.

## Homotopy of path

A homotopy of [[Path Connectedness#Definition|paths]] in $X$ is a family $f_{t} : I→X , 0 ≤ t ≤ 1$ , such that
- $f_{t}(0)=x_{0}$ and $f_{t}(1)=x_{1}$ (independent of $t$)
- The associated map $F:I\times I\to X$ defined by $F(s,t)=f_{t}(s)$ is continuous
![[Pasted image 20260508191324.png]]
### product path 
The **composition** or **product path** $f\centerdot g$ of two [[Path Connectedness#Definition|paths]] is defined by the formula 
$$
f\centerdot g(s)=\begin{cases}
f(2s),\;0\leq s\leq \frac{1}{2} \\
g(2s-1),\; \frac{1}{2}\leq s\leq1
\end{cases}
$$
![[Pasted image 20260508192634.png|232]]

## Geometric Intuition: Blender :D

In Blender (the software), one can create a smooth spine curve $C$ and use Geometry Nodes to generate a 3D tubular shape around it. One can then use a parameter $t\in[0,1]$ to control the tube’s radius so it changes continuously over time to make an animation ($t$ change continuously). 
- Consider the solid tube $V_{t}=\{ x:dist(x,C)\leq r(t) \}$
	- Each map from $V_{t}$ to $C$ is a *deformation retraction* by nearest-point projection.
- Consider the surface of the tube $S_{t}=\{ x \in \mathbb{R}^{3}:dist(x,C)=r(t) \}$
	- The changing $t$ produces a *homotopy* 
