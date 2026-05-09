 #exercise 
# 4.5 Symmetric difference
1)
$(A\cup B)\setminus (A\cap B)$ 

2)
$A\Delta B\overset{ def }{ = }\{ x|(x \in A\vee x \in B)\wedge \neg(x \in A\wedge x \in B) \}$
$=\{ x|(x \in A\vee x \in B)\wedge(\neg (x \in A)\vee \neg (x \in B)) \}$ (de Morgan's rule)
$=\{ x|((x \in A\vee x \in B)\wedge(\neg(x \in A)))\vee((x \in A\vee x \in B)\wedge(\neg(x \in B))) \}$ (distributivity law)
$=\{ x|((\neg(x \in A))\wedge(x \in A\vee x \in B))\vee ((\neg(x \in B))\wedge(x \in A\vee x \in B))\}$ (commutativity law)
$=\{ x|((\neg(x \in A)\wedge x \in A)\vee(\neg(x \in A)\wedge x \in B))\vee((\neg(x \in B)\wedge x \in A)\vee(\neg(x \in B)\wedge x \in B)) \}$(distributivity law)
$=\{ x|((\perp\vee(\neg(x \in A)\wedge x \in B))\vee((\neg(x \in B)\wedge x \in A)\vee\perp) \}$ ($\neg F\wedge F=\perp$)
$=\{ x|(\neg(x \in A)\wedge x \in B)\vee(\neg(x \in B)\wedge x \in A) \}$ ($F\vee \perp=F$)
$=\{ x|(x \in A\wedge \neg(x \in B))\vee(x \in B\wedge \neg(x \in A)) \}$ (commutativity law)
$=(A\setminus B)\cup(B\setminus A)$ (definition of $\setminus$ and $\cup$)
The claim is proved


$\neg F\wedge F$ is unsatisfiable, and therefore $\neg F\wedge F=\perp$

3)
$A\Delta B=A\Delta C$
$\implies(A\Delta B)\Delta A=(A\Delta C)\Delta A$ (doing same operation on both sides of the equation)
$\Longleftrightarrow B=C$ (by Side Proof below)

Side Proof:
**Claim**: $(A\Delta B)\Delta A=B$
**Proof**: Let $a$ be $x \in A$ and $b$ be $x\in B$, and let $a\oplus b\equiv(a\wedge \neg b)\vee(b\wedge \neg a)$
$x \in(A\Delta B)\Delta A$
$\Longleftrightarrow (a\oplus b)\oplus a$ (by definition of $A\Delta B$ and definition of $\oplus$)
$≡((a∧¬b)∨(b∧¬a))⊕a​$ (by definition of $\oplus$)
$≡(((a∧¬b)∨(b∧¬a))∧¬a)∨(¬((a∧¬b)∨(b∧¬a))∧a)$ (by definition $\oplus$)
$≡(((a∧¬b)∧¬a)∨((b∧¬a)∧¬a))∨(¬((a∧¬b)∨(b∧¬a))∧a)$ (distributivity law)
$≡(((a∧¬b)∧¬a)∨((b∧¬a)∧¬a))∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ (de Morgan's law)
$≡((a∧¬a∧¬b)∨(b∧¬a∧¬a))∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ (commutativity)
$≡((⊥∧¬b)∨(b∧¬a∧¬a))∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ ($F∧¬F ≡⊥$)
$≡((⊥∧¬b)∨(b∧¬a))∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ (idempotence)
$≡(⊥∨(b∧¬a))∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ ($F ∧⊥ ≡ ⊥$)
$≡(b∧¬a)∨((¬(a∧¬b)∧¬(b∧¬a))∧a)$ ($F ∨⊥ ≡ F$)
$≡(b∧¬a)∨(((¬a∨b)∧(¬b∨a))∧a)$ (de Morgan's law)
$≡(b∧¬a)∨((¬a∨b)∧((¬b∨a)∧a))$ (associativity)
$≡(b∧¬a)∨((¬a∨b)∧a)$ (absorption)
$≡(b∧¬a)∨((a∧b)∨(a∧¬a))$ (distributivity law)
$≡(b∧¬a)∨((a∧b)∨⊥)$ ($\neg F\wedge F=\perp$)
$≡(b∧¬a)∨(a∧b)$ ($F ∨⊥ ≡ F$)
$≡b∧(¬a∨a)$ (distributivity law)
$≡b∧(¬a∨a)$ ($F∧¬F ≡⊥$)
$≡b∧⊥$ ($F∧¬F ≡⊥$)
$≡b$ ($F ∨⊥ ≡ F$)
$\Longleftrightarrow x \in B$ (by definition of $b$)
Therefore, $\forall x(x \in (A\Delta B)\Delta A\leftrightarrow x \in B)$, meaning $A\subseteq B$ and $B\subseteq A$ by definition of $\subseteq$
Hence, $(A\Delta B)\Delta A=B$ by Lemma 3.2
The claim is proved.

# 4.8 Short questions (exam 2022)
1.
2 elements

2.
$(\varnothing,\{ 0,1 \})$
$((0,1),\{ 0,1 \})$

3.
$A=\{ 1,2,3 \}$
$B=\{ 2,3 \}$
$C=\{ 3 \}$

4.
$A=\{ \varnothing \}$

# 4.9 Short questions (exam 2021)
1. False
2. False
3. False
4. False
5. False

