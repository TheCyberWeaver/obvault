 #exercise 
# 7.2 Properties of GCD and LCM
![[Pasted image 20251106210409.png]]
##### 1)
Let $d_{1}=gcd(a,c)$ and $d_{2}=gcd(b,c)$. 
We first show that $gcd(d_{1},d_{2})=1$
- Assume there is a common divisor $x$ of $d_{1}$ and $d_{2}$ with $x>1$ , then $x|gcd(a,c)$ and $x|gcd(b,c)$
- By definition of $gcd$, we get $x|a$ and $x|c$ and $x|b$
- This contradicts to the statement that $gcd(a,b)=1$, so $gcd(d_{1},d_{2})=1$ must hold. 

We then show that $d_{1}d_{2}|gcd(ab,c)$
- Since $d_{1}|a$ and $d_{2}|b$, we can conclude that $d_{1}d_{2}|ab$
- We also know that $d_{1}|c$ and $d_{2}|c$, and $gcd(d_{1},d_{2})=1$ 
	- set $c=kd_{1}$ where $k$ a positive integer (since $d_{1}|c$)
	- so $d_{2}|c$ gives $d_{2}|kd_{1}$
	- Because $gcd(d_{1},d_{2})=1$, Euclid’s lemma implies $d_{2}|k$. Let's then write $k=d_{2}t$ where $k$ is also a positive integer
	- Therefore $c=d_{1}k=d_{1}d_{2}t$
	- Hence, $d_{1}d_{2}|c$ 
- According to the definition of $gcd(ab,c)$, we have $\forall x ((x|ab\wedge x|c)\to x|gcd(ab,c))$
- Let $x=d_{1}d_{2}$ (since $d_{1}d_{2}$ satisfies $d_{1}d_{2}|ab$ and $d_{1}d_{2}|c$). Then we must have $d_{1}d_{2}|gcd(ab,c)$

We then show that $gcd(ab,c)|d_{1}d_{2}$
- Let $d=gcd(ab,c)$ with $d|ab$ and $d|c$
- we write $d$ as $d=\prod_{i}p_{i}^{e_{i}}$. Because $gcd(a,b)=1$, each prime of $d$ divides exactly $a$ or $b$. we then split $d$ into $d=d_{a}d_{b}$ with $d_{a}|a$ (containing primes that divides $a$) and $d_{b}|b$ (containing primes that divides $b$) 
- Since $d|c$, we get $d_{a}|c$ and $d_{b}|c$. Thus $d_{a}|d_{1}$ and $d_{b}|d_{2}$
- Therefore, we get $d=d_{a}d_{b}|d_{1}d_{2}$, meaning $gcd(ab,c)|d_{1}d_{2}$
**Conclusion**
By showing $d_{1}d_{2}|gcd(ab,c)$ and $gcd(ab,c)|d_{1}d_{2}$, we proved that $d_{1}d_{2}=gcd(ab,c)$, which means $gcd(ab,c)=gcd(a,c)\cdot gcd(b,c)$ 
The claim is proved.

##### 2)
We write $a,b,c$ as followings:
$$
a=\prod_{i}p_{i}^{e_{i}} , \; b=\prod_{i}p_{i}^{f_{i}} ,\; c=\prod_{i}p_{i}^{g_{i}} 
$$
We now write the left part of the equation as
$$
lcm(a,gcd(bc))=lcm(\prod_{i}p_{i}^{e_{i}}, \prod_{i}p_{i}^{min(f_{i},g_{i})})=\prod_{i}p_{i}^{max(e_{i},min(f_{i},g_{i}))} 
$$
We now write the right part of the equation as
$$
gcd(lcm(a,b),lcm(a,c))=gcd(\prod_{i}p_{i}^{max(e_{i},f_{i})},\prod_{i}p_{i}^{max(e_{i},g_{i})})=\prod_{i}p_{i}^{min(max(e_{i},f_{i}),max(e_{i},g_{i}))} 
$$
We now only need to prove that $max(e_{i},min(f_{i},g_{i}))=min(max(e_{i},f_{i}),max(e_{i},g_{i}))$
We show that $max(x,min(y,z))=min(max(x,y),max(x,z))$
- case 1: $x\geq min(y,z)$
	- $max(x,min(y,z))=x$
	- At least one of $y$ and $z$ is smaller or equal to $z$. Therefore one of $max(x,y)$ and $max(x,z)$ must be $x$ and the other one must be greater or equal to $x$. Hence, $min(max(x,y),max(x,z))$ must be $x$. Thus, $max(x,min(y,z))=min(max(x,y),max(x,z))=x$
- case 2: $x<min(y,z)$
	- $max(x,min(y,z))=min(y,z)$
	- $max(x,y)=y$ and $max(x,z)=z$, so we have $min(max(x,y),max(x,z))=min(y,z)$
	- $max(x,min(y,z))=min(max(x,y),max(x,z))=min(y,z)$
Hence, the statement $max(x,min(y,z))=min(max(x,y),max(x,z))$ always holds
Therefore,
$$
lcm(a,gcd(bc))=\prod_{i}p_{i}^{max(e_{i},min(f_{i},g_{i}))}=\prod_{i}p_{i}^{min(max(e_{i},f_{i}),max(e_{i},g_{i}))} =gcd(lcm(a,b),lcm(a,c))
$$
The claim is proved.