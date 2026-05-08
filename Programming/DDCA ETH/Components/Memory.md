---
tags:
  - linker-exclude
---
can be implemented from multiple [[Register]]

**Addressability**: the number of bits of information stored in each location.
The entire set of unique locations in memory is referred to as the _address space_


## Reading
Use address decode to select the memory cell
![[Pasted image 20260226154751.png|542]]

If `Addr[0]` is zero, we read from the top three registers
If `Addr[0]` is one, we read from the bottom three registers


## Writing

![[Pasted image 20260226155035.png|577]]

## Example: Expandable
![[Pasted image 20260226155115.png|464]]

## Types of memory
- [[DRAM]]
- [[SRAM]]