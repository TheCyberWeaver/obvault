> [!NOTE]
> Let $n_1$​ and $n_2$​ be two positive integers that are **coprime** ($\gcd(n_1,n_2)=1$). Then for **any** pair of residues $a_1$​ and $a_2$​, the system
> 
> $$\begin{cases} x \equiv a_1 \pmod{n_1},\\ x \equiv a_2 \pmod{n_2}, \end{cases}$$
> has a **unique** solution modulo $N=n_1n_2​$.

**A simple constructive example**

$$\begin{cases} x \equiv 2 \pmod{3},\\ x \equiv 3 \pmod{5}, \end{cases}$$
$$N=3*5=15$$ $N_i=N/n:$ $$N_1=15/3=5,\ N2=15/5=3$$ Find the modular inverse: $$y_1: 5y_1 \equiv 1\ (mod 3) => y_1=2$$  $$y_2: 3y_2 \equiv 1\ (mod 5) => y_2=2$$ 
 Switch the parts together:$$x \equiv a_1N_1y_1 + a_2N_2y_2 \equiv 2*5*2+3*3*2 =38 \equiv 8\ (mod 15)$$ $$x=8+15k,\ k\in \mathbb{N}$$
 