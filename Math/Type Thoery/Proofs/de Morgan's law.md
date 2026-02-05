
> [!NOTE] In ordinary English (one direction)
> > If not A and not B, then not (A or B)
> 
> **Proof**:
> Suppose not A and not B, and also suppose A or B; we will derive a contradiction. There are two cases. If A holds, then since not A, we have a contradiction. Similarly, if B holds, then since not B, we also have a contradiction. Thus we have a contradiction in either case, so not (A or B)
> 


## Type theory translation
($\Box$ implicates what remains to be done)
Goal: find a element of type $(A\to0)\times(B\to0)\to(A+B\to0)$ (see [[Pasted image 20260205124659.png|Translation]])

Suppose not $A$ and not $B$: 
- use pattern matching: find a function $f((x,y)):\equiv\Box:A+B\to0$ where $x:A\to0$ and $y:B\to0$
- OR use recursor: find a function $f:\equiv\text{rec}_{(A\to0)\times(B\to0)}(A+B\to0,\lambda x.\lambda y.\Box)$

Also suppose $A$ or $B$: 
- find a function $f((x,y))(z):\equiv\Box:0$

There are two cases:
- use pattern matching: 
	- $f((x,y))(inl(a)):\equiv\Box:0$
	- $f((x,y))(inr(b)):\equiv\Box:0$
- OR use recursor: $f((x,y))(z):\equiv \text{rec}_{A+B}(0,\lambda a.\Box,\lambda b.\Box,z)$

Our eventual definition:
	- $f((x,y))(inl(a)):\equiv x(a)$ (note that we can write 0 here because 0 is a type, we have to construct an element of 0 (from elimination))
	- $f((x,y))(inr(b)):\equiv y(b)$


We now try to prove the other direction:
Goal: find a element of type $((A+ B)\to0)\to(A\to0)\times(B\to0)$

let $g$ be a element of this type.
$g:\equiv\lambda h.(x,y)$
with $h:A+B\to0$
$x:\equiv\lambda a.h(inl(a))$ with $x:A\to0$ and ${} inl(a):A+B {}$
$y:\equiv\lambda b.h(inr(b))$ with $y:B\to0$


## Restrictions
The rule “If not (A and B), then (not A) or (not B)” is not valid: we cannot, in general, construct an element of the corresponding type $(A\times B\to0)\to(A\to0)+(B\to0)$
This is because we do not have LEM (law of excluded middle: $\forall{A}\; (A\vee \neg A)$) (we also does not deny LEM)

The propositions-as-types logic of type theory is **constructive**
We cannot always determine a proposition has a proof or not.
we can only construct those propositions with a computational meaning.


> [!Important] LEM
> we may consistently add it as an assumption, and work conventionally without restriction

