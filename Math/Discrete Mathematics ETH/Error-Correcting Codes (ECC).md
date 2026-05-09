A sequence $a=a_{0}a_{1}\dots a_{k}$ is should be sent.
**Method**:
$c=c_{0}c_{1}\dots c_{n}=E(a)$ Encode function: $(E:A^{k}\to A^{n})$
there should also be a decode function$(D:A^{n}\to A^{k})$ so that $D(E(a)+e)=a$

## Example: trivial method
$E:A^{k}\to A^{m\cdot k}$ with $E(a)=\underbrace{ a_{0}\dots a_{0} }a_{1}\dots a_{1}\dots \underbrace{ a_{k}\dots a_{k} }_{ m }$ can correct $\left\lfloor \frac{m-1}{2} \right\rfloor$ errors (worst case)
Define $(n,k)$-code over alphabet $\mathcal{A}$ is a subset of $\mathcal{A}^{n}$ of cardinality $\lvert A \rvert^{k}$
This example is a $(m(k+1),k+1)$-error-correcting code

## Definition: Hamming distance
Consider two strings of equal length over a finite alphabet $\mathcal{A}$, the hamming distance is the number of positions where they differ

## Definition: minimum distance
The minimum distance of an error-correcting-code $\mathcal{C}$ or $d_{min}(\mathcal{C})$ is the minimum of Hamming distance between any two codewords.

### Example: 
The following code is a $(5, 2)$-code over alphabet $\{0,1 \}$ 
Let $\mathcal{C}=\{00000, 11100, 00111, 11011\}$ be the encoded codewords of $\{ 00,01,10,11 \}$
This is a sum set of $\{ 0,1 \}^{5}$ and has $\lvert \mathcal{A} \rvert^{2}=4$ elements 
The minimum distance is $3$



> [!NOTE] Geometric Intuition
> Consider each codeword in $\mathcal{C}$ as a vector in a high dimensional space (distance are defined by hamming distance ). Let $x$ be the code we receive, the correction process is to find the closest codeword vector.


## Better Method: Reed-Solomon-Code
Consider a big enough $\mathcal{A}=F$ (for example $\mathcal{A}=GF(2^{8})$) and $E:\mathcal{A}^{k}\to \mathcal{A}^{n}$ with $E((a_{0},\dots,a_{k-1}))=(a(\alpha_{0}),\dots,a(\alpha _{n-1}))$ for distinct $\alpha_{0},\dots,\alpha _{n-1}\in F$
and $a(x)=a_{0}+a_{1}x+\dots+a_{k-1}x^{k-1}\in F[x]$

Minimal distance is $n-(k-1)=n-k+1$ 
because every two $E(a),E(a')$ with $a\neq a'$ have at most $k-1$ same components.

> [!NOTE]
> This code can correct $\left\lfloor \frac{n-k}{2} \right\rfloor$ errors 
