MIPS is one concrete [[ISA]] used by MIPS processors.

MIPS is a classic **RISC** architecture, which means the instructions are designed to be simple and regular.

Different [[Microarchitecture|microarchitectures]] can implement the same MIPS ISA while preserving the same programmer-visible behavior.

## Registers

MIPS has 32 general-purpose registers.

Some common ones are:

- `$zero`: always contains `0`
- `$t0-$t9`: temporary registers
- `$s0-$s7`: saved registers
- `$sp`: stack pointer
- `$ra`: return address

## Load/store architecture

MIPS is a **load/store** architecture:

- arithmetic instructions work only on registers
- memory is accessed only with load and store instructions

Examples:

- `lw`: load word from memory into a register
- `sw`: store word from a register into memory

## Instruction formats

MIPS instructions are usually 32 bits long.

There are 3 important formats:

### R-type
Used for register-register operations such as:

- `add`: adds the values in two registers and stores the result in a register
- `sub`: subtracts one register value from another and stores the result in a register
- `and`: performs a bitwise AND on two register values
- `or`: performs a bitwise OR on two register values

### I-type
Used for immediate values and memory access such as:

- `addi`: adds a constant immediate value to a register
- `lw`: loads a 32-bit word from memory into a register
- `sw`: stores a 32-bit word from a register into memory
- `beq`: branches if the values in two registers are equal

### J-type
Used for jumps:

- `j`: jumps unconditionally to a target address
- `jal`: jumps to a target address and saves the return address in `$ra`

## Example instructions

```asm
add $t0, $t1, $t2
lw  $t0, 0($sp)
sw  $t1, 4($sp)
beq $t0, $t1, label
j   target
```

- `add $t0, $t1, $t2`: computes `$t1 + $t2` and stores the result in `$t0`
- `lw $t0, 0($sp)`: loads the word at address `$sp + 0` into `$t0`
- `sw $t1, 4($sp)`: stores the value in `$t1` at address `$sp + 4`
- `beq $t0, $t1, label`: jumps to `label` if `$t0` and `$t1` are equal
- `j target`: jumps directly to `target`

## Registers
![[Pasted image 20260320135608.png|558]]