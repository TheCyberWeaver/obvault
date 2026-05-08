---
aliases:
  - Verilog Number Literals
---
## Number Representation in Verilog

Verilog numbers are usually written as:

`N'Bvalue`

- `N`: number of bits (width)
- `B`: base
	- `b` binary
	- `h` hexadecimal
	- `d` decimal
	- `o` octal
- `value`: digits in that base

## Key Rules

- Width `N` controls storage size (zero-fill or truncation can happen to match width).
- You can use `x` (unknown/invalid) and `z` (high-impedance/floating) in literals.
- `_` is allowed inside numbers for readability.

## Examples

```verilog
4'b1001        // 4-bit binary: 1001
8'b1001        // stored as 0000_1001
8'b0000_1001   // same value, clearer formatting
8'bxX0X1zZ1    // includes x and z states

4'd5           // 0101
12'hFA3        // 1111_1010_0011
8'o12          // 000_001_010
4'h7           // 0111
12'h0          // 0000_0000_0000
```
Upper/lowercase does not change meaning.
## Unsized Literal

```verilog
'b01
```

This is an unsized literal. In many Verilog contexts it is treated as a default integer width (commonly 32 bits), so explicit sizing like `2'b01` is usually safer.