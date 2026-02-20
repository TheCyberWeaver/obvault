CMOS=pMOS+nMOS
## nMOS

![[Pasted image 20260220135601.png|473]]
good at passing logic 0
- gate=0: OFF 
- gate=1: ON //good at passing 0 (pass GND)
## pMOS
good at passing logic 1
- gate=0: ON  //good at passing 1 (pass $V_{DD}$)
- gate=1: OFF 

## Inverting logic
![[Pasted image 20260220135949.png|237]]
always use pMOS for pull-up
always use nMOS for pull-down

> [!Warning]
> exactly one network should be ON, and the other network should be OFF at any given time

Example: NOT
![[Pasted image 20260220140004.png|218]]
## Efficiency
NAND and NOR gates are more efficient than using AND and OR, since AND is built with NAND+NOT



