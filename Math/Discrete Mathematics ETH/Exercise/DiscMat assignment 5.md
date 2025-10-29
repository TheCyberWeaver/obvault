#eth #exercise 


> [!Important] Title
> Wenn Sie Zeit haben, bitte hilfen Sie mir, auch die Aufgabe 5.6 zu korrigieren.

# 5.1 Computing Representations of Relations
$\rho^{3}=\{ (1,1),(2,2),(4,4),(1,3) \}$
$M^{\rho}=\begin{bmatrix}1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \\  1 & 1 & 1 & 1\end{bmatrix}$

# 5.2 Operations on Relations
##### 1. 
transitive
- not reflexive
	- Counterexample: $2<\circ|2$ does not hold. There does not exist a number such that it is greater than 2 and can divide 2 
- not symmetric
	- Counterexample: $2<\circ|3$ holds but $3<\circ|2$ does not hold. There does not exist a number such that it is greater than 3 and can divide 2 
- transitive 
	- If $a<\circ|b$ and $b<\circ|c$, then $a<c$ and $c|c$. Therefore, we have $a<\circ|c$
##### 2. 
reflexive
- reflexive
	- For any $a\in \mathbb{N}\setminus \{ 0 \}$, we have $a|a$ and $a\equiv_{2}a$ so $a|\cup\equiv_{2}a$ always holds
- not symmetric 
	- Counterexample: $3|\cup\equiv_{2}6$ but $6|\cup\equiv_{2}3$ does not hold
- not transitive
	- Counterexample: $3|\cup\equiv_{2}5$ and $5|\cup\equiv_{2}10$, but $3|\cup\equiv_{2}10$ does not hold
##### 3. 
reflexive, symmetric 
- reflexive
	- $|$ is reflexive and $|\subseteq |\cup \hat{|}$, so $|\cup \hat{|}$ must also be reflexive
- symmetric
	- Suppose $a|\cup \hat{|}b$
	- case 1: If $a|b$, then $(b,a)\in\hat{|}$, so $(b,a)\in|\cup \hat{|}$
	- case 2: If $a\hat{|}b$, then $(b,a)\in|$, so $(b,a)\in|\cup \hat{|}$
- not transitive
	- $2|\cup\hat{|}6 \wedge 6|\cup\hat{|}3$ , however $2|\cup\hat{|}3$ does not hold

# 5.3 An Equivalence Relation
##### 1)
**Proof of reflexive**
Let $\lambda=1$ and $a,b\in \mathbb{R}$
$(a,b)\overset{ def }{ = }(\lambda a,\lambda b)=(1a,1b)=(a,b)$
$\implies(a,b)\sim(a,b)$ is true for all 

**Proof of symmetric**
Let $a,b,c,d\in \mathbb{R}$
Suppose $(a,b)\sim(c,d)$
$(a,b)\sim(c,d)\overset{ def }{ \Longleftrightarrow } \exists \lambda_{1}>0\;(a,b)=(\lambda_{1} c,\lambda_{1} d)$
$\implies a=\lambda_{1}c$ and $b=\lambda_{1}d$
$\implies c=\frac{1}{\lambda_{1}}a$ and $d=\frac{1}{\lambda_{1}}b$
$\implies(c,d)=\left( \frac{1}{\lambda_{1}}a, \frac{1}{\lambda_{1}}b \right)$
Let $\lambda_{2}=\frac{1}{\lambda_{1}}$
$\implies (c,d)=(\lambda_{2}a,\lambda_{2}b)$
$\implies (c,d)\sim(a,b)$

**Proof of transitive**
Let $a,b,c,d,e,f\in \mathbb{R}$
Suppose $(a,b)\sim(c,d)$ and $(c,d)\sim(e,f)$
$\implies(a,b)=(\lambda_{1} c,\lambda_{1}d)$ and $(c,d)=(\lambda_{2}e,\lambda_{2}f)$ with $\lambda_{1}>0$ and $\lambda_{2}>0$
$\implies (a,b)=(\lambda_{1}\lambda_{2}e,\lambda_{1}\lambda_{2}f)$ with $\lambda_{1}>0$ and $\lambda_{2}>0$
Let $\lambda_{3}=\lambda_{1}\lambda_{2}$ with $\lambda_{3}>0$
$\implies(a,b)=(\lambda_{3}e,\lambda_{3}f)$
$\implies (a,b)\sim(e,f)$

##### 2)
Each equivalence class is a line on $\mathbb{R}^{2}$ with slope 1.

# 5.4 Properties of Relations
![[Pasted image 20251023205401.png]]
##### 1)
$(a,c)\in\gamma\Longleftrightarrow \exists b\; ((a,b)\in\rho \wedge(b,c)\in\hat{\rho})$
$\Longleftrightarrow \exists b\; ((b,a)\in\hat{\rho}\wedge(c,b)\in\rho)$ (definition of $\hat{\rho}$)
$\Longleftrightarrow \exists b\; ((c,b)\in\rho \wedge(b,a)\in\hat{\rho})$ (commutativity of $\wedge$)
$\Longleftrightarrow (c,a)\in\gamma$
$\implies \gamma=\hat{\gamma}$
$\implies \gamma$ is symmetric
The claim is proved.

##### 2)
The claim is false.
Counterexample:
Let $\sigma$ be $=$ and $\pi$ be $<$ on $\mathbb{N}$
Then $\hat{\pi}$ is $>$
so $\gamma=\sigma \circ\hat{\pi}=\{ (a,c): \exists b\; (a=b\wedge b>c) \}=\{ (a,c):a>c \}=\;>$
$>$ is not symmetric because $2>1$ is true but $1>2$ is false

##### 3)
Let $\sim_{1}$ and $\sim_{2}$ be two relations on set $A$
Let $\sim_{3}$ be $\sim_{1}\cap \sim_{2}$
We prove $\sim_{3}$ is an equivalence relation by showing it's reflexive, symmetric and transitive
- reflexive
	- For any $x \in A$, $(x,x)\in \sim_{1}$ and $(x,x)\in \sim_{2}$ since both are reflexive. Hence $(x,x)\in \sim_{3}$
- symmetric
	- If $(x,y)\in \sim_{3}$, then $(x,y)\in \sim_{1}$ and $(x,y)\in \sim_{2}$,. Since $\sim_{1}$ and $\sim_{2}$ are both symmetric, we have $(y,x)\in \sim_{1}$ and $(y,x)\in \sim_{2}$. Hence $(y,x)\in \sim_{3}$
- transitive
	- If $(a,b)\in \sim_{3}$ and $(b,c)\in \sim_{3}$, then $(a,b)\in \sim_{1}\wedge(a,b)\in \sim_{2}\wedge(b,c)\in \sim_{1}\wedge(b,c)\in \sim_{2}$. By transitivity of $\sim_{1}$ and $\sim_{2}$, we have $(a,c)\in \sim_{1}\wedge (a,c)\in \sim_{2}$. Thus, $(a,c)\in \sim_{3}$
 The claim is proved.

# 5.6 Antisymmetry (exam 2021)
![[Pasted image 20251023205332.png]]
We disprove the claim by showing a counterexample:

Let $\rho$ , $\sigma$ be two antisymmetric relations on set $\{ a,b,c \}$
$\rho\overset{ def }{ = }\{ (a,b),(c,b) \}$
$\sigma\overset{ def }{ = }\{ (b,a),(b,c) \}$

$\rho \circ\sigma=\{ (x,z)|\; \exists y\;(x\;\rho \;y\wedge y\;\sigma \;z) \}=\{ (a,c),(c,a) \}$ 
since $a\rho b$ and $b\sigma c$ give $(a,c)$, and $c\rho b$ and $b\sigma a$ give $(c,a)$
$\implies\rho \circ\sigma$ is not antisymmetric, because both $(a,c)$ and $(c,a)$ are in $\rho \circ\sigma$ but $a\neq c$