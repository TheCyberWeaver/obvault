## Definition - "for all"
A **dependent function type** is the type of functions whose result type depends on the input value.
Given a type $A:\mathcal{U}$ and a [[Type Family|type family]] $B:A\to \mathcal{U}$
we construct a type of dependent functions: $\Pi_{(x:A)}B(x):\mathcal{U}$

A term of this type is a function $f$, given its input $x:A$, returns a term of $B(x)$
Formally, if $f:\Pi_{(x:A)}B(x)$, then for any $a:A$ we will have $f(a):B(a)$

![[Type family and dependent function type.excalidraw|706]]
## Example 1
Suppose we have type $\text{Bool}:\mathcal{U}$ and type family $B:\text{Bool}\to \mathcal{U}$ defined by $B\;	\text{true}=\mathbb{N}$ and $B\;	\text{false}=\text{String}$
a function ${} f:\Pi_{(x:\text{Bool})}B(x) {}$ will returns a $n:\mathbb{N}$ when given $\text{true}$ and a $s:\text{String}$ when given $\text{false}$.

## Example: fmax
we can define a dependent function $fmax:\Pi_{(n:\mathbb{N})}Fin(n+1)$ that gives the "largest" element of the resulting type. We can let $fmax(n):\equiv n_{n+1}$. 
Note that $n_{n+1}:Fin(n+1)$ (see [[Type Family#Example family of finite sets|Definition of Fin(n)]])

## Polymorphic
we can also use types as parameters, such constructed dependent functions are polymorphic over a give universe.


## Example: id
Let $id:\Pi_{(A:\mathcal{U})}A\to A$
$id$ is now a function that accept a type $A$ as input and return type $A\to A$ as output.

we generally call $id(A):A\to A$ as $id_{A}:A\to A$
using $\lambda$-calculus
$id_{A}:\equiv\lambda(x:A).x$
which gives
$id\equiv\lambda(A:\mathcal{U}).\lambda(x:A).x$
