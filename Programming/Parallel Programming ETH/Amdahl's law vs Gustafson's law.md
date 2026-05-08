> [!Definition]
> [[Amdahl's law]] and [[Gustafson's law]] both describe speedup in parallel computing, but they are based on different assumptions about how the workload changes as the number of processors grows.

## Main difference

[[Amdahl's law]] assumes a **fixed problem size**.

- we run the same job on more processors
- the sequential part limits the final speedup
- this is the usual **strong scaling** viewpoint

[[Gustafson's law]] assumes a **scaled problem size**.

- more processors are used to solve a larger job
- the parallel part grows with the number of processors
- this is closer to the **weak scaling** viewpoint

## Side-by-side comparison

| Aspect | [[Amdahl's law]] | [[Gustafson's law]] |
| --- | --- | --- |
| Problem size | fixed | grows with the number of processors |
| Main question | How much faster can the same job run? | How much larger a job can we solve in the same time? |
| Main limitation | sequential part caps speedup | sequential overhead matters less if parallel work scales |
| Scaling viewpoint | strong scaling | weak scaling |
| Overall message | pessimistic upper bound | more optimistic for large parallel systems |

## When each law is useful

- use [[Amdahl's law]] when the workload is fixed and you care about reducing runtime
- use [[Gustafson's law]] when the workload naturally grows with available computing power

> [!Important]
> The two laws do not contradict each other. They describe different scenarios.
