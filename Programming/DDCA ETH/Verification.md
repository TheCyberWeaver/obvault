---
aliases:
  - Circuit Verification
---
## Overview

Verification checks whether an implemented circuit matches its specification.

In digital design, this usually means checking the **DUT** (design under test) against expected behavior over many inputs, states, and timing situations.

Verification is different from validation:

- **verification**: did we build the circuit right?
- **validation**: did we build the right circuit for the intended use?

## Manual verification

Manual verification means reasoning about the circuit by hand.

Typical techniques:

- derive a truth table for a small combinational circuit
- simplify and check Boolean expressions
- trace signals through gates for selected input cases
- inspect the state transitions and outputs of an [[Finite State Machine|FSM]]
- reason about setup/hold constraints and delays using [[Timing]]
### Limits of manual verification

- does not scale well for large circuits
- easy to miss corner cases
- sequential circuits are harder because behavior depends on history and clock cycles
- timing-related bugs are often difficult to catch by hand alone

For a combinational circuit with few inputs, manual exhaustive checking may be possible. For larger designs, this quickly becomes impractical.

## Automatic verification

Automatic verification uses tools and scripts to check the circuit behavior.

## Simulation with a testbench

A common approach is to write a testbench in [[Introduction to Verilog|Verilog]] using `initial` and `always` constructs (see also [[Always block]]).

The testbench:

- drives inputs into the DUT
- waits for outputs to settle or for clock edges
- compares actual outputs with expected outputs
- reports mismatches automatically

Two common styles:

- **directed tests**: manually chosen cases such as zero, all-ones, overflow, reset, illegal state transitions
- **random tests**: many automatically generated inputs to explore more of the state space

## Self-checking verification

A waveform-only testbench is useful, but a **self-checking testbench** is better.

Instead of only looking at outputs manually, the testbench computes the expected result and checks it automatically:

```verilog
if (dut_y !== expected_y) begin
    $error("Mismatch: got %b expected %b", dut_y, expected_y);
end
```

This scales much better than manual waveform inspection.

## Assertions

Assertions state properties that must always hold.

Examples:

- output must never become `x` after reset
- a request must eventually be followed by an acknowledge
- an FSM must never enter an illegal state

Assertions are useful because they check design intent directly instead of only checking a few example outputs.

## Formal and equivalence checking

Other automatic verification methods include:

- **formal verification**: mathematically proves certain properties without trying input vectors one by one
- **equivalence checking**: checks whether two descriptions implement the same function, for example RTL vs synthesized netlist

Simulation can show the presence of bugs, but it cannot prove the absence of all bugs. Formal methods are stronger, but also more expensive and more specialized.

## Golden model

A **golden model** is a simple and trusted reference description of the intended behavior.

The DUT is compared against the golden model on the same inputs.

The golden model is often:

- higher-level than the RTL
- easier to understand than the real implementation
- written for correctness first, not hardware efficiency

Possible forms of a golden model:

- a mathematical formula
- a behavioral Verilog model
- a Python or C reference implementation
- a state-transition reference for a sequential system
## Example: adder verification

For a 4-bit [[Adder]], a simple golden model can be:

```verilog
expected = a + b + cin;
```

Then compare the DUT result `{cout, sum}` with `expected`.

Useful directed cases:

- `0 + 0`
- maximum input values
- cases with carry-in
- cases that generate overflow/carry-out

For a small adder, exhaustive testing is possible. For larger arithmetic units, random and property-based checking become more important.

## Manual vs automatic verification

| Method | Strength | Weakness |
| --- | --- | --- |
| Manual verification | simple, intuitive, good for understanding | does not scale, easy to miss cases |
| Automatic simulation | practical, repeatable, good debugging support | only covers tested scenarios |
| Formal/equivalence | strongest guarantees for specific properties | more complex and tool-dependent |

> [!note]
> A passing simulation does **not** prove the circuit is correct for every possible case. It only shows that the tested cases passed.
