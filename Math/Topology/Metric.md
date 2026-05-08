---
tags:
  - linker-exclude
---
## Definition
Let $X$ be a set.

A metric on $X$ is a function

$$
d : X \times X \to \mathbb{R}
$$

that assigns to every pair $(x,y) \in X \times X$ a real number $d(x,y)$, such that for all $x,y,z \in X$:
## Axioms

**Non-negativity**
$$
d(x,y) \ge 0
$$

**Identity of indiscernibles**
$$
d(x,y) = 0 \iff x = y
$$

**Symmetry**
$$
d(x,y) = d(y,x)
$$

**Triangle inequality**
$$
d(x,z) \le d(x,y) + d(y,z)
$$