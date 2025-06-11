
> [!NOTE]
> | Operation    | Notes    | Example |
| --- | --- | --- |
| external direct product |   $\prod_{i=1}^{n} G_i$ | $\mathbb{Z_2 \times Z_3}=(0,0),(0,1),(0,2),(1,0),(1,1),(1,2)$ |
| internal direct product | $G≅H×K$| $\mathbb{Z_6​≅Z_2​×Z_3​}$|

| Aspect             | External Direct Product $H\times K$                                                     | Internal Direct Product in G                                                                                |
| ------------------ | --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Starting data**  | Two _separate_ groups HH, KK.                                                           | One big group G with subgroups $H,K\subseteq G$.                                                            |
| **Underlying set** | Ordered pairs $(h,k):h\in H,\,k\in K$.                                                  | Just the elements of G.                                                                                     |
| **Group law**      | Component-wise: $(G,*),(H,+)$ $(g_1​,h_1​)\times(g_2​,h_2​)=(g_1​∗g_2​,h_1​+h_2​)$. | The original multiplication in G.                                                                           |
| **Construction**   | “External”: you build a brand-new group out of H and K.                                 | “Internal”: you recognise that $G\cong H\times K$ because G splits as H K with $H\cap K=\{e\}$ and $hk=kh$. |
| **Universality**   | Always exists for any two groups.                                                       | Only when within G those two subgroups satisfy the three internal-product axioms.                           |
| **Isomorphism**    | $H\times K$ is the group.                                                               | You get an isomorphism $\varphi: H\times K \xrightarrow{\sim} G, \varphi(h,k)=hk$.                          |

##  11.3 Example

> [!example]
> $\mathbb{Z}_{2}\times\mathbb{Z}_{3}$ is cyclic with Generator $(1,1)$

> [!question]
> Is it true that $\mathbb{Z}_{n}\times\mathbb{Z}_{m}$ is cyclic if and only if n and m are coprime to each other?

***It is true***
*Case 1:* $gcm(n,m)=1$
	pick the Generator $(1,1)$ :$$ (1,1)^{k}=(k\bmod n,k\bmod m)=(0,0)$$which means: $$k=lcm(n,m)$$ $k=lcm(n,m)=nm=\lvert \mathbb{Z}_{n}\times\mathbb{Z}_{m}\rvert$ meaning $(1,1)$ is a generator of $Z_{nm}$. 
*Case 2:* $gcm(n,m)>1$
	For any element $a,b\in\mathbb{Z}_{n}\times\mathbb{Z}_{m}$ $$ord(a,b)=lcm(ord(a),ord(b))$$ according to the Theorem of Lagrange ([[#10 The Theorem of Lagrange]]): $$ord(a)\mid n, \ ord(b)\mid m$$then: $$ord(a,b)=lcm(ord(a),ord(b))\leq lcm(n,m)<nm$$This means no generator can generate the full $\mathbb{Z}_{n}\times\mathbb{Z}_{m}$ Thus it is not cyclic	. $q.e.d.$ 

## 11.10 Example

> [!example]
> Find the order of (8, 4, 10) in the group Z12 × Z60 × Z24. 

- 8 is of order 3 in $\mathbb Z_{12}$ : $3=12/gcd(8,12)$ (6.14[[Section 6 Cyclic Groups]]) 
- 4 is of order 15 in $\mathbb Z_{60}$
- 10 is of order 12 in $\mathbb Z_{24}$
$$lcm(3,12,15)=60$$
(8,4,10) has an order of 60 in the Group Z12 × Z60 × Z24

## 11.12 Fundamental Theorem of Finitely Generated Abelian Groups 

> [!NOTE] Fundamental Theorem of Finitely Generated Abelian Groups
> Every finitely generated abelian group G is isomorphic to a direct product of cyclic groups in the form $$\mathbb{Z}_{(p_1)^{r_1}} \times \mathbb{Z}_{(p_2)^{r_2}} \times \cdots \times \mathbb{Z}_{(p_n)^{r_n}}\times \mathbb{Z}\times \mathbb{Z}\times \cdots \times \mathbb{Z}$$ where $p_i$ are primes, and $r_i$ are positive integers.
> 
> The direct product is unique except for possible rearrangement of the factors; that is, the number (**[[Betti number]]** of G) of factors $\mathbb{Z}$ is unique and the prime powers $(p_i)^{r_i}$ are unique.


> [!tip]
>  Similar to factorizing an integer into prime powers, but $2^3\neq 2^2\times 2$

> [!PDF|] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=114&selection=42,0,43,1|p.109]]
> > The proof is omitted here. 
> 
> LOL
## Isomorphism of Cyclic Group

> [!NOTE]
> $\mathbb Z_n\times \mathbb Z_m$ is isomorphic to $\mathbb Z_{nm}$ if and only if $gcd(n,m)=1$

## 11.13 Example

> [!Example]
> Find all abelian groups, up to isomorphism, of order 360. 

***up to isomorphism***: any abelian groups of order 360 should be isomorphic to one of the founded groups

make use of [[#11.12 Fundamental Theorem of Finitely Generated Abelian Groups]]
$$360=2^3 3^2 5$$ 
1. $\mathbb{Z}_2\times\mathbb{Z}_2\times\mathbb{Z}_2\times\mathbb{Z}_3\times\mathbb{Z}_3\times\mathbb{Z}_5$
2. $\mathbb{Z}_2\times\mathbb{Z}_4\times\mathbb{Z}_3\times\mathbb{Z}_3\times\mathbb{Z}_5$
3. $\mathbb{Z}_2\times\mathbb{Z}_2\times\mathbb{Z}_2\times\mathbb{Z}_9\times\mathbb{Z}_5$
4. $\mathbb{Z}_2\times\mathbb{Z}_4\times\mathbb{Z}_9\times\mathbb{Z}_5$
5. $\mathbb{Z}_8\times\mathbb{Z}_3\times\mathbb{Z}_3\times\mathbb{Z}_5$
6. $\mathbb{Z}_8\times\mathbb{Z}_9\times\mathbb{Z}_5$

## 11.14 Definition

> [!Note]
> A group G is **decomposable** if it is isomorphic to a direct product of two proper nontrivial subgroups. Otherwise G is **indecomposable**

## 11.15 Theorem
> [!info] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=114&selection=238,0,239,17|p.109]]
> > The finite **indecomposable** abelian groups are exactly the cyclic groups with order a power of a prime.
> 
> 

**Examples**
$\mathbb{Z}_2\times\mathbb{Z}_2 ≅ V_4$ **(indecomposable)**

| Group G                              | cyclic | order     | decomposable                               | conclusion     |
| ------------------------------------ | ------ | --------- | ------------------------------------------ | -------------- |
| $\mathbb{Z}_{4}$                     | ✓      | $2^{2}$   | indecomposable                             | indecomposable |
| $\mathbb{Z}_{2}\times\mathbb{Z}_{2}$ | ✗      | $2^{2}$   | Already decomposed                         | decomposable   |
| $\mathbb{Z}_{6}$                     | ✓      | $2\cdot3$ | $\cong \mathbf{Z}_{2}\times\mathbf{Z}_{3}$ | decomposable   |
| $\mathbb{Z}_{15}$                    | ✓      | $3\cdot5$ | $\cong \mathbf{Z}_{3}\times\mathbf{Z}_{5}$ | decomposable   |

Suppose $\mathbb Z_{p^{r}}$ could decompose as $\mathbb Z_{p^{i}}\times\mathbb Z_{p^{j}}$ with $i,j\ge1$ and $i+j=r$.  
In that product, the order of any element is at most $lcm(p^i,p^j)=p^{\max(i,j)}<p^{r}$ ([[#11.3 Example]]).  
But $\mathbb Z_{p^{r}}$ itself contains an element of order $p^{r}$.  
They cannot be isomorphic, so $\mathbb Z_{p^{r}}$ is indecomposable.

## 11.16 Theorem
> [!Note] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=114&selection=320,1,337,1&color=yellow|p.109]]
> > If m divides the order of a finite abelian group G, then G has a subgroup of order m.

> [!warning]
> Proof not understood

## 11.17 Theorem

> [!PDF|note] [[content/Math/_Books_/A First Course in Abstract Algebra.pdf#page=115&selection=303,0,316,10&color=note|p.110]]
> > If m is a square free integer, that is, m is not divisible by the square of any prime, then every abelian group of order m is cyclic.
> 
> extension to [[#11.3 Example]]

$G=\mathbb{Z}_{p_1} \times \mathbb{Z}_{p_2} \times \cdots \times \mathbb{Z}_{p_n}$
primes are coprime to each other. G is cyclic.
