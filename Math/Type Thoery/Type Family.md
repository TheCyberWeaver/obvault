
A **type family** is a type that _varies with a term_.

**Intuition:** it’s like an “indexed collection of types.”

If $A:\mathcal{U}$, then a type family over $A$ is  $B: A\to \mathcal{U}$.
So for each $a:A$, you get a type $B\;	a:\mathcal{U}$

> [!NOTE]
> It's natural to choose $A$ as $\mathbb{N}$ (`Nat`), but it can also be other types.

## Example: family of finite sets
The family of finite sets $Fin:\mathbb{N}\to \mathcal{U}$, where $Fin(n)$ gives a type that describes a set with exactly $n$ elements. (each element of this set has type $Fin(n)$)
- $Fin(n)$ has elements $0_{n},1_{n},\dots,(n-1)_{n}$ where $1_{n}:Fin(n)$

## Example 2
- The constant type family over $A:\mathcal{U}$ with value $C:\mathcal{U}$ is a family that ignores its "index". That is: the type family $B:A\to \mathcal{U}$ always gives a fixed type $C$. So every fiber is the same type.
	- The constant function $(\lambda(x:A).C:A\to \mathcal{U})$ (input $x:A$, output $C:\mathcal{U}$) (see [[λ-calculus]])

