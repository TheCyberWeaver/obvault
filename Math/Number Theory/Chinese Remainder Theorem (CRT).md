## Generally

> [!NOTE]
> Let $m_{1},m_{2},\dots ,m_{r}$ be pairwise relatively prime integers and let $M=\prod _{i=1}^{r}m_{i}$. For every list $a_{1},\dots,a_{r}$ with $0\leq a_{i}<m_{i}$ for $1\leq i\leq r$, the system of congruence equations
> $$
> \begin{cases}
> x\equiv _{m_{1}}a_{1} \\
> x\equiv _{m_{2}}a_{2} \\
> \dots \\
> x\equiv _{m_{r}}a_{r}
> \end{cases}
> $$
> has a unique solution $x$ satisfying $0\leq x<M$

## Case: r=2
> [!NOTE]
> Let $n_1$​ and $n_2$​ be two positive integers that are **coprime** ($\gcd(n_1,n_2)=1$). Then for **any** pair of residues $a_1$​ and $a_2$​, the system
> 
> $$\begin{cases} x \equiv a_1 \pmod{n_1},\\ x \equiv a_2 \pmod{n_2}, \end{cases}$$
> has a **unique** solution modulo $M=n_1n_2​$.

## A simple constructive example

$$\begin{cases} x \equiv 2 \pmod{3},\\ x \equiv 3 \pmod{5}, \end{cases}$$
$$M=3*5=15$$ $M_i=M/n:$ $$M_1=15/3=5,\ M_{2}=15/5=3$$ Find the modular inverse: $M_{i}N_{i}\equiv _{m_{i}}1$
$$N_1: 5N_1 \equiv 1\pmod{3} \implies N_1=2$$ $$N_2: 3N_2 \equiv 1\ \pmod{5} \implies N_2=2$$ 
 Switch the parts together: ($r=2$ the number of equations)
 $$x \equiv_{15} \sum_{i=1}^{r} a_{i}M_{i}N_{i}\equiv _{15} a_1M_1N_1 + a_2M_2N_2 \equiv_{15} 2*5*2+3*3*2 =38 \equiv_{15} 8\ (mod 15)$$ $$x=8+15k,\ k\in \mathbb{N}$$