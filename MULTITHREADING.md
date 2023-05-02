# MULTITHREADING

## What can be done
- Execution of multiple threads concurrently within a single program.

## Core concepts of Multithreading

**Thread safety:** 
> Multiple threads can safely access shared resources without causing conflicts or inconsistencies.
> 
> **Techniques** 
>   1. synchronization
>   2. atomic operations
>   3. locking.

**Synchronization:** 
> Process of controlling access to shared resources by allowing only one thread to access them at a time.
> 
> **Techniques** 
>   1. Synchronized blocks or methods.

**Deadlock:** 
> Occurs when two or more threads are blocked and waiting for each other to release resources, causing a standstill in the program's execution.
> 
> **Techniques** 
>   1. Important to understand how to prevent and resolve deadlocks.

**Race conditions:** 
> Situations where the outcome of a program depends on the order in which threads execute.
> 
> **Techniques** 
>  1. synchronization
>  2. locking.

**Thread pools:** 
> Creating a pool of reusable threads. 
> Improves performance and reduce overhead by minimizing the cost of creating and destroying threads.

**Interruption:** 
> Process of stopping a thread's execution in a safe and controlled manner. 
> Important to understand how to handle thread interruption and ensure that resources are properly released.


**Thread communication:** 
> Process of coordinating the actions of multiple threads to achieve a desired outcome. 

> **Techniques** 
>  1. wait and notify

**Concurrency utilities:** 
> Java provides a number of built-in concurrency utilities such as
> - Executors,
> - Locks, and
> - Condition Variables. 

> **Techniques** 
>  1. wait and notify
