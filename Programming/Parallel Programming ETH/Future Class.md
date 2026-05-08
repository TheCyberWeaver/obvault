> [!Definition]
> `Future<V>` is a Java interface representing the result of a computation that may become available later.

Strictly speaking, `Future<V>` is an **interface**, not a concrete class.

## Main idea

When a task is submitted to \[\[ExecutorService\]\], the caller may not want to wait immediately.

Instead, it can receive a `Future<V>` as a placeholder for the result:

```java
Future<Integer> future = pool.submit(() -> 42);
```

Later, the program can ask whether the task is done, wait for the result, or cancel it.

## Common methods

- `get()`: wait until the result is ready, then return it
- `get(timeout, unit)`: wait only up to a time limit
- `isDone()`: check whether the computation has finished
- `cancel(boolean mayInterruptIfRunning)`: try to cancel the task
- `isCancelled()`: check whether cancellation succeeded

## Example

```java
import java.util.concurrent.*;

ExecutorService pool = Executors.newFixedThreadPool(2);
Future<Integer> future = pool.submit(() -> 6 * 7);

if (!future.isDone()) {
    System.out.println("still running...");
}

int result = future.get();
pool.shutdown();
```

## What blocks and what does not?

- creating the `Future<V>` is usually immediate
- the submitted task runs asynchronously
- `future.get()` is the operation that typically blocks

This makes `Future<V>` useful when we want to start work now and collect the result later.

## Relationship with `Runnable` and `Callable`

- `Runnable`: no return value
- `Callable<V>`: returns a value of type `V`
- `Future<V>`: handle for the eventual result of a submitted task

A common pattern is:

1. create a `Callable<V>`
2. submit it to an \[\[ExecutorService\]\]
3. receive a `Future<V>`
4. call `get()` later when the result is needed

## Limitations

`Future<V>` is useful, but somewhat limited:

- `get()` is blocking
- combining multiple futures is awkward
- callbacks and pipelines are not built in

For richer asynchronous composition, Java provides `CompletableFuture`.

> [!Important]
> `Future<V>` is best thought of as a **handle to an asynchronous result**, not as the result itself.