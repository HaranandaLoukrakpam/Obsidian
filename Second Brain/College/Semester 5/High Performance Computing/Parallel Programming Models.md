# [[Parallel Programming Models]]

Parallel Programming is a programming paradigm in which multiple computations or tasks are executed simultaneously using multiple processing elements (CPU cores, GPUs, or distributed computers). Instead of executing instructions sequentially, work is divided among multiple processors to reduce execution time and improve performance.

Parallel programming forms the foundation of **High Performance Computing (HPC)** and is widely used in scientific computing, artificial intelligence, simulations, big data analytics, and cloud computing.

---

# [[Parallel Programming Concepts]]

Parallel programming involves dividing a problem into smaller sub-problems that can be solved simultaneously by multiple processors.

---

## [[Objectives of Parallel Programming]]

- Reduce execution time
    
- Improve resource utilization
    
- Increase computational performance
    
- Solve larger and more complex problems
    
- Achieve scalability
    

---

## [[Characteristics of Parallel Programming]]

- Simultaneous execution
    
- Task decomposition
    
- Communication between processors
    
- Synchronization of tasks
    
- Load balancing
    
- Scalability
    

---

## [[Advantages of Parallel Programming]]

- Faster computation
    
- Efficient CPU utilization
    
- Handles large datasets
    
- Improves throughput
    
- Supports real-time processing
    

---

## [[Challenges of Parallel Programming]]

- Race conditions
    
- Deadlocks
    
- Synchronization overhead
    
- Communication latency
    
- Load imbalance
    
- Debugging complexity
    

---

# [[Threads and Processes]]

Processes and threads are two fundamental execution units in an operating system.

---

# [[Process]]

A **Process** is an independent program in execution with its own memory space and system resources.

Each process contains:

- Program Code
    
- Data
    
- Heap
    
- Stack
    
- Registers
    
- File descriptors
    

---

## [[Characteristics of Processes]]

- Independent execution
    
- Separate memory space
    
- Higher resource consumption
    
- Communication through IPC (Inter-Process Communication)
    

---

## [[Advantages of Processes]]

- High security
    
- Fault isolation
    
- Independent execution
    

---

## [[Disadvantages of Processes]]

- Expensive to create
    
- Slow context switching
    
- Communication overhead
    

---

# [[Thread]]

A **Thread** is the smallest unit of execution within a process.

Multiple threads share the same process memory while executing independently.

---

## [[Characteristics of Threads]]

- Shared memory
    
- Lightweight
    
- Faster creation
    
- Fast context switching
    

---

## [[Advantages of Threads]]

- Better performance
    
- Lower overhead
    
- Efficient communication
    
- Shared resources
    

---

## [[Disadvantages of Threads]]

- Synchronization required
    
- Race conditions
    
- Difficult debugging
    

---

# [[Process vs Thread]]

|Feature|Process|Thread|
|---|---|---|
|Memory|Separate|Shared|
|Communication|IPC|Shared variables|
|Creation Cost|High|Low|
|Context Switching|Slow|Fast|
|Isolation|High|Low|

---

# [[Shared Memory Programming using OpenMP]]

**OpenMP (Open Multi-Processing)** is an API for parallel programming on **shared memory systems**.

It enables programmers to create multiple threads using compiler directives.

---

## [[Features of OpenMP]]

- Thread-based programming
    
- Shared memory model
    
- Easy to learn
    
- Incremental parallelization
    
- Portable across platforms
    

---

## [[OpenMP Execution Model]]

1. Master thread starts execution.
    
2. Parallel region is encountered.
    
3. Worker threads are created.
    
4. Work is distributed among threads.
    
5. Threads synchronize.
    
6. Worker threads terminate.
    
7. Master thread continues execution.
    

---

## [[OpenMP Directives]]

Common compiler directives:

- `#pragma omp parallel`
    
- `#pragma omp for`
    
- `#pragma omp sections`
    
- `#pragma omp single`
    
- `#pragma omp critical`
    
- `#pragma omp barrier`
    

---

## [[Advantages of OpenMP]]

- Simple programming model
    
- Good for multicore processors
    
- Automatic thread management
    
- Low programming effort
    

---

## [[Limitations of OpenMP]]

- Only works on shared-memory systems
    
- Limited scalability
    
- Synchronization overhead
    

---

# [[Distributed Memory Programming using MPI]]

**MPI (Message Passing Interface)** is a standardized communication library for programming distributed-memory systems.

Each processor has its own memory and communicates by sending messages.

---

## [[Features of MPI]]

- Distributed memory model
    
- Explicit communication
    
- Portable
    
- Highly scalable
    
- Suitable for supercomputers
    

---

## [[MPI Execution Model]]

Each process executes independently.

Communication occurs through:

- Sending messages
    
- Receiving messages
    
- Broadcasting
    
- Gathering
    
- Reducing data
    

---

## [[Common MPI Functions]]

- `MPI_Init()`
    
- `MPI_Finalize()`
    
- `MPI_Send()`
    
- `MPI_Recv()`
    
- `MPI_Bcast()`
    
- `MPI_Reduce()`
    
- `MPI_Barrier()`
    

---

## [[Advantages of MPI]]

- Excellent scalability
    
- Suitable for HPC clusters
    
- Efficient distributed computing
    
- Supports thousands of processors
    

---

## [[Disadvantages of MPI]]

- Difficult programming
    
- Explicit communication
    
- Communication latency
    

---

# [[OpenMP vs MPI]]

|Feature|OpenMP|MPI|
|---|---|---|
|Memory Model|Shared|Distributed|
|Parallel Unit|Threads|Processes|
|Communication|Shared Variables|Message Passing|
|Scalability|Moderate|Very High|
|Suitable For|Multicore CPUs|HPC Clusters|

---

# [[Message Passing Concepts]]

Message passing is the exchange of information between processes executing on different processors.

Since distributed systems do not share memory, all communication occurs through messages.

---

## [[Types of Communication]]

### [[Point-to-Point Communication]]

Communication between exactly two processes.

Examples:

- Send
    
- Receive
    

---

### [[Collective Communication]]

Communication among multiple processes.

Examples:

- Broadcast
    
- Scatter
    
- Gather
    
- Reduce
    
- All-Reduce
    

---

## [[Communication Modes]]

### [[Blocking Communication]]

The sender or receiver waits until communication completes.

Advantages:

- Simple programming
    

Disadvantages:

- Idle waiting
    

---

### [[Non-Blocking Communication]]

Processes continue executing while communication occurs.

Advantages:

- Better performance
    
- Overlapping communication and computation
    

Disadvantages:

- More complex programming
    

---

# [[Synchronization and Race Conditions]]

Synchronization coordinates multiple threads or processes to ensure correct execution.

---

# [[Synchronization]]

Synchronization ensures shared resources are accessed safely.

---

## [[Synchronization Mechanisms]]

- Mutex Locks
    
- Semaphores
    
- Barriers
    
- Critical Sections
    
- Atomic Operations
    
- Condition Variables
    

---

## [[Importance of Synchronization]]

- Prevents data corruption
    
- Ensures consistency
    
- Coordinates parallel execution
    
- Protects shared resources
    

---

# [[Race Conditions]]

A **Race Condition** occurs when multiple threads access shared data simultaneously and the program's result depends on the order of execution.

---

## [[Example of Race Condition]]

Two threads increment the same variable simultaneously.

Expected value:

```text
Counter = Counter + 1
```

Without synchronization, updates may be lost, producing incorrect results.

---

## [[Causes]]

- Shared variables
    
- Unsynchronized access
    
- Concurrent writes
    

---

## [[Solutions]]

- Mutex
    
- Locks
    
- Atomic operations
    
- Critical sections
    

---

# [[Deadlocks in Parallel Systems]]

A **Deadlock** occurs when two or more processes wait indefinitely for resources held by each other.

No process can continue execution.

---

## [[Necessary Conditions for Deadlock]]

1. Mutual Exclusion
    
2. Hold and Wait
    
3. No Preemption
    
4. Circular Wait
    

All four conditions must exist simultaneously.

---

## [[Example]]

Thread A holds Lock 1 and waits for Lock 2.

Thread B holds Lock 2 and waits for Lock 1.

Neither thread can proceed.

---

## [[Deadlock Prevention]]

- Resource ordering
    
- Timeout mechanisms
    
- Lock hierarchy
    
- Avoid circular waiting
    
- Resource preemption
    

---

# [[Parallel Loop Scheduling]]

Loop scheduling determines how iterations of a loop are distributed among processors.

Proper scheduling improves load balancing and performance.

---

## [[Types of Loop Scheduling]]

### [[Static Scheduling]]

Iterations are assigned before execution.

Advantages:

- Low overhead
    
- Predictable
    

Disadvantages:

- Poor load balancing
    

---

### [[Dynamic Scheduling]]

Iterations are assigned during execution.

Advantages:

- Better load balancing
    

Disadvantages:

- Higher scheduling overhead
    

---

### [[Guided Scheduling]]

Initially assigns large chunks.

Chunk sizes decrease over time.

Advantages:

- Good balance
    
- Reduced overhead
    

---

### [[Auto Scheduling]]

Compiler or runtime automatically selects the scheduling strategy.

---

## [[Importance of Loop Scheduling]]

- Reduces idle processors
    
- Improves scalability
    
- Better workload distribution
    

---

# [[Hybrid Programming Models]]

Hybrid programming combines two or more parallel programming models.

The most common hybrid model is:

**MPI + OpenMP**

- MPI distributes work across nodes.
    
- OpenMP creates threads within each node.
    

---

## [[Architecture of Hybrid Programming]]

```text
Cluster
│
├── Node 1
│     ├── OpenMP Thread 1
│     ├── OpenMP Thread 2
│     └── OpenMP Thread 3
│
├── Node 2
│     ├── OpenMP Thread 1
│     ├── OpenMP Thread 2
│     └── OpenMP Thread 3
```

MPI communicates between nodes, while OpenMP manages threads within each node.

---

## [[Advantages of Hybrid Programming]]

- Better scalability
    
- Efficient memory usage
    
- Reduced communication overhead
    
- Improved performance on modern HPC systems
    

---

## [[Disadvantages]]

- Complex programming
    
- Difficult debugging
    
- Synchronization challenges
    

---

# [[Basics of Parallel Algorithm Design]]

A parallel algorithm is an algorithm designed to execute multiple operations simultaneously.

---

## [[Characteristics of a Good Parallel Algorithm]]

- High parallelism
    
- Minimal communication
    
- Good load balancing
    
- Scalability
    
- Low synchronization overhead
    

---

## [[Steps in Parallel Algorithm Design]]

### [[Problem Decomposition]]

Divide a large problem into smaller independent tasks.

---

### [[Task Assignment]]

Assign tasks to processors.

---

### [[Communication]]

Exchange required information between processors.

---

### [[Synchronization]]

Coordinate execution to maintain correctness.

---

### [[Load Balancing]]

Ensure all processors receive approximately equal work.

---

### [[Performance Evaluation]]

Measure:

- Execution Time
    
- Speedup
    
- Efficiency
    
- Scalability
    

---

# [[Performance Metrics]]

## [[Execution Time]]

The total time required to complete a program.

---

## [[Speedup]]

Measures improvement obtained through parallel execution.

**Formula:**

```text
Speedup = Sequential Execution Time / Parallel Execution Time
```

Ideal Speedup = Number of Processors

---

## [[Efficiency]]

Measures processor utilization.

**Formula:**

```text
Efficiency = Speedup / Number of Processors
```

Efficiency ranges from **0 to 1 (or 0% to 100%)**.

---

## [[Scalability]]

The ability of a parallel program to maintain performance as the number of processors increases.

Good scalability means adding processors results in proportional performance improvement.

---

# [[Key Terms]]

|Term|Meaning|
|---|---|
|Parallel Programming|Simultaneous execution of multiple computations|
|Process|Independent executing program with its own memory|
|Thread|Lightweight execution unit within a process|
|OpenMP|Shared-memory parallel programming API|
|MPI|Message Passing Interface for distributed-memory systems|
|Synchronization|Coordination of concurrent tasks|
|Race Condition|Incorrect behavior due to unsynchronized concurrent access|
|Deadlock|Processes waiting indefinitely for each other's resources|
|Loop Scheduling|Distribution of loop iterations among processors|
|Hybrid Programming|Combination of MPI and OpenMP (or other models)|
|Load Balancing|Equal distribution of work across processors|
|Speedup|Performance improvement from parallel execution|
|Efficiency|Effectiveness of processor utilization|
|Scalability|Ability to maintain performance as processors increase|

---

# [[Exam Tips]]

### Frequently Asked Theory Questions

1. Define Parallel Programming and explain its objectives.
    
2. Differentiate between Processes and Threads.
    
3. Explain Shared Memory Programming using OpenMP.
    
4. Explain Distributed Memory Programming using MPI.
    
5. Compare OpenMP and MPI with suitable examples.
    
6. Explain Message Passing Concepts and communication modes.
    
7. What is Synchronization? Discuss various synchronization mechanisms.
    
8. Explain Race Conditions with examples and methods to prevent them.
    
9. Define Deadlock. Explain its necessary conditions and prevention techniques.
    
10. Explain Parallel Loop Scheduling and its types.
    
11. Describe Hybrid Programming Models and their advantages.
    
12. Explain the steps involved in designing an efficient Parallel Algorithm.
    
13. Define Speedup, Efficiency, and Scalability in parallel systems.