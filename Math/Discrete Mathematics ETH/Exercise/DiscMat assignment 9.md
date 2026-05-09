 #exercise 
# 9.3 Pitfalls of RSA
#### 1) Small Moduli
##### a)
We first factorize $n=133$ into $p=7$ and $q=19$
$f=\phi(n)=(p-1)(q-1)=108$
We know $d=e^{-1} \pmod{f}$ and $e$ has a modular inverse if and only if $gcd(e,f)=1$
Using Corollary 4.5, there exist $u,v\in \mathbb{Z}$ such that
$gcd(e,f)=1=u\cdot e+v\cdot f=25u+108v=1$
using the fact that $13\cdot25-3\cdot108=1$, we get $u=13,v=-3$
$d=u=13$
##### b)
$m=c^{d}\pmod{n}=R_{133}(9^{13})$
We first calculate $R_{7}(9^{13})$
$9^{13}\equiv_{7}2^{13}\equiv_{7} (2^{3})^{4}\cdot2\equiv_{7} 8^{4}\cdot2\equiv_{7}1^{4}\cdot2\equiv_{7}2$
We the calculate $R_{19}(9^{13})$
$9^{13}\equiv _{19}(9^{2})^{6}\cdot9\equiv _{19}81^{6}\cdot9\equiv _{19} 5^{6}\cdot9\equiv _{19} 25^{3}\cdot9\equiv _{19}6^{3}\cdot9\equiv _{19} 216\cdot9\equiv _{19} 7\cdot9\equiv _{19} 6$
We now solve the equation system (using CRT)
$
\begin{cases}
x\equiv 2\pmod{7} \\
x\equiv 6\pmod{19}
\end{cases}
$
We get $x=44\pmod{133}$
$m=R_{133}(9^{13})=44$
#### 2) Modulus shared between multiple users
**Case 1**: $c_{A}$ and $c_{B}$ are coprime to $n$, $gcd(c_{A},n)=gcd(c_{B},n)=1$
We know $gcd(e_{A},e_{B})=1$
using corollary 4.5 we get $ue_{A}+ve_{B}=1$ where $u,v\in \mathbb{Z}$
Eve can efficiently compute such $u,v$ using the extended Euclidean algorithm.
We know:
$c_{A}\equiv _{n}m^{e_{A}}$ , $c_{B}\equiv _{n} m^{e_{B}}$
Therefore,
$(c_{A})^{u}(c_{B})^{v}\equiv _{n}(m^{e_{A}})^{u}(m^{e_{B}})^{v}\equiv _{n}m^{ue_{A}+ve_{B}}\equiv _{n}m^{1}\equiv _{n}m$ 

There are two sub cases:
- If $u,v\geq0$: just compute $m$ using $R_{n}((c_{A})^{u}(c_{B})^{v})$
- If at least one of $u,v$ is negative:
	- Assume without loss of generosity that $u$ is negative, we write $u=-u'$
	- $(c_{A})^{u}=(c_{A})^{-u'}=(c_{A}^{-1})^{u'}$
	- Since $gcd(c_{A},n)=1$, we can write it as $ac_{A}+bn=1$ using corollary 4.5, where $a,b\in \mathbb{Z}$
	- Again we can calculate $a,b$ using extended Euclidean algorithm
	- we get $c_{A}^{-1}$ by $c_{A}^{-1}=a$ and calculate $m$ using $R_{n}((c_{A}^{-1})^{u'}(c_{B})^{v})$

**Case 2**: At least one of $u,v$ is not co-prime to n
Assume without loss of generosity that $gcd(c_{A},n)\neq1$
Let $g=gcd(c_{A},n)$ where $g\neq1$
$\implies g|n$
- $g=n$:
	- then $c_{A}\equiv _{n}0$ 
	- $\implies e_{A}^{m}\equiv _{n}0\implies m\equiv _{n}0\implies m=0$
- $1<g<n$: 
	- we know $n=pq$ where $p,q$ are prime numbers and $p,q\neq n$
	- Let $p=g$, $q=\frac{n}{g}$, we can then easily compute $\phi(n)=(p-1)(q-1)$
	- Once we have $f=\phi(n)$, we can then compute $d_{A}\equiv _{f} e_{A}^{-1}$ using the extended Euclidean algorithm.
	- Now we have the decryption key, we can compute $m$ using $R_{n}((c_{A})^{d_{A}})$
