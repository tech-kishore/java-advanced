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

**Thread safety in collections:** 
> Java provides several thread-safe collection classes that can be used in multithreaded environments.
> 1. Vector: This is a thread-safe implementation of a dynamic array, where elements can be added or removed from the end of the array.
> 1. Hashtable: This is a thread-safe implementation of a key-value map, where each key is associated with a value.
> 1. ConcurrentHashMap: This is a thread-safe implementation of a key-value map, where multiple threads can read or modify the map concurrently, without the need for synchronization.
> 1. CopyOnWriteArrayList: This is a thread-safe implementation of a dynamic array, where all write operations create a new copy of the underlying array, ensuring that reads are not affected by writes.
> 1. ConcurrentLinkedQueue: This is a thread-safe implementation of a queue, where elements can be added or removed in a non-blocking manner, allowing multiple threads to access the queue concurrently.
> 1. BlockingQueue: This is an interface that defines a queue that supports blocking operations, where a thread can wait for an element to be added or removed from the queue.
> 1. BlockingDeque: This is an interface that defines a double-ended queue that supports blocking operations, where a thread can wait for an element to be added or removed from either end of the queue.
> 1. Stack: This is a thread-safe implementation of a last-in-first-out (LIFO) stack.
> 1. PriorityQueue: This is a thread-safe implementation of a priority queue, where elements are ordered according to a comparator.
> 1. LinkedBlockingQueue: This is a thread-safe implementation of a queue, where elements are stored in a linked list and access is controlled by a mutex.
> 1. ArrayBlockingQueue: This is a thread-safe implementation of a bounded queue, where the capacity is fixed and access is controlled by a mutex.
> 1. ConcurrentSkipListMap: This is a thread-safe implementation of a sorted map, based on a skip list data structure.
> 1. ConcurrentSkipListSet: This is a thread-safe implementation of a sorted set, based on a skip list data structure.
> 1. ConcurrentLinkedDeque: This is a thread-safe implementation of a double-ended queue, based on a linked list data structure.



