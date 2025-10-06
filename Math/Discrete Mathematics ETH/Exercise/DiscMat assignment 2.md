#eth #exercise 
# 2.1 Logical Consequence

![[Pasted image 20250929124749.png|376]]

| A   | B   | $A\rightarrow B$ | $A\wedge (A\to B)$ |
| --- | --- | ---------------- | ------------------ |
| 0   | 0   | 1                | 0                  |
| 0   | 1   | 1                | 0                  |
| 1   | 0   | 0                | 0                  |
| 1   | 1   | 1                | 1                  |
Statement 1 is proved

| A   | B   | $A\rightarrow B$ | $\neg A \to \neg B$ |
| --- | --- | ---------------- | ------------------- |
| 0   | 0   | 1                | 1                   |
| 0   | 1   | 1                | 0                   |
| 1   | 0   | 0                | 1                   |
| 1   | 1   | 1                | 1                   |
Statement 2 is disproved

| A   | B   | $A\rightarrow B$ | $(A\to B)\vee(B \to A)$ |
| --- | --- | ---------------- | ----------------------- |
| 0   | 0   | 1                | 1                       |
| 0   | 1   | 1                | 1                       |
| 1   | 0   | 0                | 1                       |
| 1   | 1   | 1                | 1                       |
Statement 3 is proved

| $A$ | $B$ | $C$ | $A→B$ | $B→C$ | $(A→B)∧(B→C)$ | $A→C$ |
| --- | --- | --- | ----- | ----- | ------------- | ----- |
| 0   | 0   | 0   | 1     | 1     | 1             | 1     |
| 0   | 0   | 1   | 1     | 1     | 1             | 1     |
| 0   | 1   | 0   | 1     | 0     | 0             | 1     |
| 0   | 1   | 1   | 1     | 1     | 1             | 1     |
| 1   | 0   | 0   | 0     | 1     | 0             | 0     |
| 1   | 0   | 1   | 0     | 1     | 0             | 1     |
| 1   | 1   | 0   | 1     | 0     | 0             | 0     |
| 1   | 1   | 1   | 1     | 1     | 1             | 1     |
Statement 4 is proved

# 2.2 Satisfiability and Tautologies
![[Pasted image 20250929131439.png]]
1. satisfiable and not a tautology, 
	- example satisfiable: $A=0$ $B=1$
	- example not a tautology: $A=1$ $B=1$
2. satisfiable and tautology: proved by the table in [[#2.1 Logical Consequence|exercise 2.1.4]]

# 2.3 Simplifying a Formula

$$
F=(B\to A)\wedge \neg( (\neg A\wedge \neg C)\wedge(\neg C\vee B) )
$$
$G=A\vee(\neg B\wedge \neg \neg C)$
Proof:
- $F\equiv(\neg B\vee A)\wedge \neg( (\neg A\wedge \neg C)\wedge(\neg C\vee B) )$ Definition of $\to$
- $\equiv(\neg B\vee A)\wedge \neg(\neg A\wedge (\neg C\wedge (\neg C\vee B)))$ associativity of $\wedge$
- $\equiv (\neg B\vee A)\wedge \neg(\neg A\wedge \neg C)$ absorption
- $\equiv(\neg B\vee A)\wedge (\neg \neg A\vee \neg \neg C)$ de Morgan's rule
- $\equiv(\neg B\vee A)\wedge ( A\vee \neg \neg C)$ double negation
- $\equiv(A\vee \neg B)\wedge(A\vee \neg \neg C)$ commutativity of $\vee$
- $\equiv A\vee(\neg B\wedge \neg \neg C)$ second distributive law
$F\equiv G$ is proved
# 2.4 Knights and Knaves

> Does the left road lead to the village if and only if you are a knight?

| A   | $B$ | $A\leftrightarrow B$ | Answer |
| --- | --- | -------------------- | ------ |
| 0   | 0   | 1                    | 0      |
| 0   | 1   | 0                    | 0      |
| 1   | 0   | 0                    | 1      |
| 1   | 1   | 1                    | 1      |

$F=A\leftrightarrow B$
# 2.5 Quantifiers and Predicates

![[Pasted image 20250929143049.png]]

- $0<n\cdot m\models (0<n) \vee (0<m)$ false
- $\forall n \:\exists m\: \exists k\:(n<m\wedge m=3\cdot k)$ true
- $\forall x \:\exists n \:\exists m (prime(n)\wedge prime(m)\wedge(x=n+m))$ ???possibly true

![[Pasted image 20250929150738.png]]
![[Pasted image 20250929150748.png]]
1. For all integer x there is a integer reciprocal of x (==false==)
2. There exists an x such that x does not form a product of 1 with any y, and there exists a positive y (==true==)
