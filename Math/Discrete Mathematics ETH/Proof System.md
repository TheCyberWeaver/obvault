## Definition
$\pi=(\mathcal{S},\mathcal{P},\tau,\phi)$
 - $\mathcal{S}$: a set of statements 
 - $\mathcal{P}$: a set of proofs (e.g. $\mathcal{S}=\mathcal{P}=\{ 0,1 \}^{*}$)
 - $\tau$: semantic, a truth function $S\to \{ 0,1 \}$
 - $\phi$: verification function $\mathcal{S}\times \mathcal{P}\to \{ 0,1 \}$

We want:
$\phi$ calculate efficiently
$\pi$ complete, if for every $s \in \mathcal{S}$  $\tau(s)=1$ has a proof $p \in \mathcal{P}$ with $\phi(s,p)=1$
- The system is not missing any true theorems.
- $(M\models F)\implies(M\vdash F)$  
$\pi$ sound, if no $s \in \mathcal{S}$ with $\tau(s)=0$ has a proof $p \in \mathcal{P}$ with $\phi(s,p)=1$
- No false formula is provable.
- $(M\vdash F)\implies(M\models F)$  
### Definition: Language
$L=\{s \in S|\tau(s)=1 \}$ 

## Proof system for formula

## example
$S=\{ (M,F)|F \text{ formula}, M \text{ set of formulas}  \}$
$\tau((M,F))=1\overset{ def }{ \Longleftrightarrow } F$ is true if all $G\in M$ are true $(M\models F)$

