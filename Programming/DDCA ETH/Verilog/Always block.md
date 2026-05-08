---
aliases:
  - always block
  - Verilog always
tags:
  - programming
  - verilog
---

## Always block

An `always` block is a procedural block that runs whenever its sensitivity condition is triggered.
It is used to describe either combinational logic or sequential (clocked) logic.

## General form

```verilog
always @(sensitivity_list) begin
    // procedural statements
end
```

In SystemVerilog, prefer:

- `always_comb` for combinational logic
- `always_ff` for flip-flop logic

## Combinational `always`

Use `always @(*)` (or `always_comb`) so the block reevaluates when any input changes.

```verilog
always @(*) begin
    y = (a & b) | c;
end
```

Guidelines:

- Include default assignments to avoid inferred latches.
- Use blocking assignment `=` in combinational blocks.

## Sequential (clocked) `always`

Use edge-triggered sensitivity for registers.

```verilog
always @(posedge clk) begin
    q <= d;
end
```

With asynchronous reset:

```verilog
always @(posedge clk or posedge rst) begin
    if (rst)
        q <= 1'b0;
    else
        q <= d;
end
```

Guidelines:

- Use non-blocking assignment `<=` in clocked blocks.
- Keep one clock domain per block.

## Typical pitfalls

- Missing signals in a manual sensitivity list (`always @(a or b)`) can cause simulation/synthesis mismatch.
- Missing `else`/default branches in combinational blocks can infer latches unintentionally.
- Mixing blocking and non-blocking assignments in the same sequential block is error-prone.

## Rule of thumb

- Combinational logic: `always @(*)` + `=`
- Sequential logic: `always @(posedge/negedge clk)` + `<=`

See also [[Non-Blocking and Blocking Assignments]].
