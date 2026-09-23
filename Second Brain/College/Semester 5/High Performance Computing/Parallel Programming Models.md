# [[Parallel Programming Models]] — Unit Notes

## 1. [[Parallel Programming Models]]

A **[[Parallel Programming Model]]** provides a way for programmers to express how a problem should be divided and executed across multiple processors or cores.

The major models covered in this unit are:

1. **[[Thread-based Programming]] / [[Shared Memory Programming]]**
    
2. **[[Message Passing]] / [[Distributed Memory Programming]]**
    
3. **[[Hybrid Programming]]**
The objective is to make multiple processing units cooperate to solve a problem faster.
---
# 2. [[Parallel Programming Concepts]]

**[[Parallel Programming]]** is the process of designing a program so that multiple parts of it can execute simultaneously.

### Basic idea

```text
Sequential Program

Problem
   ↓
Task 1
   ↓
Task 2
   ↓
Task 3
   ↓
Result
```

Parallel version:

```text
             ┌→ Task 1 ─┐
Problem ─────┼→ Task 2 ─┼→ Result
             └→ Task 3 ─┘
```

### Important concepts

- **[[Parallelism]]** — executing multiple operations concurrently.
    
- **[[Concurrency]]** — multiple tasks making progress during overlapping periods.
    
- **[[Thread]]** — lightweight execution unit within a process.
    
- **[[Process]]** — independent program execution environment.
    
- **[[Synchronization]]** — coordinating concurrent execution.
    
- **[[Communication]]** — exchanging data between parallel execution units.
    
- **[[Load Balancing]]** — distributing work evenly among processors.
    

---

# 3. [[Processes and Threads]]

## [[Process]]

A **[[Process]]** is an independent instance of a running program.

Each process normally has its own:

- [[Address Space]]
    
- [[Memory]]
    
- [[Resources]]
    
- [[Execution State]]
    

Example:

```text
Process 1
├── Code
├── Data
├── Heap
└── Stack

Process 2
├── Code
├── Data
├── Heap
└── Stack
```

Processes communicate using mechanisms such as **[[Message Passing]]** or shared operating-system resources.

---

## [[Thread]]

A **[[Thread]]** is a lightweight execution path within a process.

Threads belonging to the same process typically share:

- Code
    
- Global variables
    
- Heap
    
- Other process resources

But each thread generally has its own:

- Program counter
    
- Registers
    
- Stack


```text
              Process
                 │
       ┌─────────┼─────────┐
       ↓         ↓         ↓
    Thread 1  Thread 2  Thread 3
       │         │         │
       └─────────┼─────────┘
             Shared Memory
```

### [[Process vs Thread]]

|Feature|[[Process]]|[[Thread]]|
|---|---|---|
|Memory|Separate address space|Shares process address space|
|Creation|Relatively expensive|Relatively lightweight|
|Communication|More expensive|Easier through shared memory|
|Failure isolation|Higher|Lower|
|Parallel programming|[[MPI]] commonly uses processes|[[OpenMP]] commonly uses threads|

---

# 4. [[Shared Memory Programming]] Using [[OpenMP]]

**[[OpenMP]] (Open Multi-Processing)** is an API for parallel programming on **[[Shared Memory Systems]]**.

It provides:

- Compiler directives
    
- Runtime library functions
    
- Environment variables

OpenMP is primarily used with languages such as **C, C++ and Fortran**.

### Basic model

```text
             Shared Memory
          ┌─────────────────┐
          │                 │
       Thread 1          Thread 2
          │                 │
       Thread 3          Thread 4
          │                 │
          └─────────────────┘
```

All threads belong to the same process and can access shared data.

---

# 5. [[OpenMP Parallel Region]]

A common OpenMP construct is:

```c
#pragma omp parallel
{
    printf("Hello from thread\n");
}
```

The `parallel` directive creates a team of threads that execute the enclosed block.

Conceptually:

```text
Main Thread
     │
     ↓
Create Threads
 ┌───┼───┬───┐
 ↓   ↓   ↓   ↓
 T1  T2  T3  T4
 └───┼───┴───┘
     ↓
  Continue
```

---

# 6. [[OpenMP Parallel Loop]]

One of the most useful OpenMP constructs is `parallel for`.

```c
#pragma omp parallel for
for (int i = 0; i < 100; i++) {
    A[i] = B[i] + C[i];
}
```

The iterations of the loop are distributed among available threads.

For example:

```text
Iterations: 0 1 2 3 4 5 6 7

Thread 1 → 0 1
Thread 2 → 2 3
Thread 3 → 4 5
Thread 4 → 6 7
```

This is an example of **[[Data Parallelism]]**.

---

# 7. [[Distributed Memory Programming]] Using [[MPI]]

**[[MPI]] = Message Passing Interface**

MPI is a standard programming interface used for parallel programming in **[[Distributed Memory Systems]]**.

Each process has its own memory.

```text
┌──────────────┐
│ Process 1    │
│ Local Memory │
└──────┬───────┘
       │
     Network
       │
┌──────┴───────┐
│ Process 2    │
│ Local Memory │
└──────────────┘
```

Processes communicate by **sending and receiving messages**.

---

# 8. [[Message Passing Concepts]]

[[Message Passing]] allows one process to send data to another process.

The basic operations are:

- **[[Send]]**
    
- **[[Receive]]**
    

Conceptually:

```text
Process 1                  Process 2

   Data
     │
     ↓
   SEND ───────────────→ RECEIVE
                              │
                              ↓
                            Data
```

### Example

```c
MPI_Send(...);
MPI_Recv(...);
```

`MPI_Send()` sends data.

`MPI_Recv()` receives data.

---

## [[MPI Communicator]]

A **[[Communicator]]** defines a group of processes that can communicate with each other.

The most commonly used communicator is:

```text
MPI_COMM_WORLD
```

It represents all processes participating in the MPI program.

---

## [[MPI Rank]]

Each MPI process has a unique **[[Rank]]** within a communicator.

For example, with four processes:

```text
Process       Rank

Process 0       0
Process 1       1
Process 2       2
Process 3       3
```

Rank is used to identify processes.

---

# 9. [[OpenMP vs MPI]]

|Feature|[[OpenMP]]|[[MPI]]|
|---|---|---|
|Memory model|Shared memory|Distributed memory|
|Execution unit|Threads|Processes|
|Communication|Shared variables|Messages|
|Typical system|Multicore CPU|Cluster|
|Programming difficulty|Relatively easier|More complex|
|Scalability|Within shared-memory system|Across many nodes|
|Common API|OpenMP directives|MPI functions|

---

# 10. [[Synchronization]]

**[[Synchronization]]** coordinates multiple threads or processes so that they access resources and execute operations in a controlled manner.

It is necessary when multiple execution units interact with shared data or depend on one another.

### Example

Suppose two threads update the same variable:

```text
Initial count = 0

Thread 1 → count = count + 1
Thread 2 → count = count + 1
```

Without proper synchronization, the final result may be incorrect.

---

# 11. [[Race Condition]]

A **[[Race Condition]]** occurs when multiple threads/processes access shared data concurrently and the final result depends on the timing or ordering of their operations.

Example:

```text
count = 0

Thread 1                  Thread 2

Read count → 0            Read count → 0
Add 1                      Add 1
Write 1                    Write 1
```

Expected:

```text
count = 2
```

Actual:

```text
count = 1
```

This occurs because both threads read the old value before either update becomes visible.

### Solution

Use [[Synchronization]] mechanisms such as:

- [[Locks]]
    
- [[Mutexes]]
    
- [[Critical Sections]]
    
- [[Atomic Operations]]
    
- [[Barriers]]
    

---

# 12. [[Critical Section]]

A **[[Critical Section]]** is a portion of code that accesses a shared resource and must not be executed by multiple threads simultaneously.

OpenMP:

```c
#pragma omp critical
{
    count++;
}
```

Only one thread at a time can execute the critical section.

```text
Thread 1 ──→ [ Critical Section ] ──→
Thread 2 ──→ WAIT ───────────────→ [ Critical Section ]
Thread 3 ──→ WAIT ───────────────→
```

---

# 13. [[Atomic Operation]]

An **[[Atomic Operation]]** performs a small update to shared data indivisibly.

Example:

```c
#pragma omp atomic
count++;
```

This is generally more lightweight than protecting a larger block with a critical section.

---

# 14. [[Barrier Synchronization]]

A **[[Barrier]]** forces threads to wait until all threads reach a particular point.

```text
Thread 1 ────────────┐
Thread 2 ────────┐   │
Thread 3 ─────────────┤ Barrier
Thread 4 ────────┘   │
                     ↓
                Continue
```

OpenMP:

```c
#pragma omp barrier
```

### Purpose

Ensures that no thread proceeds beyond the barrier until all required threads have arrived.

---

# 15. [[Deadlock]]

A **[[Deadlock]]** occurs when two or more processes/threads wait indefinitely for resources held by one another.

Example:

```text
Thread 1
   │
   ├── Holds Lock A
   ↓
 Waits for Lock B


Thread 2
   │
   ├── Holds Lock B
   ↓
 Waits for Lock A
```

Neither can continue.

```text
Thread 1 → waiting for Thread 2
Thread 2 → waiting for Thread 1
```

### Conditions commonly associated with deadlock

1. **[[Mutual Exclusion]]**
    
2. **[[Hold and Wait]]**
    
3. **[[No Preemption]]**
    
4. **[[Circular Wait]]**
    

### Avoiding deadlocks

- Acquire locks in a consistent order.
    
- Avoid unnecessary locks.
    
- Keep critical sections short.
    
- Use timeouts where appropriate.
    
- Carefully design resource allocation.
    

---

# 16. [[Parallel Loop Scheduling]]

When a loop is parallelized, its iterations must be distributed among threads.

OpenMP provides several scheduling strategies.

---

## [[Static Scheduling]]

Iterations are divided among threads before execution.

```c
#pragma omp parallel for schedule(static)
```

Example:

```text
Iterations: 0 1 2 3 4 5 6 7

Thread 1 → 0 1
Thread 2 → 2 3
Thread 3 → 4 5
Thread 4 → 6 7
```

### Advantages

- Low scheduling overhead
    
- Predictable
    
- Good when iterations have similar workloads
    

---

## [[Dynamic Scheduling]]

Iterations are assigned to threads as threads become available.

```c
#pragma omp parallel for schedule(dynamic)
```

Conceptually:

```text
Thread 1 → Task → Task → Task
Thread 2 → Task → Task
Thread 3 → Task → Task → Task
Thread 4 → Task
```

### Advantages

- Better load balancing
    
- Useful when iteration execution time varies
    

### Disadvantage

- Higher scheduling overhead
    

---

## [[Guided Scheduling]]

Starts with larger chunks and gradually reduces chunk size.

```c
#pragma omp parallel for schedule(guided)
```

It attempts to balance:

- [[Load Balancing]]
    
- Scheduling overhead
    

---

## [[Scheduling Comparison]]

|Schedule|Main idea|Suitable for|
|---|---|---|
|[[Static Scheduling]]|Fixed assignment|Uniform workloads|
|[[Dynamic Scheduling]]|Assign work as threads become free|Uneven workloads|
|[[Guided Scheduling]]|Decreasing chunk sizes|Large uneven workloads|

---

# 17. [[Hybrid Programming Models]]

A **[[Hybrid Programming Model]]** combines two or more parallel programming approaches.

A common HPC approach combines:

**[[MPI]] + [[OpenMP]]**

MPI is used **between nodes**, while OpenMP is used **within each node**.

```text
             HPC Cluster
                  │
       ┌──────────┴──────────┐
       ↓                     ↓
     Node 1                Node 2
       │                     │
   MPI Process            MPI Process
       │                     │
   ┌───┼───┐             ┌───┼───┐
   ↓   ↓   ↓             ↓   ↓   ↓
  T1  T2  T3             T1  T2  T3
  OpenMP                  OpenMP
```

### Why hybrid programming?

It combines:

- **[[MPI Scalability]]** across nodes
    
- **[[OpenMP Shared-Memory Parallelism]]** within each node
    

This can reduce the number of MPI processes and make better use of multicore nodes.

---

# 18. [[Basics of Parallel Algorithm Design]]

A **[[Parallel Algorithm]]** divides a problem into multiple parts that can be executed concurrently.

### Basic design process

```text
1. Identify the problem
        ↓
2. Find independent operations
        ↓
3. Partition the data/work
        ↓
4. Assign work to processors
        ↓
5. Manage communication
        ↓
6. Synchronize when required
        ↓
7. Combine results
```

---

## Important Principles

### 1. [[Decomposition]]

Break the problem into smaller tasks.

Example:

```text
Array of 1,000,000 elements
             ↓
       Divide into 4
             ↓
250,000 | 250,000 | 250,000 | 250,000
```

---

### 2. [[Data Partitioning]]

Divide data among processors.

```text
Processor 1 → Data 1
Processor 2 → Data 2
Processor 3 → Data 3
Processor 4 → Data 4
```

---

### 3. [[Load Balancing]]

Each processor should receive a reasonable amount of work.

Poor balancing:

```text
CPU 1 → ████████████████
CPU 2 → ██
CPU 3 → ███
CPU 4 → █
```

Good balancing:

```text
CPU 1 → █████
CPU 2 → █████
CPU 3 → █████
CPU 4 → █████
```

Poor load balancing causes processors to sit idle.

---

### 4. [[Communication]]

Processors may need to exchange intermediate results.

Too much communication can reduce the benefits of parallelism.

---

### 5. [[Synchronization]]

Synchronization ensures that dependent operations occur in the correct order.

---

### 6. [[Granularity]]

**[[Granularity]]** refers to the amount of computation performed between communication or synchronization events.

- **[[Fine-Grained Parallelism]]:** Small tasks, frequent communication.
    
- **[[Coarse-Grained Parallelism]]:** Larger tasks, less frequent communication.
    

Generally, excessive fine-grained parallelism can introduce significant overhead.

---

# 19. [[Speedup and Efficiency]]

Two important measures of a parallel algorithm are **[[Speedup]]** and **[[Parallel Efficiency]]**.

### [[Speedup]]

S=T1TpS = \frac{T_1}{T_p}

Where:

- T1T_1 = execution time using one processor
    
- TpT_p = execution time using pp processors
    

Example:

If a program takes 100 seconds on one processor and 25 seconds on four processors:

S=10025=4S = \frac{100}{25}=4

So the speedup is **4×**.

---

### [[Parallel Efficiency]]

E=SpE = \frac{S}{p}

For the above example:

E=44=1=100%E = \frac{4}{4}=1=100\%

In real systems, efficiency is usually below 100% because of communication, synchronization, load imbalance and other overheads.

---

# 20. [[Important Exam Definitions]]

### [[Parallel Programming]]

Designing programs so that multiple computational operations can execute concurrently.

### [[Thread]]

A lightweight execution unit within a process that shares the process's resources.

### [[Process]]

An independent executing program with its own address space.

### [[OpenMP]]

An API for shared-memory parallel programming using compiler directives, runtime functions and environment variables.

### [[MPI]]

A standard message-passing interface for communication between processes in distributed-memory systems.

### [[Message Passing]]

A communication model in which processes exchange data explicitly through messages.

### [[Synchronization]]

Coordination of parallel execution units to ensure correct ordering and safe access to shared resources.

### [[Race Condition]]

A situation where the result depends on the timing or ordering of concurrent accesses to shared data.

### [[Deadlock]]

A state where processes or threads wait indefinitely for resources held by one another.

### [[Load Balancing]]

Distributing computational work evenly among processing units.

### [[Hybrid Programming]]

A parallel programming approach combining models such as MPI and OpenMP.

### [[Parallel Algorithm]]

An algorithm that divides computation into tasks that can be executed concurrently.

---

# [[Quick Revision]]

```text
[[Parallel Programming]]
│
├── [[Processes and Threads]]
│   ├── [[Process]] → Independent execution + memory
│   └── [[Thread]]  → Lightweight execution unit
│
├── [[Shared Memory Programming]]
│   └── [[OpenMP]]
│       ├── [[OpenMP Parallel Region]]
│       ├── [[OpenMP Parallel Loop]]
│       ├── [[Critical Section]]
│       ├── [[Atomic Operation]]
│       └── [[Barrier Synchronization]]
│
├── [[Distributed Memory Programming]]
│   └── [[MPI]]
│       ├── [[MPI Communicator]]
│       ├── [[MPI Rank]]
│       ├── [[Send]]
│       └── [[Receive]]
│
├── [[Synchronization]]
│   ├── [[Critical Section]]
│   ├── [[Atomic Operation]]
│   └── [[Barrier]]
│
├── Problems
│   ├── [[Race Condition]]
│   └── [[Deadlock]]
│
├── [[Parallel Loop Scheduling]]
│   ├── [[Static Scheduling]]
│   ├── [[Dynamic Scheduling]]
│   └── [[Guided Scheduling]]
│
├── [[Hybrid Programming Models]]
│   └── [[MPI]] + [[OpenMP]]
│
└── [[Basics of Parallel Algorithm Design]]
    ├── [[Decomposition]]
    ├── [[Data Partitioning]]
    ├── [[Load Balancing]]
    ├── [[Communication]]
    ├── [[Synchronization]]
    └── [[Granularity]]
```