## What is a Category

A category $\mathcal C$ consists of *four* things:
- **Objects**: a class $Obj(\mathcal C)$ called the class of objects of $\mathcal C$
- **Morphisms**: For all $A,B\in Obj(\mathcal C)$, a set $Hom_C(A,B)$ of morphisms (called the homset of morphisms from A to B)
- **Composition**: The morphisms composition function $\circ:Hom_C(A,B)\times Hom_C(B,C)\rightarrow   Hom_C(A,C)$ 
- **Identity**: For all $A\in Obj(\mathcal C)$, a morphism $1_A\in\mathcal C(A,A)$ called the identity on A.
They follow the following properties:
	- This composition is associative: if $f\in Hom_C(A,B)$, $g\in Hom_C(B,C)$, $h\in Hom_C(C,D)$ $$(hg)f=h(gf)$$
	- for all $f\in Hom_C(A,B)$ we have $f1_A=f,\quad 1_Bf=f$.

## What is a class

A class is a collection of objects. One can think it as a fancy way of calling a collection.
> [!Tip]
> Every set can be considered as a class

We cannot have a set of all sets (because of Russell paradox)
However, we can have a class of all sets, which is called a proper class (a class that is not a set) 
	A proper class cannot be a member of any other set of class.


## Difference between Morphism and Function

| Aspect                    | Function                                                              | Morphism                                                                                    |
| ------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Definition**            | A mapping $f: A \to B$ between two **sets**                           | An arrow $f: A \to B$ in an **arbitrary category**                                          |
| **Domain & Codomain**     | Both **must be sets**                                                 | Can be **any objects** (sets, groups, spaces, etc.)                                         |
| **Structure Requirement** | No extra requirements beyond “each input has a unique output”         | Must **preserve the structure** of its category (e.g. group law, topology)                  |
| **Identity**              | Identity function $\mathrm{id}_A$ on set A                            | Identity morphism $1_A$ on object AA                                                        |
| **Examples**              | Any rule mapping elements of one set to another (e.g. $x\mapsto x^2$) | In **Set**: functions; in **Grp**: group homomorphisms; in **Top**: continuous maps |
See [[Special Morphisms]]
## Examples 1

| Category       | Objects  | Morphisms $A\to B$                          | Composition                                                                                                                                                           | Identity on A                     |
| -------------- | -------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| $\mathbf{Set}$ | all sets | all functions $A\to B$                      | usual composition of functions                                                                                                                                        | identity function $\mathrm{id}_A$ |
| $\mathbf{Rel}$ | all sets | all binary relations $R\subseteq A\times B$ | relational composition: two Relations $R\subseteq A\times B,S\subseteq B\times C$: $S\circ R=\{(a,c) \in A\times C \mid \ \exists b\in B$ so that $(aRb\wedge bSc)\}$ | the equality relation $\{(a,a)\}$ |
Similar Morphisms can also be multivalued map or partial functions...

## Examples 2
Consider an abstract Example
Let C be a category, and let A be an object of C
We define a category $C_A$ with:
- $Obj(C_A)$= all morphisms from any objects of C to A (e.g. $Z\overset{f}{\rightarrow} A$)
- Morphisms:
	- ![[Pasted image 20250618215540.png|267]]
- Composition:
	- ![[Pasted image 20250618215656.png|175]]
	- Because C is a category, we can remove the central arrow according to the composition law,
	- ![[Pasted image 20250618220152.png|199]]
	- which gives us the composition in $C_A$ (it commutes)

## Examples 3 
Consider another coslice category

Let category C=Set and A = a fixed singleton $\{*\}$ (any set that contains only one single element)

Define category Set\* as the category obtained by considering morphisms in C from the fixed object A to all objects in C.

- An object in Set\* is a morphism $f: \{*\}\rightarrow S$ 
	- This object should can be described by $(S,s)$ where $s\in S$ is any element of $S$. （a pointed set）
	- A function $f$ from the singleton set $\{\ast\}$ to any set $S$ is uniquely determined by the image of that single point—namely, once the element $s = f(\ast)$ is specified, the entire function $f$ is completely characterized. Thus we don't need to write out how $f$ looks like.
- A morphism between two such objects is $(S,s)\rightarrow(T,t)$ with set function $\sigma(s)=t$
- s and t are here basepoints.
- ![[Category Example.excalidraw]]
Object of Set\* are called **pointed sets** 

## Example 4

Consider $C_{A,B}$ 
$Obj(C_{A,B})=$
![[Pasted image 20250618231433.png|182]]
Morphisms:
![[Pasted image 20250618231456.png|273]]