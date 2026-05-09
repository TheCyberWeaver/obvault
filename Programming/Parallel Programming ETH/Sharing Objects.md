> [!Warning]
> In general, there is no guarantee that the reading thread will see a value written by another thread on a timely basis, or even at all. In order to ensure visibility of memory writes across threads, you must use synchronization.

**Visibility**: whether a write by one thread becomes observable to other threads (i.e., other threads read the latest value rather than a stale cached one).

**Atomicity**: whether an operation happens as one indivisible step from the perspective of other threads (i.e., it cannot be interleaved with other threads’ actions, so you don’t see partial results or lose updates).

### Example
```java title:"consequence of reordering"
public class NoVisibility {

 private static boolean ready;
 private static int number;

 private static class ReaderThread extends Thread {

 public void run() {
 while (!ready)
 Thread.yield();

 System.out.println(number);
 }
 }

 public static void main(String[] args) {
 new ReaderThread().start();
 number = 42;
 ready = true;
 }
}

```

This code might loop forever or output 0.
There is no guarantee that operations in one thread will be performed in the order given by the program


## Volatile
```java
volatile boolean asleep; 
... 
while (!asleep) 
	countSomeSheep();
```


> [!Warning]
> Locking can guarantee both visibility and atomicity; volatile variables can only guarantee visibility.

You can use `volatile` variables only when **all** the following criteria are met:
- Writes to the variable do not depend on its current value, **or** you can ensure that only a single thread ever updates the value.
- The variable does not participate in invariants with other state variables.
- Locking is not required for any other reason while the variable is being accessed.

## Safe publication
To publish an object safely, both the reference to the object and the object's state must be made visible to other threads at the same time.

A properly constructed object can be safely published by:
- Initializing an object reference from a static initializer;
	- `public static Holder holder = new Holder(42);`
	- Static initializers are executed by the [[JVM]] at class initialization time; because of internal synchronization in the JVM, this mechanism is guaranteed to safely publish any objects initialized in this way
- Storing a reference to it into a `volatile` field or `AtomicReference`;
- Storing a reference to it into a `final` field of a properly constructed object; or
	- see [[#Shared thread-safe]]
- Storing a reference to it into a field that is properly guarded by a lock.

Otherwise, this code can throw `AssertionError`
```java title:"Pure Craziness"
public class Holder {
 private int n;
 public Holder(int n) {this.n = n;}
 public void assertSanity() {
 if (n != n)
 throw new AssertionError("This statement is false.");
 }
}
// Unsafe publication
...
public Holder holder;
public void initialize() {
 holder = new Holder(42);
}
```

- Placing a key or value in a `Hashtable`, `synchronizedMap`, or `ConcurrentMap` safely publishes it to any thread that retrieves it from the map (whether directly or via an iterator);

- Placing an element in a `Vector`, `CopyOnWriteArrayList`, `CopyOnWriteArraySet`, `synchronizedList`, or `synchronizedSet` safely publishes it to any thread that retrieves it from the collection;

- Placing an element on a `BlockingQueue` or a `ConcurrentLinkedQueue` safely publishes it to any thread that retrieves it from the queue.

### Shared thread-safe
```java 
@Immutable
class OneValueCache {

 private final BigInteger lastNumber;
 private final BigInteger[] lastFactors;

 public OneValueCache(BigInteger i, BigInteger[] factors) {
 lastNumber = i;
 lastFactors = Arrays.copyOf(factors, factors.length);
 }

 public BigInteger[] getFactors(BigInteger i) {
 if (lastNumber == null || !lastNumber.equals(i)) {
 return null;
 } else {
 return Arrays.copyOf(lastFactors, lastFactors.length);
 }
 }
}
```
When a thread sets the volatile cache field to reference a new OneValueCache, the new cached data becomes immediately visible to other threads

## Rules for using and sharing objects
The most useful policies for using and sharing objects in a concurrent program are: 
**Thread‐confined**. A thread‐confined object is owned exclusively by and confined to one thread, and can be modified by its owning thread. 
**Shared read‐only**. A shared read‐only object can be accessed concurrently by multiple threads without additional synchronization, but cannot be modified by any thread. Shared read‐only objects include immutable and effectively immutable objects. 
**Shared thread‐safe**. A thread‐safe object performs synchronization internally, so multiple threads can freely access it through its public interface without further synchronization. 
**Guarded**. A guarded object can be accessed only with a specific lock held. Guarded objects include those that are encapsulated within other thread‐safe objects and published objects that are known to be guarded by a specific lock.