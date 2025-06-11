## 14.1 Definition Factor Group
Let $\phi:G\rightarrow G'$ 
Let $H=Ker(\phi)$, $a \in G$
The set of all cosets of H is denoted by $G/H$ (read as G over H or G modulo H)
- There exists a one-to-one relationship between $G/H$ and the elements of the group $\phi[G]$ . [[Section 13 Homomorphisms#13.15 Theorem]]
- $G/H$ and $\phi[G]$ have same amount of elements. Thus there is a onto relationship [[Section 13 Homomorphisms#13.15 Theorem]]
- A homomorphism exist: [[Section 13 Homomorphisms#13.1 Definition|Definition of Homomorphism]]
	$\mu:G/H\rightarrow \phi[G]$
	if $\mu(xH) = \phi(x)$ and $\mu(yH) = \phi(y)$ and $\mu(zH) = \phi(x)\phi(y)$ Then $(xH)(yH)=zH$
$G/H$ is isomorphic to $\phi[G]$

> [!definition]
> $G/H$ is called as a **factor group** (quotient group) or more precisely **factor group of G modulo H**

> [!Tip]
> H can also be any normal subgroup of G

## 14.2 Example

The factor Group $\mathbb Z/n\mathbb Z$ is isomorphic to $\mathbb Z_n$

Taking the example from [[Section 10 Cosets and The Theorem of Lagrange#10.3 Example|3Z]]
Let $\mu:\mathbb Z/ 3\mathbb Z\rightarrow\mathbb Z_3$
- $\mu(3\mathbb Z)=0$
- $\mu(3\mathbb Z+1)=1$
- $\mu(3\mathbb Z+2)=2$

**Computation in factor group**
find *any* element from two cosets. calculate using the operation in $G$, and the result lies in the coset that is the product of the original two cosets. 

> [!NOTE]
> **congruent modulo H**: Elements in the same coset of H

Let H be a subgroup of G
$$(aH)(bH)=(ab)H$$
This is **well defined**(independent from the choice of $h\in H$) if and only if H is a normal subgroup of G

$(ah_1)(bh_2)=a(h_1b)h_2=a(bh_3)h_2=ab(h_3h_2)$

> [!Tip]
> - $a(h_1b)h_2=a(bh_3)h_2$ because left coset is the same as the right coset (see [[Section 13 Homomorphisms#13.19 Definition normal|normal group]])
> - $h_3h_2 \in H$ because H is a group


## The Fundamental Homomorphism Theorem

> [!PDF|note] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=145&selection=166,1,264,1&color=note|p.140]]
> > Let φ : G → G′ be a group homomorphism with kernel H . Then φ[G] is a group, and μ : G/H → φ[G] given by μ(g H ) = φ(g) is an isomorphism. If γ : G → G/H is the homomorphism given by γ (g) = g H , then φ(g) = μγ (g) for each g ∈ G.
> 
> 

![[Pasted image 20250605122136.png|315]]
- $\gamma(x)=xH$ 
- $\mu(xH)=\phi(x)$
- $\phi(x)=\mu\gamma(x)$

Let H be a normal subgroup of G. Then $\gamma(x) = xH$ is a homomorphism with kernel H.
- [ ] Proof 14.9🔽 

- $\mu$ is an isomorphism of G/H with $\phi[G]$ [[#14.1 Definition Factor Group]]
- $\gamma$ is an homomorphism of G with G/H
## 14.12 Example
Classify the group $(\mathbb Z_4 \times \mathbb Z_2)/(\{0\}\times\mathbb Z_2)$ 

> [!Warning]
> $\mathbb Z_4 \times \mathbb Z_2$ is not isomorphic to $\mathbb Z_8$
> See [[Section 11 Direct Products and Finitely Generated Abelian Groups#11.12 Fundamental Theorem of Finitely Generated Abelian Groups|Fundamental Theorem of Finitely Generated Abelian Groups]]

- Let G be $\mathbb Z_4 \times \mathbb Z_2$, and H be $\{0\}\times\mathbb Z_2$ 
- Find a homomorphism $\phi$ from $G$ to $\phi[G]$ (Here to $\mathbb Z_4$) that has the Kernel $(\{0\}\times\mathbb Z_2)$. 
- $\phi:\mathbb Z_4 \times \mathbb Z_2 \rightarrow\mathbb Z_4$
- $\phi(x,y)=x$ 
- According to [[#The Fundamental Homomorphism Theorem]] $\mathbb Z_4$ is isomorphic to $(\mathbb Z_4 \times \mathbb Z_2)/(\{0\}\times\mathbb Z_2)$ 

### A general construction method of classification
- **Step 1**: Write $G$ in its decomposition as a direct sum of cyclic factors:  
  $$
  G \;\cong\; \mathbb{Z}_{n_1}\oplus \mathbb{Z}_{n_2}\oplus \cdots \oplus \mathbb{Z}_{n_k},
  \quad n_1\mid n_2\mid \cdots \mid n_k.
  $$

- **Step 2**: Describe how $H$ sits inside this decomposition, i.e., which factors or subcycles of factors it occupies.

- **Step 3**: Construct a projection (or combination of projections)  
  $$
  \phi: G \;\longrightarrow\; K
  $$  
  by “discarding” the factors corresponding to $H$ and keeping the remaining factors, ensuring  
  $$
  \ker\phi \;=\; H.
  $$

- **Step 4**: By the First Isomorphism Theorem, conclude  
  $$
  G / H \;\cong\; \phi(G).
  $$

- **Step 5**: If needed, adjust $\phi(G)$ into standard form as a direct sum of cyclic groups:  
  $$
  \phi(G)\;\cong\;\mathbb{Z}_{d_1}\oplus\mathbb{Z}_{d_2}\oplus\cdots\oplus\mathbb{Z}_{d_r},
  $$  
  where $d_1\mid d_2\mid \cdots\mid d_r$.
## 14.14 Example

> [!NOTE]
> Every subgroup H of an abelian group G is normal

## 14.15 Definition Automorphism

> [!PDF|note] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=146&selection=590,1,678,1&color=note|p.141]]
> > - An isomorphism $φ : G → G$ of a group $G$ with itself is an **automorphism** of $G$. 
> > - The automorphism $i_g : G → G$, where  $i_g(x) = gxg^{-1}$ for all $x ∈ G$, is the **inner automorphism of G** by g. 
> > - Performing $i_g$ on x is called **conjugation of x by g**. 
> > - if $i_g[H]=H$ for all $g\in G$, H is a normal subgroup 

- **Definition of conjugate subgroup**:  
  Given a group $G$ and a subgroup $H \subseteq G$, for any $g \in G$ define  
  $$
  i_g[H]=gHg^{-1} \;=\; \{\,g\,h\,g^{-1} : h \in H\,\}.
  $$  
  The set $gHg^{-1}$ is a subgroup of $G$, called a **conjugate subgroup** of $H$.

- **Isomorphism Property**:  
  The map  $H \;\longrightarrow\; gHg^{-1},\qquad h \;\mapsto\; g\,h\,g^{-1}$  is a group isomorphism. 

> [!NOTE]
> Hence every conjugate subgroup is isomorphic to $H$.

## Ways to Prove $H$ is a Normal Subgroup - Summary

1. $ghg^{−1} ∈ H$ for all $g ∈ G$ and $h ∈ H$ . 
2. $gHg^{−1} = H$ for all $g ∈ G$. 
3. $i_g[H]=H$ for all $g\in G$
4. $gH = Hg$ for all $g ∈ G$.
See [[Section 13 Homomorphisms#Ways to Prove a Subgroup $H$ Is Normal in $G$|Ways to Prove H is a Normal Subgroup]]

