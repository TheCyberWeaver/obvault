
> [!Important] 
> This concept is different from [[Section 13 Homomorphisms|Homomorphism]]
## Definition
A homeomorphism between spaces $X,Y$ is a [[Continuous Map (function in topology)|continuous function]] $\varphi:X\to Y$ which has a **continuous** inverse $\varphi ^{-1}:Y\to X$ 

necessary but not sufficient condition: $\varphi$ is bijective 

> [!Warning] 
> Note that $\varphi$ is bijective does not mean $\varphi ^{-1}$ is also continuous


In this case $X$ and $Y$ are **homeomorphic** and denote them as $X\cong Y$ 
We use the symbol $\cong$ for isomorphism here because a homeomorphism is an **isomorphism** in the [[Category Theory Intro|category]] of topological spaces. (an [[Relation#Equivalence Relations|equivalence relation]])

Therefore, the composition of two homeomorphisms is also a homeomorphism, and all self-homeomorphisms $X \to X$ form a group, called the homeomorphism group of $X$, usually denoted by $Homeo(X)$.

> [!NOTE] Title
> 所有对一块橡皮泥做的那些不撕不粘的变形 构成了一个特殊的置换群

## Properties
![[Pasted image 20251207002804.png]]


## Example
**Claim**: Any two open balls in $\mathbb{R}^{n}$ are homeomorphic
we find two functions $t:x\to x+a$ for translation and $d:x\to cx,c\in \mathbb{R}\setminus \{ 0 \}$ for scalation
These functions and there inverse are continuous
These means $d\circ t$ is a homeomorphism

**Claim**: The unit ball $\mathbb{B}^{n}$ is homeomorphic to $\mathbb{R}^{n}$ (the ball is open) ($\mathbb{B}^{2}$ is the "interior" of a circle)
$f: \mathbb{B}^{n}\to \mathbb{R}^{n}$
$x\to \frac{x}{1-\lVert x \rVert}$

$f^{-1}: \mathbb{R}^{n}\to \mathbb{B}^{n}$
$x\to \frac{x}{1+\lVert x \rVert}$

**Claim**: The unit cube $C=\{ (x,y,z)|max(\lvert x \rvert,\lvert y \rvert,\lvert z \rvert)=1 \}$ is homeomorphic to $\mathbb{S}^{2}$ ($\mathbb{B}^{n}$ is the surface of a sphere in $\mathbb{R}^{n+1}$)

> [!NOTE] Topological property
> homomorphism does not preserver size, corners or boundedness


## Definition: local homeomorphism
(a weakening of the concept homeomorphism)
A map $f:X\to Y$ is a local homeomorphism if each point $x \in X$ has a neighborhood $U\subseteq X$ such that $f(U)$ is open and $f_{|U}:U\to f(U)$ is a homeomorphism
![[Pasted image 20251211220325.png|457]]

### Example
![[Pasted image 20251211220815.png|246]]
Consider $f:\mathbb{R}\to \mathbb{S}^{1}$ with $x\mapsto e^{i 2\pi x}$
Although $f$ is not a homeomorphism ($f$ is not bijective), we can find for any point a neighborhood such that $f$ in this neighborhood is homeomorphic.

### Property
A bijective local homeomorphism is a homeomorphism.
**Proof**
 $U\subseteq X$ open. Choose any $y\in f(U)$. 
 Write $y=f(x)$ for $x \in U$. $x$ has a neighborhood $V_{x}$ (open) such that $f(V_{x})$ open and $f_{|V_{x}}$ is a homeomorphism. 
$\implies U\cap V_{x}$ open (open sets are closed under finite intersections)
and $y\in \underbrace{ f(U\cap V_{x}) }_{ open }\subseteq f(U)$
$f(U\cap V_{x})$  is open, because $U\cap V_{x}\subseteq V_{x}$ is open and $f_{|V_{x}}$ is homeomorphism
$\implies$ any $y\in f(U)$ is contained in a open set.
$\implies f(U)$ open 
$\implies$ $f$ open
$\implies$ $f$ is a homeomorphism