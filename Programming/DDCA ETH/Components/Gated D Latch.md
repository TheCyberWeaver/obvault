![[Pasted image 20260226154202.png]]
This guarantee the correct operation of an [[RS-Latch]] 
In this circuit, S and R can never be 0 at the same time!

Q takes the value of D, when write enable (WE) is set to 1

**extremely expensive**: 18 transistors

## <8Bits>
![[Pasted image 20260227132512.png]]

PRE: preset to 1
CLR: clear to 0


## Problem: Transparency

We need to store the data at the beginning of every clock cycle
![[Pasted image 20260227145423.png|338]]
and the data must be available during the **entire clock cycle**
see [[Finite State Machine]]

When we set `EN` to high, the latch is _transparent_: the latch propagates D to Q
![[Pasted image 20260227145959.png]]

We want:
![[Pasted image 20260227150030.png]]

The solution is to use [[D flip flop]]