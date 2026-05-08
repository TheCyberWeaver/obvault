> [!Definition]
> A **barrier** is a synchronization point where each participating thread waits until **all** participating threads have arrived.

## Core idea

Barriers are useful when a parallel algorithm proceeds in **phases**.

Typical pattern:

1. each thread computes its part of phase 1
2. all threads wait at the barrier
3. only after everyone has arrived may any thread start phase 2

This is needed when later work depends on the fact that the whole group has finished the previous step.

## Example intuition

Suppose multiple threads update different rows of a matrix.

- in phase 1, each thread computes new values for its assigned rows
- before phase 2 starts, all rows must be finished
- the barrier ensures no thread starts reading phase-2 data too early

Without a barrier, one thread could continue with incomplete data produced by other threads.

## Barrier vs other synchronization mechanisms

- a [[Locks|lock]] protects a critical section so only one thread accesses shared state at a time
- [[Wait and Notify|wait/notify]] is used for condition-based signaling between threads
- a barrier coordinates a **whole group** of threads at the same synchronization point

So a barrier is about **collective progress**, not mutual exclusion.

## Java example with `CyclicBarrier`

```java
import java.util.concurrent.*;

int n = 4;
CyclicBarrier barrier = new CyclicBarrier(n);

Runnable worker = () -> {
    try {
        doPhase1Work();
        barrier.await();   // wait until all n workers arrive
        doPhase2Work();
    } catch (InterruptedException | BrokenBarrierException e) {
        throw new RuntimeException(e);
    }
};
```

`barrier.await()` blocks until all registered parties have called it.  
Once the last thread arrives, they are released and can continue.

## Common Java tools

- `CyclicBarrier`: reusable barrier for a fixed number of threads
- `Phaser`: more flexible barrier with multiple phases and dynamic registration

## Failure mode

If one participating thread never reaches the barrier, the others may wait forever.

> [!Important]
> A barrier only works correctly when all participating threads agree on the same phases and all of them eventually reach the barrier.
