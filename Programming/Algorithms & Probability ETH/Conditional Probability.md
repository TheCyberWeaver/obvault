> [!NOTE] Definition
> Let A and $B$ be events with $\Pr[B]>0$
> $$\Pr[A|B]=\frac{\Pr[A\cap B]}{\Pr[B]}$$

## Basic Properties
- $\Pr[A|\Omega]=\Pr[A]$
- $\Pr[A|A]=1$
- $\Pr[A|\bar{A}]=0$
- $\Pr[A\cap B]=\Pr[A|B]\cdot \Pr[B]=\Pr[B|A]\cdot \Pr[A]$

## Bayes Formula

Let $A_1,\dots,A_n$ be pairwise disjoint events with $\Pr[A_i]>0$, and let $B$ be an event such that
$$
B \subseteq \bigcup_{i=1}^n A_i
\qquad\text{and}\qquad
\Pr[B]>0.
$$
Then for every $k \in \{1,\dots,n\}$,
$$
\Pr[A_k \mid B]
=
\frac{\Pr[A_k \cap B]}{\Pr[B]}
=
\frac{\Pr[B \mid A_k]\Pr[A_k]}{\sum_{i=1}^n \Pr[B \mid A_i]\Pr[A_i]}.
$$

## Law of total probability

Let $A_1,\dots,A_n$ be pairwise disjoint events such that
$$
A_1 \cup \cdots \cup A_n = \Omega
\qquad\text{and}\qquad
\Pr[A_i] > 0 \text{ for all } i.
$$
Then for every event $B$,
$$
\Pr[B]
=
\sum_{i=1}^{n} \Pr[B \mid A_i]\Pr[A_i].
$$

This means: split the sample space into cases $A_1,\dots,A_n$, compute the probability of $B$ inside each case, and then weight by the probability of the case.

### Short proof

Since the $A_i$ form a partition of $\Omega$,
$$
B = \bigcup_{i=1}^{n} (B \cap A_i),
$$
and these sets are pairwise disjoint. So
$$
\Pr[B]
=
\sum_{i=1}^{n} \Pr[B \cap A_i].
$$
Using
$$
\Pr[B \cap A_i] = \Pr[B \mid A_i]\Pr[A_i],
$$
we get
$$
\Pr[B]
=
\sum_{i=1}^{n} \Pr[B \mid A_i]\Pr[A_i].
$$

### Example

Suppose:
- $30\%$ of students come by bike
- $70\%$ come by train
- among bike commuters, $10\%$ are late
- among train commuters, $20\%$ are late

Let:
- $A_1$ = "student comes by bike"
- $A_2$ = "student comes by train"
- $B$ = "student is late"

Then
$$
\Pr[B]
=
\Pr[B \mid A_1]\Pr[A_1] + \Pr[B \mid A_2]\Pr[A_2]
=
0.1 \cdot 0.3 + 0.2 \cdot 0.7
=
0.17.
$$

## Independent Events

Two events $A$ and $B$ are **independent** if
$$
\Pr[A \cap B] = \Pr[A]\Pr[B].
$$

If $\Pr[B] > 0$, this is equivalent to
$$
\Pr[A \mid B] = \Pr[A].
$$

> [!Important]
> This is equivalent to saying that the [[Random Variable#Special case indicator variable|indicator variables]] $\mathbf{1}_A$ and $\mathbf{1}_B$ are independent random variables.

For multiple events $A_1,\dots,A_n$, the strongest notion is **mutual independence**:
for **every non-empty subset** $I \subseteq \{1,\dots,n\}$,
$$
\Pr\left[\bigcap_{i \in I} A_i\right] = \prod_{i \in I} \Pr[A_i].
$$

In particular (necessary but _not_ sufficient),
$$
\Pr[A_1 \cap A_2 \cap \cdots \cap A_n]
=
\Pr[A_1]\Pr[A_2]\cdots \Pr[A_n].
$$

For an infinite family of events $(A_i)_{i \in J}$, **mutual independence** means that every finite subfamily is mutually independent. Equivalently, for every distinct $i_1,\dots,i_k \in J$,
$$
\Pr[A_{i_1} \cap \cdots \cap A_{i_k}]
=
\Pr[A_{i_1}] \cdots \Pr[A_{i_k}].
$$

> [!NOTE]
> Pairwise independence is weaker: it only requires $\Pr[A_i \cap A_j] = \Pr[A_i]\Pr[A_j]$ for all pairs $i \neq j$. This does **not** imply mutual independence.

### Useful Lemma

If $A,B,C$ are **mutually independent**, then 
- $A \cap B$ and $C$ are independent
- $A \cup B$ and $C$ are independent.

Proof:
$$
\Pr[(A \cap B) \cap C]
=
\Pr[A \cap B \cap C]
=
\Pr[A]\Pr[B]\Pr[C]
=
\Pr[A \cap B]\Pr[C].
$$
So $A \cap B$ and $C$ are independent.
Also,
$$
\Pr[(A \cup B) \cap C]
=
\Pr[(A \cap C) \cup (B \cap C)]
$$
$$
=
\Pr[A \cap C] + \Pr[B \cap C] - \Pr[A \cap B \cap C]
$$
$$
=
\Pr[A]\Pr[C] + \Pr[B]\Pr[C] - \Pr[A]\Pr[B]\Pr[C]
$$
$$
=
(\Pr[A] + \Pr[B] - \Pr[A \cap B])\Pr[C]
=
\Pr[A \cup B]\Pr[C].
$$
So $A \cup B$ and $C$ are independent.

## Multiplication Principle (Chain rule)
$$
\Pr[A_1\cap A_2\cap \cdots \cap A_n]
=
\Pr[A_1]\cdot \Pr[A_2\mid A_1]\cdot \Pr[A_3\mid A_1\cap A_2]\cdots \Pr[A_n\mid A_1\cap \cdots \cap A_{n-1}]
$$

Short proof: for $n=2$ this is exactly
$$
\Pr[A_1\cap A_2]=\Pr[A_2\mid A_1]\Pr[A_1].
$$
For general $n$,
$$
\Pr[A_1\cap \cdots \cap A_n]
=
\Pr[A_n\mid A_1\cap \cdots \cap A_{n-1}] \cdot \Pr[A_1\cap \cdots \cap A_{n-1}].
$$
Apply the same identity again to $\Pr[A_1\cap \cdots \cap A_{n-1}]$, and continue recursively. This yields the full product above.

## Application: Balls into Boxes
Throw $m$ balls independently and uniformly at random into $n$ boxes. What is the probability that every ball lands in an empty box? Equivalently, what is the probability that no two balls land in the same box?

Let $A_i$ be the event that the $i$-th ball lands in an empty box. Then
$$
\Pr[A_1]=1,
\qquad
\Pr[A_2\mid A_1]=\frac{n-1}{n},
\qquad
\Pr[A_3\mid A_1\cap A_2]=\frac{n-2}{n},
$$
and in general
$$
\Pr[A_i\mid A_1\cap \cdots \cap A_{i-1}] = \frac{n-i+1}{n}.
$$
This is because after $i-1$ successful throws, exactly $n-i+1$ boxes are still empty.

By the multiplication principle,
$$
\Pr[A_1\cap \cdots \cap A_m]
=
\prod_{i=0}^{m-1}\frac{n-i}{n}
=
\frac{n(n-1)\cdots (n-m+1)}{n^m}.
$$

For $m \ll n$, we can approximate
$$
\Pr[A_1\cap \cdots \cap A_m]
=
\prod_{i=0}^{m-1}\left(1-\frac{i}{n}\right)
\approx
\prod_{i=0}^{m-1} e^{-i/n}
=
e^{-\sum_{i=0}^{m-1} i/n}
=
e^{-\frac{m(m-1)}{2n}}.
$$

So the probability that all $m$ balls land in different boxes is approximately
$$
e^{-\frac{m(m-1)}{2n}}.
$$

If $m>n$, this probability is $0$.
