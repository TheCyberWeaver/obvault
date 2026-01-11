---
tags:
  - linker-exclude
---


## Proposition 9.2.11: PSD
 symmetric matrix $A$ is said to be Positive Semidefinite (PSD) if all its eigenvalues are non-negative. If all the [[Eigenvalues|eigenvalues]] of $A$ are strictly positive then we say $A$ is Positive Definite (PD).

Using [[Spectral Theorem#Proposition 9.2.10 (Rayleigh Quotient)|Rayleigh Quotient]]
PSD $\Longleftrightarrow x^{\top}Ax\geq0\forall{x \in \mathbb{R}^{n}}$
PD $\Longleftrightarrow x^{\top}Ax>0\forall{x \in \mathbb{R}^{n}}$

Eine diagonal-dominant matrix is always PSD
$\implies A\in \mathbb{R}^{n\times n}$ symmetric and $A_{ii}>\sum_{j\neq i}\lvert A_{ij} \rvert\forall{i \in \{ 1,\dots,n \}}$

## Definition: Gram Matrix
Let $A\in \mathbb{R}^{m\times n}$, the matrix $G=A^{\top}A\in \mathbb{R}^{n\times n}$ is a gram matrix

> [!Important] Equivalent Notations
> A matrix $G$ is a gram matrix $\Longleftrightarrow$ $G$ ist PSD

$\implies$
$x^{\top}Gx=x^{\top}A^{\top}Ax=(Ax)^{\top}(Ax)=\lVert Ax \rVert^{2}\geq0$

$\Longleftarrow$
$M=V\Lambda V^{\top}$ ([[Spectral Theorem]])
Let $B\in \mathbb{R}^{n\times n}$ such that $\Lambda=B^{2}$ with $\Lambda _{ii}=B_{ii}B_{ii}$ (since all entries of $\Lambda$ are positive)
$M=VBBV^{\top}=VB(VB)^{\top}$
let $C=(VB)^{\top}\implies M=C^{\top}C$ ($M$ is gram)

## Proposition 9.12.15

> [!NOTE]
> Given a real matrix $A\in \mathbb{R}^{m\times n}$ .The non-zero [[Eigenvalues|eigenvalues]] of $A^{\top}A$ and $AA^{\top}$ are the same.
> 

**Proof**:
$A^{\top}Av=\lambda v$ with $(\lambda\neq0)$
$\implies AA^{\top}Av=A\lambda v\implies(AA^{\top})(Av)=\lambda(Av)$
Let $w=Av$
$AA^{\top}w=\lambda w$
We still need to prove that $w\neq0$:
$N(A^{\top}A)=N(A)\neq \{ 0 \}$
$\implies w=Av\neq0$ (otherwise $Av=0\implies N(A)=\{ 0 \}$)



