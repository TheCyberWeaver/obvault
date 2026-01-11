
or order relation
> [!PDF|note] [[Discrete Mathematics ETH.pdf#page=70&selection=213,0,213,56&color=note|Discrete Mathematics ETH, p.60]]
> > A partial order on a set $A$ is a relation that is **reflexive**, **antisymmetric**, and **transitive**
> 
> The only difference to an [[Relation#Equivalence Relations|equivalence relation]] is **antisymmetric** instead of symmetric
> Noted as $\preceq$

### Example
$A=\mathbb{Z}$, [[Relation]] $\preceq= \leq$

## Definition 
$$
\prec\overset{ def }{ = }\preceq \setminus \text{id}
$$
### Example
$A=\mathbb{N}\setminus \{ 0 \},\preceq=|$ (division relation)
$A=\mathcal P(B),\preceq=\subseteq$

## Definition Poset

$(A;\preceq)$ is a poset. It's just a partial order relation on a set, and this thing is called a poset

## Lemma
If $(A;\preceq)$ is a poset, $\prec$ is transitive

$a\prec b\implies a\preceq b \; \wedge a\neq b$
$b\prec c\implies b\preceq c \; \wedge b\neq c$
$a\preceq b \wedge \; b\preceq c\implies a\preceq c$
### Hasse diagrams
![[Pasted image 20251020144645.png|481]]

## Combination of Posets
### Direct Product

$(A;\preceq)\times(B;\sqsubseteq)$ is $(A\times B;\leq)$ with
$(a_{1},b_{1})\leq(a_{2},b_{2})\overset{ def }{ \Longleftrightarrow }(a_{1}\preceq a_{2})\wedge(b_{1}\sqsubseteq b_{2})$

(see similar concept [[Section 11 Direct Products and Finitely Generated Abelian Groups|External Direct Product in Groups]])

### lexicographic order

For $(A;\preceq)$ and $(B;\sqsubseteq)$, $(A\times B;\leq _{lex})$ is also a poset.
	$(a_{1},b_{1})\leq _{lex}(a_{2},b_{2})\overset{ def }{ \Longleftrightarrow }(a_{1}\prec a_{2})\vee(a_{1}=a_{2}\wedge b_{1}\sqsubseteq b_{2})$

> [!NOTE]
> Think of the relations of two-digits numbers (A is the first digit, B is the second digit)

## Definition: totally ordered

> [!Quote] 
> If any two elements of a poset $(A; \preceq)$ are comparable, then A is called **totally ordered** (or linearly ordered) by $\preceq$.

The hasse diagram would look like a line. (reason why it is also called as linearly ordered)
## Definition: well-ordered


> [!Quote] 
> A poset $(A; \preceq)$ is **well-ordered** if it is totally ordered and if every non-empty subset of A has a least element.

> [!NOTE] 
> every totally ordered finite poset is well-ordered
