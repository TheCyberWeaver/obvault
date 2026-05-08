---
aliases:
  - Java Memory Model
---
> [!Definition]
> The **Java Memory Model (JMM)** defines which executions and outcomes are legal for a Java program with multiple threads.

Without synchronization, Java does **not** guarantee that other threads observe writes in source-code order. The outcome is not literally "anything", but it can still be very surprising.

## Why JMM matters

- It gives a formal meaning to `volatile`, `synchronized`, thread `start()`, and `join()`.
- It explains **visibility** and **ordering** between threads.
- It still allows **data races**: a racy read may observe a write that is not the latest one in wall-clock time.

## Actions and executions

The JMM models a run as **actions** plus ordering relations between them.

Examples of actions:
- `read(x): 1` means "read variable `x`, and the value observed is `1`"
- `write(x): 1`
- volatile read / volatile write
- monitor lock / unlock

Example:

```java
int x = 0;

// Thread 1
x = 1;

// Thread 2
int r = x;
```

One possible execution contains:
- `write(x): 1`
- `read(x): 1`

Another legal execution may contain:
- `write(x): 1`
- `read(x): 0`

if there is no synchronization between the threads.

## Program Order (PO)

**Program order** is the total order of actions **inside one thread**.

```java
// Thread 1
x = 1;
y = 1;
```

Within Thread 1, `write(x)` is before `write(y)` in **program order**.

But PO says nothing about other threads:

```java
// Thread 1
x = 1;
y = 1;

// Thread 2
int r1 = y;
int r2 = x;
```

Thread 2 may still see `r1 == 1` and `r2 == 0`, because PO is only intra-thread. It links executions back to the original code, but it does **not** by itself guarantee cross-thread visibility.

## Synchronization Actions (SA) and Synchronization Order (SO)

Some actions are special: they participate in synchronization.

Synchronization actions include:
- read/write of a `volatile` variable
- `lock` / `unlock` of a monitor
- first and last action of a thread (synthetic)
- actions that start a thread
- actions that detect thread termination, such as `join()`

These actions form the **synchronization order (SO)**:
- SO is a **total order**
- all threads agree on that order
- synchronization actions inside one thread remain in PO order

Example with `volatile`:

```java
volatile int v = 0;

// Thread 1
v = 1;

// Thread 2
int r = v;
```

The volatile write and volatile read are synchronization actions. The JMM places them in the single global synchronization order.

## Synchronizes-With (SW)

**Synchronizes-with** connects specific synchronization actions that "see" each other.

Important cases:
- a `volatile` write synchronizes-with a later `volatile` read of the same variable
- a monitor `unlock` synchronizes-with a later `lock` of the same monitor
- `Thread.start()` synchronizes-with the started thread's first action
- a thread's last action synchronizes-with another thread successfully returning from `join()`

Example with `volatile`:

```java
int data = 0;
volatile boolean ready = false;

// Thread 1
data = 42;
ready = true;

// Thread 2
if (ready) {
    int r = data;   // guaranteed to see 42
}
```

Why? The write `ready = true` synchronizes-with the read that sees `ready == true`. That makes the earlier write to `data` visible as well.

## Happens-Before (HB)

The most useful relation is **happens-before**.

- PO edges are part of HB
- SW edges are part of HB
- HB is the transitive closure of PO and SW

So if:
- `A` is before `B` in program order, and
- `B` synchronizes-with `C`

then `A` happens-before `C`.

Example with `synchronized`:

```java
int value = 0;
final Object lock = new Object();

// Thread 1
synchronized (lock) {
    value = 7;
}

// Thread 2
synchronized (lock) {
    int r = value;  // guaranteed to see 7
}
```

The unlock in Thread 1 synchronizes-with the later lock in Thread 2, so the write `value = 7` happens-before the read.

## HB consistency

When a thread reads a variable, it may see:
- the **last write ordered before it by HB**, or
- another write that is **not ordered** with it

This is why Java still allows races.

Example:

```java
int x = 0;

// Thread 1
x = 1;

// Thread 2
x = 2;

// Thread 3
int r = x;
```

If there is no HB relation, `r` may legally become `0`, `1`, or `2`.

> [!Warning]
> If two conflicting accesses are not ordered by happens-before, you have a **data race**. The program is still defined by the JMM, but the result may be unexpected.

## Minimal rules to remember

- **PO**: order inside one thread only
- **SO**: one global order for synchronization actions
- **SW**: specific synchronization edges, such as volatile-write to volatile-read
- **HB**: the order that actually matters for visibility

## Practical takeaway

- Use `volatile` for simple visibility flags (see [[Sharing Objects#Volatile|Volatile]])
- Use `synchronized` or locks for compound state changes (see [[Locks]])
- Use `start()` / `join()` as real synchronization edges
- If there is no happens-before relation, assume reads may see stale values
