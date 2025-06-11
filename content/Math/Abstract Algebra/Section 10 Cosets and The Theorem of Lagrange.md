## 10.2 Definition of Cosets

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=102&selection=491,1,561,0&color=note|p.97]]
> > Let H be a subgroup of a group G. The subset $a H = \{ah | h ∈ H \}$ of G is the **left coset of H** containing a, while the subset $H a = \{ha | h ∈ H \}$ is the** right coset** of H containing a.
> 
> 
## 10.3 Example
$3\mathbb Z=\{\cdots,-3,0,3,\cdots\}$
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
We see the partition of the group again forms a group.
## The Theorem of Lagrange
> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=105&selection=241,0,254,1&color=note|p.100]]
>
> > Every coset (left or right) of a subgroup H of a group G has the same number of elements as H .

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

> [!PDF|yellow] [[A First Course in Abstract Algebra.pdf#page=106&selection=91,2,120,1&color=yellow|p.101]]
>
> > The number of left cosets of H in G is *the index* (G : H ) of H in G.

## 10.14 Theorem

> [!PDF|note] [[A First Course in Abstract Algebra.pdf#page=106&selection=189,0,261,1&color=note|p.101]]
>
> > Suppose H and K are subgroups of a group G such that K ≤ H ≤ G, and suppose (H : K ) and (G : H ) are both finite. Then (G : K ) is finite, and (G : K ) = (G : H )(H : K )

$$
(G:H)=|G|/|H|
$$
$$
(G:H)(H:K)=|G|/|H|*|H|/|K|=|G|/|K|=(G:K)
$$