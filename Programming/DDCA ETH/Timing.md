For Combinational logic, there are two kinds of delays: **propagation delay** and **contamination delay**.

 **propagation delay**: the maximum time from when an input changes until the outputs reach their final value.
**contamination delay**: the minimum time from when an input changes until any output starts to change its value


> [!NOTE] measurement
> We measure delay from the 50% point of the input/output signal. Half-way between LOW and HIGH

![[Pasted image 20260225213951.png|308]]


> [!NOTE] Temperature
> circuits slowing down when hot and speeding up when cold

## Critical paths are slower
![[Pasted image 20260225213546.png|424]]

## Glitches
![[Pasted image 20260225214443.png|322]]
![[Pasted image 20260225214455.png]]

Logically, as $B$ goes from 1 to 0, output $Y$ should not change. However, we can observe a short period of 0 because of the delay of the gates.
Glitches can occur as we transit from a blue circle to another. A way of avoiding this is to add extra hardware to make a glitch proof circuit. However, this still cannot prevent glitches when multiple inputs transit simultaneously. Therefore, our goal is not to eliminate them, but to be aware that they exist.
![[Pasted image 20260225215736.png]]

## Sequential delays

When an FSM signal is **registered** (state bits, registered outputs), it changes *after* the active clock edge.

- **Contamination delay clock-to-q** `t_ccq` (min): earliest time after the clock edge when `Q` may start changing.
- **Propagation delay clock-to-q** `t_pcq` (max): latest time after the clock edge when `Q` is guaranteed stable.

How these appear in basic synchronous timing (ignoring skew/jitter terms):
- **Hold:** `t_ccq(min) + t_cd(comb) >= t_hold`
- **Setup:** `t_pcq(max) + t_pd(comb) + t_setup <= T_clk`

(`t_cd` = min/contamination delay of the combinational path, `t_pd` = max/propagation delay.)



## Ensuring correct sequential operation (R1 -> CL -> R2)

For two edge-triggered registers `R1` (launch) and `R2` (capture) with combinational logic `CL` between them, the input of `R2` (often labeled `D2`) must be **stable** around the capturing clock edge:

- Stable for at least `t_setup` **before** the active clock edge.
- Remain stable for at least `t_hold` **after** the active clock edge.

This creates both a **minimum** and **maximum** allowable delay from `R1.Q` to `R2.D`:

- **CL too fast -> hold violation at R2:** new data reaches `R2.D` too soon after the clock edge, so `R2` may capture the wrong value.
  - Condition (same clock, no skew/jitter): `t_ccq(min) + t_cd(comb) < t_hold`
- **CL too slow -> setup violation at R2:** new data arrives too late before the next clock edge, so `R2` may not capture the intended value.
  - Condition (same clock, no skew/jitter): `t_pcq(max) + t_pd(comb) > T_clk - t_setup`

Rule of thumb: **setup** is usually fixed by making the path faster or slowing the clock; **hold** is fixed by making the *minimum* path delay longer (e.g., added delay/buffers), not by changing `T_clk`.
![[Pasted image 20260306153724.png|459]]
### Overview
![[Pasted image 20260306153838.png]]