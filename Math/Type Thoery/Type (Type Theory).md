---
tags:
  - linker-exclude
---
## Definition
To specify a type, we need:
- [[#Formation rule]]
- [[#Constructors]] (introduction rules)
- [[#Eliminators]] (elimination rules)
- [[#Computation rule]] (β-reduction)
- _optional_ uniqueness principle (η-expansion)


## Formation rule
A **formation rule** tells you **when a type is well-formed**, $i$.$e$. when you are allowed to _form_ a new type expression.

## Constructors
how to construct elements of that type

## Eliminators
An **eliminator** is the canonical principle for **using** (eliminating) values of a type

The eliminator states the _elimination principle_ by giving a term with a specific **type**

$i$.$e$. defining functions **out of** that type by analyzing how the value could have been constructed.


There are two common forms:
### Non-dependent eliminator (recursor)
it defines a function into a _constant_ target type.
> [!Comment]
> What a bad name!, a recursor is not recursive

defines a plain function:
$$
f:T\to C
$$
where $C$ does not depend on the input

### Dependent eliminator (induction)
Defines a dependent function ([[Π-types (Dependent function types)]]):
$$
f: \Pi_{(x:T)}C(x)
$$
where type $C(x)$ depend on $x$.

## Computation rule
how an eliminator acts on a constructor

The **computation rule** (β-rule) states how that recursor **reduces/evaluates** when you apply it to a constructor.
# Examples

## Example: Product type A×B

Formation rule:
If $A:\mathcal{U}$ and ${} B:\mathcal{U} {}$, then
$$
A \times B : \mathcal{U}
$$

Constructor:
If $a:A$ and $b:B$, then
$$
(a,b) : A \times B
$$
or the constructor is pairing:
$(\cdot,\cdot):A\to B\to A\times B$

Eliminator ([[Recursor|recursor]]):
$$
rec_{A\times B} : \prod_{C:\mathcal{U}}\; (A \to B \to C)\to (A\times B \to C)
$$
Meaning:
we choose a result type $C$
we give a rule $g:A\to B\to C$ telling how to produce a $C$ from components $a:A$ and $b:B$,
then $\text{rec}_{A\times B}(C,g)$ is the function $f:A\times B\to C$

Computation rule (β):
$$
rec_{A\times B}(C,g,(a,b)) \equiv g(a)(b)
$$
We can define special cases:
- $\text{pr}_{1}:A\times B\to A$ with computation rule $\text{pr}_{1}(a,b)\equiv a$
- $\text{pr}_{2}:A\times B\to A$ with computation rule $\text{pr}_{2}(a,b)\equiv b$

Uniqueness:
$\forall x:A\times B, x=(\text{pr}_{1}(x),\text{pr}_{2}(x))$
![[Pasted image 20260202213756.png|470]]
> [!NOTE]
> > actually we could define ${} A\times B:\equiv \prod_{x:2}\text{rec}_{2}(\mathcal{U},A,B,x) {}$
> Note that $A \times B$ could be constructed as an indexed one over the two-element type **2**


## Example: Coproduct type A+B

Formation rule:
If $A:\mathcal{U}$ and $B:\mathcal{U}$, then
$$
A + B : \mathcal{U}
$$

Constructors:
$$
inl : A \to A+B
$$
$$
inr : B \to A+B
$$

Eliminator ([[Recursor|recursor]]):
$$
rec_{A+B} : \prod_{C:\mathcal{U}}\; (A\to C)\to (B\to C)\to (A+B \to C)
$$

Computation rules (β):
$$
rec_{A+B}(C,f,g,inl(a)) \equiv f(a)
$$
$$
rec_{A+B}(C,f,g,inr(b)) \equiv g(b)
$$

![[Pasted image 20260202213102.png]]

> [!NOTE]
> > actually we could define $A+B:\equiv \sum_{x:2}\text{rec}_{2}(\mathcal{U},A,B,x)$
> Note that $A + B$ could be constructed as an indexed one over the two-element type **2**

## Example: Unit type 1

Formation rule:
$1:\mathcal{U}$

Constructor (introduction rule):
$\star:1$

Eliminator ([[Recursor|recursor]]):
$$
rec_1 : \prod_{C:\mathcal{U}}\; C \to (1 \to C)
$$
Induction:
$\text{ind}_{1}:\Pi_{C:1\to \mathcal{U}}C(\star)\to \Pi_{x:1}C(x)$
This means, if you have a family $C:1\to \mathcal{U}$, to produce $f:\Pi_{x:1}C(x)$
it suffices to give $c:C(\star)$
$\text{ind}_{1}:(C,c,\star):\equiv c$

Computation rule (β-rule):
$$
rec_1(C,c,\star) \equiv c
$$
![[Pasted image 20260202213901.png]]
### prove the propositional uniqueness principle for 1
Step 1:
Define family $C:1\to \mathcal{U}$ by $C(x):\equiv(x=\star)$
so a term of $\prod_{x:1}C(x)$ is exactly a term of $\prod_{x:1}(x=\star)$

Step 2:
Induction for the unit type says:
$\text{ind}_{1}:\Pi_{C:1\to \mathcal{U}}C(\star)\to \Pi_{x:1}C(x)$
so it suffices to give a term of $C(\star)$

Step 3: base case
Compute: $C(\star)\equiv(\star=\star)$
and we always have $\text{refl}_{\star}:\star=\star$

Step 4:
we define $\text{upun}:\equiv \text{ind}_{1}(\lambda x.x=\star,\text{refl}_{\star})$

check:
- for any $x:1$, $\text{upun}(x):x=\star$
- by computation rule $\text{upun}(\star)\equiv\text{refl}_{\star}$
## Example: Empty type 0

Formation rule:
$0:\mathcal{U}$

Constructor:
(none)

Eliminator ([[Recursor|recursor]] / ex falso):
$$
rec_0 : \prod_{C:\mathcal{U}}\; 0 \to C
$$

Computation rule:
(none)
![[Pasted image 20260202213938.png]]
## Example: Natural numbers N

Formation rule:
$$
\mathbb N : U
$$

Constructors:
$$
0 : \mathbb N
$$
$$
succ : \mathbb N \to \mathbb N
$$

Eliminator ([[Recursor|recursor]] / primitive recursion):
$$
rec_{\mathbb N} : \prod_{C:U}\; C \to (\mathbb N \to C \to C)\to (\mathbb N \to C)
$$

Computation rules (β):
$$
rec_{\mathbb N}(C,c_0,c_s,0) \equiv c_0
$$
$$
rec_{\mathbb N}(C,c_0,c_s,succ(n)) \equiv c_s(n,rec_{\mathbb N}(C,c_0,c_s,n))
$$


## Example: Lists List(A)

Formation rule:
If $A:U$, then
$$
List(A) : U
$$

Constructors:
$$
nil : List(A)
$$
$$
cons : A \to List(A) \to List(A)
$$

Eliminator ([[Recursor|recursor]] / fold):
$$
rec_{List(A)} :
\prod_{C:U}\;
C \to (A \to List(A)\to C \to C)\to (List(A)\to C)
$$

Computation rules (β):
$$
rec(\_,c_{nil},c_{cons},nil) \equiv c_{nil}
$$
$$
rec(\_,c_{nil},c_{cons},cons(a,\ell))
\equiv
c_{cons}(a,\ell,rec(\_,c_{nil},c_{cons},\ell))
$$

## Other examples
Similarly we can also define types like $A\to B$, $\prod_{(a:A)}B(a)$ or $\sum_{(a:A)}B(a)$

## Propositions
We treat propositions as types and the evidence (proofs) as elements of this type.
![[Pasted image 20260205124659.png]]
![[Pasted image 20260205142320.png]]

$A\to B$ means: we can find a function such that it matches all elements of $A$ to elements of $B$.
$\implies$ For every proof of $A$ we can find a proof of $B$. 
Case 1: if $A$ is true $\implies$ there is a proof of $A$ $\implies$ there is a proof of $B$ $\implies$ $B$ is true
Case 2: if $A$ is false $\implies$ it is easy to define a function from $A$ to $B$, (any mapping would do the job, since the function is never called) $\implies$ $A\to B$ is true

We see $A\to B$ (type theory) and $A\to B$ (first order logic) are equivalent.

