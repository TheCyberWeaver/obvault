$$
\ln(n!)=n\ln n-n+O(\ln n)
$$
![[Pasted image 20251006105129.png|388]]

### explanation
$\ln(n!)-n\ln n+n\leq c\ln n \quad \exists c>0$
$\frac{n!}{\frac{n^{n}}{e^{n}}}\leq n^{c}$
$n!\leq\left( \frac{n}{e} \right)^{n}\cdot n^{c}$

**Another approach**
$n!<\left( \frac{n}{2} \right)^{n}<n^{n}\implies \lim_{ n \to \infty } \frac{n^{n}}{n!}=\infty$

