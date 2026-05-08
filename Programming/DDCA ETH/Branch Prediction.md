---
aliases:
  - Branch Predictor
---
## Overview

**Branch prediction** is a [[Microarchitecture|microarchitectural]] technique that guesses the outcome of a control-flow instruction before the condition is fully known.
It is mainly used in [[Pipelining|pipelined]] and out-of-order processors to avoid waiting until the branch is resolved.

Typical branches are:
- conditional branches such as `beq`, `bne`
- unconditional jumps
- calls and returns

The predictor usually tries to answer two questions:
- **direction prediction**: is the branch taken or not taken?
- **target prediction**: if it is taken, what is the next program counter?
![[Pasted image 20260423173535.png|389]]

## Static branch prediction

A **static** predictor does not learn from past executions.
It uses a fixed rule such as:

- always predict **not taken**
- always predict **taken**
- backward branches predicted taken, forward branches predicted not taken

> [!NOTE]
> Backward branches often come from loops, so predicting them as taken is often reasonable.

## Dynamic branch prediction

A **dynamic** predictor uses past branch behavior to improve future guesses.
This is important because many branches are strongly correlated with recent execution history.

### 1-bit predictor

The simplest dynamic predictor stores one bit per branch:
- predict taken if the bit is `1`
- predict not taken if the bit is `0`
- after execution, update the bit to the actual outcome
![[Pasted image 20260423172733.png|421]]
This works well for branches with stable behavior.
However, it performs poorly for loop branches because one unusual iteration can flip the prediction immediately.

### 2-bit saturating counter

A common improvement is a **2-bit saturating counter**.
It has four states:

| State | Meaning |
| --- | --- |
| `00` | strongly not taken |
| `01` | weakly not taken |
| `10` | weakly taken |
| `11` | strongly taken |
![[Pasted image 20260423173250.png|393]]
The predictor changes state gradually:
- on a taken branch, move one step toward `strongly taken`
- on a not-taken branch, move one step toward `strongly not taken`

So a single unusual outcome does not immediately reverse the prediction.
This makes loop branches much more predictable.

### Local and global history

More advanced predictors use history patterns.

- **local history** tracks the recent behavior of one specific branch
- **global history** tracks the recent outcomes of many branches together

![[Pasted image 20260423173636.png|346]]
### Perceptron predictor

A **perceptron predictor** uses a small linear classifier instead of only table counters.
It combines bits of branch history with a set of learned weights and computes a score:

$$
\text{score}=w_0+\sum_i w_i h_i
$$
![[Pasted image 20260423173851.png|450]]
If the score is positive, predict taken; otherwise predict not taken.
This allows the predictor to learn longer-range correlations than simple 2-bit counter schemes.

Its main disadvantages are higher hardware cost and a slower prediction/update path.

### TAGE predictor

**TAGE** stands for **tagged geometric history length** predictor.
It uses several predictor tables in parallel, where each table is indexed with a different history length.
![[Pasted image 20260423174121.png|454]]

So:
- short histories capture simple recent patterns
- long histories capture more complex correlations
- tags help decide whether an entry really matches the current branch/history

TAGE is widely used because it gives very high accuracy while remaining practical to implement.

## Branch Target Buffer

A **branch target buffer** (**BTB**) is a cache-like structure that stores the destination address of previously seen taken branches.

Without a BTB, the processor may know that a branch is likely taken but still not know the target quickly enough.
With a BTB, the fetch stage can immediately redirect instruction fetch to the predicted target.

So in practice:
- the direction predictor guesses whether the branch is taken
- the BTB supplies the predicted target address

## Speculative execution

Branch prediction is closely tied to **speculation**.
The processor executes instructions on the predicted path before it knows whether that path is correct.

If the prediction was correct:
- the speculative work becomes useful and execution continues normally

If the prediction was wrong:
- younger speculative instructions are squashed
- the pipeline is flushed or partially flushed
- fetching restarts from the correct PC

In an [[Out-of-order Execution|out-of-order processor]], recovery is usually coordinated with the [[Reorder Buffer]], so wrongly speculated results do not become architecturally visible.
