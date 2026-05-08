## Overview
We divide the instruction into different stages
![[Pasted image 20260326155752.png|408]]
(for explanation of the design see [[Multi-cycle Processor|Multicycle Processor]])

The basic idea to fully utilize the idle stages
![[Pasted image 20260326155927.png|555]]

## An ideal pipeline
Goal: increase throughput with little increase in hardware cost.

An ideal pipeline works best when:
- the _same operation is repeated_ on many different inputs
- the repeated operations are _independent_
- there are _no dependencies_ between successive operations
- processing can be divided into _uniform-latency_ suboperations
- the suboperations _do not share resources_

Example: many laundry loads go through the same sequence of steps.

![[Pasted image 20260327144117.png]]
Full Design: 
![[Pasted image 20260327145331.png]]
## realistic throughput

Let
- $T$: total combinational delay
- $S$: register delay
Then for a nonpipelined design,
![[Pasted image 20260327143817.png|447]]
$$
\text{Throughput} = \frac{1}{T+S}.
$$
For an ideal $k$-stage pipeline with perfectly balanced stages,
![[Pasted image 20260327143850.png]]
$$
\text{Throughput}_{k\text{-stage}} = \frac{1}{T/k + S}.
$$

So pipelining increases throughput, but the register delay $S$ limits the gain.
Even with many stages, the throughput cannot improve beyond the overhead caused by the pipeline registers.

> [!NOTE]
> This assumes perfect division of work between stages.

However, stage division are usually not perfect:
![[Pasted image 20260327143715.png|697]]


## Cost of pipelining

Let
- $G$: combinational logic cost
- $R$: register cost

Then for a nonpipelined design,
$$
\text{Cost} = G + R.
$$

For a $k$-stage pipeline,
$$
\text{Cost}_{k\text{-stage}} = G + Rk.
$$

So pipelining improves throughput, but it also increases hardware cost because more registers are needed.
