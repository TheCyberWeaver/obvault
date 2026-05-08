---
aliases:
  - uArch
---
## Overview

A **microarchitecture** is the internal hardware organization used to implement an [[ISA]].
It is mostly hidden from the programmer, but it determines performance, area, power consumption, and clock frequency.

Two processors may implement the same ISA while using very different microarchitectures.
That distinction is the main point of [[ISA vs Microarchitecture]].
## Main building blocks

A microarchitecture is usually described in terms of:

- a **datapath** with ALU, buses, multiplexers, and [[Register|registers]]
- a **control unit** that generates the control signals
- memory interfaces and storage structures
- internal state elements that hold intermediate results
- timing constraints that limit the clock period, as discussed in [[Timing]]

In a classical [[von Neumann Model]] processor, these blocks cooperate to carry instructions through the execution cycle.

### Multi-cycle microarchitecture

In a **multi-cycle** design, an instruction is split across multiple clock cycles.
This allows the processor to reuse hardware blocks in different phases of execution.
See [[Multi-cycle Processor]] for the datapath, control, and comparison with a single-cycle architecture.

### Beyond the basic models

Modern processors often go beyond single-cycle and multi-cycle designs with:

- [[Pipelining|pipelining]]
- superscalar issue
- [[Out-of-order Execution|out-of-order execution]]
- speculation

These are still microarchitectural choices.
As long as the externally visible behavior stays the same, software still sees the same ISA.

## Microarchitecture and execution style

Even if the [[ISA]] exposes a mostly sequential control-flow model, the microarchitecture may still exploit internal parallelism.
In that sense, ideas related to the [[Dataflow Model]] can appear inside the implementation even when the visible machine model is not a pure dataflow machine.

## Example

[[MIPS]] can be implemented by a simple single-cycle core, a multi-cycle controller, or a pipelined processor.


