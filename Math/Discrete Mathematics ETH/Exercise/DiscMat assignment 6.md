#eth #exercise 
> [!Important] Title
> Wenn Sie Zeit haben, bitte hilfen Sie mir, auch die Aufgabe 6.7 zu korrigieren.

# 6.5 Equinumerous sets
![[Pasted image 20251030205425.png]]
##### 1）
To prove $A$ and $\mathcal{P}(A)$ are not equinumerous, we need to show that there does not exist a bijective function $f:A\to \mathcal{P}(A)$.
Assume there is a bijective function $f:A\to \mathcal{P}(A)$
we then consider the set $B=\{ x \in A|x\not\in f(x) \}$
Since $B\subseteq A$, $B\in \mathcal{P}(A)$
However, $B$ contains all elements that are not in $f(x)$, meaning that $B$ differs from every $f(x)$. So $B\not\in \mathcal{P}(A)$
This leads to contradiction. Hence, The statement is proved.

##### 2)
According to [[Discrete Mathematics ETH.pdf#page=80&selection=717,0,721,14&color=note|Corollary 3.21]] The rational numbers $\mathbb{Q}$ are countable.
$\mathbb{Q}$ in not finite, therefore $\mathbb{Q}\sim \mathbb{N}$ ([[Discrete Mathematics ETH.pdf#page=79&selection=63,0,63,12&color=note|Theorem 3.17]])

By definition $C\subseteq \mathbb{Q}$ and $D\subseteq \mathbb{Q}$. 
According to [[Discrete Mathematics ETH.pdf#page=78&selection=200,0,214,1&color=note|Lemma 3.15 (iii)]] $C\preceq \mathbb{Q}$ and $D\preceq \mathbb{Q}$ 
We prove that if $C\preceq \mathbb{N}$:
- Let $i:C\to \mathbb{Q}$ be injective ([[Discrete Mathematics ETH.pdf#page=78&selection=4,0,4,14&color=note|Definition 3.42 (ii)]]) and $b:\mathbb{Q}\to \mathbb{N}$ be bijective (also injective) ([[Discrete Mathematics ETH.pdf#page=78&selection=4,0,4,14&color=note|Definition 3.42 (i)]])
- Define $g=b\circ i:C\to \mathbb{N}$. By transitivity of injectivity, $g$ is also injective.
- $C\preceq\mathbb{N}$ ([[Discrete Mathematics ETH.pdf#page=78&selection=4,0,4,14&color=note|Definition 3.42 (ii)]])
We can do the same to $D$, and we get $D\preceq \mathbb{N}$

Thus, the sets $C$ and $D$ are countable. ([[Discrete Mathematics ETH.pdf#page=78&selection=200,0,214,1&color=note|Lemma 3.15 (iii)]])
Since they are not finite, $C\sim \mathbb{N}$ and $D\sim \mathbb{N}$ ([[Discrete Mathematics ETH.pdf#page=79&selection=63,0,63,12&color=note|Theorem 3.17]])
$\implies C\sim \mathbb{N}$ and $\mathbb{N}\sim D$ , using symmetry of $\sim$ ($\sim$ is an equivalence relation by [[Discrete Mathematics ETH.pdf#page=78&selection=160,0,160,10&color=note|Lemma 3.15 (i)]])
$\implies C\sim D$ using transitivity of $\sim$ ($\sim$ is an equivalence relation by Lemma 3.15 (i) )
$\implies$The sets $C$ and $D$ are equinumerous.
The statement is proved


# 6.6 Uncountability
##### 1)
We define an injective function $\{ 0,1 \}^{\infty}\to A$ as followings:
$f(b)=b$
**proof of being a function**: This is well defined since $\{ 0,1 \}\in \{ 0,\dots,9 \}$
**Proof of injectivity**: let $b,b'\in$ $\{ 0,1 \}^{\infty}$ be arbitrary such that $b\neq b'$. 
	Then we have $b\neq b'\implies f(b)\neq f(b')$. 
	Therefore, $f$ is injective.

Since there is an injective function from $\{ 0,1 \}^{\infty}$ to $A$ we know that $\{ 0,1 \}^{\infty}\preccurlyeq A$. Now assume $A$ was countable. Then $A\preccurlyeq\mathbb{N}$ and per injectivity of $\preccurlyeq$ we get $\{ 0,1 \}^{\infty}\preccurlyeq\mathbb{N}$. But this means that $\{ 0,1 \}^{\infty}$ is countable, which is a contradiction.

##### 2)
We define an injective function $[0,1)\to A$ as followings:
$f(t)=(\cos(2\pi t),\sin(2\pi t))$
 
**proof of being a function**: 
- well defined: for each $t\in[0,1)$, $(\cos(2\pi t),\sin(2\pi t))$ is a single ordered pair in $\mathbb{R}^{2}$
- totally defined: $\cos$ and $\sin$ are defined on all real numbers and therefore defined on $[0,1)$

**Proof of injectivity**: let $b,b'\in$ $[0,1)$ be arbitrary such that $b\neq b'$. 
	Then we have $b\neq b'\implies (\cos(2\pi b),\sin(2\pi b))\neq (\cos(2\pi b'),\sin(2\pi b'))\implies f(b)\neq f(b')$. 
	Therefore, $f$ is injective.

Since there is an injective function from $[0,1)$ to $A$ we know that $[0,1)\preccurlyeq A$. Now assume $A$ was countable. Then $A\preccurlyeq\mathbb{N}$ and per injectivity of $\preccurlyeq$ we get $[0,1)\preccurlyeq\mathbb{N}$. But this means that $[0,1)$ is countable, which is a contradiction.


# 6.7 fogof (exam 2022)
![[Pasted image 20251030232550.png]]
1.
Assume $f$ is not injective
There exists some $a,b\in X$ with $a\neq b$ but $f(a)=f(b)$
$\implies(f \circ g)(f(a))=(f\circ g)(f(b))$
$\implies f\circ g\circ f$ is not injective. Contradiction
$f$ is injective.

2.
Assume $f$ is not surjective
There exists some $b\in Y$ such that $b\not\in \{ f(a)|a\in X \}$
$\implies$ There is some $b\in Y$ such that $b \not\in \{ f((g\circ f) (a))\;| \; (g\circ f) (a)\in X\}$
$\implies$ There is some $b\in Y$ such that $b \not\in \{ f((g\circ f) (a))\;| \; a\in X\}$
$\implies f\circ g\circ f$ is not surjective. Contradiction
$f$ is surjective.

3.
We showed in previous tasks that $f$ is bijective (injective and surjective)
This means $f^{-1}$ exists, and must also be bijective
let $h\overset{ def }{ = }f\circ g\circ f$ 
$\implies g=f^{-1}\circ h \circ f^{-1}$
We know $f^{-1}$ and $h$ are both bijective. By the transitivity of bijection, we know $g$ is also bijective, and therefore injective.

4.
We showed in the previous task that $g$ is bijective. Therefore, $g$ is also surjective.