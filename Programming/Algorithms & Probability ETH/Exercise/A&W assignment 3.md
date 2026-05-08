## T3.1 Probability spaces

## a)  
![[Pasted image 20260401225849.png]]
### Probability space
The sample space is $\Omega = \{1,2,3,4,5,6\}^3$  
An atomic event is one concrete outcome $(x_1,x_2,x_3)$, where $x_i$ is the result of die $i$.  
$\Pr[(x_{1},x_{2},x_{3})]=\frac{1}{\lvert \Omega \rvert}=\frac{1}{216}$
### sum at least 16  
We want all triples $(x_1,x_2,x_3)$ such that $x_1 + x_2 + x_3 \ge 16$
Sum = 18  
$$
(6,6,6)
$$
Sum = 17  
$$  
(5,6,6),\ (6,5,6),\ (6,6,5)  
$$
Sum = 16  
$$  
(4,6,6),\ (6,4,6),\ (6,6,4),\ (5,5,6),\ (5,6,5),\ (6,5,5)
$$
### Probability of $E$  
There are 10 atomic events:  
$$  
\Pr(E) = \frac{\lvert E \rvert }{\lvert \Omega \rvert }= \frac{10}{216} = \frac{5}{108}.  
$$
### first die shows 6 given $E$  
$$  
\Pr(x_1=6 \mid E) = \frac{\Pr(x_1=6 \cap E)}{\Pr(E)}.  
$$
There are 6 atomic events in $E$ whose first dice shows 6. Hence
$$  
\Pr(x_1=6 \mid E)  
= \frac{6/216}{10/216}  
= \frac{6}{10}  
= \frac{3}{5}.  
$$
## b)
![[Pasted image 20260401225855.png]]
### Probability space  
An atomic event is an ordered 4-tuple of distinct cards:  
$$  
\Omega = \{(c_1,c_2,c_3,c_4): c_i \text{ distinct cards}\}.  
$$
with $c_1,c_2$ are Alice’s cards and $c_3,c_4$ are Bob’s cards  
Number of atomic event $52 \cdot 51 \cdot 50 \cdot 49=6,497,400$
$\Pr[(c_{1},c_{2},c_{3},c_{4})]=\frac{1}{\lvert \Omega \rvert}=\frac{1}{6497400}$
### Computations
$$
\Pr[A]= \frac{3}{51} = \boxed{\frac{1}{17}}
$$
$$
\Pr[B]=\Pr[A]=\boxed{\frac{1}{17}}
$$

$\Pr[A\cap B]=\Pr[A]\cdot \Pr[B|A]$
We first calculate $\Pr[B|A]$
case 1:  Bob's first card has the same value as Alice's pair
contribution: $\frac{2}{50}\cdot \frac{1}{49}$
case 2:  Bob's first card does not have the same value as Alice's pair
contribution: $\frac{48}{50}\cdot \frac{3}{49}$
In total $\Pr[B|A]=\frac{2}{50}\cdot \frac{1}{49}+\frac{48}{50}\cdot \frac{3}{49}=\frac{146}{2450}=\frac{73}{1225}$
Therefore  
$$  
\Pr[A\cap B]=\Pr[A]\cdot \Pr[B|A] 
= \frac{1}{17}\cdot\frac{73}{1225}  
= \boxed{\frac{73}{20825}}  
$$
$$
\Pr[A|B]=\frac{\Pr[A\cap B]}{\Pr[B]}=\frac{\frac{73}{20825}}{\frac{1}{17}}=\boxed{\frac{73}{1225}}
$$
## c)
![[Pasted image 20260401225901.png]]
### Probability space  
$$  
\Omega = \{M,N\} \times \{H,T\}^k.  
$$
with ${} \Pr[N]=\Pr[M]=\frac{1}{2} {}$

### Pr\[N|E\]
We first calculate $\Pr[E]$ :
By total probability $\Pr[E]=\Pr[E\cap N]+\Pr[E\cap M]=\Pr[E|M]\cdot\Pr[M]+\Pr[E|N]\cdot \Pr[N]$
  
we know $\Pr[E\mid M]=1,  \qquad  \Pr[E\mid N]=\left(\frac12\right)^k$
Hence
$$  
\Pr[E] 
= \frac12 + \frac{1}{2^{k+1}}
$$
By Bayes’ rule:  
$$
\Pr(N\mid E)= \frac{\Pr(E\mid N)\Pr(N)}{\Pr(E)}
$$
By substitution:
$$  
\Pr[N\mid E]  
= \frac{\left(\frac12\right)^k \cdot \frac12}  
{\frac12 + \frac{1}{2^{k+1}}}  
= \frac{\frac{1}{2^{k+1}}}
{\frac12 + \frac{1}{2^{k+1}}}=\boxed{\frac{1}{2^{k}+1}}
$$
### >99%

We want $\Pr[M|E]>0.99$
$$
\Pr[M|E] =1-\Pr[N|E] =1-\frac{1}{2^{k}+1}=\frac{2^{k}}{2^{k}+1}>0.99\;\text{, $k$ is integer}
$$
By using calculator we get $\boxed{k\geq7}$
