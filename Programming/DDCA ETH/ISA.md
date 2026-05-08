---
aliases:
  - Instruction Set Architecture
---
## Overview

An **instruction set architecture (ISA)** is the programmer-visible contract between software and hardware.

If two processors implement the same ISA correctly, the same machine code should run on both even if their internal circuits are very different.

## What belongs to the ISA

- the instruction set and opcodes
- the register set and other programmer-visible state
- the supported data types
- the available addressing modes
- the memory organization visible to software
- the meaning of control-flow instructions

This is why LC-3 and [[MIPS]] are both examples of an ISA, not examples of a particular hardware implementation.

## The instruction set as the core of the ISA

The instruction set defines three especially important things:

- **opcodes**: which operations exist
- **data types**: which kinds of values can be manipulated
- **addressing modes**: how operands are found in registers or memory

These choices strongly affect compiler design, code density, and hardware complexity.

## ISA trade-offs

### Instructions / opcodes

- more complex instructions can do more work per instruction and may reduce code size
- simpler instructions are easier to decode, control, and optimize in hardware

This is one of the classic trade-offs behind RISC vs. more complex instruction sets.

### Data types

- more data types map more directly to high-level languages
- fewer data types simplify hardware, but software may need extra instructions or emulation

### Addressing modes

- more addressing modes can make memory access more expressive and compact
- fewer addressing modes simplify decode logic and usually fit a cleaner load/store design

For example, LC-3 uses several addressing modes, while [[MIPS]] keeps a simpler load/store style.

## Semantic gap

The **semantic gap** is the distance between high-level programming languages and the ISA.

A smaller semantic gap usually means the ISA provides more complex instructions or richer data types, so software maps more directly onto the machine.
A larger semantic gap usually means a simpler ISA, so compilers do more work while hardware can stay simpler.
