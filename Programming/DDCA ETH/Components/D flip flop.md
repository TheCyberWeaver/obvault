A D flip flop can be constructed from two [[Gated D Latch]]
the first one is called _master_ and the second one is called _slave_
## <8Bits>
![[Pasted image 20260227133250.png]]

## How the data is actually stored
Ignore `PRE` and `CLR` for the moment and focus only on `D` and `CP`.

### Case 1: `CP = 0`
Because the **master latch** is driven by the **inverted clock**:
- so the **master is enabled**
- the **slave is disabled**
 
**Master latch:** 
It continuously samples `D` and writes that value into its internal bistable storage.
**Slave latch:** 
Since it is disabled, it keeps its previous value unchanged.
#### Clock changes from `0 -> 1`
When the rising edge arrives:
- the **master closes**
- the **slave opens**

**For the master:** 
Its input path is now cut off from `D`, but its internal feedback keeps the last sampled value.
**For the slave:** 
Since it is now enabled, it reads the value currently stored in the master and copies it.
Therefore, `Qout` becomes the value that the master had just locked in

---
### Case 2: `CP = 1`

Now:
- the master is disabled and holds its value
- the slave is enabled

So during the whole `CP = 1` phase:
- the output remains stable
#### Clock changes from `1 -> 0`

When the falling edge arrives:
- the slave closes and keeps the current output
- the master opens and starts tracking the new input `D` again
