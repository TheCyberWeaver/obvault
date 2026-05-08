> [!Note] Problem
> Given a network $N=(V,A,c,s,t)$, find the flow $f$ with the greatest [[Flow Network#Definition - Value|value]]

## Definition - cut
A **cut** in the network is a partition of the vertex set $V$ into two disjoint subsets $S$ and $T$ such that $s \in S, t \in T$

The **capacity** of a cut $(S, T)$ is the total capacity of all edges from $S$ to $T$:
$$
c(S, T)
\;=\;
\sum_{\substack{u \in S \\ v \in T}} c(u, v).
$$

### Example
![[Pasted image 20260507104159.png|275]]

**Observation**
Any **s-t cut** in a flow network places an **upper bound** on the value of any feasible flow.

## Maximum flow
If we find, for a flow $f$, an $s$-$t$ cut $(S, T)$ such that
$$
\operatorname{cap}(S, T) = \operatorname{val}(f)
$$
then $f$ is a **maximum flow**

### Lemma
We claim:

$\text{val}(f)\overset{ (i) }{ = }f(S,T)-f(T,S)\overset{ (ii) }{ \leq } f(S,T)\overset{ (i i i) }{ \leq }\text{cap}(S,T)$

(i) 

$$
\operatorname{val}(f)
= \sum_{u \in V : (s,u) \in A} f(s,u)
- \sum_{u \in V : (u,s) \in A} f(u,s)
$$
$$
= \sum_{v \in S}
\underbrace{ \left(\sum_{u \in V : (v,u) \in A} f(v,u) - \sum_{u \in V : (u,v) \in A} f(u,v) \right) }_{ =0 \text{ for }v\neq s }
$$
$$
= \sum_{(u,w) \in (S \times T) \cap A} f(u,w)
-
\sum_{(u,w) \in (T \times S) \cap A} f(u,w)
$$ ($S\times T\cap A$ makes sure those edges exist (equivalently all edges ($u$,$v$) such that $u\in S$ and $v\in V$))
$$
= f(S,T) - f(T,S)
$$

(ii) proved by showing $f(S,T)\geq0$ 
(iii) proved by [[Flow Network#Capacity Constraint|capacity constraint]]


## Maxflow-Mincut Theorem
> [!Important] Maxflow-Mincut Theorem
> In any [[Flow Network|flow network]], the maximum value of a flow equals the minimum capacity of an s-t cut

formally
$$
\text{max}_{f} \text{val(f)}=\text{min}_{(S,T)} \text{cap}(S,T)
$$
This means we could find a minimum $s$-$t$ cut in finite steps, and a minimal cut always exists. 


## Characterization of Maximum Flow

Let $N$ be a network (without oppositely directed edges).

A flow $f$ is a **maximum flow** $\;\Longleftrightarrow\;$ there is no directed $s$–$t$ path in the residual network $N_f$.

For every maximum flow $f$, there exists an $s$–$t$ cut $(S, T)$ such that
$$
\operatorname{val}(f) = \operatorname{cap}(S, T).
$$

**Proof** $\Longleftarrow$
There is no directed $s$–$t$ path in the residual network $N_f$ $\implies$  there exists an $s$–$t$ cut $(S, T)$ such that $\operatorname{cap}(S, T) = \operatorname{val}(f)$ $\implies f$ is a maximum flow.

$S:=$ nodes in $N_{f}$ that can be reached from $s$
$T:=V\setminus S$

For all $e\in(S\times T)\cap A$ there is $f(e)=c(e)\implies f(S,T)=\text{cap}(S,T)$
For all $e'\in(T\times S)\cap A$ there is $f(e')=0\implies f(T,S)=0$
$\implies\text{val}(f)=f(S,T)-f(T,S)=\text{cap}(S,T)$ 
