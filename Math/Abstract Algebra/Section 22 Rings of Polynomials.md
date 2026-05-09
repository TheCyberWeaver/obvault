## Intro
The Ring $R[x]$ contains the polynomials with coefficients in the ring $R$. We will call x an **indeterminate** (不定元) rather than a variable.

Definition of a polynomial as an infinite formal sum
$$\sum^{\infty}_{i=0}a_ix^i = a_0+a_1x+\cdots+a_nx^n+\cdots$$
so that we have $0+a_1x$ and $0+a_1x+0x^2$ regarded as the same polynomial

> [!Tips]
> The degree of $f(x)$ is the largest i such that $a_i\neq 0$. If all $a_i=0$, then the degree of $f(x)$ is undefined.

- It can be proven that $(R[x])[y]$ is isomorphic to $(R[y])[x]$ 
So we can write $R[x,y]$ as the ring of polynomials in two indeterminates x and y with coefficients in R.

## 22.4 The Evaluation Homomorphisms for Field Theory

Define the map $\phi_a:F[x]\rightarrow E$ as $$\phi_\alpha(a_0+a_1x+\cdots+a_nx^n)=a_0+a_1\alpha+\cdots+a_n\alpha^n$$
![[Pasted image 20250617213627.png|333]]
$\phi$ is a homomorphism because:
$$\phi_\alpha (f(x)+g(x))=\phi_\alpha (f(x))+\phi_\alpha (f(x))$$
$$\phi_\alpha (f(x)g(x))=\phi_\alpha (f(x))\phi_\alpha (f(x))$$
If $F$ is a [[Field|field]] then $F[x]$ is an [[Integral Domain|integral domain]], meaning the polynomial is solvable under factorization.
