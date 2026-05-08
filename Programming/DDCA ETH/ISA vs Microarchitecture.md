## Overview

[[ISA]] and [[Microarchitecture]] describe two different levels of a processor.

The [[ISA]] is the interface visible to software.
The [[Microarchitecture]] is the internal hardware organization that implements that interface.

## Core difference

| Question                                    | [[ISA]]                  | [[Microarchitecture]]         |
| ------------------------------------------- | ------------------------ | ----------------------------- |
| What does it describe?                      | What the machine must do | How the hardware does it      |
| Visible to programmers?                     | Yes                      | Mostly no                     |
| Determines binary compatibility?            | Yes                      | No, if the ISA stays the same |
| Strongest effect on performance/power/area? | Indirectly               | Directly                      |

## What software sees
Software can rely on ISA-level facts such as:

- which instructions exist
- what registers are available
- which data types are supported
- how addressing modes work
- what result an instruction must produce

## What hardware designers choose
Hardware designers choose how to realize the ISA in circuits:

- how many cycles instructions take
- how the control unit is organized
- whether hardware units are reused or duplicated
- how long the critical path is
- how much parallelism is exploited internally

