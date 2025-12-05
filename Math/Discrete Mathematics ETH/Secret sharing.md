Goal: share a secret $S\in F$ between $n$ people so that 
- every combination from $t-1$ people cannot restore $S$
- every combination from $t$ people can restore $S$

For $t=n$:
Choose **randomly** $y_{1},y_{2},\dots,y_{n}$ with $\sum_{i=1}^{n}y_{i}=S$

The general solution ($\lvert F \rvert\geq n+1$)
- choose distinct $\alpha_{0}=0,\alpha_{1},\dots,\alpha _{n}\in F$
- choose **randomly** $a(x)\in F[x]$ from degree $\leq t-1$ with $a(\alpha_{0})=a(0)=S$
- Person $i$ get $a(\alpha _{i})$ for $(i=[n])$
- For any $t-1$ shares, $a(\alpha_{1})\dots a(\alpha _{t-1})$, every $a(0)=S$ is possible
- For any $t$ shares, $a(\alpha _{i_{1}}),\dots,a(\alpha _{i_{t}})$ makes interpolation $a(x)$ possible $a(0)=S$
