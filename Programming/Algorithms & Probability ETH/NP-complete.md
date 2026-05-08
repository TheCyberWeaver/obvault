## Classes of Problems: P and NP

### P (Polynomial Time)

The class of **decision problems** (problems with a “yes” or “no” answer) that can be solved by a deterministic algorithm in polynomial time.

Problems in **P** are considered *efficiently solvable*.

**Example:** 
The Eulerian Tour problem belongs to the class **P**.

---

### NP (Nondeterministic Polynomial Time)

The class of decision problems for which a “yes” answer can be verified in polynomial time, given a suitable **certificate** or **proof**.

More formally, a problem is in **NP** if there exists a nondeterministic algorithm that can solve it in polynomial time.

A nondeterministic algorithm can be thought of as making “lucky guesses” that always lead to a solution if one exists.

## NP-complete
a problem $\Pi \in NP$ is NP-complete if $\Pi \in P\implies P=NP$