## Definition

Let $S$ be a set of symbols. The **free group on $S$**, written $F(S)$, is the group whose elements are all finite words made from symbols in $S$ and their formal inverses, with only the cancellation rules
$$
ss^{-1}=e,\qquad s^{-1}s=e
$$
for every $s\in S$.

> [!NOTE]
> "Free" means there are no relations between the generators except the group axioms. So unless a word can be simplified by cancelling adjacent inverse pairs, it represents a different group element.

## Example
In the free group $F(a,b)$, we may build words like
$$
a,\quad b,\quad a^{-1},\quad ab,\quad aba^{-1},\quad ab^{-1}a^{-1}b.
$$
$$
(ab^{-1})(ba^{-1})=ab^{-1}ba^{-1}=aa^{-1}=e.
$$
> [!Warning] 
> $F(a,b)$ is not [[Section 4 Groups|abelian]].

## **Nielsen–Schreier theorem**

> [!NOTE] Nielsen–Schreier theorem
> every subgroup of a free group is free

