## 10.2 Definition of Cosets

> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=102&selection=491,1,561,0&color=note|p.97]]
> > Let H be a subgroup of a group G. The subset $a H = \{ah | h ∈ H \}$ of G is the **left coset of H** containing a, while the subset $H a = \{ha | h ∈ H \}$ is the** right coset** of H containing a.
> 
> 
## 10.3 Example

> [!Example]
> $3\mathbb Z=\{\cdots,-3,0,3,\cdots\}$

The **left cosets** of $3\mathbb Z$ of $\mathbb Z$ are:
- $1+3\mathbb Z$
- $2+3\mathbb Z$
The **right cosets** of $3\mathbb Z$ of $\mathbb Z$ are:
- $3\mathbb Z +1$
- $3\mathbb Z+2$

> [!NOTE]
> For a subgroup H of an abelian group G, the partition of G into left cosets of H and the partition into right cosets are the same. Trivial

## 10.4 Example
partition of $\mathbb Z_6$ into cosets of the subgroup $H=\{0,3\}$ 
the cosets are $\{0,3\}\{1,4\}\{2,5\}$ 
![[Pasted image 20250605105608.png|459]]
We see the partition of the group again forms a group. This group is called as [[Section 14 Factor Groups#14.1 Definition Factor Group|Factor Group]]

## The Theorem of Lagrange
> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=105&selection=241,0,254,1&color=note|p.100]]
>
> > Every coset (left or right) of a subgroup H of a group G has the same number of elements as H .

**Proof:**

The proof relies on the concept of **cosets**. A left coset of $H$ in $G$ is a set of the form $gH=\{gh∣h∈H\}$ for some $g∈G$. Similarly, a right coset is $Hg=\{hg∣h∈H\}$. We will focus on left cosets, but the argument is analogous for right cosets.

1. **Cosets partition G:** The left cosets of H partition G. This means that every element of G belongs to exactly one left coset of H. To see this:
    
    - Every element $g∈G$ belongs to the coset $gH$ (since $g=ge$ and $e∈H$).
    - If two cosets $g_{1}​H$ and $g_{2}H$ intersect (i.e., have a common element), then they are equal. Suppose $g_{1}h_{1}=g_{2}h_{2}$​ for some $h_{1}​,h_{2}​∈H$. Then $g_{1}=g_{2}h_{2}h_{1}−1$​. Since $H$ is a subgroup, $h_{2}h_{1}−1​∈H$. Let $h_{3}​=h_{2}​h_{1}−1$​. Then $g_{1}=g_{2}h_{3}$​, and therefore $g_{1}H=g_{2}h_{3}​H=g_{2}H$. Thus if two left cosets intersect they are equal.
2. **All cosets have the same size:** Every left coset $gH$ has the same [[Cardinality|cardinality]] as H. This can be shown by defining a bijection $f:H→gH$ by $f(h)=gh$. This function is clearly surjective, and it’s injective because if $gh_{1}​=gh_{2}$​, then $h_{1}​=h_{2}$ by the cancellation law in $G$.
    
3. **Order of G is the sum of coset sizes:** Since the cosets partition $G$ and all have size $\lvert H \rvert$, the order of $G$ is the number of cosets multiplied by the size of each coset. Let n be the number of distinct left cosets of $H$ in $G$. Then $\lvert G \rvert=n\lvert H \rvert$.

## 10.11 Theorem

> [!NOTE]
> Every group of prime order is cyclic

a non-identity element g: $H=\\langle g\\rangle\\in G$
$$
⟨g⟩={ gk∣k∈Z },
$$
which has size $ord⁡(g)$.
Lagrange says $ord⁡(g)$ divides $\\lvert G\\rvert=p$.
Since$$ g≠e, ord⁡(g)>1$$The only divisors of the prime p are 1 and p.  
Therefore $$ord⁡(g)=p$$

## 10.13 Definition

> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=106&selection=91,2,120,1&color=yellow|p.101]]
>
> > The number of left cosets of H in G is *the index* (G : H ) of H in G.

## 10.14 Theorem

> [!PDF|note] [[Math/_Books_/A First Course in Abstract Algebra.pdf#page=106&selection=189,0,261,1&color=note|p.101]]
>
> > Suppose H and K are subgroups of a group G such that K ≤ H ≤ G, and suppose (H : K ) and (G : H ) are both finite. Then (G : K ) is finite, and (G : K ) = (G : H )(H : K )

$$
(G:H)=|G|/|H|
$$
$$
(G:H)(H:K)=|G|/|H|*|H|/|K|=|G|/|K|=(G:K)
$$