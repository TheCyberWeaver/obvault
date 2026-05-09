> [!Definition]
> A class is **thread‐safe** if it behaves correctly when _accessed from multiple threads_, regardless of the scheduling or interleaving of the execution of those threads by the runtime environment, and with no additional synchronization or other coordination on the part of the calling code.


```java title:"A Stateless Servlet"
@ThreadSafe 
public class StatelessFactorizer implements Servlet { 
	public void service(ServletRequest req, ServletResponse resp) { 
 BigInteger i = extractFromRequest(req); 
 BigInteger[] factors = factor(i); 
 encodeIntoResponse(resp, factors); 
	} 
}
```

One thread accessing a `StatelessFactorizer` cannot influence the result of another thread accessing the same `StatelessFactorizer`, since two threads do not share state.


> [!Important] 
> Stateless objects are always thread‐safe.

writing correct concurrent programs is primarily about managing access to shared, mutable state
## Counter Safety

```java title:"java.util.concurrent.atomic.AtomicLong"
@ThreadSafe public class CountingFactorizer implements Servlet { 
	private final AtomicLong count = new AtomicLong(0); 
	public long getCount() { return count.get(); } 
	
	public void service(ServletRequest req, ServletResponse resp) { 
 BigInteger i = extractFromRequest(req); 
 BigInteger[] factors = factor(i); 
 count.incrementAndGet(); //two threads cannot increment it at the sametime
 encodeIntoResponse(resp, factors); 
	}
}
```


## Counter Example
```java title:"AtomicReference"
@NotThreadSafe
public class UnsafeCachingFactorizer implements Servlet {

 private final AtomicReference<BigInteger> lastNumber =
 new AtomicReference<BigInteger>();

 private final AtomicReference<BigInteger[]> lastFactors =
 new AtomicReference<BigInteger[]>();

 public void service(ServletRequest req, ServletResponse resp) {

 BigInteger i = extractFromRequest(req);

 if (i.equals(lastNumber.get())) {
 encodeIntoResponse(resp, lastFactors.get());
 } else {
 BigInteger[] factors = factor(i);
 lastNumber.set(i);
 lastFactors.set(factors);
 encodeIntoResponse(resp, factors);
 }
 }
}

```

The problem here is that `lastNumber` and `lastFactors` are not synchronized, although each of them are thread safe. It can happen that last Number is updated and last Factor is not yet updated.

```java title:"Solution with poor concurrency"
@ThreadSafe
public class SynchronizedFactorizer implements Servlet {

 @GuardedBy("this")
 private BigInteger lastNumber;

 @GuardedBy("this")
 private BigInteger[] lastFactors;

 public synchronized void service(ServletRequest req, ServletResponse resp) {
 BigInteger i = extractFromRequest(req);

 if (i.equals(lastNumber)) {
 encodeIntoResponse(resp, lastFactors);
 } else {
 BigInteger[] factors = factor(i);
 lastNumber = i;
 lastFactors = factors;
 encodeIntoResponse(resp, factors);
 }
 }
}

```

`synchronized` is a intrinsic lock

```java title:"a good solution"
@ThreadSafe
public class CachedFactorizer implements Servlet {

 @GuardedBy("this")
 private BigInteger lastNumber;

 @GuardedBy("this")
 private BigInteger[] lastFactors;

 @GuardedBy("this")
 private long hits;

 @GuardedBy("this")
 private long cacheHits;

 public synchronized long getHits() {
 return hits;
 }

 public synchronized double getCacheHitRatio() {
 return (double) cacheHits / (double) hits;
 }

 public void service(ServletRequest req, ServletResponse resp) {
 BigInteger i = extractFromRequest(req);
 BigInteger[] factors = null;

 synchronized (this) {
 ++hits;
 if (i.equals(lastNumber)) {
 ++cacheHits;
 factors = lastFactors.clone();
 }
 }

 if (factors == null) {
 factors = factor(i);
 synchronized (this) {
 lastNumber = i;
 lastFactors = factors.clone();
 }
 }

 encodeIntoResponse(resp, factors);
 }
}

```
## Reentrancy
In Java, intrinsic locks are reentrant, if a thread tries to acquire a lock that it already holds, the request succeeds
```java
public class Widget {

 public synchronized void doSomething() {
 ...
 }
}
public class LoggingWidget extends Widget {

 @Override
 public synchronized void doSomething() {
 System.out.println(toString() + ": calling doSomething");
 super.doSomething();
 }
}
```

Therefore, this code does **NOT** deadlock


> [!Warning] 
> Avoid holding locks during lengthy computations or operations at risk of not completing quickly such as network or console I/O.
