## Example: Gluing a segment
![[Pasted image 20260220235721.png|414]]
By defining the endpoints as being in the same equivalence class, we basically connect the endpoints and the resulting [[Quotient Space|quotient space]] is homeomorphic to a circle.

![[Pasted image 20260221000350.png]]
Consider this orange subset, it is open (see [[Subspace]]) and includes $[0]$ and $[1]$, so on our quotient space, the corresponding set must also be open.
![[Pasted image 20260221000502.png|365]]
A better way to draw this quotient space is of course to draw a circle
![[Pasted image 20260221000643.png]]

Here we have the quotient map $w:I\to S^{1}$
$s\mapsto e^{2\pi i\cdot s}$

we check that $q(0)=e^{2\pi i\cdot0}=1=e^{2\pi i}=q(1)$

## Example: glue ball into sphere

Consider a closed disk (2-dimensional ball) $\bar{\mathbb{B}}^{2}\subseteq \mathbb{R}^{2}$, 
and an equivalence relation $\sim:=((x,y)\sim(x,-y))$
We get $\bar{\mathbb{B}}^{2}/\sim \;\cong \mathbb{S}^{2}$
![[Pasted image 20260221001238.png|561]]

## Example: gluing square edges
![[Pasted image 20260221001343.png|423]]

## Cone on a space X
Let $X$ be a space
Consider the [[Product Space|product space]] $X\times I$
we define $\sim:=((x,0)\sim(y,0)\forall x,y\in X)$
![[Pasted image 20260221002113.png]]

We denote $X\times I/\sim\;=\; CX$

> [!NOTE]
> we also have $C\mathbb{S}^{2}\; \cong\; \mathbb{B}^{3}$
> Whether the "vertex" is inside of the sphere or outside of the sphere does not matter

We have here a quotient map $q:X\times I\to CX$ 


## Wedge sum
![[Pasted image 20260221003152.png]]
$\sim:=((x_{i}\sim x_{j})\;	\forall{i,j})$
We then define the wedge sum as
$$
\bigvee_{i}X_{i}\;:=\;\coprod _{i}X_{i}/\sim
$$
![[Pasted image 20260221003511.png|237]]
In the case of having only two spaces we have: $X\vee Y=(X\sqcup Y)/\sim$
This can also be viewed as a [[Adjunction Space]]
## Example: Normalization
$q:\mathbb{R}^{n+1}\setminus \{ 0 \}\to \mathbb{S}^{n}$
$x\mapsto \frac{x}{\lvert x \rvert}$
![[Pasted image 20260222003717.png|223]]

## Example: R/Z
$\mathbb{R}/\mathbb{Z}=\mathbb{R}/(x\sim y\Longleftrightarrow x-y\in \mathbb{Z})$
Let $q:\mathbb{R}\to \mathbb{R}/\mathbb{Z}$
![[Pasted image 20260222013223.png|417]]

To define $\tilde{f}$ we only need to have $q(x)=q(x')\implies f(x)=f(x')$ using universal property. 
This is indeed true (easily checked)
So there is an unique continuous $\tilde{f}$ to make the graph commute

To find for example $\tilde{f}([0])$ we can just find an element $x$ of the preimage of $[0]$ in $\mathbb{R}$, and find $f(x)$. In this case let's choose $x=1$, and $f(1)$ gives $\sin(2\pi)=0$. When we choose $x=2$, then $f(2)$ still gives 0.

Actually $\mathbb{R}/\mathbb{Z}$ is homeomorphic to $\mathbb{S}^{1}$
![[Pasted image 20260222013934.png|100]]

To show $\mathbb{R}/\mathbb{Z}$ is homeomorphic to $\mathbb{S}^{1}$:
![[Pasted image 20260222210610.png|361]]
Note that we have $x-x'\in \mathbb{Z}\Longleftrightarrow e^{2\pi i\cdot x}=e^{2\pi i\cdot x'}$ ([[#Example Gluing a segment]])
By using [[Quotient Space#Uniqueness of Quotients|uniqueness of quotient maps]] we can clearly see that $\mathbb{R}/\mathbb{Z}\cong \mathbb{S}^{1}$
