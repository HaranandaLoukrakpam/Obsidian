# 1. Introduction to High Performance Computing (HPC)

## 1.1 Definition of High Performance Computing

[[High Performance Computing (HPC)]] refers to the use of powerful computing systems and parallel processing techniques to solve complex computational problems at very high speeds.

HPC combines multiple processors, large memory systems, high-speed interconnections and specialised software to perform calculations that would take a conventional computer an extremely long time to complete.

HPC systems are designed to process large volumes of data and execute complex operations efficiently by dividing a problem into smaller tasks and processing them simultaneously.

**Example:**

- Weather forecasting requires processing enormous amounts of atmospheric data.
    
- Scientific simulations require millions or billions of mathematical calculations.
    
- Artificial Intelligence requires processing large datasets during model training.
    

## 1.2 Characteristics of HPC

The major characteristics of High Performance Computing are:

1. **High Processing Speed:** Performs billions or trillions of calculations per second.
    
2. **Parallel Processing:** Multiple processors execute different parts of a problem simultaneously.
    
3. **Large Memory Capacity:** Handles massive datasets and computational workloads.
    
4. **High-Speed Communication:** Uses fast interconnection networks for communication between processors.
    
5. **Scalability:** Computing capacity can be increased by adding more processors or computing nodes.
    
6. **High Reliability:** Designed to support long-running computational tasks.
    
7. **High Data Throughput:** Processes and transfers large quantities of data efficiently.
    

## 1.3 Units of Computing Performance

HPC performance is commonly measured in [[FLOPS (Floating Point Operations Per Second)]], which represents the number of floating-point calculations a computer can perform in one second.

|Unit|Meaning|
|---|---|
|FLOPS|Floating-point operations per second|
|KFLOPS|Thousand FLOPS|
|MFLOPS|Million FLOPS|
|GFLOPS|Billion FLOPS|
|TFLOPS|Trillion FLOPS|
|PFLOPS|Quadrillion FLOPS|
|EFLOPS|Quintillion FLOPS|

**Example:**

A computer capable of performing 1 TFLOPS can theoretically perform one trillion floating-point operations per second.

## 1.4 Difference Between Traditional Computing and HPC

|Traditional Computing|High Performance Computing|
|---|---|
|Usually uses a single computer system.|Uses multiple processors or computing nodes.|
|Designed for general-purpose tasks.|Designed for computationally intensive tasks.|
|Relatively lower processing capacity.|Extremely high processing capacity.|
|Limited scalability.|Highly scalable architecture.|
|Usually handles moderate datasets.|Handles massive datasets.|
|Examples: Desktop PCs and laptops.|Examples: Supercomputers and HPC clusters.|

---

# 2. Need for HPC in Modern Computing

## 2.1 Why is HPC Required?

Modern scientific, industrial and technological applications generate enormous amounts of data and require complex calculations.

Traditional computers may take days, months or even years to solve certain computational problems. HPC reduces this execution time by distributing computations across multiple processors.

The need for HPC has increased because of:

1. **Big Data Processing:** Modern applications generate massive datasets that require high-speed processing.
    
2. **Artificial Intelligence:** Training deep learning models requires millions or billions of mathematical operations.
    
3. **Scientific Research:** Scientific simulations require complex mathematical calculations.
    
4. **Weather Forecasting:** Atmospheric conditions must be simulated using large numerical models.
    
5. **Medical Research:** Genomic analysis and drug discovery require intensive computation.
    
6. **Financial Modelling:** Financial institutions use computational models to analyse market risks and predict possible outcomes.
    
7. **Engineering Simulations:** Aerospace, automobile and structural engineering use simulations to test designs.
    
8. **Real-Time Processing:** Certain applications require results within strict time constraints.
    

## 2.2 Applications of HPC

### A. Weather Forecasting

HPC processes atmospheric data such as temperature, pressure, humidity and wind speed to predict weather conditions.

### B. Artificial Intelligence and Machine Learning

HPC accelerates the training of machine learning and deep learning models using parallel processing and GPUs.

### C. Healthcare and Bioinformatics

HPC is used for DNA sequencing, protein structure prediction, medical imaging and drug discovery.

### D. Financial Services

HPC performs financial simulations, portfolio optimisation, risk assessment and algorithmic trading analysis.

### E. Space Research

Space agencies use HPC for spacecraft simulations, astronomical research and analysing satellite data.

### F. Engineering and Manufacturing

HPC is used in computational fluid dynamics (CFD), structural analysis and automobile crash simulations.

## 2.3 Advantages of HPC

- Faster execution of complex computations.
    
- Ability to process massive datasets.
    
- Improved accuracy of scientific simulations through more detailed models.
    
- Supports advanced research and innovation.
    
- Reduces the time required for complex experiments.
    
- Enables large-scale AI and machine learning applications.
    

## 2.4 Limitations of HPC

- High installation and maintenance costs.
    
- Requires specialised hardware and software.
    
- High electricity consumption and cooling requirements.
    
- Complex programming and system administration.
    
- Communication overhead between processors.
    
- Not every problem can be efficiently parallelised.
    

---

# 3. Flynn's Classification of Computer Architectures

## 3.1 Introduction

[[Flynn's Classification]] is a classification system introduced by [[Michael J. Flynn]] in 1966.

It categorises computer architectures based on the number of simultaneous instruction streams and data streams processed by a computer system.

An **instruction stream** represents a sequence of instructions executed by a processor.

A **data stream** represents the sequence of data processed by those instructions.

Flynn's classification contains four categories:

1. [[SISD (Single Instruction Single Data)]]
    
2. [[SIMD (Single Instruction Multiple Data)]]
    
3. [[MISD (Multiple Instruction Single Data)]]
    
4. [[MIMD (Multiple Instruction Multiple Data)]]
    

## 3.2 SISD – Single Instruction Single Data

### Definition

[[SISD]] is a computer architecture in which a single processor executes one instruction stream on one data stream at a time.

It follows the traditional sequential processing model, where instructions are executed one after another.

### Working

1. The processor fetches an instruction from memory.
    
2. It decodes the instruction.
    
3. It processes a single data item.
    
4. The result is stored in memory.
    
5. The next instruction is executed.
    

### Diagram

```
       Instruction Stream
               |
               v
        +--------------+
        |   Processor  |
        +--------------+
               |
               v
           Data Stream
               |
               v
            Output
```

### Example

A traditional single-core computer executing a sequential program.

### Characteristics

- One processor.
    
- One instruction stream.
    
- One data stream.
    
- Sequential execution.
    
- Simple architecture.
    

### Advantages

- Simple design and implementation.
    
- Easy to program.
    
- Suitable for sequential applications.
    

### Disadvantages

- Limited processing speed.
    
- Cannot exploit multiple processing units.
    
- Inefficient for large computational problems.
    

## 3.3 SIMD – Single Instruction Multiple Data

### Definition

[[SIMD]] is a computer architecture in which a single instruction is executed simultaneously on multiple data elements using multiple processing elements.

It is commonly used in data-parallel applications.

### Working

1. A single control unit generates an instruction.
    
2. The same instruction is distributed to multiple processing elements.
    
3. Each processing element operates on different data.
    
4. Results are generated simultaneously.
    

### Diagram

```
          Single Instruction
                  |
                  v
            +-----------+
            | Control   |
            |   Unit    |
            +-----------+
                  |
       +----------+----------+
       |          |          |
       v          v          v
   +-------+  +-------+  +-------+
   | PE 1  |  | PE 2  |  | PE 3  |
   +-------+  +-------+  +-------+
       |          |          |
       v          v          v
     Data 1     Data 2     Data 3
       |          |          |
       v          v          v
    Result 1   Result 2   Result 3
```

### Example

Suppose we have two arrays:

A = [1, 2, 3, 4]

B = [5, 6, 7, 8]

We want to add corresponding elements.

A SIMD processor performs the same addition instruction across multiple data elements:

A + B = [6, 8, 10, 12]

### Applications

- Image processing.
    
- Scientific calculations.
    
- Graphics processing.
    
- Matrix operations.
    
- Vector processing.
    
- Multimedia applications.
    

### Advantages

- High data-processing speed.
    
- Efficient for repetitive calculations.
    
- Reduces instruction overhead.
    
- Suitable for large-scale numerical operations.
    

### Disadvantages

- Not suitable for every type of problem.
    
- Less efficient when different data elements require different instructions.
    
- Conditional operations can reduce efficiency.
    

## 3.4 MISD – Multiple Instruction Single Data

### Definition

[[MISD]] is a computer architecture in which multiple processing units execute different instruction streams on the same data stream.

It is a relatively uncommon architecture in general-purpose computing.

### Working

1. A single data stream is supplied to multiple processing units.
    
2. Each processing unit executes a different instruction.
    
3. Different processing operations are performed on the same input data.
    
4. The outputs can be compared or combined.
    

### Diagram

```
              Single Data Stream
                      |
          +-----------+-----------+
          |           |           |
          v           v           v
      +-------+   +-------+   +-------+
      |  PE 1 |   |  PE 2 |   |  PE 3 |
      +-------+   +-------+   +-------+
          ^           ^           ^
          |           |           |
       Instr. 1    Instr. 2    Instr. 3
          |           |           |
          +-----------+-----------+
                      |
                      v
                   Results
```

### Example

A fault-tolerant system may process the same sensor input through different computational algorithms to detect errors or verify results.

### Applications

- Fault-tolerant computing.
    
- Certain safety-critical systems.
    
- Redundant signal processing.
    

### Advantages

- Can improve reliability through independent processing.
    
- Useful for fault detection.
    
- Supports multiple analytical operations on the same input.
    

### Disadvantages

- Complex architecture.
    
- Expensive implementation.
    
- Limited practical applications.
    
- Difficult to design and manage.
    

## 3.5 MIMD – Multiple Instruction Multiple Data

### Definition

[[MIMD]] is a computer architecture in which multiple processors execute different instruction streams on different data streams simultaneously.

Each processor can operate independently and perform different tasks.

### Working

1. Multiple processors receive separate instructions.
    
2. Each processor works on its own data.
    
3. Processors execute different operations simultaneously.
    
4. Results are produced independently or combined when required.
    

### Diagram

```
     +----------+    +----------+    +----------+
     |Processor1|    |Processor2|    |Processor3|
     +----------+    +----------+    +----------+
          |               |               |
     Instruction 1  Instruction 2  Instruction 3
          |               |               |
        Data 1          Data 2          Data 3
          |               |               |
          v               v               v
       Result 1        Result 2        Result 3
```

### Example

A multicore processor running:

- A browser on one core.
    
- A music player on another core.
    
- A background application on another core.
    

### Applications

- Multicore computers.
    
- Supercomputers.
    
- HPC clusters.
    
- Distributed computing.
    
- Servers.
    

### Advantages

- Supports independent parallel tasks.
    
- High computational performance.
    
- Flexible architecture.
    
- Suitable for complex applications.
    
- Can scale by adding processors.
    

### Disadvantages

- Complex programming.
    
- Synchronisation is required.
    
- Communication overhead may occur.
    
- Race conditions and deadlocks can arise.
    

## 3.6 Comparison of Flynn's Four Architectures

|Feature|SISD|SIMD|MISD|MIMD|
|---|---|---|---|---|
|Instruction streams|Single|Single|Multiple|Multiple|
|Data streams|Single|Multiple|Single|Multiple|
|Processing|Sequential|Data parallel|Different operations on same data|Independent parallel tasks|
|Processors|One|Multiple processing elements|Multiple|Multiple|
|Example|Traditional single-core CPU|Vector processor|Fault-tolerant processing|Multicore CPU|
|Usage|General sequential tasks|Image and matrix processing|Specialised systems|HPC and distributed systems|

**Important examination point:** SIMD and MIMD are especially important in parallel computing. SISD represents conventional sequential computing, while MISD is comparatively rare.

---

# 4. Types of Parallelism

## 4.1 Definition of Parallelism

[[Parallelism]] is the ability of a computer system to execute multiple operations or tasks simultaneously to reduce execution time and improve performance.

A large computational problem can be divided into smaller independent parts that are processed concurrently.

The three major types covered in this syllabus are:

1. [[Data Parallelism]]
    
2. [[Task Parallelism]]
    
3. [[Instruction Level Parallelism (ILP)]]
    

## 4.2 Data Parallelism

### Definition

[[Data Parallelism]] is a parallel computing technique in which the same operation is performed simultaneously on different portions of a dataset.

The data is divided into smaller parts, and multiple processing units perform the same computation on different portions.

### Working

1. Divide a large dataset into smaller sections.
    
2. Assign each section to a different processor.
    
3. Execute the same instruction on all sections.
    
4. Combine the results if required.
    

### Example

Adding two arrays:

```
A = [1, 2, 3, 4]
B = [5, 6, 7, 8]

Processor 1: 1 + 5 = 6
Processor 2: 2 + 6 = 8
Processor 3: 3 + 7 = 10
Processor 4: 4 + 8 = 12

Result = [6, 8, 10, 12]
```

### Applications

- Image processing.
    
- Matrix multiplication.
    
- Scientific simulations.
    
- Machine learning.
    
- GPU computing.
    

### Advantages

- Efficient processing of large datasets.
    
- High throughput.
    
- Easy to apply to repetitive operations.
    

### Disadvantages

- Requires divisible datasets.
    
- Data dependencies may limit parallel execution.
    
- Communication and synchronisation may be required.
    

## 4.3 Task Parallelism

### Definition

[[Task Parallelism]] is a parallel computing technique in which different processors execute different tasks or operations simultaneously.

Unlike data parallelism, where the same operation is performed on different data, task parallelism involves executing different operations.

### Working

1. Divide a program into independent tasks.
    
2. Assign different tasks to different processors.
    
3. Execute the tasks simultaneously.
    
4. Combine their outputs when necessary.
    

### Example

In a multimedia application:

```
Processor 1 -> Audio Processing
Processor 2 -> Video Processing
Processor 3 -> User Interface
Processor 4 -> File Management
```

All tasks can execute concurrently.

### Applications

- Web servers.
    
- Multimedia applications.
    
- Operating systems.
    
- Scientific applications.
    
- Multitasking environments.
    

### Advantages

- Different operations can execute simultaneously.
    
- Improves overall system utilisation.
    
- Suitable for independent workloads.
    

### Disadvantages

- Task dependencies may restrict execution.
    
- Scheduling can become complicated.
    
- Synchronisation may be necessary.
    

## 4.4 Instruction Level Parallelism (ILP)

### Definition

[[Instruction Level Parallelism (ILP)]] refers to the ability of a processor to execute multiple independent instructions simultaneously or in overlapping stages within a single program.

ILP is generally achieved through processor-level techniques rather than explicitly dividing an application among separate processors.

### Techniques of ILP

**1. Pipelining**

[[Pipelining]] divides instruction execution into stages so that multiple instructions can be processed simultaneously at different stages.

Example:

```
Instruction 1: Fetch -> Decode -> Execute
Instruction 2:          Fetch -> Decode -> Execute
Instruction 3:                   Fetch -> Decode -> Execute
```

**2. Superscalar Execution**

[[Superscalar Architecture]] allows a processor to issue and execute multiple independent instructions in a single clock cycle using multiple execution units.

**3. Out-of-Order Execution**

[[Out-of-Order Execution]] allows the processor to execute independent instructions before earlier instructions that are waiting for data or other resources, while preserving the correct architectural result.

### Example

Consider:

```
A = B + C
D = E + F
G = H * I
```

These instructions are independent and may be executed simultaneously by different execution units.

### Advantages

- Improves processor utilisation.
    
- Increases instruction throughput.
    
- Reduces execution time.
    
- Does not necessarily require additional processor cores.
    

### Disadvantages

- Hardware design is complex.
    
- Data dependencies limit parallel execution.
    
- Requires dependency detection and scheduling.
    

## 4.5 Comparison of Types of Parallelism

|Feature|Data Parallelism|Task Parallelism|Instruction Level Parallelism|
|---|---|---|---|
|Main concept|Same operation on different data|Different tasks executed simultaneously|Multiple independent instructions executed concurrently|
|Focus|Data|Tasks|Instructions|
|Implementation|Multiple processing elements|Multiple threads or processors|Processor architecture|
|Example|Adding array elements|Audio and video processing|Pipelining|
|Common usage|GPUs|Multicore systems|Modern CPUs|

---

# 5. Multicore and Manycore Processors

## 5.1 Processor Core

A [[Processor Core]] is an individual processing unit within a CPU that can independently execute instructions.

A processor may contain one or multiple cores.

Each core generally has its own execution units and registers, while other resources, such as caches and memory controllers, may be shared.

## 5.2 Multicore Processors

### Definition

A [[Multicore Processor]] is a CPU that contains two or more independent processing cores integrated into a single processor chip.

Each core can execute instructions independently, allowing multiple tasks or threads to run simultaneously.

### Architecture

```
        +--------------------------------+
        |       Multicore Processor      |
        |                                |
        |  +--------+     +--------+     |
        |  | Core 1 |     | Core 2 |     |
        |  +--------+     +--------+     |
        |                                |
        |  +--------+     +--------+     |
        |  | Core 3 |     | Core 4 |     |
        |  +--------+     +--------+     |
        |                                |
        |       Shared Cache             |
        +--------------------------------+
                     |
                     v
                 Main Memory
```

### Characteristics

- Contains multiple CPU cores.
    
- Supports parallel execution.
    
- Often uses shared memory.
    
- Suitable for multitasking.
    
- Improves performance without requiring multiple separate CPU packages.
    

### Examples

Dual-core, quad-core, hexa-core and octa-core processors.

### Advantages

- Better multitasking.
    
- Increased processing performance.
    
- Improved energy efficiency compared with increasing the clock frequency indefinitely.
    
- Suitable for parallel applications.
    

### Disadvantages

- Requires parallelised software to achieve maximum benefit.
    
- Synchronisation and communication overhead.
    
- Increased chip complexity.
    
- Shared resource contention can occur.
    

## 5.3 Manycore Processors

### Definition

[[Manycore Processor]] refers to a processor architecture containing a large number of processing cores, often designed to perform highly parallel computational workloads.

Manycore systems focus on high throughput and massive parallel processing.

### Characteristics

- Contains a large number of processing cores.
    
- Designed for data-parallel and highly parallel workloads.
    
- Often provides substantial aggregate computational throughput.
    
- Commonly uses specialised memory and interconnection arrangements.
    
- Particularly useful for scientific computing and AI workloads.
    

### Example

[[GPU (Graphics Processing Unit)]] architectures contain hundreds or thousands of processing elements or cores, depending on the architecture and how cores are counted.

### Applications

- Deep learning.
    
- Scientific simulations.
    
- Image processing.
    
- Large-scale numerical computations.
    
- Graphics rendering.
    

## 5.4 Difference Between Multicore and Manycore

|Multicore|Manycore|
|---|---|
|Contains multiple processing cores.|Contains a large number of processing cores.|
|Often optimised for general-purpose computing.|Often optimised for massive parallel workloads.|
|Focuses on balanced performance.|Focuses on high parallel throughput.|
|Common in desktop and server CPUs.|Common in GPUs and specialised processors.|
|Often has more complex individual cores.|Often uses simpler or more throughput-oriented cores.|

**Important:** There is no universally fixed numerical boundary between multicore and manycore. The distinction is primarily architectural and workload-oriented.

---

# 6. Memory Hierarchy and Cache Concepts

## 6.1 Memory Hierarchy

### Definition

[[Memory Hierarchy]] is the organisation of computer storage into different levels based on speed, capacity and cost.

The purpose of memory hierarchy is to provide fast access to frequently used data while maintaining a large and affordable storage capacity.

Generally:

- Higher levels are faster, smaller and more expensive per bit.
    
- Lower levels are slower, larger and cheaper per bit.
    

### Memory Hierarchy Diagram

```
             Fastest
                |
                v
          +-----------+
          | Registers |
          +-----------+
                |
          +-----------+
          | L1 Cache  |
          +-----------+
                |
          +-----------+
          | L2 Cache  |
          +-----------+
                |
          +-----------+
          | L3 Cache  |
          +-----------+
                |
          +-----------+
          | Main RAM  |
          +-----------+
                |
          +-----------+
          | SSD / HDD |
          +-----------+
                |
                v
             Slowest
```

### Levels of Memory Hierarchy

**1. Registers**

[[Registers]] are the smallest and fastest storage locations inside a CPU. They temporarily hold instructions, addresses and data currently being processed.

**2. Cache Memory**

[[Cache Memory]] is a small, high-speed memory located inside or close to the processor. It stores frequently accessed data and instructions to reduce access time.

**3. Main Memory (RAM)**

[[RAM (Random Access Memory)]] stores programs and data currently being used by the computer. It is larger but slower than cache memory.

**4. Secondary Storage**

[[Secondary Storage]] includes SSDs and HDDs. It provides permanent storage for data and programs but is slower than RAM.

### Comparison of Memory Levels

|Memory|Speed|Capacity|Cost per bit|
|---|---|---|---|
|Registers|Highest|Very small|Highest|
|L1 Cache|Very high|Small|Very high|
|L2 Cache|High|Small/medium|High|
|L3 Cache|Lower than L2|Medium/larger|Lower|
|RAM|Moderate|Large|Lower|
|SSD/HDD|Lower|Very large|Lowest|

## 6.2 Cache Memory

### Definition

[[Cache Memory]] is a small and fast memory that stores copies of frequently or recently accessed data from main memory.

It reduces the time required by the CPU to access data and instructions.

### Why is Cache Memory Required?

The CPU operates much faster than main memory. If the CPU had to access RAM for every instruction and data item, it would frequently remain idle while waiting for memory.

Cache memory helps reduce this performance gap.

### Working of Cache Memory

1. The CPU requests data.
    
2. The cache controller checks whether the requested data is present.
    
3. If the data is present, a cache hit occurs.
    
4. If the data is absent, a cache miss occurs.
    
5. The required data is fetched from a lower memory level.
    
6. The data may be stored in the cache for future use.
    

### Cache Hit

[[Cache Hit]] occurs when the requested data is found in cache memory.

### Cache Miss

[[Cache Miss]] occurs when the requested data is not found in cache memory and must be retrieved from a lower level of memory.

### Cache Hit Ratio

The [[Cache Hit Ratio]] represents the percentage of memory accesses that are successfully served by the cache.

$$$$  $$
\text{Hit Ratio} = \frac{\text{Number of Cache Hits}}{\text{Total Memory Accesses}}  
$$

### Cache Miss Ratio

$$  
\text{Miss Ratio} = 1 - \text{Hit Ratio}  
$$

**Example:**

If a processor performs 100 memory accesses and 90 are cache hits:

$$  
\text{Hit Ratio} = \frac{90}{100} = 0.9 = 90%  
$$

Therefore, the cache hit ratio is 90%, and the miss ratio is 10%.

## 6.3 Levels of Cache Memory

**L1 Cache:**

- Closest to the CPU core.
    
- Usually the smallest cache.
    
- Generally the fastest cache.
    
- Often divided into instruction and data caches.
    

**L2 Cache:**

- Larger than L1.
    
- Usually slower than L1.
    
- May be private to a core or shared, depending on architecture.
    

**L3 Cache:**

- Usually larger than L1 and L2.
    
- Generally slower than L1 and L2.
    
- Often shared among multiple CPU cores.
    

## 6.4 Locality of Reference

[[Locality of Reference]] is the principle that programs tend to access the same memory locations or nearby memory locations repeatedly over a short period.

It is the fundamental principle behind cache memory.

There are three major types:

### 1. Temporal Locality

[[Temporal Locality]] means that if a memory location is accessed once, it is likely to be accessed again in the near future.

**Example:** Repeatedly accessing a variable inside a loop.

### 2. Spatial Locality

[[Spatial Locality]] means that if a memory location is accessed, nearby memory locations are likely to be accessed soon.

**Example:** Accessing consecutive elements of an array.

### 3. Sequential Locality

[[Sequential Locality]] refers to the tendency of programs to access memory locations in a sequential order.

**Example:** Executing consecutive instructions in a program.

## 6.5 Cache Mapping Techniques

[[Cache Mapping]] determines how blocks of main memory are placed into cache memory.

The three common techniques are:

**1. Direct Mapping**

Each block of main memory can be placed in only one specific cache line.

- Simple implementation.
    
- Fast access.
    
- May cause frequent conflicts.
    

**2. Fully Associative Mapping**

A block of main memory can be placed in any cache line.

- Flexible placement.
    
- Reduces conflict misses.
    
- Requires more complex searching hardware.
    

**3. Set-Associative Mapping**

Cache memory is divided into sets, and a memory block can be placed in any line within its assigned set.

- Combines advantages of direct and associative mapping.
    
- Common in modern processors.
    

## 6.6 Cache Coherence

[[Cache Coherence]] is the mechanism that ensures multiple cached copies of shared data remain consistent in a multiprocessor system.

For example, if two CPU cores have cached copies of the same memory location and one core modifies the value, the other core must not continue using an outdated copy.

Cache coherence protocols help maintain consistency.

Examples include [[MESI Protocol]], which uses the states Modified, Exclusive, Shared and Invalid.

## 6.7 Advantages of Cache Memory

- Reduces average memory access time.
    
- Improves CPU performance.
    
- Reduces frequent access to main memory.
    
- Exploits temporal and spatial locality.
    

## 6.8 Limitations of Cache Memory

- Limited storage capacity.
    
- More expensive per bit than RAM.
    
- Cache misses increase memory access time.
    
- Cache coherence introduces complexity in multiprocessor systems.
    

---

# 7. Shared Memory and Distributed Memory Systems

## 7.1 Shared Memory Systems

### Definition

[[Shared Memory System]] is a parallel computing architecture in which multiple processors or cores access a common address space.

Processors communicate by reading and writing shared variables stored in the common memory.

### Architecture

```
       +----------+  +----------+  +----------+
       | CPU 1    |  | CPU 2    |  | CPU 3    |
       +----------+  +----------+  +----------+
             |            |            |
             +------------+------------+
                          |
                    +-----------+
                    | Shared    |
                    | Memory    |
                    +-----------+
```

### Working

1. Multiple processors are connected to a common memory system.
    
2. Each processor executes its assigned tasks.
    
3. Processors read data from shared memory.
    
4. Processors communicate by updating shared variables.
    
5. Synchronisation mechanisms prevent conflicting memory operations.
    

### Types of Shared Memory Systems

**1. UMA – Uniform Memory Access**

[[UMA (Uniform Memory Access)]] is a shared-memory architecture in which all processors have approximately equal access time to main memory.

Characteristics:

- Equal memory access time.
    
- Simpler memory organisation.
    
- Common in traditional symmetric multiprocessor systems.
    

**2. NUMA – Non-Uniform Memory Access**

[[NUMA (Non-Uniform Memory Access)]] is a shared-address-space architecture in which memory access time depends on the location of the memory relative to the processor.

Characteristics:

- Each processor or processor group has local memory.
    
- Local memory access is generally faster.
    
- Remote memory access is generally slower.
    
- Suitable for larger multiprocessor systems.
    

### Advantages of Shared Memory Systems

- Easier communication between processors.
    
- Convenient programming model.
    
- Data can be shared through common variables.
    
- Suitable for multicore systems.
    

### Disadvantages

- Memory contention may occur.
    
- Synchronisation is required.
    
- Race conditions can occur.
    
- Scalability can be limited by shared resources.
    
- Cache coherence can become complex.
    

## 7.2 Distributed Memory Systems

### Definition

[[Distributed Memory System]] is a parallel computing architecture in which each processor or computing node has its own private memory.

Processors communicate by explicitly exchanging messages through an interconnection network.

### Architecture

```
  +-------------+       +-------------+
  | Processor 1 |       | Processor 2 |
  +-------------+       +-------------+
        |                     |
  +-------------+       +-------------+
  | Memory 1    |       | Memory 2    |
  +-------------+       +-------------+
        |                     |
        +---------+-----------+
                  |
          Interconnection
              Network
                  |
        +---------+-----------+
        |                     |
  +-------------+       +-------------+
  | Processor 3 |       | Processor 4 |
  +-------------+       +-------------+
        |                     |
  +-------------+       +-------------+
  | Memory 3    |       | Memory 4    |
  +-------------+       +-------------+
```

### Working

1. Each node has its own processor and private memory.
    
2. Each processor executes its assigned portion of the program.
    
3. A processor cannot directly access another node's private memory.
    
4. Data is exchanged through message passing.
    
5. Results are combined to complete the computation.
    

### Advantages

- Highly scalable.
    
- Each node has independent memory.
    
- Suitable for large-scale parallel applications.
    
- Adding nodes can increase computational capacity.
    
- Avoids a single globally shared memory bottleneck.
    

### Disadvantages

- Programming is more complex.
    
- Explicit communication is required.
    
- Communication overhead can occur.
    
- Data distribution must be managed carefully.
    

## 7.3 Difference Between Shared and Distributed Memory

|Shared Memory|Distributed Memory|
|---|---|
|Processors share a common address space.|Each processor has private memory.|
|Communication occurs through shared variables.|Communication occurs through message passing.|
|Easier to program initially.|Requires explicit communication management.|
|Memory contention can occur.|Network communication overhead can occur.|
|Scalability may be limited.|Generally highly scalable.|
|Common in multicore systems.|Common in HPC clusters.|
|OpenMP is commonly used.|MPI is commonly used.|

## 7.4 Hybrid Memory Architecture

[[Hybrid Memory Architecture]] combines shared-memory and distributed-memory approaches.

A typical HPC cluster contains multiple computing nodes. Each node contains multiple CPU cores sharing memory, while different nodes communicate through a network.

```
          HPC Cluster
               |
       +-------+-------+
       |               |
       v               v
   Node 1            Node 2
       |               |
  +---------+     +---------+
  | CPU Cores|     | CPU Cores|
  +---------+     +---------+
       |               |
  +---------+     +---------+
  | Shared  |     | Shared  |
  | Memory  |     | Memory  |
  +---------+     +---------+
       |               |
       +-------+-------+
               |
         Network
```

Hybrid programming commonly combines:

- [[OpenMP]] for shared-memory parallelism.
    
- [[MPI]] for distributed-memory communication.
    

---

# 8. Interconnection Networks

## 8.1 Definition

[[Interconnection Network]] refers to the communication infrastructure that connects processors, memory modules, storage devices and other components in a parallel computing system.

It enables processors and computing nodes to exchange data and coordinate their operations.

Interconnection networks are important in HPC because communication speed affects the overall performance of parallel applications.

## 8.2 Requirements of Interconnection Networks

A good interconnection network should provide:

1. **High Bandwidth:** Ability to transfer large amounts of data per second.
    
2. **Low Latency:** Minimum delay during communication.
    
3. **Scalability:** Ability to support additional processors and nodes.
    
4. **Reliability:** Consistent communication with minimal failures.
    
5. **Low Cost:** Efficient implementation and maintenance.
    
6. **High Throughput:** Ability to support multiple communications simultaneously.
    

## 8.3 Important Network Terminology

**1. Bandwidth**

[[Bandwidth]] refers to the amount of data that can be transferred through a network per unit of time.

**2. Latency**

[[Latency]] refers to the time required for data to travel from one point to another.

**3. Topology**

[[Network Topology]] refers to the physical or logical arrangement of nodes and communication links in a network.

**4. Scalability**

The ability of a network to maintain efficient communication as the number of connected nodes increases.

## 8.4 Types of Interconnection Network Topologies

### 1. Bus Topology

[[Bus Topology]] connects multiple processors or devices through a common communication bus.

```
 CPU 1      CPU 2      CPU 3
   |          |          |
===+==========+==========+===
          Common Bus
```

**Advantages:**

- Simple design.
    
- Low implementation cost.
    
- Easy to understand.
    

**Disadvantages:**

- Shared bandwidth.
    
- Bus contention.
    
- Limited scalability.
    

### 2. Ring Topology

[[Ring Topology]] connects each node to two neighbouring nodes, forming a circular communication structure.

```
       Node 1 ------ Node 2
          |             |
          |             |
       Node 4 ------ Node 3
```

**Advantages:**

- Simple connectivity.
    
- Predictable communication structure.
    
- Can support organised data transfer.
    

**Disadvantages:**

- Communication may pass through multiple nodes.
    
- Link or node failure can affect communication unless redundancy is provided.
    
- Latency can increase with the number of nodes.
    

### 3. Mesh Topology

[[Mesh Topology]] connects nodes to neighbouring nodes in a grid-like arrangement.

```
 Node 1 ----- Node 2 ----- Node 3
   |            |            |
   |            |            |
 Node 4 ----- Node 5 ----- Node 6
   |            |            |
   |            |            |
 Node 7 ----- Node 8 ----- Node 9
```

**Advantages:**

- Multiple communication paths.
    
- Good scalability for structured systems.
    
- Supports parallel communication.
    

**Disadvantages:**

- Requires more connections.
    
- Routing can be complex.
    
- Communication distance varies.
    

### 4. Tree Topology

[[Tree Topology]] organises nodes hierarchically, with parent and child connections.

```
             Node 1
            /      \
        Node 2     Node 3
        /  \       /  \
      N4   N5     N6   N7
```

**Advantages:**

- Hierarchical organisation.
    
- Easy to expand.
    
- Suitable for structured communication.
    

**Disadvantages:**

- Higher-level nodes may become bottlenecks.
    
- Failure of an upper-level node can affect multiple nodes.
    

### 5. Hypercube Topology

[[Hypercube Topology]] is a network structure in which nodes are connected according to the binary representation of their addresses.

A hypercube with N dimensions contains:
$$\text{Number of Nodes} = 2^N  
$$

Each node is connected to N neighbouring nodes.

**Examples:**

- 1-dimensional hypercube: 2 nodes.
    
- 2-dimensional hypercube: 4 nodes.
    
- 3-dimensional hypercube: 8 nodes.
    

**Advantages:**

- Multiple communication paths.
    
- Relatively low communication diameter.
    
- Supports parallel communication efficiently.
    

**Disadvantages:**

- Complex physical implementation for large systems.
    
- Number of connections increases with dimensions.
    

## 8.5 Comparison of Network Topologies

|Topology|Structure|Main Advantage|Main Disadvantage|
|---|---|---|---|
|Bus|Common shared connection|Simple and inexpensive|Limited bandwidth|
|Ring|Circular connection|Simple organisation|Multiple-hop delay|
|Mesh|Grid arrangement|Multiple paths|More connections|
|Tree|Hierarchical|Structured expansion|Upper-level bottlenecks|
|Hypercube|Binary-connected nodes|Low network diameter|Complex implementation|

---

# 9. Overview of Supercomputers

## 9.1 Definition

[[Supercomputer]] is an extremely powerful computing system designed to perform complex calculations and process massive amounts of data at very high speeds.

Supercomputers use thousands or even millions of processing elements, high-speed memory systems and advanced interconnection networks to achieve enormous computational performance.

They are primarily used for scientific research, engineering simulations, weather forecasting, national security and large-scale AI applications.

## 9.2 Characteristics of Supercomputers

1. Extremely high computational performance.
    
2. Large numbers of processors and computing nodes.
    
3. High-speed interconnection networks.
    
4. Large memory capacity.
    
5. Advanced cooling systems.
    
6. High data-transfer capabilities.
    
7. Support for parallel programming models.
    
8. High power consumption and specialised infrastructure.
    

## 9.3 Components of a Supercomputer

**1. Compute Nodes**

[[Compute Nodes]] are individual computing units containing processors, memory and other hardware components.

**2. Processing Units**

Supercomputers use CPUs and GPUs to perform calculations.

**3. Memory System**

Large memory systems store the data required for computational tasks.

**4. Interconnection Network**

Connects different computing nodes and enables fast communication.

**5. Storage System**

Provides high-capacity storage for large datasets and simulation results.

**6. Cooling System**

Removes heat generated by processors and other hardware components.

**7. Job Scheduler**

Manages computational jobs and allocates resources to users.

## 9.4 Applications of Supercomputers

- Weather and climate prediction.
    
- Space exploration.
    
- Nuclear and molecular simulations.
    
- Artificial intelligence.
    
- Genomics and biomedical research.
    
- Oil and gas exploration.
    
- Computational fluid dynamics.
    
- Financial modelling.
    

## 9.5 Examples of Supercomputers

### 1. Frontier

[[Frontier Supercomputer]] is an exascale supercomputer located at Oak Ridge National Laboratory in the United States.

It became the first publicly recognised exascale supercomputer in the TOP500 list in 2022.

### 2. Fugaku

[[Fugaku Supercomputer]] is located at RIKEN in Japan.

It was developed using Fujitsu A64FX processors and is known for scientific simulations, medical research and computational applications.

### 3. El Capitan

[[El Capitan Supercomputer]] is located at Lawrence Livermore National Laboratory in the United States.

It is an exascale-class system designed for advanced scientific and national security applications.

### 4. PARAM Siddhi-AI

[[PARAM Siddhi-AI]] is an Indian AI-focused high-performance computing system developed under the National Supercomputing Mission.

### 5. AIRAWAT

[[AIRAWAT]] is an Indian AI supercomputing infrastructure developed to support AI research and applications.

## 9.6 Advantages of Supercomputers

- Extremely high computational speed.
    
- Solves complex scientific problems.
    
- Supports large-scale simulations.
    
- Processes enormous datasets.
    
- Accelerates research and technological development.
    

## 9.7 Limitations of Supercomputers

- Extremely expensive.
    
- Requires specialised infrastructure.
    
- High electricity consumption.
    
- Requires skilled professionals.
    
- Complex maintenance and administration.
    

---

# 10. TOP500 Systems

## 10.1 Introduction to TOP500

[[TOP500]] is an international project that ranks the world's most powerful supercomputers based on their performance using the [[LINPACK Benchmark]].

The ranking is generally published twice a year:

- June
    
- November
    

TOP500 provides information about the development and performance of high-performance computing systems around the world.

## 10.2 Purpose of TOP500

1. To rank the world's most powerful supercomputers.
    
2. To measure and compare computational performance.
    
3. To track developments in HPC technology.
    
4. To study processor and system architecture trends.
    
5. To encourage improvements in high-performance computing.
    

## 10.3 LINPACK Benchmark

[[LINPACK]] is a software benchmark used to evaluate the floating-point computational performance of computers.

It measures how efficiently a computer solves a large system of dense linear equations.

The benchmark reports performance in FLOPS.

The TOP500 ranking primarily uses the High Performance LINPACK (HPL) benchmark.

### Important LINPACK Performance Measurements

**Rmax:**

[[Rmax]] represents the measured maximum performance achieved by a computer system during the LINPACK benchmark.

**Rpeak:**

[[Rpeak]] represents the theoretical peak floating-point performance of the system.

The efficiency of the system relative to its theoretical peak can be expressed as:

$$  
\text{Efficiency} = \frac{Rmax}{Rpeak} \times 100  
$$

## 10.4 Exascale Computing

[[Exascale Computing]] refers to computing systems capable of performing at least one exaFLOP, or one quintillion floating-point operations per second.

$$  
1 \text{ ExaFLOP} = 10^{18} \text{ FLOPS}  
$$

Exascale computing enables researchers to solve extremely complex scientific and industrial problems.

Examples include:

- Advanced climate modelling.
    
- Molecular simulations.
    
- Nuclear research.
    
- AI and deep learning.
    
- Large-scale scientific simulations.
    

## 10.5 Significance of TOP500

- Provides a global comparison of supercomputer performance.
    
- Helps identify technological trends.
    
- Encourages research and development.
    
- Demonstrates improvements in processor architectures.
    
- Provides information about the growth of exascale computing.
    

**Note:** TOP500 rankings change every six months. Specific rankings and system performance figures should be checked against the latest published list when required.

Official website: [https://www.top500.org/](https://www.top500.org/)

---

# 11. Important Mathematical Concepts and Formulas

Although Unit I is primarily theoretical, the following formulas help understand computing performance and architecture.

## 11.1 FLOPS

$$
\text{FLOPS} = \frac{\text{Floating Point Operations}}{\text{Execution Time}}  
$$

## 11.2 Number of Hypercube Nodes

$$$$  
N = 2^d  
$$$$

Where:

- N = Number of nodes.
    
- d = Number of dimensions.
    

## 11.3 Cache Hit Ratio

$$  
\text{Hit Ratio} = \frac{\text{Cache Hits}}{\text{Total Memory Accesses}}  
$$

## 11.4 Cache Miss Ratio

$$  
\text{Miss Ratio} = 1 - \text{Hit Ratio}  
$$

## 11.5 Average Memory Access Time

$$  
AMAT = T_{hit} + (M_r \times P_m)  
$$

Where:

- AMAT = Average Memory Access Time.
    
- T_hit = Cache hit time.
    
- M_r = Cache miss rate.
    
- P_m = Miss penalty.
    

---

# 12. Important Differences for Examinations

## 12.1 CPU vs GPU

|CPU|GPU|
|---|---|
|Central Processing Unit|Graphics Processing Unit|
|Usually contains fewer, more complex cores.|Usually contains many parallel processing elements.|
|Optimised for low-latency general-purpose tasks.|Optimised for high-throughput parallel tasks.|
|Good for sequential and diverse workloads.|Good for data-parallel workloads.|
|Commonly handles operating system tasks.|Commonly accelerates graphics, AI and simulations.|

## 12.2 Cache Memory vs RAM

|Cache Memory|RAM|
|---|---|
|Very fast memory.|Slower than cache.|
|Small capacity.|Larger capacity.|
|Expensive per bit.|Less expensive per bit.|
|Located inside or close to CPU cores.|Connected to the processor through a memory subsystem.|
|Stores frequently accessed data.|Stores currently running programs and data.|

## 12.3 Parallel Computing vs Distributed Computing

|Parallel Computing|Distributed Computing|
|---|---|
|Multiple processing units work on a problem simultaneously.|Multiple independent computers cooperate over a network.|
|Can use shared or distributed memory.|Typically uses separate memory spaces.|
|Focuses on reducing computation time.|Focuses on sharing resources and completing distributed tasks.|
|May operate within one computer.|Usually involves multiple networked computers.|

---

# 13. Important Examination Questions

## 2-Mark Questions

1. Define High Performance Computing.
    
2. What is parallel processing?
    
3. Define FLOPS.
    
4. What is Flynn's Classification?
    
5. Define SISD and SIMD.
    
6. What is MIMD architecture?
    
7. Define data parallelism.
    
8. What is task parallelism?
    
9. Define multicore processor.
    
10. What is a cache hit?
    
11. Define memory hierarchy.
    
12. What is cache coherence?
    
13. Define shared memory.
    
14. What is distributed memory?
    
15. Define interconnection network.
    
16. What is a supercomputer?
    
17. What is TOP500?
    
18. Define exascale computing.
    
19. What is NUMA?
    
20. What is locality of reference?
    

## 4–5-Mark Questions

1. Explain the need and importance of HPC in modern computing.
    
2. Explain Flynn's classification with suitable diagrams.
    
3. Differentiate between SISD, SIMD, MISD and MIMD.
    
4. Explain the three types of parallelism with examples.
    
5. Differentiate between data parallelism and task parallelism.
    
6. Explain multicore and manycore processors.
    
7. Explain memory hierarchy with a diagram.
    
8. Explain cache memory and its different levels.
    
9. Explain temporal and spatial locality.
    
10. Differentiate between shared and distributed memory systems.
    
11. Explain UMA and NUMA architectures.
    
12. Explain different interconnection network topologies.
    
13. Explain the architecture and characteristics of a supercomputer.
    
14. Explain the purpose and significance of TOP500.
    
15. Explain the LINPACK benchmark.
    

## 8–10-Mark Questions

1. Explain the fundamentals of High Performance Computing, including its need, characteristics and applications.
    
2. Discuss Flynn's classification of computer architectures with suitable diagrams, examples and comparisons.
    
3. Explain different types of parallelism and discuss their applications.
    
4. Describe multicore and manycore processor architectures with diagrams.
    
5. Explain the memory hierarchy, cache organisation, locality of reference and cache coherence.
    
6. Explain shared-memory and distributed-memory architectures with diagrams and comparisons.
    
7. Discuss various interconnection network topologies used in parallel computing.
    
8. Describe the architecture, characteristics and applications of modern supercomputers.
    
9. Explain the TOP500 project and the role of the LINPACK benchmark in evaluating supercomputer performance.
    

---

# 14. Quick Revision

|Topic|Key Point to Remember|
|---|---|
|HPC|High-speed computation using powerful parallel systems|
|Flynn's Classification|Four architectures based on instruction and data streams|
|SISD|One instruction, one data|
|SIMD|One instruction, multiple data|
|MISD|Multiple instructions, one data|
|MIMD|Multiple instructions, multiple data|
|Data Parallelism|Same operation on different data|
|Task Parallelism|Different tasks executed simultaneously|
|ILP|Multiple independent instructions executed concurrently|
|Multicore|Multiple cores in one processor|
|Manycore|Large number of processing cores|
|Memory Hierarchy|Storage arranged according to speed, capacity and cost|
|Cache|Fast memory storing frequently accessed data|
|Temporal Locality|Reuse of recently accessed data|
|Spatial Locality|Accessing nearby memory locations|
|Shared Memory|Multiple processors access common memory|
|Distributed Memory|Each node has private memory|
|UMA|Approximately equal memory access time|
|NUMA|Access time depends on memory location|
|Interconnection Network|Connects processors and computing nodes|
|Supercomputer|Extremely powerful computational system|
|TOP500|Ranks the world's most powerful supercomputers|
|LINPACK|Measures floating-point computational performance|
|Exascale|At least 10¹⁸ floating-point operations per second|

---

# 15. Conclusion

High Performance Computing plays an important role in modern computing by enabling the execution of complex computational problems at extremely high speeds.

Its foundation is based on parallel processing, different processor architectures, efficient memory organisation and high-speed interconnection networks.

Understanding Flynn's classification, types of parallelism, multicore and manycore processors, memory hierarchy, shared and distributed memory systems, and supercomputer architectures provides the foundation for studying parallel programming and performance optimisation in the following units.

**End of Chapter 1 – Fundamentals of HPC and Parallel Architectures.**