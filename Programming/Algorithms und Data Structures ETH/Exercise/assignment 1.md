#eth #exercise
# 1.1
![[Pasted image 20250922213827.png|522]]
Base: $S_{1}=1^3=\frac{1^{2}(1+1)^{2}}{4}=1$
Steps: $n\to n+1$
- $1^{3}+\dots+n^{3}+(n+1)^{3}$
- $=\frac{n^{2}(n+1)^{2}}{4}+(n+1)^{3}$
- $=\frac{n^{2}(n+1)^{2}}{4}+n^{3}+3n^{2}+3n+1$
- $=\frac{n^{2}(n+1)^{2}}{4}+\frac{4n^{3}+12n^{2}+12n+4}{4}$
- $=\frac{n^{2}(n+1)^{2}}{4}+\frac{4n(n^{2}+2n+1)+(4n^{2}+8n+4)}{4}$
- $=\frac{n^{2}(n+1)^{2}+4n(n+1)^{2}+4(n+1)^{2}}{4}$
- $=\frac{(n+1)^{2}(n^{2}+4n+4)}{4}$
- $=\frac{(n+1)^{2}(n+2)^{2}}{4}$
# 1.2
The proof re-derives the induction hypothesis, and does not prove for the $k+1$ case.
In order to prove the hypothesis, one need to prove $\sqrt{ k }+\frac{1}{\sqrt{ k+1 }}\leq \sqrt{ k+1 }$ which is actually false.  
# 1.3
a) $\lim_{ m \to \infty } \frac{100m^{3}+10m^{2}+m}{0.001m^5}\leq\lim_{ m \to \infty } \frac{111m^{3}}{0.001m^5}=\lim_{ m \to \infty }\frac{111000}{m^2}=0$
b) $\lim_{ m \to \infty } \frac{\log(m^{3})}{(\log m)^{3}}=\lim_{ m \to \infty }\frac{3\log m}{(\log m)^{3}}=\lim_{ m \to \infty }\frac{3}{(\log m)^{2}}=0$
c) $\lim_{ m \to \infty } \frac{e^{2m}}{2^{3m}}=\lim_{ m \to \infty }\left( \frac{e^{2}}{8} \right)^m \approx \lim_{ m \to \infty }0.92^m=0$ 
d) $\lim_{ m \to \infty } \frac{\log(f(m))}{\log(g(m))}$ 
	Counterexample:
	$f(m)=e^{2m}$, $g(m)=2^{3m}$
	$\lim_{ m \to \infty } \frac{2m}{\ln (2) \cdot 3m}=\frac{2}{3\ln(2)}$
The statement is disapproved.

e) $\lim_{ m \to \infty } \frac{\ln(\sqrt{ \ln(m) })}{\sqrt{ \ln(\sqrt{ m }) }}= \lim_{ m \to \infty }\frac{\frac{1}{2}\ln(\ln (m))}{\sqrt{ \frac{1}{2}\ln(m) }}$ 
	let $x=\ln (m)$
	$=\lim_{ x \to \infty }\frac{\ln(x)}{2\sqrt{ \frac{1}{2}x }}=\frac{\ln(x)}{\sqrt{ 2x }}$
	$=\lim_{ x \to \infty }\frac{\frac{1}{x}}{\frac{\sqrt{ 2 }}{2} \frac{1}{\sqrt{ x }}}=\lim_{ x \to \infty }\frac{\sqrt{ 2 }}{\sqrt{ x }}=0$ (L'Hopital's rule)
# 1.4

a) 
Hypothesis: $\frac{1}{2}\cdot \frac{3}{4}\cdot\dots \cdot \frac{2n-1}{2n}\leq \frac{1}{\sqrt{ 3n+1 }},\quad n\geq 1$
Base: $n=1$: $\frac{1}{2}\leq \frac{1}{\sqrt{ 3\cdot 1+1 }}=\frac{1}{2}$
Steps: $\frac{1}{2}\cdot \frac{3}{4}\cdot\dots \cdot \frac{2n-1}{2n}\cdot \frac{2(n+1)-1}{2(n+1)}\leq \frac{1}{\sqrt{ 3n+1 }}\cdot \frac{2n+1}{2n+2}$
- $\frac{1}{\sqrt{ 3n+1 }}\cdot \frac{2n+1}{2n+2}\leq \frac{1}{\sqrt{ 3n+4 }}$
- $(2n+1)\sqrt{ 3n+4 }\leq(2n+2)\sqrt{ 3n+1 }$
- $(2n+1)^{2}(3n+4)\leq(2n+2)^{2}\sqrt{ 3n+1 }$
- $(4n^{2}+4n+1)(3n+4)\leq (4n^{2}+8n+4)(3n+1)$
- $12n^{3}+28n^{2}+19n+4\leq 12n^{3}+28n^{2}+20n+4$
- $0\leq n$
which is true because $n\geq 1$, and the hypothesis is proven.

b)
![[Pasted image 20250923165050.png]]

Although the statement $\frac{1}{2}\cdot \frac{3}{4}\cdot\dots \cdot \frac{2n-1}{2n} \leq\frac{1}{\sqrt{3x+1}} \leq\frac{1}{\sqrt{3x}}$ is true, we need to calculate $\frac{\sqrt{ 3n }}{\sqrt{ 3n+3 }}$ instead of $\frac{\sqrt{ 3n+1 }}{\sqrt{ 3n+4 }}$ during the induction proof. However, the following inequality holds for all $n\geq1$ 
$$\frac{\sqrt{ 3n }}{\sqrt{ 3n+3 }}\leq \frac{\sqrt{ 3n+1 }}{\sqrt{ 3n+4 }}$$
, which means we have a stricter boundary causing the induction proof to fail.


