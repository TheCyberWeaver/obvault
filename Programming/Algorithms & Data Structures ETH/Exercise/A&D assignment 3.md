#eth #exercise 
# 3.1 Asymptotic growth
a)
$\lim_{ n \to \infty } \frac{\log _{a}(n)}{\log _{b}(n)}=\log _{b}a=C\in \mathbb{R}^{+}$
$\implies \log _{a}(n)\leq O(\log _{b}(n))$ and $\log _{b}(n)\leq O(\log _{a}(n))$
$\implies \log _{a}(n)=\Theta(\log _{b}(n))$
The statement is proved

$\lim_{ n \to \infty } \frac{a^{n}}{b^{n}}=\lim_{ n \to \infty }\left( \frac{a}{b} \right)^{n}$
If $a>b$ then $\frac{a}{b}>1$ meaning that $\lim_{ n \to \infty } \frac{a^{n}}{b^{n}}=\infty$
In this case $a^{n}\not\leq O(b^{n})$
Te statement is disproved

b)
$\lim_{ n \to \infty } \frac{n}{\log(n)}=\lim_{ n \to \infty } \frac{1}{\frac{1}{n}}=\lim_{ n \to \infty }n=\infty$
The statement is proved

$\lim_{ n \to \infty }n(e^{1/n}-1)=\lim_{ n \to \infty } \frac{e^{1/n}-1}{\frac{1}{n}}$
Note that:
	$\lim_{ n \to \infty }e^{1/n}-1=0$
	$\lim_{ n \to \infty } \frac{1}{n}=0$
$\lim_{ n \to \infty } \frac{e^{1/n}-1}{\frac{1}{n}}=\lim_{ n \to \infty } \frac{-n^{-2}e^{1/n}}{-n^{-2}}=\lim_{ n \to \infty }e^{1/n}=e^{0}=1$
The statement is proved


$\lim_{ n \to \infty } \frac{\frac{n^{1/n}-1}{n}}{ \frac{\ln(n)}{n^{2}}}= \lim_{ n \to \infty }\frac{(n^{1/n}-1)}{\frac{\ln(n)}{n}}=\lim_{ n \to \infty } \frac{e^{\frac{\ln n}{n}}-1}{\frac{\ln n}{n}}$
We can show that $\lim_{ n \to \infty } \frac{\ln n}{n}=\lim_{ n \to \infty } \frac{1}{n}=0$
So $\lim_{ n \to \infty } \frac{e^{\frac{\ln n}{n}}-1}{\frac{\ln n}{n}}=\lim_{ x \to 0 } \frac{e^{x}-1}{x}=\lim_{ x \to 0 }e^{x}=e^{0}=1$
The statement is proved

# 3.2 substring counting

a) naive algorithm

```
has_k_ones(string s)
	int cnt = 0
	for i=0 to s.length-1
		if s[i]=='1' then cnt++
	if cnt==k then return true
	else return false
```

```
int cnt=0
for i=0 to n-k
	for j=i+k to n
		if has_k_ones(s[i:j])
		cnt++
```

We need $O(n^{2})$ time to iterate through every possible substring of $S$, and for each substring we need $O(n)$ time to check if it has $k$ ones (using the function has_k_ones). Thus, we need $O(n^{3})$ time to solve the problem

b)
``` hl:3
t[0...n]
int j=0
for i=0 to n-1
	if s[i]==1
		j++
	t[j]++
```

the pseudocode contains a single loop that iterate through the string. Thus the runtime is $O(n)$

c)
```
cnt=0
for l=0 to k
	cnt+=suffix[l]*prefix[k-l]
```
If there is `l` ones in the suffix of $S[0\dots m]$, there should be `k-l` ones in the prefix of $S[m+1\dots j]$. And the pseudocode adds up all the possible combinations of suffix of $S[0\dots m]$ and prefix of $S[m+1\dots j]$. 

This step costs k operations. Since when $k>n$ the solution of the problem is trivial, we always have $k\leq n$. Thus this step costs $O(n)$

d)
```
spanning(m,k,s)
	suffix[]=calcualte_suffix()
	prefix[]=calcualte_prefix()
	cnt=0
	for l=0 to k
		cnt+=min(suffix[l],prefix[k-l])
	
	leftstring=s[0:m]
	rightstring=s[m+1:s.length]
	
	cnt+=spanning(leftstring.length/2,k,leftstring)
	cnt+=spanning(rightstring.length/2,k,rightstring)
	return cnt
```

$T(n)=2T\left( \frac{n}{2} \right)+O(n)$
$T(n)=2\left( \underbrace{ 2T\left( \frac{n}{4} \right) }_{ \log _{2}n \text{ times} }+O\left( n \right) \right)+O(n)$
$T(n)=2^{\log _{2}n}+\log _{2}n\cdot O(n)$
$T(n)=O(n\log n)$

# 3.3 Counting function calls in loops

a)
$2(n+1)+2n+1=4n+3$
$\Theta(n)$

b)
$1^{3}+2^{3}+\dots+n^{3}=(1+2+\dots+n)^{2}=\left( \frac{n(n+1)}{2} \right)^{2}= \frac{n^{2}(n+1)^{2}}{4}$
$\Theta(n^{4})$

### Another method
$$
\sum_{i=1}^{n} i^{3}=\Theta(n^{4})
$$
**Proof**:
$$
(n+1)^{4}-1=\sum_{i=1}^{n} i^{4}-(i-1)^{4}=\sum_{i=1}^{n} i^{4}-(i^{4}-4i^{3}+6i^{2}-4i+1)
$$
$$
=4\sum_{i=1}^{n} i^{3}-6\sum_{i=1}^{n} i^{2}+4\sum_{i=1}^{n} i-\sum_{i=1}^{n} 1
$$

# 3.4
a)
```
int f[n]
f[0]=0
f[1]=1
for i=2 to n
	f[i]=f[i-1]+f[i-2]
```

The algorithm costs $O(n)$
The algorithm contains a single loop that iterate from 2 to n. Within each iteration only one addition operation will be operated.

***Optimize the storage ($O(1)$ memory)***
```
f0=0
f1=1
for i=2 to n
	f0,f1=f1,f0+f1
return f1
```


b)
```
int f[]
int i=0
while f[i]<k do
	f[i+1]=f[i]+f[i-1]
	i++
```
The algorithm continues to calculate the next Fibonacci number until it reaches $k$, so that we know `f[i]` is the answer when the program ends.

Using the bound proved in [[A&D assignment 2#2.2 Fibonacci numbers|Exercise 2.2]] , we know $f_{n}\geq \frac{1}{3}\cdot 1.5^{n}$
so we can find the answer as long as  $\frac{1}{3}\cdot 1.5^{n}\geq k$
$1.5^{n}\geq3k$
$n\geq \log_{1.5}3k$
assume n is the smallest n
$n=\left\lceil  \frac{\log 3k}{\log 1.5}  \right\rceil$
$n\leq\frac{\log 3k}{\log 1.5}+1=\frac{\log 3+\log k}{\log 1.5}+1= \frac{\log k}{\log 1.5}+\frac{\log 3}{\log 1.5}+1$
Therefore, there exists $C,D\in R$ such that
$n\leq C\cdot \log k+D$
Hence
$n=O(\log k)$

# 3.5
a)
$A_{n}(a)=\left( A_{\frac{n}{2}}(a) \right)^{2}$

b)
```
power(a,n)
	if(n==1)return a
	int ans=power(a,n/2)
	return ans*ans
```

c)
$\log_{2}n$ times of integer multiplications

d)
IH: $Power(a,n)=a^{n}$ for all $n\in \mathbb{N}$ of the form $n=2^{k}$ for some $k\in \mathbb{N}_{0}$
Base: $k=0$
	$n=2^{0}=1$
	$Power(a,1)=a=a^{1}$ (shown by the line 2)
IS: $k\to k+1$
	$n\to 2n$
	$Power(a,2n)=Power(a,n)\cdot Power(a,n)=a^{n}\cdot a^{n}=a^{2n}$ (shown by the line 3 and 4)

e)
```c++
int power(int a, int n) {
    if (n == 0) return 1;
    int ans = power(a, n / 2);
    ans *= ans;
    if (n & 1) ans *= a;
    return ans;
}
```
OR
```c++
int power(int a,int n){
	return n?power(a*a,n/2)*(n&1?a:1):1;
}
```