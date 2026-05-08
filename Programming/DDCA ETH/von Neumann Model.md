## Overview

The **von Neumann model** is the classical stored-program model of a computer.
Instructions and data are kept in memory, and the processor executes them in a mostly _sequential_ **fetch-decode-execute** style.

In a von Neumann machine:

- the program counter selects the next instruction
- instructions are fetched from memory
- data is moved between memory and registers
- the control unit and datapath carry out each step of execution

## Cycle

- **Fetch**: read the next instruction from memory using the program counter
- **Decode**: identify the operation and operand locations
- **Evaluate address**: compute the effective address if memory is needed
- **Fetch operands**: read the required register or memory values
- **Execute**: perform the ALU operation or branch decision
- **Store result**: write the result back to a register or memory

It is a useful contrast to the [[Dataflow Model]], where execution is driven more directly by data dependencies instead of a mainly sequential instruction stream.

One well-known limitation is the **von Neumann bottleneck**: instructions and data compete for memory bandwidth, which can restrict performance.
