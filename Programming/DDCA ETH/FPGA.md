## Overview
![[Pasted image 20260227155937.png]]
**Switch** (S) Box: Connect horizontal and vertical wires
**Connection** (C) Box: Connect neighboring LUTs to each other and to the vertical wires
**[[LUT]]** (L): Look up table (implement functions), Typically use LUTs with 6-bit select input
- MegaBytes of distributed on-chip memory
![[Pasted image 20260227160132.png|214]]
There is general-purpose processor embedded within the FPGA chip


## Disadvantages

- Not as fast and power efficient as dedicated hardware customized for an algorithm
- Reconfigurability comes at a cost: significant area and latency overhead

## Design Flow
![[Pasted image 20260227160518.png]]

- Vivado (CAD)