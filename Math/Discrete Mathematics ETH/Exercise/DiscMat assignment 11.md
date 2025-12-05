#eth #exercise 
# 11.2 A new linear code
##### 1)
![[Pasted image 20251204192319.png]]

Let $c=(c_{1},\dots,c_{n})$ where $c_{i}\in F$ for $i \in [n]$
Take any $x,y\in \mathcal{C}$, for each coordinate $i$:
If $(x+y)_{i}\neq0$, then $x_{i}\neq0$ or $y_{i}\neq0$  (If both are $0$, then $(x+y)_{i}=x_{i}+y_{i}=0$)
Let $s(c)$ denotes the set of coordinates $i$ where $c_{i}\neq0$, with $hw(c)=\lvert s(c) \rvert$
So all $i \in s(x+y)$, we have $i \in s(x)$ or $i \in s(y)$
Therefore, we must have $s(x+y)\subseteq s(x)\cup s(y)$
$\implies\lvert s(x+y) \rvert\leq \lvert s(x) \cup s(y) \rvert\leq \lvert s(x) \rvert+\lvert s(y) \rvert$ (inequality for finite set)
$\implies hw(x+y)\leq hw(x)+hw(y)$

##### 2)
![[Pasted image 20251204192325.png]]
Let $c_{1},c_{2}\in\mathcal{C}$ such that $c_{1}\neq c_{2}$ and $d(c_{1},c_{2})=d_{min}(\mathcal{C})$ 
Let $c_{3}\in\mathcal{C}$ such that $hw(c_{3})=min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$
we know that $hw(c_{3})=d(c_{3},0_{n})$ according to the definition of $hw$

We first prove that $d_{min}(\mathcal{C})\leq min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$:
We prove this by using contradiction.
Suppose $d_{min}(\mathcal{C})> min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$, and we have $hw(c_{3})=d(c_{3},0_{n})<d(c_{1},c_{2})$
We have $\forall x,y\in\mathcal{C}\;	(d(c_{1},c_{2})\leq d(x,y))$ according to the definition of $d_{min}(\mathcal{C})$
Let $x=c_{3},y=0_{n}$, we get $d(c_{1},c_{2})\leq d(c_{3},0_{n})$
This contradicts to our assumption. Therefore, we proved $d_{min}(\mathcal{C})\leq min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$

Then, we prove that $d_{min}(\mathcal{C})\geq min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$:
Since $\mathcal{C}$ is linear, $c_{1}-c_{2}$ must still be in $\mathcal{C}$
We have $hw(c_{3})\leq hw(c_{1}-c_{2})$ (there is no such $c\in \mathcal{C}\setminus \{ 0^{n} \}$ such that $hw(c)<hw(c_{3})$)
We now prove that $hw(c_{1}-c_{2})=d(c_{1},c_{2})$ 
By definition $d(c_{1},c_{2})=\lvert \{ i \in[n]|c_{1i}\neq c_{2i} \} \rvert$ 
$hw(c_{1}-c_{2})=\lvert \{ i \in[n]|(c_{1}-c_{2})_{i}\neq0 \} \rvert$
For each coordinate $i$:
- If $c_{1i}=c_{2i}$, then $(c_{1}-c_{2})_{i}=c_{1i}-c_{2i}=0$
- Conversely, If $(c_{1}-c_{2})_{i}=0$, then $c_{1i}-c_{2i}=0$
	- $\implies c_{1i}=c_{2i}$
- Thus, $c_{1i}\neq c_{2i}\Longleftrightarrow (c_{1}-c_{2})_{i}\neq0$
- $\implies hw(c_{1}-c_{2})=d(c_{1},c_{2})$

$\implies hw(c_{3})\leq d(c_{1},c_{2})$
$\implies d_{min}(\mathcal{C})\geq min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$

**Conclusion**:
Since we proved both inequalities in opposite directions, we must have $d_{min}(\mathcal{C})= min_{c\in\mathcal{C}\setminus \{ 0^{n} \}}hw(c)$
The claim is proved.

##### 3)
![[Pasted image 20251204192336.png]]

Let $u_{3}\in U$ with $hw(u_{3})=d_{min}(U)$ and $v_{3}\in V$ with $hw(v_{3})=d_{min}(V)$ (using the result from previous question)

We first prove that $d_{min}(\mathcal{D})\leq min(2d_{min}(U),d_{min}(V))$
- Take $v=0^{n}$, then $u_{3}||u_{3}\in \mathcal{D}$ 
	- $hw(u_{3}||u_{3})=hw(u_{3})+hw(u_{3})$ (because concatenation just sums the weights of the two halves)
	- $=2hw(u_{3})=2d_{min}(U)$ (using result from previous question)
	- Therefore, $d_{min}(\mathcal{D})\leq 2d_{min}(U)$
- Take $u=0^{n}$, then $0^{n}||v_{3}\in \mathcal{D}$
	- and $hw(0^{n}||v_{3})=hw(v_{3})=d_{min}(V)$ (using result from previous question)
	- Therefore, $d_{min}(\mathcal{D})\leq d_{min}(V)$
- Hence $d_{min}(\mathcal{D})\leq min(2d_{min}(U),d_{min}(V))$

Then, we prove that $d_{min}(\mathcal{D})\geq min(2d_{min}(U),d_{min}(V))$
Take any non zero pair $(u,v)\in U\times V$
**Case 1** $v=0^{n}$
- Then $u\neq0^{n}$
- $hw(u||u)=hw(u)+hw(u)=2hw(u)\geq2d_{min}(U)$
**Case 2** $v\neq0^{n}$
- $hw(u||(u+v))=hw(u)+hw(u+v)$
- By using the result from question 1 we get
- $hw(u)+hw(u+v)\geq2hw(u)+hw(v)\geq hw(v)\geq d_{min}(V)$ 

In all cases, $hw(u||(u+v))\geq min(2d_{min}(U),d_{min}(V))$
$u||(u+v)\in \mathcal{D}$
Therefore $d_{min}(\mathcal{D})\geq min(2d_{min}(U),d_{min}(V))$ (using result from previous question)

**Conclusion**:
Since we proved both inequalities in opposite directions, we must have $d_{min}(\mathcal{D})=min(2d_{min}(U),d_{min}(V))$
The claim is proved.