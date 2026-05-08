---
aliases:
  - Multicycle Processor
---
## Overview

A **multi-cycle processor** executes one instruction across several clock cycles instead of forcing all work into one long cycle.
It is a basic [[Microarchitecture|microarchitectural]] design that reduces the amount of work done in each cycle and allows hardware resources to be reused.

![[Pasted image 20260326155357.png]]
## Typical execution phases

A multi-cycle processor often breaks instruction execution into phases such as:
- instruction fetch
- instruction decode and register read
- ALU operation or address calculation
- data memory access when needed
- register writeback when needed

![[Pasted image 20260326155630.png]]
Not every instruction uses every phase.
The controller activates only the steps required for the current instruction.

## Datapath and control

Because execution is spread across multiple cycles, the processor needs internal state to hold intermediate results between phases.
The control logic is usually implemented as a [[Finite State Machine]].
![[Pasted image 20260326155436.png]]
## Why it is useful

- the clock period can be shorter because each cycle contains less combinational logic
- hardware blocks such as the ALU and memory interface can be reused across phases
- instructions with different amounts of work can naturally take different numbers of cycles

## Difference to single-cycle architecture

| Aspect               | Multi-cycle processor                                   | Single-cycle architecture                           |
| -------------------- | ------------------------------------------------------- | --------------------------------------------------- |
| Instruction length   | One instruction may take several cycles                 | Every instruction finishes in one cycle             |
| Clock period         | Shorter, because each cycle does less work              | Longer, because it must fit the slowest instruction |
| CPI                  | Usually greater than `1` and depends on the instruction | Usually `1`                                         |
| Hardware usage       | Reuses functional units across cycles                   | Often needs less sharing and a longer datapath      |

## Not the same as pipelining

A multi-cycle processor spreads one instruction over multiple cycles.
A pipelined processor overlaps multiple instructions in different stages at the same time.
see [[Pipelining]] for details