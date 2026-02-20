
## a object’s intrinsic monitor lock

```java
public synchronized void f() { ... }   // locks on this
```
OR equivalently
```java
public void f() {
  synchronized (this) { ... }          // locks on this
}
```

Both acquire the same lock: the monitor associated with the current instance (`this`). Only one thread can hold it at a time; other threads trying to enter any `synchronized(this)` block or any `synchronized` instance method on the same object will block.


## Private Lock
```java
public class PrivateLock {
    private final Object myLock = new Object(); // The lock
    @GuardedBy("myLock")
    Widget widget;
    void someMethod() {
        synchronized (myLock) {
            // Access or modify the state of widget
        }
    }
}
```

