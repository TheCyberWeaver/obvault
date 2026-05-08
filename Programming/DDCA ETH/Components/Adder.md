## sequential: ripple carry adder
An ordinary cluster of 4 full-adders
![[Pasted image 20260227134842.png|595]]
However, this is too slow when we try to build larger circuits, because we must calculate bit by bit.
## <8Bits>
![[Pasted image 20260227134653.png]]
## parallel: carry-lookahead Adder
In reality we prefer to to build 32-bits adder with a sequence of 4bits carry-lookahead adders (CLA)
![[Pasted image 20260227135046.png]]


## Example: ripple carry adder AND CLA delay 
Compare the delays of a 32-bit ripple-carry adder and a 32-bit carry-lookahead adder with 4-bit blocks. Assume that each two-input gate delay is 100 ps and that a full adder delay is 300 ps. 

**Solution**: The propagation delay of the 32-bit ripplecarry adder is 32 × 300 ps = 9.6 ns. 
![[Pasted image 20260227141015.png]]
The CLA has tpg = 100 ps, tpg_block = 6 × 100 ps = 600 ps, and tAND_OR = 2 × 100 ps = 200 ps. According to Equation 5.6, the propagation delay of the 32-bit carry-lookahead adder with 4-bit blocks is thus 100 ps + 600 ps + (32/4 − 1) × 200 ps + (4 × 300 ps) = 3.3 ns, almost three times faster than the ripple-carry adder