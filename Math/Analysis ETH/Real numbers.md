## Theorem 1.1.2: 

> [!NOTE] 
> $\mathbb{R}$ is a _commutative_, _ordered field_ that is _order-complete_. $\mathbb{R}$ is non-trivial
## Axioms:
### Axioms of Addition (A):
$(\mathbb{R},+)$ is an abelian group:
(A1) Associativity: $\forall x,y,z \in \mathbb{R} : (x+y)+z = x+(y+z)$
(A2) Neutral Element: $\exists 0 \in \mathbb{R}, \forall x \in \mathbb{R} : x+0 = x$
(A3) Inverse Element: $\forall x \in \mathbb{R}, \exists y \in \mathbb{R} : x+y = 0$ This $y$ is denoted as $-x$.
(A4) Commutativity: $\forall x,y \in \mathbb{R} : x+y = y+x$
### Axioms of Multiplication (M):
$(\mathbb{R}\setminus \{ 0 \},\cdot)$ is an abelian group:
(M1) Associativity: $\forall x,y,z \in \mathbb{R} : (x \cdot y)\cdot z = x \cdot (y \cdot z)$
(M2) Neutral Element: $\exists 1 \in \mathbb{R}, \forall x \in \mathbb{R} : x \cdot 1 = x$
(M3) Inverse Element: $\forall x \in \mathbb{R} \setminus \{0\}, \exists y \in \mathbb{R} : x \cdot y = 1$ This $y$ is denoted as $x^{-1}$ or $\frac{1}{x}$.
(M4) Commutativity: $\forall x,y \in \mathbb{R} : x \cdot y = y \cdot x$
### Distributivity (D):
$\mathbb{R}$ is a field:
$$\forall x,y,z \in \mathbb{R} : x \cdot (y+z) = x \cdot y + x \cdot z$$
### Order Axioms (O):
$\leq$ is a total order
(O1) Reflexivity: $\forall x \in \mathbb{R} : x \le x$
(O2) Transitivity: $\forall x,y,z \in \mathbb{R} : (x \le y \land y \le z) \Rightarrow x \le z$
(O3) Antisymmetry: $\forall x,y \in \mathbb{R} : (x \le y \land y \le x) \Rightarrow x = y$
(O4) Totality: $\forall x,y \in \mathbb{R} : x \le y \lor y \le x$
### Compatibility Axioms (K):
(K1)
$$\forall x,y,z \in \mathbb{R} : x \le y \Rightarrow x+z \le y+z$$
(K2)
$$\forall x,y \in \mathbb{R} : (x \ge 0 \land y \ge 0) \Rightarrow x \cdot y \ge 0$$
### Order Completeness
This is the crucial axiom that distinguishes $\mathbb{R}$ from $\mathbb{Q}$.

Let $A \subseteq \mathbb{R}$ and $B \subseteq \mathbb{R}$ be non-empty sets such that

$$
A \ne \varnothing, \quad B \ne \varnothing
$$
and
$$
\forall a \in A, \forall b \in B : a \le b.
$$
Then there exists a $c \in \mathbb{R}$ such that

$$
\forall a \in A, \forall b \in B : a \le c \le b.
$$
**Interpretation of Order Completeness:** This axiom states that there are no “gaps” in the real number line. Every set bounded above has a least upper bound (supremum), and every set bounded below has a greatest lower bound (infimum).
#### From the view of topology space
This is saying:
> [!NOTE]
> In the order topology, $\mathbb{R}$ is connected (equivalently, every continuous map $\mathbb{R} \to \{0,1\}$ is constant), and it is a linear order without gaps.

This is a stronger statement than [[Math/Topology/Connectedness|Connectedness]]
## Definition: Supremum & Infimum
Suppose $(X,\leq)$ is a poset with $A\subseteq X$
- Supremum: least upper bound
	- $\forall{a\in A}\; (a\leq\text{sup } A)$ (the least such bound)
	- similar to [[Topology#closure|closure in topology]] under $\subseteq$
	- $\text{sup }A=\text{inf }$upper bounds
- Infimum: greatest lower bound
	- $\forall{a\in A}\; (a\geq\text{inf } A)$ (the greatest such bound)
	- similar to [[Topology#interior|interior in topology]] under $\subseteq$

## Corollary: Archimedean Principle
- $\forall{x\in \mathbb{R},y>0}\; \exists{n\in \mathbb{N}}:\;ny>x$
	- Let $y=1$ , then $\forall{x \in \mathbb{R}}\; \exists n\in \mathbb{N}$ such that $n>x$.
- $\forall{\varepsilon>0}\; \exists{n\in \mathbb{N}} :\; \frac{1}{n}<\varepsilon$


