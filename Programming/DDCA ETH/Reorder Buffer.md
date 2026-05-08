---
aliases:
  - ROB
---
## Overview

A **reorder buffer** is used in [[Out-of-order Execution|out-of-order processors]].
- **in-order commit**, so the visible machine state changes in program order
- **precise exceptions**, so traps appear as if instructions executed one by one
- **branch misprediction recovery**, by discarding speculative results that should not become visible

## ROB entry

A ROB entry usually contains:

- the destination register, or information that the instruction writes to memory
- the result value, or a tag/reference to where the value will come from
- a **ready** bit that says whether execution has finished
- an **exception** bit or status field
- sometimes the program counter or branch information for recovery
![[Pasted image 20260402160531.png]]

> [!NOTE]
> A [[Out-of-order Execution#Scoreboarding|scoreboard]] decides when an instruction may execute.
> A reorder buffer makes sure results commit in order and supports recovery.

## Execution vs commit

It is useful to separate three steps:
- **issue / dispatch**: send the instruction into the machine and allocate tracking state
- **execute / complete**: compute the result when operands and functional units are ready
- **commit / retire**: make the result architecturally visible

The reorder buffer allows execution to be out of order while commit stays in order.
## Example intuition

Suppose instruction `I3` finishes before `I2`.
Without a reorder buffer, `I3` might update the visible state too early.
If `I2` then causes an exception, the processor would show an incorrect state.

With a reorder buffer, `I3` can finish early and wait.
Its result becomes visible only when all older instructions have committed first.

