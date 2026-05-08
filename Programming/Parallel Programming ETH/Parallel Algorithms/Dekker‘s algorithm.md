> [!Definition]
> **Dekker's algorithm** is one of the first software-only algorithms for **mutual exclusion** between two threads.

## Core idea

- Each thread raises its own `flag` before entering the critical section.
- If both threads want to enter, a shared `turn` variable breaks the tie.
- When leaving, a thread gives priority to the other thread and lowers its flag.
