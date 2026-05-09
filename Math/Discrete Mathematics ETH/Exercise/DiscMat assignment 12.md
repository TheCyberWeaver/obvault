 #exercise

# 12.5 Statements about Formulas
##### 1）
$$
\exists{x}\; (F\vee G)\equiv(\exists{x}\; F\vee \exists{x}\; G)
$$
We prove the statement by showing that every model $\mathcal{A}$ for $\exists{x}\; (F\vee G)$ is also a model for $(\exists{x}\; F\vee \exists{x}\; G)$ and vice versa.

We first prove $\exists{x}\; (F\vee G)\models(\exists{x}\; F\vee \exists{x}\; G)$
Let $\mathcal{A}$ be a model such that $\mathcal{A}(\exists{x}\; (F\vee G))=1$ 
$\implies$ $\mathcal{A}_{[x\to u]}(F\vee G)=1$ for some $u$ in $U$ (semantics of $\exists$)
$\implies$ $\mathcal{A}_{[x\to u]}(F)=1$ or $\mathcal{A}_{[x\to u]}(G)=1$ (semantics of $\vee$)
Case Distinction:
- Case 1: $A_{[x\to u]}(F)=1$
	- $\implies \mathcal{A}(\exists{x}\; F)=1$ (semantics of $\exists$)
	- $\implies \mathcal{A}(\exists{x}\; F\vee \exists{x}\; G)=1$ (semantics of $\vee$)
- Case 2: $A_{[x\to u]}(G)=1$
	- $\implies \mathcal{A}(\exists{x}\; G)=1$ (semantics of $\exists$)
	- $\implies \mathcal{A}(\exists{x}\; F\vee \exists{x}\; G)=1$ (semantics of $\vee$)

$\implies \mathcal{A}(\exists{x}\; F\vee \exists{x}\; G)=1$
$\implies\exists{x}\; (F\vee G)\models(\exists{x}\; F\vee \exists{x}\; G)$

We then prove that $(\exists{x}\; F\vee \exists{x}\; G)\models \exists{x}\; (F\vee G)$
Let $\mathcal{A}$ be a model such that $\mathcal{A}(\exists{x}\; F\vee \exists{x}\; G)=1$ 
$\implies$ $\mathcal{A}(\exists{x}\; (F))=1$ or $\mathcal{A}(\exists{x}\; (G))=1$ (semantics of $\vee$)
$\implies$ $\mathcal{A}_{[x\to u]}(F)=1$ for some $u$ in $U$ or $\mathcal{A}_{[x\to u]}(G)=1$ for some $u$ in $U$ (semantics of $\exists$)
Case Distinction:
- Case 1: $\mathcal{A}_{[x\to u]}(F)=1$ for some $u$ in $U$
	- $\implies \mathcal{A}_{[x\to u]}(F\vee G)=1$ for some $u$ in $U$ (semantics of $\vee$)
	- $\implies \exists{x}\; (F\vee G)$ (semantics of $\exists$)
- Case 2: $A_{[x\to u]}(G)=1$ for some $u$ in $U$
	- $\implies \mathcal{A}_{[x\to u]}(F\vee G)=1$ for some $u$ in $U$ (semantics of $\vee$)
	- $\implies \exists{x}\; (F\vee G)$ (semantics of $\exists$)

$\implies\mathcal{A}(\exists{x}\; (F\vee G))=1$
$\implies(\exists{x}\; F\vee \exists{x}\; G)\models \exists{x}\; (F\vee G)$
$\implies (\exists{x}\; F\vee \exists{x}\; G)\equiv \exists{x}\; (F\vee G)$ (together with the other direction)
The statement is proved

##### 2）
$$
\exists{x}\; \exists{y}\; F\equiv \exists{y}\; \exists{x}\; F
$$
We prove the statement by showing that every model $\mathcal{A}$ for $\exists{x}\; \exists{y}\; F$ is also a model for $\exists{y}\; \exists{x}\; F$ and vice versa.

Let $\mathcal{A}$ be a model such that $\mathcal{A}(\exists{x}\; \exists{y}\; F)=1$ 
$\Longleftrightarrow \mathcal{A}_{[x\to u]}(\exists{y}\; F)=1$ for some $u$ in $U$ (semantics of $\exists$)
$\Longleftrightarrow \mathcal{A}_{[x\to u][y\to v]}(F)=1$ for some $u$ in $U$ and for some $v$ in $U$ (semantics of $\exists$)
$\Longleftrightarrow \mathcal{A}_{[y\to v][x\to u]}(F)=1$ (updating different variables commutes)
$\Longleftrightarrow \mathcal{A}_{[y\to v]}(\exists{x}\; F)=1$ (semantics of $\exists$)
$\Longleftrightarrow \mathcal{A}(\exists{y}\; \exists{x}\; F)=1$ (semantics of $\exists$)
$\implies \exists{x}\; \exists{y}\; F\equiv \exists{y}\; \exists{x}\; F$ (The proof for the other direction is analogous if we exchange $x$ and $y$)

##### 3）
$$\forall{x}\; \exists{y}\; F\equiv \exists{y}\; \forall{x}\; F$$

We disprove this statement by providing a counterexample
let $U=\mathbb{N}$
let $F\overset{ def }{ = }P(x,y)$
let $P(x,y)=1\overset{ def }{ \Longleftrightarrow }x=y$ (interpreted as equality)

The statement can be rewritten as 
$\forall{x}\; \exists{y}\; (x=y)\equiv \exists{y}\; \forall{x}\; (x=y)$
We first consider the left side. For any given $x$, we can choose $y=x$, then $x=y$ is true. Therefore, the left side is evaluated to true. 
However, on the right side, if such a $y$ existed, then we would have $0=y$ and $1=y$, hence $1=0$, contradiction.
Thus there is a model $\mathcal{A}$ such that $\mathcal{A}(\forall{x}\; \exists{y}\; F)=1$ and $\mathcal{A}(\exists{y}\; \forall{x}\; F)=0$, which breaks the logical equivalence.

Hence, the statement is disproved.