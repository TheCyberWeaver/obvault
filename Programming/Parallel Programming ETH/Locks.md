## a object’s intrinsic monitor lock

```java
public synchronized void f() { ... } // locks on this
```
OR equivalently
```java
public void f() {
 synchronized (this) { ... } // locks on this
}
```

Both acquire the same lock: the monitor associated with the current instance (`this`). Only one thread can hold it at a time; other threads trying to enter any `synchronized(this)` block or any `synchronized` instance method on the same object will block.


> [!Important] 
> Locks are specific to objects. Every object has a lock.

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

## Read/write lock

The **reader/writer lock** is a synchronization abstraction with three possible states:
- **not held**
- **held for writing** by exactly one thread
- **held for reading** by one or more threads

The essential constraints are:
- `0 <= writers <= 1`
- `0 <= readers`
- `writers * readers == 0`

### Operations
- `acquire_write()`: block while the lock is held for reading or writing; otherwise enter as writer
- `release_write()`: leave the write-critical section
- `acquire_read()`: block while the lock is held for writing; otherwise enter as reader
- `release_read()`: leave the read-critical section; if the last reader leaves, the lock becomes free

```java title:"Example use"
class Hashtable<K,V> {
    RWLock lk = new RWLock();

    void insert(K key, V val) {
        int bucket = hashval(key);
        lk.acquire_write();
        try {
            // write val to array[bucket]
        } finally {
            lk.release_write();
        }
    }

    V lookup(K key) {
        int bucket = hashval(key);
        lk.acquire_read();
        try {
            // read array[bucket]
            return null;
        } finally {
            lk.release_read();
        }
    }
}
```

### Simple monitor-based implementation

```java title:Example
class RWLock {
    int writers = 0;
    int readers = 0;

    synchronized void acquire_write() {
        while (writers > 0 || readers > 0) {
            try { wait(); }
            catch (InterruptedException e) {}
        }
        writers++;
    }

    synchronized void acquire_read() {
        while (writers > 0) {
            try { wait(); }
            catch (InterruptedException e) {}
        }
        readers++;
    }

    synchronized void release_read() {
        readers--;
        notifyAll();
    }

    synchronized void release_write() {
        writers--;
        notifyAll();
    }
}
```

This implementation is **not fair**. It gives priority to readers:

- while readers are active, more readers may continue to enter
- a waiting writer cannot proceed until all readers have finished
- newly arriving readers may keep delaying that writer

So writers can starve.
### A fairer model
A fairer idea is:
- when a writer finishes, let the readers that are **already waiting** pass
- after those readers have passed, allow the next writer in
- readers arriving later should not indefinitely cut ahead of waiting writers

```java title:Example
class RWLock {
    int writers = 0;
    int readers = 0;
    int writersWaiting = 0;
    int readersWaiting = 0;
    int writersWait = 0;

    synchronized void acquire_read() {
        readersWaiting++;
        while (writers > 0 || (writersWaiting > 0 && writersWait <= 0)) {
            try { wait(); }
            catch (InterruptedException e) {}
        }
        readersWaiting--;
        writersWait--;
        readers++;
    }

    synchronized void release_read() {
        readers--;
        notifyAll();
    }

    synchronized void acquire_write() {
        writersWaiting++;
        while (writers > 0 || readers > 0 || writersWait > 0) {
            try { wait(); }
            catch (InterruptedException e) {}
        }
        writersWaiting--;
        writers++;
    }

    synchronized void release_write() {
        writers--;
        writersWait = readersWaiting;
        notifyAll();
    }
}
```

Here, `writersWait` counts how many currently waiting readers are allowed to pass before a waiting writer may enter.

This is only **fairer**, not perfect FIFO fairness. A common refinement is to introduce an upper bound `k`, so that after a writer finishes, at most `k` readers may pass before the next writer gets a chance.

### In Java

Java's `synchronized` does not directly support reader/writer locking. Instead, Java provides:
`{java icon} import java.util.concurrent.locks.ReentrantReadWriteLock; 

Its interface is different from `synchronized`:
- `readLock()` returns a lock object for readejrs
- `writeLock()` returns a lock object for writers
- those objects use `lock()` and `unlock()`

```java title:Example
import java.util.concurrent.locks.ReentrantReadWriteLock;

ReentrantReadWriteLock rw = new ReentrantReadWriteLock();

rw.readLock().lock();
try {
    readSharedState();
} finally {
    rw.readLock().unlock();
}

rw.writeLock().lock();
try {
    updateSharedState();
} finally {
    rw.writeLock().unlock();
}
```

> [!Warning]
> This library lock should not be thought of as "writer-priority", and it does not support reader-to-writer upgrading.


