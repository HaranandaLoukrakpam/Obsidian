## 1. Introduction to Performance Analysis

[[Performance Analysis]] is the process of measuring and evaluating how efficiently a computer system or parallel program performs a task.

In [[High Performance Computing (HPC)]], performance analysis helps determine whether a parallel program uses available processors, memory, and communication resources effectively.

### Objectives of Performance Analysis

- Measure program execution time.
    
- Evaluate processor and memory utilisation.
    
- Identify performance bottlenecks.
    
- Compare sequential and parallel implementations.
    
- Improve scalability and efficiency.
    
- Reduce communication and synchronisation overhead.
    

### Performance Optimization

[[Performance Optimization]] is the process of modifying a program or system to improve its performance without changing its intended output.

Common optimization techniques include:

- Improving algorithms.
    
- Reducing unnecessary calculations.
    
- Optimising memory access.
    
- Improving load balancing.
    
- Reducing communication overhead.
    
- Using parallel processing efficiently.
    

---

## 2. Performance Metrics

[[Performance Metrics]] are quantitative measurements used to evaluate the performance of a computer system.

Important performance metrics include execution time, throughput, latency, speedup, and efficiency.

### 2.1 Execution Time

[[Execution Time]] is the total time required by a computer or program to complete a task.

It is commonly divided into:

1. **Wall-clock time:** Actual elapsed time from the start to the completion of a program.
    
2. **CPU time:** Time spent executing instructions on the CPU.
    

In parallel computing, execution time is generally measured from the beginning of program execution until all parallel tasks are completed.

**Formula:**

$$T = T_{finish} - T_{start}$$
Where:

- T = Execution time
    
- Tfinish = Completion time
    
- Tstart = Starting time
    

**Example:**

If a program starts at 10:00 AM and finishes at 10:05 AM:

Execution time = 5 minutes.

### 2.2 Throughput

[[Throughput]] is the number of tasks or operations completed by a system per unit of time.

**Formula:**

$$Throughput = \frac{Number\ of\ completed\ tasks}{Total\ time}$$

**Example:**

If a server processes 1,000 requests in 10 seconds:

$$Throughput = \frac{1000}{10} = 100\ requests/second$$

Higher throughput means the system can process more work in a given period.

### 2.3 Latency

[[Latency]] is the time taken to complete a single operation or respond to a request.

**Example:**

If a computer takes 0.5 seconds to respond to a request, its response latency is 0.5 seconds.

**Difference between Throughput and Latency:**

|Throughput|Latency|
|---|---|
|Measures work completed per unit time|Measures time taken for one operation|
|Higher is generally better|Lower is generally better|
|Focuses on quantity|Focuses on response time|
|Example: 100 requests/second|Example: 10 ms/request|

### 2.4 Speedup

[[Speedup]] measures how much faster a parallel program executes compared to its sequential version.

**Formula:**

$$S(p) = \frac{T_s}{T_p}$$

Where:

- S(p) = Speedup using p processors
    
- Ts = Sequential execution time
    
- Tp = Parallel execution time
    

**Example:**

A program takes 100 seconds on one processor and 25 seconds on four processors.

$$S(4) = \frac{100}{25} = 4$$

Therefore, the speedup is 4 times.

**Types of Speedup:**

1. **Linear Speedup:** Speedup increases proportionally with the number of processors.
    $$S(p) = p$$
2. **Sublinear Speedup:** Speedup is less than the number of processors because of overhead and other limitations.
    $$S(p) < p$$
3. **Superlinear Speedup:** Speedup is greater than the number of processors. It may occur due to improved cache utilisation or other architectural effects.
    $$S(p) > p$$
### 2.5 Efficiency

[[Parallel Efficiency]] measures how effectively multiple processors are utilised during parallel execution.

**Formula:**

$$E(p) = \frac{S(p)}{p}$$

Or,

$$E(p) = \frac{T_s}{p \times T_p}$$

Where:

- E(p) = Parallel efficiency
    
- S(p) = Speedup
    
- p = Number of processors
    

Efficiency is generally expressed as a percentage.

**Example:**

If speedup is 4 using 8 processors:

$$E(8) = \frac{4}{8} = 0.5 = 50%
$$

Therefore, the parallel efficiency is 50%.

### Important Performance Metrics Summary

|Metric|Meaning|Desired Result|
|---|---|---|
|Execution Time|Time required to finish a task|Lower|
|Throughput|Tasks completed per unit time|Higher|
|Latency|Time for one operation|Lower|
|Speedup|Improvement over sequential execution|Higher|
|Efficiency|Effective processor utilisation|Higher|

---

## 3. Amdahl's Law

[[Amdahl's Law]] explains the theoretical maximum improvement in program execution time when only a portion of the program can be parallelised.

It states that the speedup of a program is limited by the portion that must execute sequentially.

### Concept

A program consists of two parts:

1. **Serial Portion:** The part that must execute sequentially.
    
2. **Parallel Portion:** The part that can be divided among multiple processors.
    

Even if the parallel portion executes infinitely fast, the serial portion remains and limits the overall speedup.

### Formula

$$S(p) = \frac{1}{(1-P)+\frac{P}{p}}$$

Where:

- S(p) = Overall speedup
    
- P = Parallelisable fraction of the program
    
- 1 − P = Serial fraction
    
- p = Number of processors
    

### Diagram

```
             Total Program
                   |
          +--------+--------+
          |                 |
     Serial Part       Parallel Part
          |                 |
   One processor     Multiple processors
          |                 |
          +--------+--------+
                   |
             Final Result
```

### Numerical Example

Suppose:

- 80% of a program is parallelisable.
    
- 20% is serial.
    
- 4 processors are used.
    

Given:

P = 0.8

p = 4

Using Amdahl's Law:

$$S(4) = \frac{1}{(1-0.8)+\frac{0.8}{4}}$$

$$S(4) = \frac{1}{0.2+0.2}$$

$$S(4) = \frac{1}{0.4} = 2.5$$

**Answer:** The maximum speedup is 2.5 times.

### Amdahl's Law with Infinite Processors

When the number of processors approaches infinity:

$$S_{max} = \frac{1}{1-P}$$

For the previous example:

$$S_{max} = \frac{1}{1-0.8} = 5$$

Therefore, even with infinitely many processors, the maximum speedup is 5 times.

### Advantages

- Helps estimate the maximum possible speedup.
    
- Identifies the importance of reducing serial portions.
    
- Helps determine whether parallelisation is worthwhile.
    

### Limitations

- Assumes a fixed problem size.
    
- Does not fully account for communication and synchronisation overhead.
    
- Assumes the serial and parallel fractions remain constant.
    

**Key Point:** Amdahl's Law is mainly used for fixed-size problems.

---

## 4. Gustafson's Law

[[Gustafson's Law]] explains how parallel computing can achieve better speedup when the problem size increases with the number of processors.

Unlike Amdahl's Law, it assumes that larger problems can be solved by using more processors.

### Concept

As more processors become available, the system can process larger datasets or more complex problems in approximately the same amount of time.

For example:

- A small weather simulation may run on 4 processors.
    
- A much larger weather simulation can run on 100 processors.
    
- More processors allow the system to solve a larger problem.
    

### Formula

$$S(p) = p - \alpha(p-1)$$

Where:

- S(p) = Scaled speedup
    
- p = Number of processors
    
- α = Serial fraction of execution time in the parallel execution
    

### Numerical Example

Suppose:

- Number of processors = 8
    
- Serial fraction = 0.1
    

Using Gustafson's Law:

$$S(8) = 8 - 0.1(8-1)$$

$$S(8) = 8 - 0.7$$
$$S(8) = 7.3$$

**Answer:** The scaled speedup is 7.3 times.

### Advantages

- Supports larger problem sizes.
    
- Demonstrates the usefulness of adding processors.
    
- More realistic for many scientific and HPC applications.
    

### Limitations

- Assumes the problem can grow with available resources.
    
- Larger problems may introduce additional memory and communication overhead.
    
- Requires careful load balancing.
    

### Difference Between Amdahl's Law and Gustafson's Law

|Amdahl's Law|Gustafson's Law|
|---|---|
|Assumes fixed problem size|Assumes scaled problem size|
|Focuses on fixed workload speedup|Focuses on scaled speedup|
|Serial portion limits speedup|Serial portion is considered in a growing workload|
|Often predicts diminishing returns|Shows how larger workloads benefit from more processors|
|Useful for fixed-size problems|Useful for large scientific simulations|

**Important:** Amdahl's Law and Gustafson's Law are not contradictory. They analyse parallel performance under different assumptions.

---

## 5. Scalability Analysis

[[Scalability]] is the ability of a parallel system to maintain or improve its performance when additional processors or computing resources are added.

A scalable system can handle increasing workloads efficiently.

### Types of Scalability

#### 5.1 Strong Scaling

[[Strong Scaling]] measures how execution time changes when the number of processors increases while keeping the total problem size constant.

Example:

A fixed dataset of 1 million records is processed using 2, 4, 8, and 16 processors.

The goal is to reduce execution time.

#### 5.2 Weak Scaling

[[Weak Scaling]] measures how execution time changes when both the problem size and number of processors increase proportionally.

Example:

- 2 processors process 1 million records.
    
- 4 processors process 2 million records.
    
- 8 processors process 4 million records.
    

The goal is to maintain approximately the same execution time.

### Strong Scaling vs Weak Scaling

|Strong Scaling|Weak Scaling|
|---|---|
|Fixed total problem size|Problem size increases with processors|
|Measures reduction in execution time|Measures ability to maintain execution time|
|Work per processor decreases|Work per processor remains approximately constant|
|Useful for fixed workloads|Useful for large-scale simulations|

### Factors Affecting Scalability

- Communication overhead.
    
- Synchronisation overhead.
    
- Load imbalance.
    
- Memory bandwidth.
    
- Processor availability.
    
- Network latency.
    
- Serial portions of a program.
    

### Ideal Scalability

An ideal parallel system achieves linear speedup.

$$S(p) = p$$

Its efficiency is:

$$E(p) = 1 = 100%
$$

In real systems, perfect scalability is difficult because communication, synchronisation, and resource limitations introduce overhead.

---

## 6. Load Balancing Techniques

[[Load Balancing]] is the process of distributing computational tasks evenly among available processors so that no processor remains unnecessarily idle while others are overloaded.

### Need for Load Balancing

- Improves processor utilisation.
    
- Reduces execution time.
    
- Prevents idle processors.
    
- Improves parallel efficiency.
    
- Reduces workload imbalance.
    

### Types of Load Balancing

#### 6.1 Static Load Balancing

[[Static Load Balancing]] distributes tasks among processors before program execution.

The task distribution generally remains fixed during execution.

Example:

If 100 tasks are divided among 4 processors:

- Processor 1: 25 tasks
    
- Processor 2: 25 tasks
    
- Processor 3: 25 tasks
    
- Processor 4: 25 tasks
    

**Advantages:**

- Simple to implement.
    
- Low scheduling overhead.
    
- Suitable for predictable workloads.
    

**Disadvantages:**

- Cannot easily handle unpredictable workloads.
    
- May cause imbalance if tasks take different amounts of time.
    

#### 6.2 Dynamic Load Balancing

[[Dynamic Load Balancing]] distributes tasks during program execution according to processor availability and workload.

Example:

If one processor finishes its tasks early, it can receive additional work from a shared task queue.

**Advantages:**

- Handles unpredictable workloads.
    
- Improves resource utilisation.
    
- Adapts to changing execution times.
    

**Disadvantages:**

- Higher scheduling overhead.
    
- More complex implementation.
    
- May require additional communication.
    

### Static vs Dynamic Load Balancing

|Static|Dynamic|
|---|---|
|Tasks assigned before execution|Tasks assigned during execution|
|Fixed distribution|Flexible distribution|
|Low overhead|Higher overhead|
|Suitable for predictable workloads|Suitable for unpredictable workloads|
|Easier to implement|More complex|

### Load Balancing Methods

1. **Round Robin:** Assigns tasks sequentially to available processors.
    
2. **Centralised Scheduling:** A central scheduler distributes tasks.
    
3. **Work Stealing:** Idle processors take tasks from busy processors.
    
4. **Task Queues:** Processors obtain work from a shared or distributed queue.
    
5. **Partitioning:** Divides data or computation into approximately equal workloads.
    

---

## 7. Profiling Tools

[[Profiling]] is the process of collecting information about program execution to understand where time and computing resources are being consumed.

A [[Profiler]] helps developers identify inefficient code, performance bottlenecks, and resource usage.

### Objectives of Profiling

- Identify slow functions.
    
- Measure CPU utilisation.
    
- Analyse memory usage.
    
- Detect unnecessary computations.
    
- Find communication overhead.
    
- Improve application performance.
    

### Types of Profiling

#### 7.1 CPU Profiling

Measures how much CPU time is consumed by different functions or program sections.

Example: Finding which function consumes the most execution time.

#### 7.2 Memory Profiling

Analyses memory allocation, memory usage, and memory leaks.

Example: Identifying unnecessary memory allocation.

#### 7.3 I/O Profiling

Measures input/output operations, including file access and storage performance.

#### 7.4 Communication Profiling

Measures communication time between processors in distributed systems.

Example: Analysing time spent in MPI_Send and MPI_Recv operations.

### Common Profiling Tools

|Tool|Purpose|
|---|---|
|[[gprof]]|CPU profiling for C/C++ programs|
|[[Valgrind]]|Memory debugging and profiling|
|[[perf]]|Linux performance analysis|
|[[Intel VTune Profiler]]|CPU, memory, and threading analysis|
|[[NVIDIA Nsight]]|GPU and CUDA performance analysis|
|[[TAU]]|Performance profiling of parallel programs|
|[[Score-P]]|Profiling and tracing HPC applications|

### Profiling Workflow

```
     Run the Program
            |
            v
     Collect Performance Data
            |
            v
      Analyse the Results
            |
            v
    Identify Bottlenecks
            |
            v
     Optimise the Program
            |
            v
       Run Again
            |
            v
    Compare Performance
```

**Important:** Profiling should be performed before and after optimisation to verify whether the changes actually improve performance.

---

## 8. Bottleneck Identification

[[Bottleneck Identification]] is the process of finding the component or operation that limits the overall performance of a computer system.

A bottleneck prevents the system from achieving its maximum possible performance.

### Common Types of Bottlenecks

#### 8.1 CPU Bottleneck

Occurs when the processor is overloaded with computational tasks.

Example: A program performs too many complex calculations.

#### 8.2 Memory Bottleneck

Occurs when memory access becomes slower than the processor's ability to execute instructions.

Example: A program frequently accesses data from RAM instead of cache.

#### 8.3 I/O Bottleneck

Occurs when input/output operations slow down program execution.

Example: Reading large files from slow storage.

#### 8.4 Communication Bottleneck

Occurs when processors spend too much time exchanging data.

Example: An MPI program performs frequent communication between nodes.

#### 8.5 Synchronisation Bottleneck

Occurs when processors frequently wait for locks, barriers, or other synchronisation operations.

### Methods of Identifying Bottlenecks

- Use profiling tools.
    
- Monitor CPU and memory utilisation.
    
- Analyse execution time of individual functions.
    
- Measure communication and synchronisation time.
    
- Compare sequential and parallel execution.
    
- Examine cache misses and memory bandwidth.
    

### Example

Suppose a parallel program has the following execution breakdown:

|Operation|Time|
|---|---|
|Computation|40 seconds|
|Communication|30 seconds|
|Synchronisation|20 seconds|
|I/O|10 seconds|
|Total|100 seconds|

Communication and synchronisation together consume 50% of execution time.

Therefore, reducing communication and synchronisation overhead should be a major optimisation priority.

---

## 9. Cache Optimization

[[Cache Optimization]] is the process of improving cache utilisation to reduce memory access time and increase program performance.

A [[CPU Cache]] is a small, high-speed memory located close to or inside the processor.

### Why Cache Optimization Is Important

- Cache access is faster than RAM access.
    
- Reduces memory latency.
    
- Improves CPU utilisation.
    
- Reduces unnecessary memory access.
    
- Improves execution time.
    

### Locality of Reference

[[Locality of Reference]] describes the tendency of programs to access the same memory locations or nearby memory locations repeatedly.

There are two major types:

#### 9.1 Temporal Locality

[[Temporal Locality]] means recently accessed data or instructions are likely to be accessed again soon.

Example:

```
for (int i = 0; i < 100; i++) {
    sum += 10;
}
```

The variable `sum` is accessed repeatedly.

#### 9.2 Spatial Locality

[[Spatial Locality]] means memory locations near a recently accessed location are likely to be accessed soon.

Example:

```
int arr[100];

for (int i = 0; i < 100; i++) {
    printf("%d", arr[i]);
}
```

Array elements are accessed sequentially, improving spatial locality.

### Cache Optimization Techniques

1. **Loop Interchange:** Changes the order of nested loops to improve memory access patterns.
    
2. **Loop Tiling:** Divides large loops into smaller blocks that fit better in cache.
    
3. **Data Reuse:** Reuses previously loaded data instead of accessing memory repeatedly.
    
4. **Data Alignment:** Aligns data to memory boundaries for efficient access.
    
5. **Avoiding Cache Thrashing:** Reduces repeated replacement of useful cache blocks.
    

### Example: Loop Interchange

Consider a two-dimensional array in C, which is stored in row-major order.

Less cache-friendly access:

```
for (int j = 0; j < N; j++) {
    for (int i = 0; i < N; i++) {
        sum += A[i][j];
    }
}
```

More cache-friendly access:

```
for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
        sum += A[i][j];
    }
}
```

The second version accesses adjacent elements in memory, generally improving spatial locality.

### Cache Hit and Cache Miss

- [[Cache Hit]]: Required data is found in cache.
    
- [[Cache Miss]]: Required data is not found in cache and must be fetched from a lower memory level.
    

**Cache Hit Ratio:**

$$Hit\ Ratio = \frac{Cache\ Hits}{Total\ Memory\ Accesses}$$

**Cache Miss Ratio:**

$$Miss\ Ratio = 1 - Hit\ Ratio$$

**Average Memory Access Time (AMAT):**

$$AMAT = Hit\ Time + (Miss\ Rate \times Miss\ Penalty)$$

A higher cache hit ratio generally results in better performance.

---

## 10. Memory Access Optimization

[[Memory Access Optimization]] involves improving the way a program reads and writes data to memory to reduce delays and improve performance.

### Importance

- Reduces memory latency.
    
- Improves memory bandwidth utilisation.
    
- Minimises cache misses.
    
- Reduces unnecessary data movement.
    
- Improves parallel application performance.
    

### Memory Access Optimization Techniques

#### 10.1 Sequential Memory Access

Access memory locations in sequence rather than jumping randomly between locations.

Example:

```
for (int i = 0; i < N; i++) {
    sum += arr[i];
}
```

This improves spatial locality.

#### 10.2 Loop Tiling

[[Loop Tiling]] divides large loops into smaller blocks to improve cache utilisation.

Example:

```
for (int i = 0; i < N; i += BLOCK) {
    for (int j = 0; j < N; j += BLOCK) {
        for (int x = i; x < i + BLOCK && x < N; x++) {
            for (int y = j; y < j + BLOCK && y < N; y++) {
                C[x][y] += A[x][y] + B[x][y];
            }
        }
    }
}
```

The smaller blocks can improve cache reuse.

#### 10.3 [[Data Alignment]]

Organises data according to memory alignment requirements to improve access efficiency.

#### 10.4 Avoiding Unnecessary Memory Allocation

Repeated allocation and deallocation can increase overhead. Reusing memory buffers where appropriate improves efficiency.

#### 10.5 Reducing Data Movement

Moving data between CPU, RAM, and GPU can be expensive. Keeping data close to the processor that uses it can improve performance.

### Cache Optimization vs Memory Access Optimization

|Cache Optimization|Memory Access Optimization|
|---|---|
|Focuses on efficient cache usage|Focuses on overall memory access|
|Improves cache hit ratio|Reduces memory access overhead|
|Uses locality and cache blocking|Uses sequential access and data organisation|
|Reduces cache misses|Reduces latency and data movement|

---

## 11. Communication Overhead Reduction

[[Communication Overhead]] is the time and resources spent exchanging data between processors in a parallel system instead of performing useful computations.

Communication overhead is especially important in [[Distributed Memory Systems]] where processors exchange data through a network.

### Causes of Communication Overhead

- Frequent message passing.
    
- Large amounts of transferred data.
    
- Network latency.
    
- Synchronisation between processors.
    
- Unnecessary data exchange.
    
- Poor task distribution.
    

### Techniques to Reduce Communication Overhead

#### 11.1 Communication Aggregation

Combines multiple small messages into one larger message.

This reduces the number of communication operations.

#### 11.2 Data Locality

Assigns tasks to processors that already have the required data.

This reduces unnecessary data transfer.

#### 11.3 Overlapping Communication and Computation

Allows useful computation to continue while data is being transferred.

Non-blocking MPI operations can help achieve this.

#### 11.4 Reducing Synchronisation

Avoids unnecessary barriers and locks.

#### 11.5 Efficient Data Partitioning

Divides data so that processors perform most operations on locally available data.

### Communication Overhead Example

Suppose a parallel program spends:

- 70 seconds on computation.
    
- 30 seconds on communication.
    

Total execution time = 100 seconds.

If communication time is reduced to 10 seconds:

New execution time = 70 + 10 = 80 seconds.

Speedup due to optimisation:

$$$$Speedup = \frac{100}{80} = 1.25$$$$

The optimisation improves execution time by 20%.

---

## 12. Benchmarking

[[Benchmarking]] is the process of measuring and comparing the performance of computer systems using standardised tests or workloads.

In HPC, benchmarking helps evaluate:

- Processor performance.
    
- Parallel processing capability.
    
- Memory performance.
    
- System scalability.
    
- Overall computing performance.
    

### Objectives of Benchmarking

- Compare supercomputers.
    
- Evaluate hardware performance.
    
- Measure parallel computing efficiency.
    
- Identify performance limitations.
    
- Track improvements after optimisation.
    

### Types of Benchmarking

1. **Synthetic Benchmarking:** Uses specially designed tests to measure particular hardware capabilities.
    
2. **Application Benchmarking:** Uses real-world applications to evaluate performance.
    
3. **Microbenchmarking:** Measures small operations, such as memory access or communication latency.
    

---

## 13. LINPACK Benchmark

[[LINPACK]] is a benchmark used to measure the floating-point computing performance of a computer system.

It measures how quickly a system solves a dense system of linear equations using numerical methods.

The benchmark is commonly used to evaluate supercomputer performance.

### Working Principle

LINPACK solves a system of linear equations:

$$AX = B$$

Where:

- A = Coefficient matrix
    
- X = Unknown vector
    
- B = Result vector
    

The performance is measured in [[FLOPS]] (Floating Point Operations Per Second).

### LINPACK and TOP500

The [[TOP500]] ranking uses the [[High Performance LINPACK (HPL)]] benchmark to rank the world's most powerful supercomputers.

Two important performance values are:

1. **Rmax:** Actual maximum performance achieved during the benchmark.
    
2. **Rpeak:** Theoretical peak computing performance of the system.
    

Performance is commonly expressed in:

- GFLOPS = 10⁹ FLOPS
    
- TFLOPS = 10¹² FLOPS
    
- PFLOPS = 10¹⁵ FLOPS
    
- EFLOPS = 10¹⁸ FLOPS
    

### Advantages

- Provides a standard performance measurement.
    
- Useful for comparing supercomputers.
    
- Measures large-scale floating-point performance.
    

### Limitations

- Focuses mainly on dense linear algebra.
    
- Does not represent every real-world workload.
    
- Performance may differ for applications with irregular memory access or communication patterns.
    

---

## 14. SPEC HPC Benchmark

[[SPEC HPC]] is a benchmark suite designed to evaluate the performance of high-performance computing systems using scientific and technical applications.

It is associated with the [[Standard Performance Evaluation Corporation (SPEC)]].

### Objectives

- Evaluate HPC system performance.
    
- Measure real-world application performance.
    
- Compare different computing platforms.
    
- Analyse parallel application scalability.
    

### Characteristics

- Uses scientific and engineering workloads.
    
- Evaluates parallel processing performance.
    
- Represents application-level computing tasks.
    
- Provides standardised benchmarking methods.
    

### Examples of HPC Workloads

- Weather forecasting.
    
- Computational fluid dynamics.
    
- Molecular modelling.
    
- Scientific simulations.
    
- Engineering applications.
    

### LINPACK vs SPEC HPC

|LINPACK|SPEC HPC|
|---|---|
|Measures floating-point performance using linear algebra|Evaluates performance using HPC application workloads|
|Uses dense matrix calculations|Uses scientific and technical applications|
|Important for TOP500 rankings|Useful for application-level evaluation|
|Focuses on numerical computation performance|Represents a broader range of HPC workloads|

---

## 15. Important Formula Sheet

| Concept                | Formula                                                  |
| ---------------------- | -------------------------------------------------------- |
| Execution Time         | $$T = T_{finish} - T_{start}$$                           |
| Throughput             | $$Throughput = \frac{Tasks}{Time}$$                      |
| Speedup                | $$S(p) = \frac{T_s}{T_p}$$                               |
| Efficiency             | $$E(p) = \frac{S(p)}{p}$$                                |
| Amdahl's Law           | $$S(p) = \frac{1}{(1-P)+\frac{P}{p}}$$                   |
| Amdahl Maximum Speedup | $$S_{max} = \frac{1}{1-P}$$                              |
| Gustafson's Law        | $$S(p) = p-\alpha(p-1)$$                                 |
| Ideal Speedup          | $$S(p) = p$$                                             |
| Ideal Efficiency       | $$E(p) = 1$$                                             |
| Cache Hit Ratio        | $$Hit\ Ratio = \frac{Hits}{Total\ Accesses}$$            |
| Cache Miss Ratio       | $$Miss\ Ratio = 1-Hit\ Ratio$$                           |
| AMAT                   | $$AMAT = Hit\ Time + (Miss\ Rate \times Miss\ Penalty)$$ |

---

## 16. Important Comparisons for Examinations

### Amdahl's Law vs Gustafson's Law

|Amdahl's Law|Gustafson's Law|
|---|---|
|Fixed problem size|Scaled problem size|
|Limits speedup due to serial portion|Analyses speedup as workload increases|
|Focuses on fixed workload|Focuses on larger workloads|

### Strong Scaling vs Weak Scaling

|Strong Scaling|Weak Scaling|
|---|---|
|Fixed problem size|Increasing problem size|
|More processors reduce execution time|More processors handle more work|
|Measures time reduction|Measures scalability for growing workloads|

### Static vs Dynamic Load Balancing

|Static|Dynamic|
|---|---|
|Fixed task assignment|Runtime task assignment|
|Low overhead|Higher overhead|
|Predictable workloads|Unpredictable workloads|

### LINPACK vs SPEC HPC

|LINPACK|SPEC HPC|
|---|---|
|Dense linear algebra benchmark|Application-based benchmark|
|Measures floating-point performance|Measures HPC application performance|
|Used in TOP500|Used for application-level comparison|

---

## 17. Important Examination Questions

### 2-Mark Questions

1. Define performance analysis.
    
2. What is execution time?
    
3. Define throughput and latency.
    
4. What is speedup in parallel computing?
    
5. Define parallel efficiency.
    
6. State Amdahl's Law.
    
7. State Gustafson's Law.
    
8. What is scalability?
    
9. Differentiate strong scaling and weak scaling.
    
10. Define load balancing.
    
11. What is profiling?
    
12. What is a performance bottleneck?
    
13. Define cache hit and cache miss.
    
14. What is communication overhead?
    
15. What is benchmarking?
    
16. What is LINPACK?
    
17. What is SPEC HPC?
    
18. Define Rmax and Rpeak.
    

### 5-Mark Questions

1. Explain the different performance metrics used in HPC.
    
2. Explain Amdahl's Law with a numerical example.
    
3. Explain Gustafson's Law with a numerical example.
    
4. Differentiate Amdahl's Law and Gustafson's Law.
    
5. Explain strong scaling and weak scaling.
    
6. Describe static and dynamic load balancing.
    
7. Explain profiling tools and their importance.
    
8. Discuss different types of performance bottlenecks.
    
9. Explain cache optimisation techniques.
    
10. Describe memory access optimisation techniques.
    
11. Explain methods of reducing communication overhead.
    
12. Compare LINPACK and SPEC HPC benchmarks.
    

### 10-Mark Questions

1. Explain performance metrics in parallel computing, including execution time, throughput, latency, speedup, and efficiency.
    
2. Explain Amdahl's Law and Gustafson's Law with suitable numerical examples and comparisons.
    
3. Discuss scalability analysis and explain strong and weak scaling.
    
4. Explain load balancing techniques and their importance in parallel computing.
    
5. Discuss profiling, bottleneck identification, and performance optimisation techniques.
    
6. Explain cache optimisation and memory access optimisation with suitable examples.
    
7. Explain communication overhead and discuss techniques to reduce it.
    
8. Explain LINPACK and SPEC HPC benchmarks and compare their applications.
    

---

## 18. Quick Revision

|Topic|Key Point|
|---|---|
|Performance Analysis|Measures system and program performance|
|Execution Time|Total time to complete a task|
|Throughput|Tasks completed per unit time|
|Latency|Time taken for one operation|
|Speedup|Sequential time divided by parallel time|
|Efficiency|Speedup divided by processor count|
|Amdahl's Law|Fixed-size problem; serial portion limits speedup|
|Gustafson's Law|Larger problem sizes can benefit from more processors|
|Strong Scaling|Fixed workload, more processors|
|Weak Scaling|Workload increases with processor count|
|Load Balancing|Distributes work evenly|
|Profiling|Measures program resource usage|
|Bottleneck|Component limiting performance|
|Cache Optimisation|Improves cache utilisation|
|Memory Optimisation|Reduces memory access overhead|
|Communication Overhead|Time spent exchanging data|
|LINPACK|Dense linear algebra benchmark|
|SPEC HPC|Scientific application benchmark|

## 19. Conclusion

Performance analysis and optimisation are essential parts of [[High Performance Computing]]. They help evaluate how efficiently processors, memory, and communication resources are used.

Concepts such as [[Amdahl's Law]], [[Gustafson's Law]], [[Scalability]], and [[Load Balancing]] help understand the behaviour of parallel systems. Profiling, cache optimisation, memory access optimisation, and communication overhead reduction improve program performance.

Finally, benchmarks such as [[LINPACK]] and [[SPEC HPC]] provide standardised methods for evaluating and comparing HPC systems.