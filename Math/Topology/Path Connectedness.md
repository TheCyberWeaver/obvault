## Definition - Path
Let $X$ be a topological space and $p,q\in X$. A _path_ in $X$ from $p$ to $q$ is a continuous map $f:I\to X$ with $f(0)=p$ and $f(1)=q$

A space $X$ is called _path-connected_ if and only if for all $p,q\in X$, there is a _path_ in $X$ from $p$ to $q$ 

## Properties
basically the same as [[Math/Topology/Connectedness|Connectedness]]. 

> [!NOTE]
> Every continuous image of a path-connected space is path-connected

**Proof**:
Let $p,q\in f(X)$. Take $x \in f^{-1}(p)$ and $y\in f^{-1}(q)$
![[Pasted image 20260226132822.png|351]]
$f$ is continuous and $\gamma$ is continuous $\implies f\circ\gamma$ is continuous
$f\circ \gamma(0)=f(x)=p$ and $f\circ\gamma(1)=f(y)=q$
$\implies f\circ\gamma$ is a path $\implies$ The image $f(X)$ is path-connected

> [!NOTE]
> Let $\{ B_{\alpha} \}_{\alpha \in A}$ be a collection of path-connected subspaces of $X$ with a point in common. Then $\bigcup _{\alpha \in A}B_{\alpha}$ is path-connected

For Proof, see [[Math/Topology/Connectedness#Properties subspaces|connectedness]]

## relation to [[Math/Topology/Connectedness|Connectedness]]

> [!NOTE]
> path-connectedness $\implies$ connectedness

Let $X$ be path-connected. Fix $p \in X$. For any $x \in X$ there exists $\gamma _{x}:p\rightsquigarrow x$ 
$\gamma _{x}([0,1])$ is connected because $[0,1]$ is connected and $\gamma _{x}$ is continuous.

We can write $X=\bigcup _{x \in X}\gamma _{x}([0,1])$
Since the union of connected spaces that shares a common point is again connected (point $p$), $X$ must be connected

> [!NOTE]
> Under [[Manifold|manifold]], connectedness and path-connectedness are equivalent

### Example of the converse direction: Topologist's sine curve

A standard example is the topologist’s sine curve:
$$
S=\{(x,\sin(1/x)) : x>0\}\;\cup\;\{(0,y) : -1\le y\le 1\}\subset \mathbb{R}^2.
$$
![[Pasted image 20260226141045.png|375]]
Why this works:

The set $\{(x,\sin(1/x)) : x>0\}$ oscillates infinitely often as $x\to 0^+$.
Its closure adds the whole vertical segment $\{(0,y) : -1\le y\le 1\}$.
The resulting set $S$ is connected.

But it is not path-connected: there is no continuous path inside $S$ from a point on the vertical segment, such as $(0,0)$, to a point on the oscillating part, such as $(1,\sin 1)$.



