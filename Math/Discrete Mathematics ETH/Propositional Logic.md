#eth 

## Bausteine
- **Symbole** (A,B,C...) können Werte 0,1 annehmen
- **Operatoren** ($\neg,\wedge,\vee,\to, \leftrightarrow$) (nicht, und, oder, Implikation, Äquivalenz)
- **Formeln** Ausdrücke von Operation und Symbolen 

| A   | B   | $A\wedge B$ | $A\vee B$ | $A\to B$ | $A\leftrightarrow B$ |
| --- | --- | ----------- | --------- | -------- | -------------------- |
| 0   | 0   | 0           | 0         | 1        | 1                    |
| 0   | 1   | 0           | 1         | 1        | 0                    |
| 1   | 0   | 0           | 1         | 0        | 0                    |
| 1   | 1   | 1           | 1         | 1        | 1                    |

> [!NOTE]
> $A\to B\equiv\neg A\vee B$
> $F\equiv\top$ "F allgemeingültig" immer 1
> $F\equiv\perp$ "F unerfüllbar" immer 0



**Tautologie**: immer 1 (or **valid**)

> [!Definition ]
> Logische Konsequenz: $F\models G$ 
> if for all truth assignments to the propositional symbols appearing in F or G, the truth value of G is 1 if the truth value of F is 1.

Beobachtung: $(F\to G \quad allgemeingültig)\leftrightarrow (F\models G)$
Beispiel

| A   | B   | $A\rightarrow B$ | $A\wedge (A\to B)$ | $(A\wedge (A\to B))\to B$ |
| --- | --- | ---------------- | ------------------ | ------------------------- |
| 0   | 0   | 1                | 0                  | 1                         |
| 0   | 1   | 1                | 0                  | 1                         |
| 1   | 0   | 0                | 0                  | 1                         |
| 1   | 1   | 1                | 1                  | 1                         |
$\implies A\wedge(A\to B)\models B$

## Modus Ponens

Ziel: Aussage $S$
Vorgehen:
1. Finde geeignete Aussage $R$
2. Beweise $R$
3. Beweise $R\implies S$

### Falsches Beispiel
Theorem $1<0$
Beweise: $1>0\implies 2<1$ (+1 beide Seite)
		$\implies 2>1$ (\*1, weil 1 negativ ist)

Man sollte anders um beweisen, vom Wahres anfangen
It’s crucial **not** to confuse the direction of implication. **Proving S⟹R and R is true** does **not** imply that S is true.
## Lemma 2.1
![[Pasted image 20250924145817.png]]


## Semantics
![[Pasted image 20251211181817.png]]

## Definition: Literal
A **literal** is an atomic formula or the negation of an atomic formula.
For example: $L$ or $\neg L$
## Definition: Clause
A **clause** is a set of **literals**.

## Resolution Calculus
![[Pasted image 20251221153518.png|539]]

This calculus is rule is written as
$\{ K_{1},K_{2} \}\vdash_{res}K$
The resolution calculus contains only this one rule, $\mathrm{Re}s=\{ res \}$

> [!Warning] 
> It is important to point out that resolution steps must be carried out one by one


