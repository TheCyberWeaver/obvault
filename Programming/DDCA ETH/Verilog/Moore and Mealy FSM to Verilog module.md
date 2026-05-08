---
aliases:
  - Moore FSM
  - Mealy FSM
  - FSM to Verilog
---
## What you map from the diagram

An FSM diagram always has the same pieces in hardware:

1) **State [[Register|register]]** (remembers current state)
2) **Next-state logic** (computes `next_state`)
3) **Output logic** (computes outputs)

How you place outputs in the diagram decides where they appear in Verilog:

| Model | Output depends on | Where it appears |
|---|---|---|
| **Moore** | current **state** only | output logic is a function of `state` |
| **Mealy** | **state + inputs** | output logic is a function of `state` and inputs |

Rule of thumb when translating a diagram:
- **Circle (state)** → one `case(state)` branch
- **Arrow (transition)** labeled `cond / out` →
  - `cond` becomes the `if/else` that selects `next_state`
  - for **Mealy**, `out` is assigned inside the same conditional
  - for **Moore**, `out` usually comes from a dedicated output state

---
## Template: Moore FSM (3 always blocks)

```verilog
module fsm_moore (
    input  wire clk,
    input  wire rst_n,
    input  wire in,
    output reg  out
);
    // 1) State encoding
    localparam S0 = 2'd0,
               S1 = 2'd1,
               S2 = 2'd2,
               S3 = 2'd3;

    reg [1:0] state, next_state;

    // 2) State register
    always @(posedge clk or negedge rst_n) begin
        if (!rst_n)
            state <= S0;
        else
            state <= next_state;
    end

    // 3) Next-state logic (combinational)
    always @(*) begin
        next_state = state; // default (avoids latches)
        case (state)
            S0: begin
                if (in) next_state = S1;
            end
            S1: begin
                if (in) next_state = S2;
                else    next_state = S0;
            end
            S2: begin
                if (in) next_state = S2;
                else    next_state = S3; // output state, for example
            end
            S3: begin
                next_state = S0;
            end
            default: next_state = S0;
        endcase
    end

    // 4) Output logic (combinational, depends only on state)
    always @(*) begin
        out = 1'b0; // default
        case (state)
            S3: out = 1'b1; // Moore output asserted in an output state
            default: out = 1'b0;
        endcase
    end
endmodule
```

Notes:
- Moore outputs typically change **only after a clock edge** (because `state` changes on the clock).
- If you want a *registered* output, put `out <= ...` in a clocked `always @(posedge clk ...)` instead.

---
## Template: Mealy FSM (combined next-state + output)

Mealy outputs are usually computed in the same combinational block as `next_state` because both depend on `(state, inputs)`.

```verilog
module fsm_mealy (
    input  wire clk,
    input  wire rst_n,
    input  wire in,
    output reg  out
);
    localparam S0 = 2'd0,
               S1 = 2'd1,
               S2 = 2'd2;

    reg [1:0] state, next_state;

    always @(posedge clk or negedge rst_n) begin
        if (!rst_n)
            state <= S0;
        else
            state <= next_state;
    end

    // next_state + out (combinational)
    always @(*) begin
        next_state = state; // default
        out        = 1'b0;  // default (avoid inferred latches)

        case (state)
            S0: begin
                if (in) next_state = S1;
            end
            S1: begin
                if (in) next_state = S2;
                else    next_state = S0;
            end
            S2: begin
                if (!in) begin
                    // Example: transition condition also drives output (Mealy)
                    out        = 1'b1;
                    next_state = S0;
                end
            end
            default: begin
                next_state = S0;
                out        = 1'b0;
            end
        endcase
    end
endmodule
```

Notes:
- Mealy outputs can change **within the cycle** as inputs change (combinationally). That’s correct by definition, but it can create glitches if `in` is not synchronized.

---
## Concrete example: Sequence detector “101”

This is a common way to see the Moore/Mealy timing difference:
- **Mealy** can assert `z` in the *same* cycle the final `1` arrives.
- **Moore** asserts `z` in the *next* cycle (because it asserts based on the new state).

### Moore “101” (pulse one cycle later)

```verilog
module seq101_moore (
    input  wire clk,
    input  wire rst_n,
    input  wire x,
    output reg  z
);
    localparam IDLE = 2'd0,  // nothing
               S1   = 2'd1,  // saw 1
               S10  = 2'd2,  // saw 10
               S101 = 2'd3;  // saw 101 (output state)

    reg [1:0] state, next_state;

    always @(posedge clk or negedge rst_n) begin
        if (!rst_n) state <= IDLE;
        else        state <= next_state;
    end

    always @(*) begin
        next_state = state;
        case (state)
            IDLE: if (x)  next_state = S1;
            S1:   if (!x) next_state = S10; else next_state = S1;
            S10:  if (x)  next_state = S101; else next_state = IDLE;
            S101: if (x)  next_state = S1; else next_state = S10; // allow overlap
            default: next_state = IDLE;
        endcase
    end

    always @(*) begin
        z = (state == S101);
    end
endmodule
```

### Mealy “101” (pulse immediately)

```verilog
module seq101_mealy (
    input  wire clk,
    input  wire rst_n,
    input  wire x,
    output reg  z
);
    localparam IDLE = 2'd0, // nothing
               S1   = 2'd1, // saw 1
               S10  = 2'd2; // saw 10

    reg [1:0] state, next_state;

    always @(posedge clk or negedge rst_n) begin
        if (!rst_n) state <= IDLE;
        else        state <= next_state;
    end

    always @(*) begin
        next_state = state;
        z          = 1'b0;

        case (state)
            IDLE: begin
                if (x) next_state = S1;
            end
            S1: begin
                if (!x) next_state = S10;
                else    next_state = S1;
            end
            S10: begin
                if (x) begin
                    z          = 1'b1; // Mealy output on transition
                    next_state = S1;   // overlap: last '1' can start a new match
                end else begin
                    next_state = IDLE;
                end
            end
            default: begin
                next_state = IDLE;
                z          = 1'b0;
            end
        endcase
    end
endmodule
```
