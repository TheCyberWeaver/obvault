#eth #exercise 
# 0.1

## a
Hypothesis: $\sum_{i=0}^n i=\frac{n(n+1)}{2}$
Base: $1=1$
Steps: $n\to n+1$
- $1+\dots+n+(n+1)=\frac{(n+1)(n+2)}{2}=\frac{n(n+1)}{2}+\frac{2(n+1)}{2}=\frac{n(n+1)}{2}+n+1$

## b
![[Pasted image 20250922100307.png|540]]
Hypothesis: $T(n)\geq 6n^{2} -2n$
Base: $T(1)=4\geq 4$
Steps: $k\to k+1$
- $n=2^k, n\to 2n$
- $T(2n)\geq 4T(n)+6n$
- $\geq4(6n^{2}-2n)+6n$
- $=24n^{2}-2n$
- $\geq 24n^{2}-4n$
- $=6(2n)^{2}-2(2n)$
# Asymptotic Growth

> [!NOTE]
> f grows asymptotically faster than g if $\lim_{ n \to \infty }\frac{g(n)}{f(n)}=0$
> Formal Definition:
> $\forall\varepsilon>0,\exists N \in \mathbb{N}: \forall i\geq N$ 
> $$\frac{g(i)}{f(i)}<\varepsilon$$ 

# 0.2
a) $\lim_{ n \to \infty }\frac{n}{n\log n}=\lim_{ n \to \infty }\frac{1}{\log n}$
	$N:=\lceil 2^{1/\varepsilon} \rceil$
	$\forall i\geq N, \frac{g(i)}{f(i)}=\log i\leq \log N<\varepsilon$
b) $\lim_{ n \to \infty } \frac{10n^{2}+100n+1000}{n^3}\leq \frac{10n^{2}+100n^{2}+1000^{2}}{n^3}=\frac{1110n^{2}}{n^3}=\frac{1110}{n}$
	$N:=\lceil \frac{1110}{\varepsilon} \rceil$
	$\forall i\geq N, \frac{g(i)}{f(i)}\leq\frac{1110}{i}\leq \frac{1110}{N}<\varepsilon$
c) $\lim_{ n \to \infty }\frac{2^n}{3^n}=\left( \frac{2}{3} \right)^n$
	$N:=\lceil \log_{\frac{2}{3}}\varepsilon \rceil$
	$\forall i\geq N, \frac{g(i)}{f(i)}\leq \left( \frac{2}{3} \right)^i\leq \left( \frac{2}{3} \right)^N<\varepsilon$

# 0.3
a) $\lim_{ n \to \infty }\frac{n\ln n}{n^{1.01}}=\frac{1+\ln n}{1.01n^{0.01}}=\frac{\frac{1}{n}}{1.01\cdot 0.01n^{-0.99}}=\frac{1}{1.01\cdot0.01n^{0.01}}=0$
b) $\lim_{ n \to \infty } \frac{n}{e^n}=\frac{1}{e^n}=0$
c) $\lim_{ n \to \infty } \frac{n^{2}}{e^n}= \frac{2n}{e^n}=\frac{1}{e^n}=0$
d) $\lim_{ n \to \infty }=\frac{n^{100}}{1.01^n}=\frac{100!}{(\ln 1.01)^{100}1.01^n}=0$
e) $\lim_{ n \to \infty }= \frac{\log \log n}{\log n}=\frac{\log n}{n}=\frac{1}{n\ln 2}=0$
f) $\lim_{ n \to \infty }\frac{(\log n)^{100}}{2^{\sqrt{ \log n }}}=\frac{x^{200}}{2^x},x=\sqrt{ \log n }$
	$=\frac{200!}{(\ln 2)^{200} 2^x}=0$
g) $\lim_{ n \to \infty }\frac{2^{\sqrt{ \log n }}}{n^{0.01}},x=\sqrt{ \log n }$
	$=\frac{2^{\sqrt{ x }}}{2^{0.01x}}=2^{\sqrt{ x }-0.01x}$
	Note that $\lim_{ x \to \infty }\sqrt{ x }-0.01x=-\infty$
	$\lim_{ x \to \infty }2^{\sqrt{ x }-0.01x}=0$

# 0.4
a) $n^{3}$
b) $n^{3}$
c) $n^{2}$
d) $n\log n$
e) $\log n$
f) $n^{\frac{\log_{5} \log_{6} n}{4}}$

# 0.5

