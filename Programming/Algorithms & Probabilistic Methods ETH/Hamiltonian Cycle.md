A **Hamiltonian cycle** (or **Hamilton cycle**) in a graph is a **simple cycle that visits every vertex exactly once and returns to the start**.

## Application: Rotary Encoder

![[Pasted image 20260219131530.png|195]]![[Pasted image 20260219125749.png|462]]
There are $k$ light emitters and light detectors.
We want to arrange the holes on the plate in a certain way such that they encode $2^{k}$ directions.
For $k=2$, we want to have 00, 01, 10, 11. However, we also want the codes of any two neighboring directions to differ in only one bit, because the light detectors are much more precise than the positions of the holes.

We can model this problem as finding a Hamiltonian cycle on a $k$ dimensional hypercube.

Solving this problem is straightforward. Suppose we have a Hamiltonian cycle on $k-1$ dimensional hypercube. We first break it into a Hamiltonian path, then duplicate the hypercube along the $k$-th dimension and finally connect the two paths together to form a new cycle.

How it looks like:
![[Pasted image 20260219131722.png|274]]![[Pasted image 20260219131654.png|239]]


