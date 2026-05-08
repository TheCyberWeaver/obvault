> [!Definition]
> `ExecutorService` is a Java interface for executing tasks asynchronously using a managed pool of worker threads.

## Why use it?

Instead of creating threads manually with `new Thread(...)`, `ExecutorService` lets us:

- reuse threads
- limit the number of concurrent workers
- submit tasks conveniently
- manage shutdown in a structured way

This usually makes concurrent code simpler and more efficient.

## Common creation patterns

```java
import java.util.concurrent.*;

ExecutorService fixed = Executors.newFixedThreadPool(4);
ExecutorService single = Executors.newSingleThreadExecutor();
ExecutorService cached = Executors.newCachedThreadPool();
```

Different pools are useful for different workloads:

- **fixed thread pool**: stable number of worker threads
- **single thread executor**: tasks run one after another
- **cached thread pool**: flexible number of threads for short-lived tasks

## `execute()` vs `submit()`

Two common ways to send work to an executor are:

- `execute(Runnable task)`: fire-and-forget, no return value
- `submit(...)`: returns a [[Future <>]] for tracking completion, cancellation, or a result.

Examples:

```java
pool.execute(() -> System.out.println("hello"));
Future<Integer> f = pool.submit(() -> 42);
```

`submit(Runnable)` also returns a `Future<?>`, even though the task itself does not produce a useful value.

## Example

```java
import java.util.concurrent.*;

ExecutorService pool = Executors.newFixedThreadPool(4);

Future<Integer> result = pool.submit(() -> {
    return 21 + 21;
});

int value = result.get();
pool.shutdown();
```

Here:

- the task runs in the thread pool
- `result.get()` waits until the computation finishes
- `shutdown()` tells the executor to stop accepting new tasks

## Lifecycle management

Important methods:

- `shutdown()`: stop accepting new tasks, finish already submitted tasks
- `shutdownNow()`: try to stop immediately, often by interrupting workers
- `awaitTermination(...)`: wait until the pool has actually terminated

Failing to shut down an executor can leave background threads running.

## Related interfaces

- `Callable<V>`: like `Runnable`, but returns a value and may throw checked exceptions
- `ScheduledExecutorService`: for delayed or periodic tasks

For divide-and-conquer parallelism, Java also provides [[Fork-Join Framework]], whose `ForkJoinPool` is a specialized executor.

> [!Important]
> `ExecutorService` is a general-purpose abstraction for task execution. It separates **what work should be done** from **which thread actually runs it**.
