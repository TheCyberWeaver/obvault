> [!Definition]
> **Latency** is the time needed for one job to finish.
> **Throughput** is the number of jobs completed per unit time.

$$
\text{Throughput} = \frac{\text{number of completed jobs}}{\text{total time}}.
$$
## Pipeline example

In a processor [[Pipelining|pipeline]], many instructions overlap in execution.
Because of this, throughput increases: after the pipeline is full, ideally one instruction finishes per cycle.
But the latency of one instruction is still about the time needed to pass through all stages.