> [!Definition]
> A `Virtual Thread` is a lightweight Java thread managed mostly by the JVM rather than being permanently tied to one operating-system thread.

## Overview

`Virtual Thread` is part of Project Loom. Its goal is to let Java run a very large number of concurrent tasks without needing the same number of OS threads.

Compared with a traditional platform thread:

- a virtual thread is much cheaper to create
- blocking operations such as waiting for I/O do not necessarily block an OS thread for the entire duration
- the JVM can mount and unmount virtual threads onto a smaller pool of carrier threads

This makes virtual threads especially useful for applications with many concurrent, mostly I/O-bound tasks, such as web servers, RPC handlers, or database-backed services.

## Which Java version introduced it?

`Virtual Thread` was introduced in stages:
- **Java 19**: first introduced as a **preview feature** (`JEP 425`)
- **Java 20**: second preview (`JEP 436`)
- **Java 21**: finalized as a standard feature (`JEP 444`)
## Example

```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    Future<String> future = executor.submit(() -> {
        Thread.sleep(1000);
        return "done";
    });

    System.out.println(future.get());
}
```

Here each submitted task can run in its own virtual thread.
### Real-world example

One simple example is an echo-style socket server that accepts a connection and handles it in a new virtual thread:

```java
while (true) {
    Socket clientSocket = serverSocket.accept();
    // Accept incoming connections
    // Start a service thread
    Thread.ofVirtual().start(() -> {
        try (
            PrintWriter out =
                new PrintWriter(clientSocket.getOutputStream(), true);
            BufferedReader in = new BufferedReader(
                new InputStreamReader(clientSocket.getInputStream()));
        ) {
            String inputLine;
            while ((inputLine = in.readLine()) != null) {
                System.out.println(inputLine);
                out.println(inputLine);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    });
}
```

In practice, virtual threads let you write code in the familiar blocking style without paying the same scalability cost as creating one platform thread per request.

## Important limitation

`Virtual Thread` is not a magic speed-up for CPU-bound computation.

If the bottleneck is pure CPU work, virtual threads usually do not make the program faster. Their main benefit is scalability for workloads that spend a lot of time blocked on I/O.

## Relationship to existing concurrency tools

Virtual threads still work with familiar Java concurrency APIs such as [[ExecutorService]] and `Future<V>`.

The major change is that Java can now afford the "one task, one thread" style in many more cases than before.