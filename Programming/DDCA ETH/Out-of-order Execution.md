---
aliases:
  - OoO
---
## Dependence types
### Flow dependence (RAW)
**Read after write**:
instruction $I_2$ reads a value that instruction $I_1$ writes.

```asm title:Example
add $t0, $t1, $t2
sub $t3, $t0, $t4
```

The second instruction needs the value produced by the first one.
This is a **true data dependence**, so it cannot be removed by simple renaming.
For solution see [[#Handling flow dependences]]

### Anti-dependence (WAR)
**Write after read**:
instruction $I_1$ reads a location that instruction $I_2$ later writes.

```asm title:Example
sub $t3, $t0, $t4
add $t0, $t1, $t2
```

The later write must not happen too early, otherwise the first instruction would read the wrong value.
This is a **name dependence**, not a true flow of data.
It can usually be removed by [[Register|register]] renaming.

### Output dependence (WAW)

**Write after write**:
two instructions write the same location

```asm title:Example
add $t0, $t1, $t2
sub $t0, $t3, $t4
```

The final visible value of `$t0` must come from the second instruction.
This is also a **name dependence**, and it can usually be removed by register renaming.

> [!NOTE]
> **register renaming** is a central idea in out-of-order processors.
> It removes false dependences, so the scheduler can execute more instructions in parallel.
## Handling flow dependences

There are several fundamental ways to handle a **flow dependence**:

- detect it and _wait_ until the value is available in the register file. Add `nop` instructions to create bubbles.
- detect it and _forward / bypass_ the value to the dependent instruction
- detect it and _eliminate_ the dependence at the software level
- detect it and _move it_ out of the way by executing independent instructions first
- _predict_ the needed value, execute speculatively, and later _verify_
- _do something else while waiting_, for example fine-grained multithreading

### Combinational dependence check logic
The hardware compares source and destination registers with combinational logic and then decides to stall, forward, or proceed.
This is simple and fast for small pipelines, but it scales poorly.
### Scoreboarding
A **scoreboard** keeps centralized status information about instructions, registers, and functional units.
It allows an instruction to proceed only when the needed resources and operands are ready, so hazards are avoided in a more systematic way.


## Handling WAR and WAW
Modern out-of-order processors also need a way to let instructions finish out of order without exposing results in the wrong order.
That is the role of the [[Reorder Buffer]].