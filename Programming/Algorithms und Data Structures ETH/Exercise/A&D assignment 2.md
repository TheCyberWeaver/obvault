#eth #exercise
# 2.1 Induction
a)
IH: $2^{n}>n^{2},\: n\geq5$
Base: $n=5$ 
	$2^{5}=32>25=5^{2}$
IS: $n\to n+1$
- $2^{n+1}=2\cdot 2^{n}\overset{IH }{ > }2n^{2}$
- We need to show that $2n^{2}>(n+1)^{2}$
	- $\Longleftrightarrow n^{2}>2n+1$
	- $\Longleftrightarrow n^{2}-2n+1>2$
	- $\Longleftrightarrow (n-1)^{2}-2>0$
	- for $n\geq5$ the equation holds because for $n=5$:  $(5-1)^{2}-2=14>0$
Hence $2n^{2}>(n+1)^{2}$ and $2^{n+1}>(n+1)^{2}$
Thus, the hypothesis is proved.

b)
IH: $(1+x)^{n}=\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i}$
Base: $n=1$
	$1+x=\sum_{i=0}^{1}\begin{pmatrix}1 \\ i\end{pmatrix}x^{i}=\begin{pmatrix}1 \\ 0\end{pmatrix}x^{0}+\begin{pmatrix}1 \\ 1\end{pmatrix}x^1=1+x$
IS: $n\to n+1$
- $(1+x)^{n+1}=(1+x)^{n}(1+x) \overset{ IH }{ = } (1+x)\cdot\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i}$
- $=\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i}+\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i+1}$
- $=\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i}+\sum_{i=1}^{n+1}\begin{pmatrix}n \\ i-1\end{pmatrix}x^{i}$
- $=\sum_{i=0}^{n}\begin{pmatrix}n \\ i\end{pmatrix}x^{i}+\sum_{i=1}^{n}\begin{pmatrix}n \\ i-1\end{pmatrix}x^{i}+x^{n+1}$
- =$\begin{pmatrix}n \\ 0\end{pmatrix}x^{0}+\sum_{i=1}^{n}\begin{bmatrix}\begin{pmatrix}n \\ i\end{pmatrix}+\begin{pmatrix}n \\ i-1\end{pmatrix}\end{bmatrix}x_{i}+\begin{pmatrix}n+1 \\ n+1\end{pmatrix}x^{n+1}$
- $=\begin{pmatrix}n+1 \\ 0\end{pmatrix}x^{0}+\sum_{i=0}^{n}\begin{pmatrix}n+1 \\ i\end{pmatrix}x^{i}+\begin{pmatrix}n+1 \\ n+1\end{pmatrix}x^{n+1}$
- $=\sum_{i=0}^{n+1}\begin{pmatrix}n+1 \\ i\end{pmatrix}x^{i}$
The hypothesis is proved.
# 2.2 Fibonacci numbers
IH: $f_{n}\geq \frac{1}{3}\cdot 1.5^{n}$ for $n\geq 1$
Base: 
$n=1$
$f_{1}=1\geq 0.5= \frac{1}{3}\cdot 1.5^{1}$
$n=2$
$f_{2}=1\geq 0.75 = \frac{1}{3}\cdot 1.5^{2}$
IS: $n\to n+1$
- $f_{n+1}=f_{n}+f_{n-1}\overset{ IH }{ \geq } \frac{1}{3}(1.5^{n}+1.5^{n-1})$
- We need to show that $\frac{1}{3}(1.5^{n}+1.5^{n-1})\geq \frac{1}{3}\cdot 1.5^{n+1}$
	- $\Longleftrightarrow 1.5^{n}+1.5^{n-1}\geq 1.5^{n+1}$
	- $\Longleftrightarrow (1.5+1)1.5^{n-1}\geq 1.5^{2}\cdot 1.5^{n-1}$
	- $\Longleftrightarrow 2.5>2.25$
Hence $\frac{1}{3}(1.5^{n}+1.5^{n-1})\geq \frac{1}{3}\cdot 1.5^{n+1}$
Thus, the hypothesis is proved.

### better bound
$f_{n}\leq c\cdot\alpha ^{n}$
$1+\alpha=\alpha^{2}$
$\alpha= \frac{1+\sqrt{ 5 }}{2}$

Also known as the the **golden ratio** $\varphi$
# 2.3 O-notation quiz
![[Pasted image 20251001133627.png]]
1. $\lim_{ n \to \infty } \frac{f(n)}{g(n)}=\lim_{ n \to \infty }\frac{2n^{5}+10n^{2}}{\frac{1}{100}n^{6}}=\lim_{ n \to \infty } \frac{200}{n}+\lim_{ n \to \infty } \frac{1000}{n^{4}}=0+0=0$ 
	-  Using Theorem 1, the statement is proved.
2. $\lim_{ n \to \infty } \frac{n^{10}+2n^{2}+7}{100n^{9}}=\lim_{ n \to \infty } \frac{n+2n^{-7}+7n^{-9}}{100}=\infty$
	-  Using Theorem 1, the statement is disproved.
3. $\lim_{ n \to \infty } \frac{e^{1.2n}}{e^{n}}=\lim_{ n \to \infty }e^{0.2n}=\infty$
	- Using Theorem 1, the statement is disproved.
4. $\lim_{ n \to \infty } \frac{n^{ \frac{2n+3}{n+1}}}{n^{2}}=\lim_{ n \to \infty }n^{ \frac{2n+3}{n+1}-2}=\lim_{ n \to \infty }n^{ \frac{1}{n+1}}=\lim_{ n \to \infty }e^{\ln(n^{1/n+1})}=\lim_{ n \to \infty }e^{\frac{\ln n}{n+1}}=e^{0}=1$

![[Pasted image 20251001133621.png]]
$$
f(n)=\begin{cases}
1 \quad \text{when n is odd}\\
2 \quad \text{when n is even}
\end{cases}
$$
$$
g(n)=\begin{cases}
2 \quad \text{when n is odd}\\
1 \quad \text{when n is even}
\end{cases}
$$

# 2.4 
a)
Since $i>2^{j-1}$ 
$\frac{1}{i}\leq \frac{1}{2^{j-1}}$
There are in total $2^{j}-(2^{j-1}+1)+1=2^{j-1}$ terms
so the sum of the terms must be less or equal than $\frac{2^{j-1}}{2^{j-1}}=1$
Thus $S_{j}\leq 1$ is proved.

b)
Since $i\leq2^{j-1}$ 
$\frac{1}{i}\geq \frac{1}{2^{j}}$
There are in total $2^{j}-(2^{j-1}+1)+1=2^{j-1}$ terms
so the sum of the terms must be greater or equal than $\frac{2^{j-1}}{2^{j}}=\frac{1}{2}$
Thus $S_{j}\geq \frac{1}{2}$ is proved.

c)
$\sum_{i=1}^{2^{k}} \frac{1}{i}=1+\sum_{j=1}^{k}S_{j}$
- We know from (a) that $S_{j}\leq 1$ so 
	$1+\sum_{j=1}^{k}S_{j}\leq 1+k\cdot 1=k+1$
- We know from (b) that $S_{j}\geq \frac{1}{2}$ so
	$1+\sum_{j=1}^{k}S_{j}\geq 1+ k\cdot \frac{1}{2}= \frac{2+k}{2}> \frac{k+1}{2}$

d)

$$
\sum_{i=1}^{n} \frac{1}{i}\leq\sum_{i=1}^{2^{\lceil \log _{2}n \rceil}} \leq \lceil \log _{2}n \rceil +1\leq \log _{2}n=2
$$
$$
\sum_{i=1}^{n} \frac{1}{i}\geq \sum_{i=1}^{2^{\lfloor \log _{2}n \rfloor }} \geq \frac{\lfloor \log _{2}n \rfloor +1}{2}\geq \frac{\log _{2}n}{2}
$$
# 2.5 
![[Pasted image 20251001133656.png|474]]
a)
we first show that
$\ln(n!)\leq n\ln n$
$\Longleftrightarrow e^{\ln(n!)}\leq e^{n\ln n}$
$\Longleftrightarrow n!\leq (e^{\ln n})^{n}=n^{n}$
Using the Definition 1 of O-notation:
	We set $f(n)=\ln(n!),g(n)=n\ln n,C=1,N=1.$ Then
	$\ln (n!)\leq C\cdot n\ln n\quad \forall n\geq N$
Thus the statement is proved
**Another approach**
$\ln(n!)=\ln(1\cdot2\cdot\dots\cdot n)=\sum_{i=1}^{n}\ln(i)\leq \sum_{i=1}^{n}\ln(n)=n\ln n$

b)
$\left( \frac{n}{2} \right)^{\frac{n}{2}}\leq n!$
$\Longleftrightarrow \ln\left( \left( \frac{n}{2} \right)^{n/2} \right)\leq \ln(n!)$
$\Longleftrightarrow \frac{n}{2}\ln\left( \frac{n}{2} \right)\leq \ln(n!)$
$\Longleftrightarrow \frac{n}{2}\ln n-\frac{n}{2}\cdot\ln2 \leq \ln(n!)$
so we know $\frac{n}{2}\ln n-\frac{n}{2}\cdot\ln2 \leq O(\ln(n!))$
Hence $\frac{n}{2}\ln n \leq O(\ln(n!))$ using Theorem 2 with the fact that $n<O(\ln(n!))$
And using theorem 2 again we know $n\ln n<O(\ln(n!))$

# Bonus
prove $n^{n}\leq O(n!)$
$n\ln n\leq O(\ln(n!))$
$n\ln n\leq c\cdot \ln(n!)$
$n^{n}\leq (n!)^{c}$
statement disproved

Good to know: [[Stirling's approximation]]
