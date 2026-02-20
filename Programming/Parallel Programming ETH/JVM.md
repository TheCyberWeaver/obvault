## Pipeline
![[Pasted image 20260217105929.png]]

![[Pasted image 20260217102438.png]]

## Bytecode Interpreter
 - JVM is a stack based abstract machine: bytecodes pop and push values on the stack
 - local variables and parameters are stored in registers
## Memory Allocators
Object allocation in Java invokes the JVM memory allocator. The JVM memory allocator often has to ask the underlying OS for memory which it then manages internally.
- JVM memory allocator works concurrently
## Garbage Collectors
- works concurrently
- periodically free memory that are unreachable
- Concurrent garbage collectors are _very difficult to get correct_
## Native Interface
When calling native methods, one convert the JVM parameters into machine registers following the calling convention
- some support concurrency some **not**
- `public static native int print(double d);`

