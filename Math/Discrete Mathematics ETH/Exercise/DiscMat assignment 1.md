#eth #exercise 
# 1.1 The Punctured Chessboard
## 1
![[Pasted image 20250921220451.png]]
10 Cases
![[Pasted image 20250921230406.png|217]]
## 2
![[Pasted image 20250921220641.png|310]]
![[Pasted image 20250921230423.png|482]]
Note that 3\*4 and 2\*3 rectangles can always be filled will L shapes

# 1.2 A False Proof
![[Pasted image 20250921234543.png|317]]
The initial assumption is false. The proof proves only "if a largest natural number exists, it must be 1", but it does not prove that such a number exists.
# 1.3 Interpreting Propositional Formulas in Natural Language
![[Pasted image 20250922000207.png]]
## 1.
- i) Mario remembered to pay his rent **implies** Mario is not getting evicted.
- ii) **Either** Mario forgot to pay his rent and is getting evicted **or** Mario remembered to pay his rent and is not getting evicted.
## 2.
- i) $\neg A \wedge \neg B$ 
- ii) $(A\vee B)\wedge\neg(A\wedge B)$
## 3.
- $F_{3}$ : $A ∨ B$
	- Mario forgot to pay his rent or he is getting evicted (possibly both)
- $F_{4}$ : $(\neg A ∧ \neg B) ∨ (A ∧ B)$
	- Either Mario did neither, or he did both.

# 1.4 Logical Equivalence via Function Tables
![[Pasted image 20250922131227.png]]

## 1.

| A   | B   | C   | $(B\to C)\to(\neg(A\to C)\wedge\neg(A\vee B))$ |
| --- | --- | --- | ---------------------------------------------- |
| 0   | 0   | 0   | 0                                              |
| 0   | 0   | 1   | 0                                              |
| 0   | 1   | 0   | 1                                              |
| 0   | 1   | 1   | 0                                              |
| 1   | 0   | 0   | 0                                              |
| 1   | 0   | 1   | 0                                              |
| 1   | 1   | 0   | 1                                              |
| 1   | 1   | 1   | 0                                              |
## 2.
$$
\neg C \wedge B
$$

# 1.5 Two New Logical Operators
## 1.
![[Pasted image 20250921234123.png|548]]
We only need to consider the cases where $A\neq B$:
- $0♡1\neq1♡0$
- $0♢1=1♢0$
$\implies$ ♡ is **not** commutative, ♢ is commutative
## 2.
![[Pasted image 20250921234111.png|519]]

| A   | B   | C   | (¬A♡B)♢(B♡C) | ¬(A♢B)♡¬(A♢C) |
| --- | --- | --- | ------------ | ------------- |
| 0   | 0   | 0   | 1            | 1             |
| 0   | 0   | 1   | 1            | 0             |
| 0   | 1   | 0   | 1            | 1             |
| 0   | 1   | 1   | 0            | 1             |
| 1   | 0   | 0   | 0            | 1             |
| 1   | 0   | 1   | 0            | 1             |
| 1   | 1   | 0   | 1            | 0             |
| 1   | 1   | 1   | 0            | 1             |
Table (¬A♡B)♢(B♡C) and table ¬(A♢B)♡¬(A♢C) are different. The hypothesis is false

## 3.
![[Pasted image 20250921234057.png]]
B♡(A♢C)

# 1.6 Simplifying a Formula
$$
F=((\neg A\vee \neg B)\wedge \neg A)\wedge ((\neg B\wedge \neg A)\vee C)
$$
![[Pasted image 20250922133247.png|493]]
- $F=\neg A\wedge ((\neg B\wedge \neg A)\vee C)$ : absorption from Lemma 2.1
- $F=(\neg A \wedge(\neg B\wedge \neg A)) \vee (\neg A\wedge C)$ : first distributive law
- $F=((\neg B\wedge \neg A)\wedge \neg A) \vee (\neg A\wedge C)$ : commutativity 
- $F=(\neg B\wedge (\neg A\wedge \neg A)) \vee (\neg A\wedge C)$ : associativity 
- $F=(\neg B\wedge \neg A) \vee (\neg A\wedge C)$ :  idempotence
- $F=\neg A \wedge (\neg B\vee C)$ :  idempotence
