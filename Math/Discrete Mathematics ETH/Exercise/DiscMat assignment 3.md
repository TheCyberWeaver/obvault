 #exercise 
# 3.1 Expressing Relationship of Humans in Predicate Logic
1. $\text{great-grandpar}(x,y)\overset{ def }{ \Longleftrightarrow } \exists i,j\quad par(x,i)\wedge par(i,j)\wedge par(j,y)$
2. $\text{cousins}(x,y)\overset{ def }{ \Longleftrightarrow }\exists i,j\;(i\neq j) par(i,x)\wedge par(j,y)\wedge(\exists k\; par(k,i)\wedge par(k,j))$ 

# 3.2 From Natural Language to a Formula

- $\neg \exists x\forall y\; (x>y)$
- $\forall x(prime(x)\to\forall k(k|x\to k=1\vee k=x))$
- $\forall x\;((\exists y\;(x\cdot y=1))\to x=1)$
- $\forall x\;(prime(x)\to \forall a,b\;((x|a\cdot b)\leftrightarrow(x|a\vee x|b)))$

# 3.3 Winning Strategy
1.
$$
\exists a_{1}a_{2}\forall b_{1},b_{2}(a_{1}+(a_{2}+b_{1})^{|b_{2}|+1}=1)
$$
The statement is false

2.
$$
\exists a_{1}\forall b_{1}\exists a_{2}\forall b_{2}(a_{1}+(a_{2}+b_{1})^{|b_{2}|+1}=1)
$$
The statement is true
Alice chooses $a_{1}=0$ and $a_{2}=1-b_{1}$

# 3.4 Indirect Proof of an Implication

1.
**Claim**: $n^{2}$ is odd $\to$ $n$ is odd
**Proof**:
Assume $n$ is even, then $n=2k$ for some $k\in \mathbb{Z}$. Hence
$$
n^{2}=(2k)^{2}=4k^{2}=2(2k^{2})
$$
so $n^{2}$ is even. Thus the contrapositive "$n$ is even $\to$ $n^{2}$" is even holds, so the original statement holds.

2.
**Claim**: $42^{n}-1$ is a prime $\to$ $n$ is odd
**Proof**:
Assume $n$ is even, then $n=2k$ for some $k\in \mathbb{Z}$. Hence
$42^{n}=42^{2k}=(42^{k})^{2}-1=(42^{k}+1)(42^{k}-1)$
so $42^{n}$ can be divided by $42^{k}+1$ and $42^{k}-1$ showing that it is not a prime.
Thus the contrapositive "$n$ is even $\to$ $42^{n}-1$ is not a prime" holds, so the original statement holds.
# 3.5 Case Distinction
1.
**Claim**: $n^{3}+2n+6$ is divisible by $3$ for all $n\in\mathbb{N}$
**Proof**:
case 1: $n=3k$ for some $k\in \mathbb{N}$
$(3k)^{3}+2(3k)+6=27k^{3}+6k+6=3(9k^{3}+2k+2)$
$\implies 3|n^{3}+2n+6$

case 2: $n=3k+1$ for some $k\in \mathbb{N}$
$(3k+1)^{3}+2(3k+1)+6=27k^{3}+27k^{2}+9k+1+6k+2+6=27k^{3}+27k^{2}+15k+9$
$=3(9k^{3}+9k^{2}+5k+3)$
$\implies 3|n^{3}+2n+6$

case 3: $n=3k+2$ for some $k\in \mathbb{N}$
$(3k+2)^{3}+2(3k+2)+6=27k^{3}+54k^{2}+36k+8+6k+4+6=27k^{3}+54k^{2}+42k+18$
$=3(9k^{3}+18k^{2}+14k+6)$
$\implies 3|n^{3}+2n+6$

All cases are proved. Thus the statement holds


2.
**Claim**: $p$ and $p^{2}+2$ are primes $\to$ $p^{3}+2$ is prime
**Proof**:
case 1: $p=3k$ for some $k\in \mathbb{N}$
Since $p$ is a prime, $k$ must be 1, so $p=3$
$p^{2}+2=3^{2}+2=11$ 
$p^{3}+3=3^{3}+2=29$
11 and 29 are primes, the statement holds.

case 2: $p=3k+1$ for some $k\in \mathbb{N}$ 
$p^{2}+2=(3k+1)^{2}+2=9k^{2}+6k+1+2=3(3k^{2}+2k+1)$
$\implies p^{2}+2$ has the factor 3 and therefore not a prime.

case 3: $p=3k+2$ for some $k\in \mathbb{N}$
$p^{2}+2=(3k+2)^{2}+2=9k^{2}+12k+4+2=3(3k^{2}+4k+2)$
$\implies p^{2}+2$ has the factor 3 and therefore not a prime.

The hypothesis forces $p=3$, and then $p^{3}+2$ is a prime. Thus, the statement holds.
# 3.6 Proof by Contradiction
1.
**Claim**: the sum of a rational number and an irrational number is irrational
**Proof**:
Assume the sum of a rational number and an irrational number is rational.
$a+b=c$ where $a,c$ are rational, and $b$ is irrational
$\implies$ $c-a=b$
This contradicts the fact that the difference of two rational numbers is rational, so the original statement holds.

2.
**Claim**: $2^{1/n}$ is irrational for $n>2$
**Proof**:
Assume $2^{1/n}$ is rational, then
$2^{1/n}=\frac{p}{q}$ for some $p,q\in \mathbb{Z}^{+}$
$2^{1/n}q=p$
$2q^{n}=p^{n}$
$q^{n}+q^{n}=p^{n}$
This contradicts the Fermat's Last Theorem, so the original statement holds.

# 3.7 New Proof Patterns

1.
The pattern claims $\neg S \to(T_{1}\vee T_{2})\wedge(\neg T_{1}\vee \neg T_{2})) \models S$
Assume $S:=p$ , $T_{1}:=p$ , $T_{2}:=\neg p$
$((p\vee \neg p)\wedge(\neg p\vee \neg \neg p))\implies (\top\wedge \top)\implies \top$
$\implies\neg p\to \top \models p$ 
$\top \models p$

If $p$ is false, then the statement fails, and therefore does does not prove for $S$
Thus, the proof pattern is not sound.

2.
The pattern claims $\neg R\wedge((S\wedge \neg T)\to R)\models S\to T$
$\implies \neg R\wedge(\neg(S\wedge \neg T)\vee R)\models S\to T$
$\implies (\neg R\wedge \neg(S\wedge \neg T))\vee(\neg R\wedge R)\models S\to T$
$\implies \neg R\wedge \neg(S\wedge \neg T)\models S\to T$
$\implies \neg R\wedge (\neg S\vee \neg \neg T)\models S\to T$
$\implies \neg R\wedge (\neg S\vee T)\models S\to T$
$\implies \neg R\wedge(S\to T)\models S\to T$

Since we showed that $R$ is false, then $\neg R$ is true.
Therefore $\neg R\wedge(S\to T)\equiv S\to T$
and $S\to T\models S\to T$
Thus, the proof pattern is sound.