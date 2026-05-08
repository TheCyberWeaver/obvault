---
aliases:
  - Verilog Assignment Types
tags:
  - programming
  - verilog
---
## Non-Blocking and Blocking Assignments

In Verilog procedural blocks (`always`), there are two assignment operators:

- Blocking assignment: `=`
- Non-blocking assignment: `<=`

Using the right one is important for correct hardware behavior.

## Blocking Assignment (`=`)

- Executes in order, line by line, inside the same `always` block.
- The left-hand side updates immediately for following statements in that block.
- Commonly used for combinational logic (`always @(*)`).

```verilog
always @(*) begin
    y = a & b;
    z = y | c;   // uses updated y immediately
end
```

## Non-Blocking Assignment (`<=`)

- Schedules updates to happen at the end of the current time step.
- Right-hand sides are evaluated first, then all left-hand sides update together.
- Commonly used for sequential (clocked) logic (`always @(posedge clk)`).

```verilog
always @(posedge clk) begin
    q1 <= d;
    q2 <= q1;    // q2 gets old q1 (register behavior)
end
```

## Why This Matters

If you use blocking assignment in clocked logic, simulation can behave differently from intended register hardware.

```verilog
always @(posedge clk) begin
    q1 = d;
    q2 = q1;     // q2 now gets d immediately in simulation
end
```

This does not model two cascaded flip-flops correctly.

## Rule of Thumb

- Use `=` in combinational `always @(*)` blocks.
- Use `<=` in clocked `always @(posedge clk)` / `always @(negedge clk)` blocks.
- Avoid mixing `=` and `<=` in the same block unless you have a very specific reason.

See also [[Always block]].
