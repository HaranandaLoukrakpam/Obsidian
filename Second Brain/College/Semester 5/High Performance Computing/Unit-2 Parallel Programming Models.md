# 1. Introduction to Parallel Programming

## 1.1 Definition of Parallel Programming

[[Parallel Programming]] is a programming technique in which a computational problem is divided into smaller tasks that are executed simultaneously using multiple processing units.

Instead of executing all instructions sequentially on a single processor, parallel programming allows multiple processors or cores to perform different parts of a program concurrently.

The main objective is to reduce execution time, improve computational performance and efficiently utilise available hardware resources.

**Example:**

Suppose a program needs to add 1,000 numbers.

- In sequential programming, one processor performs all 1,000 additions.
    
- In parallel programming, four processors can each perform approximately 250 additions simultaneously.
    

## 1.2 Need for Parallel Programming

Parallel programming is required because modern computational applications involve large datasets and complex calculations.

Major reasons include:

1. **Reduced Execution Time:** Multiple processors execute tasks simultaneously.
    
2. **Increased Performance:** Improves computational throughput.
    
3. **Large-Scale Problem Solving:** Makes complex scientific problems easier to process.
    
4. **Resource Utilisation:** Efficiently uses multicore CPUs and GPUs.
    
5. **Scalability:** Allows applications to utilise additional computing resources.
    
6. **Real-Time Processing:** Supports applications that require quick results.
    
7. **Big Data Processing:** Handles large datasets efficiently.
    

## 1.3 Characteristics of Parallel Programming

- Multiple tasks execute concurrently.
    
- Workloads are divided among processing units.
    
- Communication may occur between tasks.
    
- Synchronisation is required when tasks share resources.
    
- Execution order may vary.
    
- Performance depends on workload distribution and communication overhead.
    

## 1.4 Sequential Programming vs Parallel Programming

|Sequential Programming|Parallel Programming|
|---|---|
|Executes instructions one after another.|Executes multiple operations simultaneously.|
|Usually uses one execution stream.|Uses multiple execution streams.|
|Simpler to design and debug.|More complex to design and debug.|
|Generally takes longer for parallelisable workloads.|Can reduce execution time.|
|Limited use of multiple cores.|Utilises multiple cores or processors.|
|No parallel synchronisation required.|Synchronisation may be required.|

---

# 2. Parallel Programming Concepts

## 2.1 Concurrency

[[Concurrency]] refers to the ability of a system to manage multiple tasks during overlapping periods of time.

Tasks may make progress alternately or simultaneously, depending on the hardware.

Concurrency does not necessarily mean that tasks execute at exactly the same time.

**Example:** A computer downloads a file while a user listens to music and browses the internet.

## 2.2 Parallelism

[[Parallelism]] refers to the actual simultaneous execution of multiple operations using multiple processing units.

**Example:** Four CPU cores simultaneously process four separate portions of an image.

## 2.3 Difference Between Concurrency and Parallelism

|Concurrency|Parallelism|
|---|---|
|Multiple tasks make progress during overlapping periods.|Multiple tasks execute simultaneously.|
|Can occur on a single processor through task switching.|Requires multiple execution resources for simultaneous execution.|
|Focuses on task management.|Focuses on simultaneous execution.|
|Example: Multitasking.|Example: Multicore processing.|

## 2.4 Decomposition

[[Decomposition]] is the process of dividing a large computational problem into smaller tasks that can be executed independently or concurrently.

Types include:

**1. Data Decomposition**

Divides the dataset into smaller sections and assigns them to different processors.

Example: Dividing a large matrix into four sections.

**2. Task Decomposition**

Divides a program into different independent operations.

Example: Assigning image processing, audio processing and data analysis to different processors.

## 2.5 Granularity

[[Granularity]] refers to the size of individual tasks in a parallel program and the amount of computation performed between communication or synchronisation operations.

Types:

- **Fine-Grained Parallelism:** A program is divided into many small tasks.
    
- **Coarse-Grained Parallelism:** A program is divided into fewer, larger tasks.
    

Fine-grained parallelism may provide more opportunities for parallel execution but can introduce higher communication and scheduling overhead.

Coarse-grained parallelism generally reduces communication overhead but may provide fewer opportunities for parallelism.

---

# 3. Threads and Processes

## 3.1 Process

### Definition

[[Process]] is a program that is currently being executed by an operating system.

A process has its own address space, memory resources and execution state.

Each process typically contains:

- Program code.
    
- Data section.
    
- Heap memory.
    
- Stack.
    
- Process control information.
    

### Characteristics of Processes

1. Each process has its own virtual address space.
    
2. Processes are isolated from one another.
    
3. A process can contain one or more threads.
    
4. Communication between processes requires inter-process communication mechanisms.
    
5. Process creation and context switching generally involve more overhead than threads.
    

### Example

Running a web browser and a music player simultaneously creates separate processes.

## 3.2 Thread

### Definition

[[Thread]] is the smallest unit of execution that can be independently scheduled within a process.

A process can contain multiple threads that share the same process address space.

Each thread has:

- Its own program counter.
    
- Its own registers.
    
- Its own stack.
    
- Its own execution state.
    

Threads within the same process share:

- Program code.
    
- Global variables.
    
- Heap memory.
    
- Process resources.
    

### Example

A web browser may use:

- One thread for user interface operations.
    
- Another thread for downloading data.
    
- Another thread for rendering web pages.
    

## 3.3 Process Architecture

```
       Operating System
              |
       +--------------+
       |  Process 1   |
       |              |
       |  Code        |
       |  Data        |
       |  Heap        |
       |  Stack       |
       +--------------+

       +--------------+
       |  Process 2   |
       |              |
       |  Code        |
       |  Data        |
       |  Heap        |
       |  Stack       |
       +--------------+
```

Each process has a separate virtual address space.

## 3.4 Thread Architecture

```
           Process
              |
     +--------+--------+
     |        |        |
     v        v        v
  Thread 1 Thread 2 Thread 3

     Shared Resources
  +----------------------+
  | Code                 |
  | Global Data          |
  | Heap                 |
  +----------------------+
```

Each thread has its own execution state and stack but shares the process resources.

## 3.5 Difference Between Threads and Processes

|Process|Thread|
|---|---|
|Program in execution.|Execution unit within a process.|
|Has a separate address space.|Shares the process address space.|
|More resource-intensive.|Generally lightweight.|
|Communication requires IPC mechanisms.|Communication can occur through shared variables.|
|Context switching is generally more expensive.|Context switching is generally less expensive.|
|More isolated.|Less isolated from other threads in the same process.|
|Failure is often isolated to the process.|A serious thread failure can affect the entire process.|

## 3.6 Multithreading

[[Multithreading]] is the ability of a process to execute multiple threads concurrently.

It improves application responsiveness and allows multiple CPU cores to execute different threads simultaneously.

**Advantages:**

- Better CPU utilisation.
    
- Improved responsiveness.
    
- Efficient resource sharing.
    
- Reduced overhead compared with separate processes.
    

**Disadvantages:**

- Race conditions.
    
- Deadlocks.
    
- Synchronisation complexity.
    
- Difficult debugging.
    

---

# 4. Shared Memory Programming Using OpenMP

## 4.1 Introduction to OpenMP

[[OpenMP (Open Multi-Processing)]] is an API used for parallel programming on shared-memory systems.

It provides compiler directives, runtime library routines and environment variables that allow programmers to create parallel programs.

OpenMP is mainly used with:

- C
    
- C++
    
- Fortran
    

It is commonly used on multicore processors.

## 4.2 Features of OpenMP

1. Supports shared-memory parallel programming.
    
2. Uses multiple threads.
    
3. Provides compiler directives.
    
4. Supports parallel loops.
    
5. Provides synchronisation mechanisms.
    
6. Supports thread scheduling.
    
7. Simplifies parallel programming.
    

## 4.3 OpenMP Architecture

```
             Main Program
                  |
                  v
            Master Thread
                  |
          Parallel Region
                  |
       +----------+----------+
       |          |          |
       v          v          v
   Thread 0   Thread 1   Thread 2
       |          |          |
       +----------+----------+
                  |
             Synchronisation
                  |
                  v
              Main Program
```

OpenMP commonly follows a fork-join execution model.

## 4.4 Fork-Join Model

[[Fork-Join Model]] is a parallel execution model in which a master thread creates multiple worker threads when entering a parallel region.

After completing the parallel work, the worker threads synchronise and join the master thread.

### Working

1. The program begins with a single master thread.
    
2. The master thread encounters a parallel region.
    
3. Multiple worker threads are created.
    
4. Threads execute tasks simultaneously.
    
5. Threads synchronise at the end of the parallel region.
    
6. Execution continues with the master thread.
    

## 4.5 OpenMP Syntax

OpenMP uses compiler directives to specify parallel regions.

General syntax in C/C++:

```
#pragma omp directive [clause]
{
    // Parallel code
}
```

The directive tells the compiler how to parallelise a particular section of code.

## 4.6 Basic OpenMP Program

**Example: Hello World using OpenMP**

```
#include <stdio.h>
#include <omp.h>

int main()
{
    #pragma omp parallel
    {
        printf("Hello from thread %d\n",
               omp_get_thread_num());
    }

    return 0;
}
```

**Explanation:**

- `#include <omp.h>` includes the OpenMP library.
    
- `#pragma omp parallel` creates a parallel region.
    
- `omp_get_thread_num()` returns the thread ID.
    
- Each thread executes the statement inside the parallel region.
    

The output order is not guaranteed because threads execute concurrently.

## 4.7 Important OpenMP Directives

### 1. Parallel Directive

[[Parallel Directive]] creates a team of threads to execute a parallel region.

```
#pragma omp parallel
{
    printf("Hello World\n");
}
```

### 2. For Directive

[[OpenMP For Directive]] distributes loop iterations among threads.

```
#pragma omp parallel for
for(int i = 0; i < 10; i++)
{
    printf("%d\n", i);
}
```

Each iteration is assigned to a thread according to the scheduling policy.

### 3. Sections Directive

[[OpenMP Sections]] divides independent code sections among different threads.

```
#pragma omp parallel sections
{
    #pragma omp section
    {
        printf("Task 1\n");
    }

    #pragma omp section
    {
        printf("Task 2\n");
    }
}
```

### 4. Single Directive

[[OpenMP Single Directive]] ensures that a code block is executed by only one thread in the team.

```
#pragma omp parallel
{
    #pragma omp single
    {
        printf("Executed by one thread\n");
    }
}
```

### 5. Critical Directive

[[OpenMP Critical Directive]] allows only one thread at a time to execute a particular code section.

```
#pragma omp critical
{
    count++;
}
```

It prevents simultaneous access to the protected code section.

### 6. Atomic Directive

[[OpenMP Atomic Directive]] ensures that a particular memory operation is performed atomically.

```
#pragma omp atomic
count++;
```

It is generally more lightweight than a critical section for supported simple memory operations.

### 7. Barrier Directive

[[OpenMP Barrier]] forces all threads in a team to wait until every thread reaches the barrier.

```
#pragma omp barrier
```

## 4.8 OpenMP Clauses

|Clause|Purpose|
|---|---|
|`private`|Creates a separate uninitialised variable for each thread.|
|`shared`|Allows threads to access the same variable.|
|`firstprivate`|Gives each thread a private copy initialised from the original value.|
|`lastprivate`|Copies the value from the logically last iteration or section to the original variable.|
|`reduction`|Combines private results from threads using a specified operation.|
|`num_threads`|Specifies the requested number of threads.|
|`schedule`|Controls the distribution of loop iterations.|

### Example of Reduction

```
#include <stdio.h>
#include <omp.h>

int main()
{
    int sum = 0;

    #pragma omp parallel for reduction(+:sum)
    for(int i = 1; i <= 100; i++)
    {
        sum += i;
    }

    printf("Sum = %d\n", sum);

    return 0;
}
```

The reduction clause creates private partial sums and combines them using addition.

## 4.9 Advantages of OpenMP

- Easy to implement shared-memory parallelism.
    
- Requires relatively few changes to existing sequential code.
    
- Supports multiple threads.
    
- Provides flexible scheduling and synchronisation.
    
- Suitable for multicore processors.
    

## 4.10 Limitations of OpenMP

- Primarily designed for shared-memory systems.
    
- Scalability is limited by the available shared-memory architecture.
    
- Race conditions may occur.
    
- Requires compiler support.
    
- Synchronisation overhead can reduce performance.
    

---

# 5. Distributed Memory Programming Using MPI

## 5.1 Introduction to MPI

[[MPI (Message Passing Interface)]] is a standardised communication interface used for parallel programming on distributed-memory systems.

It allows different processes to communicate by sending and receiving messages through an interconnection network.

MPI is widely used in scientific computing, supercomputers and HPC clusters.

MPI is a standard, not a programming language or a specific implementation.

Common implementations include:

- Open MPI.
    
- MPICH.
    

## 5.2 Features of MPI

1. Supports distributed-memory computing.
    
2. Provides message-passing communication.
    
3. Supports point-to-point communication.
    
4. Supports collective communication.
    
5. Supports communication between multiple processes.
    
6. Highly scalable.
    
7. Supports parallel applications across multiple nodes.
    

## 5.3 MPI Architecture

```
          MPI Program
               |
      +--------+--------+
      |        |        |
      v        v        v
   Process 0 Process 1 Process 2
      |        |        |
   Memory 0 Memory 1 Memory 2
      |        |        |
      +--------+--------+
               |
       Interconnection
           Network
```

Each process has its own private memory.

Processes exchange information using messages.

## 5.4 Important MPI Concepts

### 1. MPI Process

[[MPI Process]] is an independent execution unit participating in an MPI parallel program.

Each process has its own rank and private address space.

### 2. Communicator

[[MPI Communicator]] defines a group of processes that can communicate with one another.

The most commonly used communicator is `MPI_COMM_WORLD`, which includes all processes started by the MPI program.

### 3. Rank

[[MPI Rank]] is the unique identifier assigned to each process within a communicator.

For example, if four processes are running, their ranks are:

```
Process 0 -> Rank 0
Process 1 -> Rank 1
Process 2 -> Rank 2
Process 3 -> Rank 3
```

### 4. Size

The communicator size represents the total number of processes in a communicator.

## 5.5 Basic MPI Program

**Example: Hello World using MPI**

```
#include <stdio.h>
#include <mpi.h>

int main(int argc, char *argv[])
{
    int rank, size;

    MPI_Init(&argc, &argv);

    MPI_Comm_rank(MPI_COMM_WORLD, &rank);
    MPI_Comm_size(MPI_COMM_WORLD, &size);

    printf("Hello from process %d of %d\n",
           rank, size);

    MPI_Finalize();

    return 0;
}
```

### Explanation

- `MPI_Init()` initialises the MPI execution environment.
    
- `MPI_Comm_rank()` obtains the process rank.
    
- `MPI_Comm_size()` obtains the total number of processes.
    
- `MPI_Finalize()` terminates the MPI environment.
    

### Compilation and Execution

```
mpicc hello.c -o hello
mpirun -np 4 ./hello
```

Here:

- `mpicc` is the MPI compiler wrapper.
    
- `-np 4` requests four processes.
    
- `./hello` executes the program.
    

## 5.6 Important MPI Functions

|Function|Purpose|
|---|---|
|`MPI_Init()`|Initialises MPI.|
|`MPI_Finalize()`|Terminates MPI.|
|`MPI_Comm_rank()`|Returns process rank.|
|`MPI_Comm_size()`|Returns communicator size.|
|`MPI_Send()`|Sends a message.|
|`MPI_Recv()`|Receives a message.|
|`MPI_Bcast()`|Broadcasts data to all processes in a communicator.|
|`MPI_Reduce()`|Combines values from multiple processes into a result.|
|`MPI_Scatter()`|Distributes portions of data from one process to multiple processes.|
|`MPI_Gather()`|Collects data from multiple processes into one process.|
|`MPI_Barrier()`|Synchronises processes in a communicator.|

---

# 6. Message Passing Concepts

## 6.1 Definition

[[Message Passing]] is a communication technique in which processes exchange information by explicitly sending and receiving messages.

It is commonly used in distributed-memory parallel systems where each process has its own private memory.

A message generally contains:

- Data.
    
- Source process.
    
- Destination process.
    
- Message tag.
    
- Communicator.
    

## 6.2 Point-to-Point Communication

[[Point-to-Point Communication]] involves direct communication between two processes.

One process sends a message, and another process receives it.

### MPI_Send()

Used to send data from one process to another.

General syntax:

```
MPI_Send(
    buffer,
    count,
    datatype,
    destination,
    tag,
    communicator
);
```

### MPI_Recv()

Used to receive data from another process.

General syntax:

```
MPI_Recv(
    buffer,
    count,
    datatype,
    source,
    tag,
    communicator,
    status
);
```

### Example

```
if(rank == 0)
{
    int data = 100;

    MPI_Send(&data, 1, MPI_INT,
             1, 0, MPI_COMM_WORLD);
}
else if(rank == 1)
{
    int data;

    MPI_Recv(&data, 1, MPI_INT,
             0, 0, MPI_COMM_WORLD,
             MPI_STATUS_IGNORE);

    printf("Received: %d\n", data);
}
```

In this example:

- Process 0 sends the value 100.
    
- Process 1 receives the value.
    
- Process 1 prints the received value.
    

## 6.3 Collective Communication

[[Collective Communication]] involves communication among all processes within a communicator.

Important collective operations include:

### 1. Broadcast

[[MPI_Bcast]] sends the same data from one root process to all processes in a communicator.

```
MPI_Bcast(&data, 1, MPI_INT,
          0, MPI_COMM_WORLD);
```

### 2. Scatter

[[MPI_Scatter]] distributes different portions of an array from a root process to multiple processes.

```
MPI_Scatter(sendbuf, 1, MPI_INT,
            recvbuf, 1, MPI_INT,
            0, MPI_COMM_WORLD);
```

### 3. Gather

[[MPI_Gather]] collects data from all processes and stores it at a root process.

```
MPI_Gather(sendbuf, 1, MPI_INT,
           recvbuf, 1, MPI_INT,
           0, MPI_COMM_WORLD);
```

### 4. Reduce

[[MPI_Reduce]] combines values from multiple processes using an operation such as addition, maximum or minimum.

```
MPI_Reduce(&local, &global, 1,
           MPI_INT, MPI_SUM,
           0, MPI_COMM_WORLD);
```

### 5. Barrier

[[MPI_Barrier]] makes all processes in a communicator wait until every process reaches the barrier.

```
MPI_Barrier(MPI_COMM_WORLD);
```

## 6.4 Types of Message Passing

**1. Blocking Communication**

[[Blocking Communication]] is a communication operation that does not return until its specified completion conditions are satisfied.

For example, a blocking send may return when the message buffer can safely be reused. This does not necessarily mean the receiver has already processed the message.

**2. Non-Blocking Communication**

[[Non-Blocking Communication]] initiates a communication operation and returns before the operation is necessarily complete.

Examples:

- `MPI_Isend()`
    
- `MPI_Irecv()`
    

Completion is checked using functions such as `MPI_Wait()` or `MPI_Test()`.

### Difference Between Blocking and Non-Blocking Communication

|Blocking|Non-Blocking|
|---|---|
|Waits for specified completion conditions.|Returns before communication necessarily finishes.|
|Easier to understand.|More flexible.|
|May restrict overlapping computation and communication.|Allows computation and communication to overlap.|
|Can contribute to deadlocks if used incorrectly.|Requires careful management of request completion.|

---

# 7. Synchronization in Parallel Systems

## 7.1 Definition

[[Synchronization]] is the coordination of multiple threads or processes to ensure correct execution and proper access to shared resources.

It prevents conflicting operations and ensures that tasks execute in the required order.

Synchronization is essential when multiple execution units access shared data.

## 7.2 Need for Synchronization

1. Prevents race conditions.
    
2. Protects shared resources.
    
3. Maintains data consistency.
    
4. Coordinates execution order.
    
5. Prevents incorrect results caused by concurrent operations.
    

## 7.3 Synchronization Mechanisms

### 1. Mutex

[[Mutex (Mutual Exclusion Lock)]] is a synchronisation mechanism that allows only one thread at a time to access a protected critical section.

Example:

```
pthread_mutex_lock(&lock);

/* Critical section */
count++;

pthread_mutex_unlock(&lock);
```

### 2. Semaphore

[[Semaphore]] is a synchronisation mechanism that uses a counter to control access to shared resources.

Two basic operations are:

- Wait (P): Decreases the semaphore value or blocks if the resource is unavailable.
    
- Signal (V): Increases the semaphore value and may wake a waiting process.
    

Types:

**Binary Semaphore:** Has two logical states and is commonly used for signalling or mutual exclusion.

**Counting Semaphore:** Maintains a count representing the available number of resources.

### 3. Barrier Synchronization

[[Barrier Synchronization]] ensures that all participating threads or processes reach a specific point before any of them proceeds beyond it.

### 4. Critical Section

[[Critical Section]] is the part of a program where shared resources are accessed or modified.

Only one thread should execute a mutually exclusive critical section at a time.

### 5. Atomic Operations

[[Atomic Operation]] is an operation that executes as a single indivisible unit.

Other threads cannot observe it in a partially completed state.

Examples include atomic increment and compare-and-swap operations.

## 7.4 Critical Section Problem

The [[Critical Section Problem]] occurs when multiple processes or threads attempt to access shared data simultaneously.

A correct solution should satisfy three important conditions:

1. **Mutual Exclusion:** Only one process or thread can execute the protected critical section at a time.
    
2. **Progress:** If no process is executing in the critical section, the selection of the next process should not be postponed indefinitely.
    
3. **Bounded Waiting:** A process should not wait indefinitely to enter the critical section.
    

---

# 8. Race Conditions

## 8.1 Definition

[[Race Condition]] occurs when multiple threads or processes access shared data concurrently, and the final result depends on the unpredictable order of execution.

It generally occurs when at least one operation modifies shared data without proper synchronisation.

## 8.2 Example of Race Condition

Consider:

```
int count = 0;
```

Two threads execute:

```
count++;
```

The increment operation internally involves:

1. Reading the current value.
    
2. Adding one.
    
3. Writing the updated value.
    

Suppose both threads read the value 0 before either writes the result.

```
Initial count = 0

Thread 1 reads 0
Thread 2 reads 0

Thread 1 calculates 0 + 1
Thread 2 calculates 0 + 1

Thread 1 writes 1
Thread 2 writes 1

Final count = 1
```

The expected result was 2, but the actual result is 1.

This is called a race condition.

## 8.3 Prevention of Race Conditions

Race conditions can be prevented using:

1. Mutex locks.
    
2. Semaphores.
    
3. Critical sections.
    
4. Atomic operations.
    
5. Proper data partitioning.
    
6. Thread-safe programming techniques.
    

### Example Using OpenMP Critical

```
#include <stdio.h>
#include <omp.h>

int main()
{
    int count = 0;

    #pragma omp parallel
    {
        #pragma omp critical
        {
            count++;
        }
    }

    printf("Count = %d\n", count);

    return 0;
}
```

The critical directive ensures that only one thread increments the variable at a time.

---

# 9. Deadlocks

## 9.1 Definition

[[Deadlock]] is a condition in which two or more processes or threads remain permanently blocked because each is waiting for a resource held by another.

As a result, none of the processes can continue execution.

## 9.2 Example of Deadlock

Consider two threads and two resources:

- Thread 1 holds Resource A and waits for Resource B.
    
- Thread 2 holds Resource B and waits for Resource A.
    

```
       Thread 1
           |
     Holds Resource A
           |
     Waits for B
           |
           v

       Resource B
           |
       Held by T2
           |
       Waits for A
           |
           v

       Resource A
           |
       Held by T1
```

Neither thread can proceed.

## 9.3 Four Necessary Conditions for Deadlock

According to [[Coffman Conditions]], deadlock can occur when all four conditions are present simultaneously.

### 1. Mutual Exclusion

At least one resource must be non-shareable.

Only one process can use that resource at a time.

### 2. Hold and Wait

A process holds one resource while waiting to acquire another resource.

### 3. No Preemption

Resources cannot be forcibly taken away from a process. They must be released voluntarily.

### 4. Circular Wait

A circular chain of processes exists in which each process waits for a resource held by the next process.

## 9.4 Deadlock Prevention

Deadlock can be prevented by breaking at least one of the four necessary conditions.

Methods include:

1. **Resource Ordering:** Acquire resources in a fixed order.
    
2. **Avoid Hold and Wait:** Require processes to request all required resources before execution.
    
3. **Allow Preemption:** Permit resources to be taken away under suitable conditions.
    
4. **Avoid Circular Wait:** Establish a fixed resource acquisition hierarchy.
    

## 9.5 Deadlock Avoidance

[[Deadlock Avoidance]] is a technique in which the system checks whether allocating a resource will keep the system in a safe state.

An example is the [[Banker's Algorithm]].

## 9.6 Deadlock Detection

[[Deadlock Detection]] involves identifying whether a deadlock has occurred by examining resource allocation and waiting relationships.

## 9.7 Deadlock vs Race Condition

|Deadlock|Race Condition|
|---|---|
|Processes become permanently blocked.|Final output depends on execution order.|
|Occurs due to circular resource waiting.|Occurs due to unsynchronised shared data access.|
|Execution may stop completely.|Execution may continue with incorrect results.|
|Prevented by resource management.|Prevented by proper synchronisation.|

---

# 10. Parallel Loop Scheduling

## 10.1 Definition

[[Parallel Loop Scheduling]] is the process of distributing loop iterations among multiple threads or processors to achieve efficient parallel execution.

It is particularly important in OpenMP because loops are commonly used in scientific and numerical applications.

## 10.2 Need for Loop Scheduling

- Distributes work among threads.
    
- Reduces workload imbalance.
    
- Improves processor utilisation.
    
- Reduces idle time.
    
- Improves execution performance.
    

## 10.3 OpenMP Scheduling Types

### 1. Static Scheduling

[[Static Scheduling]] assigns loop iterations to threads before execution begins.

Each thread receives a predetermined portion of the iterations.

Example:

```
#pragma omp parallel for schedule(static, 2)
for(int i = 0; i < 8; i++)
{
    printf("%d\n", i);
}
```

With four threads and chunk size 2, iterations are assigned in groups of two.

**Advantages:**

- Low scheduling overhead.
    
- Predictable work distribution.
    
- Suitable for uniform workloads.
    

**Disadvantages:**

- Poor load balancing when iteration workloads vary significantly.
    

### 2. Dynamic Scheduling

[[Dynamic Scheduling]] assigns chunks of iterations to threads as they become available.

Example:

```
#pragma omp parallel for schedule(dynamic, 2)
for(int i = 0; i < 8; i++)
{
    printf("%d\n", i);
}
```

Threads request additional chunks when they complete their current work.

**Advantages:**

- Better load balancing for irregular workloads.
    
- Reduces idle time.
    

**Disadvantages:**

- Higher scheduling overhead.
    
- Work assignment is less predictable.
    

### 3. Guided Scheduling

[[Guided Scheduling]] dynamically assigns progressively smaller chunks of iterations to available threads.

Example:

```
#pragma omp parallel for schedule(guided)
for(int i = 0; i < 100; i++)
{
    // Computation
}
```

**Advantages:**

- Reduces scheduling overhead compared with very small dynamic chunks.
    
- Can balance irregular workloads.
    

**Disadvantages:**

- More complex scheduling behaviour.
    
- Not always optimal for every workload.
    

### 4. Runtime Scheduling

[[Runtime Scheduling]] allows the scheduling policy to be selected at runtime using the `OMP_SCHEDULE` environment variable.

Example:

```
#pragma omp parallel for schedule(runtime)
for(int i = 0; i < 100; i++)
{
    // Computation
}
```

## 10.4 Comparison of Loop Scheduling

|Scheduling|Work Distribution|Main Advantage|
|---|---|---|
|Static|Predetermined|Low overhead|
|Dynamic|Assigned as threads become available|Better load balancing|
|Guided|Progressively smaller dynamic chunks|Balances overhead and workload|
|Runtime|Selected at runtime|Flexibility|

---

# 11. Hybrid Programming Models

## 11.1 Definition

[[Hybrid Programming Model]] combines two or more parallel programming approaches to utilise different levels of parallelism in a computing system.

In HPC, the most common hybrid model combines MPI and OpenMP.

MPI is used for communication between computing nodes, while OpenMP is used for parallel execution among CPU cores within each node.

## 11.2 Architecture

```
                 HPC Cluster
                      |
          +-----------+-----------+
          |                       |
          v                       v
        Node 1                  Node 2
          |                       |
      MPI Process 0           MPI Process 1
          |                       |
    +-----+-----+           +-----+-----+
    |     |     |           |     |     |
    v     v     v           v     v     v
   T0    T1    T2          T0    T1    T2
          |                       |
     Shared Memory           Shared Memory

       MPI Communication Between Nodes
```

## 11.3 Working of Hybrid Programming

1. An HPC application starts multiple MPI processes across different nodes.
    
2. Each MPI process manages a portion of the overall computation.
    
3. Within each node, OpenMP creates multiple threads.
    
4. Threads share the node's memory.
    
5. MPI processes exchange data between nodes.
    
6. The final results are combined.
    

## 11.4 Advantages

- Utilises multiple nodes and CPU cores.
    
- Reduces the number of MPI processes required.
    
- Exploits shared-memory parallelism within each node.
    
- Can improve scalability.
    
- Makes efficient use of modern HPC clusters.
    

## 11.5 Disadvantages

- More complex programming.
    
- Requires careful synchronisation.
    
- Thread affinity and resource management can be challenging.
    
- Performance tuning is difficult.
    

## 11.6 Comparison of OpenMP, MPI and Hybrid Programming

|Feature|OpenMP|MPI|Hybrid|
|---|---|---|---|
|Memory model|Shared memory|Distributed memory|Both|
|Parallel unit|Threads|Processes|Processes and threads|
|Communication|Shared variables|Messages|Both|
|Typical usage|Multicore systems|Clusters|Large HPC systems|
|Programming complexity|Moderate|Moderate to high|High|
|Scalability|Usually limited to a shared-memory node|Can scale across many nodes|Can scale across nodes and cores|

---

# 12. Basics of Parallel Algorithm Design

## 12.1 Definition

[[Parallel Algorithm Design]] is the process of developing algorithms that divide a computational problem into smaller tasks that can execute simultaneously.

The objective is to improve execution speed, resource utilisation and scalability.

## 12.2 Steps in Parallel Algorithm Design

### Step 1: Problem Decomposition

Divide the problem into smaller independent tasks.

Example: Divide a large matrix into smaller blocks.

### Step 2: Identify Dependencies

Identify which tasks depend on the results of other tasks.

Independent tasks can execute simultaneously, while dependent tasks may require synchronisation.

### Step 3: Task Assignment

Assign tasks to available processors or threads.

### Step 4: Communication

Determine how processors exchange required data.

### Step 5: Synchronisation

Ensure that tasks coordinate correctly when accessing shared resources or waiting for results.

### Step 6: Performance Evaluation

Measure execution time, speedup, efficiency and scalability.

## 12.3 Important Concepts in Parallel Algorithm Design

### 1. Task Dependency

[[Task Dependency]] occurs when one task requires the output of another task before it can execute correctly.

### 2. Load Balancing

[[Load Balancing]] is the distribution of computational work among processors so that no processor remains unnecessarily idle while others are overloaded.

### 3. Communication Overhead

[[Communication Overhead]] is the additional time spent exchanging data between processors or threads instead of performing useful computation.

### 4. Synchronisation Overhead

[[Synchronization Overhead]] refers to the time spent coordinating the execution of multiple threads or processes.

### 5. Granularity

Determines the size of individual parallel tasks.

### 6. Scalability

[[Scalability]] refers to the ability of a parallel application to maintain or improve performance as more computing resources are added.

## 12.4 Types of Parallel Algorithm Decomposition

### A. Data Decomposition

The input dataset is divided among multiple processing units.

Example: Each processor calculates a section of a large matrix.

### B. Functional Decomposition

Different functions or operations are assigned to different processing units.

Example:

- Processor 1: Data collection.
    
- Processor 2: Data processing.
    
- Processor 3: Result analysis.
    

### C. Recursive Decomposition

A problem is repeatedly divided into smaller subproblems until the subproblems become sufficiently small to solve.

Example: Parallel implementation of merge sort.

## 12.5 Example: Parallel Matrix Addition

Suppose two matrices A and B need to be added.

Sequential approach:

```
For each row:
    For each column:
        C[i][j] = A[i][j] + B[i][j]
```

Parallel approach:

```
Processor 1 -> Add first rows
Processor 2 -> Add second rows
Processor 3 -> Add third rows
Processor 4 -> Add fourth rows
```

Each processor calculates a different portion of the result matrix.

Since each matrix element can be calculated independently, matrix addition is suitable for data parallelism.

## 12.6 Characteristics of a Good Parallel Algorithm

- Contains sufficient independent tasks.
    
- Minimises communication overhead.
    
- Provides balanced workload distribution.
    
- Minimises unnecessary synchronisation.
    
- Makes efficient use of available processors.
    
- Maintains correctness.
    
- Scales effectively with additional resources.
    

## 12.7 Limitations of Parallel Algorithms

- Not every problem can be parallelised.
    
- Communication can become expensive.
    
- Synchronisation introduces overhead.
    
- Load imbalance reduces performance.
    
- Debugging is difficult.
    
- Sequential portions limit overall speedup.
    

---

# 13. Important Comparisons for Examinations

## 13.1 OpenMP vs MPI

|OpenMP|MPI|
|---|---|
|Shared-memory programming model.|Distributed-memory programming model.|
|Uses threads.|Uses processes.|
|Communicates through shared variables.|Communicates through messages.|
|Mainly uses compiler directives.|Uses communication library functions.|
|Easier to implement for multicore systems.|Suitable for distributed systems.|
|Example: `#pragma omp parallel`|Example: `MPI_Send()`|

## 13.2 Mutex vs Semaphore

|Mutex|Semaphore|
|---|---|
|Locking mechanism.|Counter-based synchronisation mechanism.|
|Usually provides mutual exclusion.|Controls access to one or more resources.|
|Normally has ownership semantics.|Generally does not have mutex-style ownership semantics.|
|Commonly used to protect critical sections.|Used for resource management and signalling.|

## 13.3 Static vs Dynamic Scheduling

|Static Scheduling|Dynamic Scheduling|
|---|---|
|Assigns work before execution.|Assigns work during execution.|
|Low overhead.|Higher overhead.|
|Suitable for uniform workloads.|Suitable for irregular workloads.|
|Predictable assignment.|Flexible assignment.|

## 13.4 Blocking vs Non-Blocking MPI

|Blocking|Non-Blocking|
|---|---|
|Waits for completion conditions.|Initiates communication and returns earlier.|
|Simpler implementation.|More flexible implementation.|
|Less opportunity for overlap.|Allows overlap of computation and communication.|
|Example: `MPI_Send()`|Example: `MPI_Isend()`|

---

# 14. Important Examination Questions

## 2-Mark Questions

1. Define parallel programming.
    
2. What is concurrency?
    
3. Define decomposition.
    
4. What is granularity?
    
5. Define process.
    
6. What is a thread?
    
7. Define multithreading.
    
8. What is OpenMP?
    
9. What is MPI?
    
10. What is a communicator in MPI?
    
11. Define process rank.
    
12. What is message passing?
    
13. Define collective communication.
    
14. What is synchronization?
    
15. Define critical section.
    
16. What is a race condition?
    
17. Define deadlock.
    
18. What is a semaphore?
    
19. Define parallel loop scheduling.
    
20. What is hybrid programming?
    
21. Define load balancing.
    
22. What is communication overhead?
    

## 4–5-Mark Questions

1. Explain the concepts of parallel programming.
    
2. Differentiate between concurrency and parallelism.
    
3. Explain processes and threads.
    
4. Differentiate between threads and processes.
    
5. Explain the fork-join model of OpenMP.
    
6. Explain important OpenMP directives with examples.
    
7. Explain OpenMP clauses.
    
8. Explain MPI architecture and its features.
    
9. Explain important MPI functions.
    
10. Explain point-to-point and collective communication.
    
11. Differentiate between blocking and non-blocking communication.
    
12. Explain synchronisation mechanisms in parallel systems.
    
13. Explain race conditions with an example.
    
14. Explain deadlock and its four necessary conditions.
    
15. Explain parallel loop scheduling techniques.
    
16. Explain hybrid programming models.
    
17. Explain the steps involved in parallel algorithm design.
    

## 8–10-Mark Questions

1. Explain parallel programming concepts, their characteristics and applications.
    
2. Describe threads and processes with diagrams and explain their differences.
    
3. Explain shared-memory programming using OpenMP with architecture and programming examples.
    
4. Discuss the important OpenMP directives and clauses with suitable examples.
    
5. Explain distributed-memory programming using MPI with architecture and important functions.
    
6. Explain message passing concepts and different communication methods in MPI.
    
7. Discuss synchronisation mechanisms in parallel systems with suitable examples.
    
8. Explain race conditions and deadlocks, including their causes and prevention methods.
    
9. Explain different parallel loop scheduling techniques in OpenMP.
    
10. Describe hybrid programming models and explain how MPI and OpenMP work together.
    
11. Explain the fundamental steps and considerations involved in parallel algorithm design.
    

---

# 15. Quick Revision

|Topic|Key Point|
|---|---|
|Parallel Programming|Simultaneous execution of multiple operations|
|Concurrency|Multiple tasks make overlapping progress|
|Parallelism|Multiple operations execute simultaneously|
|Decomposition|Dividing a problem into smaller tasks|
|Granularity|Size of individual tasks|
|Process|Program in execution|
|Thread|Smallest independently schedulable execution unit|
|Multithreading|Multiple threads within a process|
|OpenMP|Shared-memory parallel programming API|
|Fork-Join|Master thread creates and joins worker threads|
|Parallel Directive|Creates a parallel region|
|For Directive|Distributes loop iterations|
|Critical|Protects a code section from concurrent execution|
|Atomic|Makes a supported memory operation indivisible|
|Reduction|Combines partial results|
|MPI|Distributed-memory communication standard|
|Rank|Unique process identifier|
|Communicator|Group of communicating processes|
|MPI_Send|Sends a message|
|MPI_Recv|Receives a message|
|MPI_Bcast|Broadcasts data|
|MPI_Scatter|Distributes data|
|MPI_Gather|Collects data|
|MPI_Reduce|Combines data|
|Synchronization|Coordinates parallel execution|
|Mutex|Mutual exclusion lock|
|Semaphore|Counter-based resource control|
|Race Condition|Result depends on execution order|
|Deadlock|Processes wait indefinitely for resources|
|Static Scheduling|Predetermined work assignment|
|Dynamic Scheduling|Work assigned as threads become available|
|Hybrid Programming|Combines programming models|
|Load Balancing|Distributes workload efficiently|
|Communication Overhead|Time spent exchanging data|

---

# 16. Conclusion

Parallel programming is an essential component of High Performance Computing because it allows large computational problems to be divided into smaller tasks and executed simultaneously.

Threads and processes provide the foundation for concurrent execution. OpenMP enables shared-memory parallel programming, while MPI supports communication between processes in distributed-memory systems.

Synchronization mechanisms such as mutexes, semaphores, barriers and atomic operations maintain correct execution. Understanding race conditions, deadlocks, loop scheduling and parallel algorithm design is essential for developing efficient and scalable HPC applications.

**End of Chapter 2 – Parallel Programming Models.**