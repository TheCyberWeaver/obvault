
## What `wait()` really does

Inside `synchronized (lock)`, calling `lock.wait()`:

1. Releases the monitor of `lock`.
2. Puts the current thread into waiting state.
3. Later, after `notify()` / `notifyAll()` (or interrupt/timeout), the thread must re-acquire the same lock.
4. Execution continues right after `wait()`.

So it is not a real "jump out of the synchronized block".  
It is: pause at `wait()`, temporarily give up the lock, then continue after re-locking.

```java
synchronized (lock) {
    System.out.println("before wait");
    lock.wait();
    System.out.println("after wait");
}
```

## What `notify()` / `notifyAll()` really do

Inside `synchronized (lock)`, calling `lock.notify()` or `lock.notifyAll()`:

1. **Does not release the lock immediately.**
2. Marks one (arbitrary) waiting thread (`notify`) or all waiting threads (`notifyAll`) on `lock` as candidates to wake up.
3. Those awakened threads **cannot continue immediately**, because the current thread still owns the monitor.
4. Only after the current thread exits the `synchronized` block (or otherwise releases the monitor), can a woken thread compete to re-acquire the same lock.
5. After re-acquiring the lock, the awakened thread continues from right after its `wait()` call.


## Why `wait()` must be in `while`, not `if`

`wait()` returning does **not** guarantee the condition is true.  
A wake-up can happen because of:

- spurious wakeups
- `notifyAll()` waking multiple threads
- state changes by another thread before this thread re-acquires the lock

Correct pattern:

```java
synchronized (lock) {
    while (!condition) {
        lock.wait();
    }
    // safe: condition is true here
}
```

Not safe:

```java
synchronized (lock) {
    if (!condition) {
        lock.wait();
    }
    // condition may be false again
}
```

## Contrast with `sleep()`

- `wait()`: releases the lock.
- `sleep()`: does not release the lock.
