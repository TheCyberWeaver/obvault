> [!Definition]
> **Peterson's algorithm** is a simple software-only algorithm for **mutual exclusion** between two threads.

## Core idea

- Thread `i` sets `flag[i] = true` and then sets `turn = other`.
- It waits while `flag[other] && turn == other`.
- If both threads compete at the same time, the `turn` variable decides who waits.

## Properties

- It guarantees mutual exclusion, progress, and bounded waiting for **two** threads under sequential consistency.
- It is simpler and cleaner than [[Dekker‘s algorithm]], but today it is mostly of theoretical interest.

## Entry and exit protocol

For thread `i` with `other = 1 - i`:

- **entry**:
  - set `flag[i] = true`
  - set `turn = other`
  - wait while `flag[other] && turn == other`
- **exit**:
  - set `flag[i] = false`

If both threads want to enter at the same time, both raise their flags, but the last write to `turn` gives priority to one thread and forces the other to wait.

## Java example

```java
public final class PetersonLock {
    private final boolean[] flag = new boolean[2];
    private volatile int turn;

    public void lock(int i) {
        int other = 1 - i;
        flag[i] = true;
        turn = other;

        while (flag[other] && turn == other) {
            Thread.onSpinWait();
        }
    }

    public void unlock(int i) {
        flag[i] = false;
    }
}
```

Usage:

```java
PetersonLock lock = new PetersonLock();

// thread 0
lock.lock(0);
try {
    // critical section
} finally {
    lock.unlock(0);
}

// thread 1
lock.lock(1);
try {
    // critical section
} finally {
    lock.unlock(1);
}
```

## Extension to n threads: Filter lock

One extension of Peterson's idea to `n` threads is the **filter lock**.

- Threads pass through levels `1,2,...,n-1`
- at each level, one thread is marked as the `victim`
- a thread waits if it is still the victim and some other thread is at the same or a higher level

```java
import java.util.concurrent.atomic.AtomicIntegerArray;
class FilterLock {
	AtomicIntegerArray level;
	AtomicIntegerArray victim;
	volatile int n;
	
	FilterLock(int n) {
		this.n = n;
		level = new AtomicIntegerArray(n);
		victim = new AtomicIntegerArray(n);
	}
	// ∃k ≠ me: level[k] >= i (lev)
	boolean Others(int me, int lev) {
	    for (int k = 0; k < n; ++k)
	        if (k != me && level.get(k) >= lev) return true;
	    return false;
	}
	
	public void Acquire(int me) {
	    for (int lev = 1; lev < n; ++lev) {
	        level.set(me, lev);
	        victim.set(lev, me);
	        while (me == victim.get(lev) && Others(me, lev));
	    }
	}
	
	public void Release(int me) {
	    level.set(me, 0);
	}
}
```

> [!Important]
> Filter lock extends Peterson's algorithm from `2` threads to `n` threads.
