## Definition - Network
A **Network** is a tuple $(V,A,c,s,t)$
Let $G = (V, A)$ be a acyclic directed graph representing a network. A **flow network** has the following properties:

- Each edge $(u, v) \in A$ has a capacity $c(u, v) \ge 0$.
- There is a distinguished source vertex $s \in V$.
- There is a distinguished sink vertex $t \in V$, with $s \ne t$.

Think of the network as a system of pipes. The source $s$ pumps fluid in, and the sink $t$ collects the outflow.

## Definition - Flow
A **flow** in the network is a function $f : V \times V \to \mathbb{R}$ satisfying the following conditions:

### Capacity Constraint
For all $(u, v) \in E$,
$$
0 \le f(u, v) \le c(u, v)
$$
### Flow Conservation (except at source and sink)
For all $v \in V \setminus \{s, t\}$,
$$
\sum_{u \in V} f(u, v) = \sum_{w \in V} f(v, w)
$$

### Skew Symmetry (convenience condition)
$$
f(u, v) = -f(v, u)
$$

This ensures that defining $f(u, v)$ for existing edges is sufficient — the reverse flow is implicitly determined.

## Example
![[Pasted image 20260507102650.png]]

## Definition - Value
The **value** of a flow $f$ is defined as

$$
\operatorname{val}(f)
\;:=\;
\operatorname{netoutflow}(s)
\;:=\;
\sum_{\substack{u \in V \\ (s,u) \in A}} f(s,u)
\;-\;
\sum_{\substack{u \in V \\ (u,s) \in A}} f(u,s).
$$

> [!NOTE] Lemma
> The **net inflow** of the sink $t$ equals the **value of the flow**, i.e.,
> 
> $$
> \operatorname{netinflow}(t)
> \;:=\;
> \sum_{\substack{u \in V \\ (u,t) \in A}} f(u,t)
> \;-\;
> \sum_{\substack{u \in V \\ (t,u) \in A}} f(t,u)
> \;=\;
> \operatorname{val}(f)
> $$
