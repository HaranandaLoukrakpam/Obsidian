# [[Fundamentals of HPC and Parallel Architectures]]

---

# [[Introduction to High Performance Computing]]

## Definition

**High Performance Computing (HPC)** is the use of powerful computers, clusters, and parallel processing techniques to solve computational problems that require extremely high processing power, large memory capacity, and fast data communication.

Unlike traditional computers that execute tasks sequentially, HPC systems execute multiple computations simultaneously using thousands or even millions of processor cores.

HPC is commonly used in:

- Scientific research
    
- Artificial Intelligence and Machine Learning
    
- Weather forecasting
    
- Climate modeling
    
- Space exploration
    
- Genomics and bioinformatics
    
- Financial simulations
    
- Cryptography
    
- Engineering simulations
    
- Oil and gas exploration
    

---

## Characteristics of HPC

- Massive computational power
    
- Parallel execution of tasks
    
- High-speed networking
    
- Large memory capacity
    
- Scalability
    
- High reliability
    
- Efficient resource utilization
    

---

## Goals of HPC

- Reduce computation time
    
- Solve larger and more complex problems
    
- Increase simulation accuracy
    
- Improve throughput
    
- Handle massive datasets
    

---

## Components of an HPC System

- Compute Nodes
    
- CPUs
    
- GPUs
    
- High-speed Interconnect
    
- Storage Systems
    
- Scheduling Software
    
- Parallel Programming Frameworks (MPI, OpenMP, CUDA)
    

---

# [[Need for HPC in Modern Computing]]

Modern applications generate enormous amounts of data and require immense computational power. Traditional sequential computers are no longer sufficient.

---

## Reasons HPC is Needed

### Scientific Simulations

Examples:

- Earthquake prediction
    
- Molecular dynamics
    
- Astrophysics
    
- Nuclear research
    

---

### Artificial Intelligence

Training large language models and deep neural networks requires:

- Thousands of GPUs
    
- Massive datasets
    
- Parallel computation
    

---

### Big Data Analytics

Organizations analyze petabytes of data for:

- Business intelligence
    
- Fraud detection
    
- Customer analytics
    

---

### Weather Forecasting

Weather models solve millions of mathematical equations every second.

Without HPC:

- Forecasts become inaccurate
    
- Processing would take days
    

---

### Medical Research

Applications include:

- DNA sequencing
    
- Drug discovery
    
- Protein folding
    
- Disease modeling
    

---

### Engineering Design

Used for:

- Aircraft simulation
    
- Automotive crash testing
    
- Structural analysis
    
- Computational Fluid Dynamics (CFD)
    

---

### Entertainment

HPC accelerates:

- Movie rendering
    
- Game physics
    
- Visual effects
    
- Animation
    

---

## Benefits of HPC

- Faster execution
    
- Better accuracy
    
- Reduced development time
    
- Energy-efficient large-scale computing
    
- Solves problems impossible for conventional computers
    

---

# [[Flynn's Classification]]

Flynn's Taxonomy classifies computer architectures based on the number of instruction streams and data streams.

|Architecture|Instruction Stream|Data Stream|
|---|---|---|
|SISD|Single|Single|
|SIMD|Single|Multiple|
|MISD|Multiple|Single|
|MIMD|Multiple|Multiple|

---

# [[SISD]]

**Single Instruction Single Data**

One processor executes one instruction on one data item at a time.

### Characteristics

- Sequential execution
    
- No parallelism
    
- Traditional von Neumann architecture
    

### Advantages

- Simple design
    
- Easy programming
    
- Low hardware complexity
    

### Disadvantages

- Slow for computationally intensive tasks
    
- Poor scalability
    

### Examples

- Traditional desktop processors (single-core execution)
    
- Basic microcontrollers
    

---

# [[SIMD]]

**Single Instruction Multiple Data**

One instruction operates simultaneously on multiple data elements.

Ideal for repetitive operations on large datasets.

---

### Characteristics

- Same instruction
    
- Different data elements
    
- Data parallelism
    

---

### Applications

- Image processing
    
- Video encoding
    
- Matrix multiplication
    
- Machine Learning
    
- Graphics rendering
    

---

### Advantages

- High throughput
    
- Efficient for vector operations
    
- Lower execution time
    

---

### Disadvantages

- Less effective for irregular computations
    
- Branch divergence reduces efficiency
    

---

### Examples

- GPU architectures
    
- Intel AVX
    
- ARM NEON
    
- NVIDIA CUDA cores
    

---

# [[MISD]]

**Multiple Instruction Single Data**

Multiple processors perform different operations on the same data.

Very rare in practical systems.

---

### Characteristics

- Multiple algorithms
    
- Same input data
    
- Fault tolerance
    

---

### Applications

- Spacecraft systems
    
- Safety-critical computing
    
- Redundant control systems
    

---

### Advantages

- High reliability
    
- Fault detection
    
- Increased safety
    

---

### Disadvantages

- Expensive
    
- Rarely used
    
- Complex implementation
    

---

# [[MIMD]]

**Multiple Instruction Multiple Data**

Multiple processors execute different instructions on different data independently.

Most modern HPC systems use MIMD architecture.

---

### Characteristics

- Independent processors
    
- Independent memory
    
- Supports multitasking
    
- Highly scalable
    

---

### Applications

- Supercomputers
    
- Cloud computing
    
- Distributed systems
    
- HPC clusters
    

---

### Advantages

- Excellent scalability
    
- Flexible
    
- Supports heterogeneous workloads
    

---

### Disadvantages

- Synchronization overhead
    
- Communication latency
    
- More complex programming
    

---

# [[Types of Parallelism]]

Parallelism refers to performing multiple operations simultaneously.

Major types:

- Data Parallelism
    
- Task Parallelism
    
- Instruction Level Parallelism
    

---

# [[Data Parallelism]]

Same operation is performed on multiple pieces of data simultaneously.

---

### Example

Adding two vectors:

Instead of processing one element at a time,

```
A1+B1
A2+B2
A3+B3
A4+B4
```

all additions occur simultaneously.

---

### Characteristics

- Same instruction
    
- Different data
    
- Excellent scalability
    

---

### Applications

- Machine Learning
    
- Matrix multiplication
    
- Image processing
    
- Video rendering
    

---

### Advantages

- Simple to scale
    
- High efficiency
    
- Excellent GPU performance
    

---

# [[Task Parallelism]]

Different processors perform different tasks simultaneously.

---

### Example

A web browser:

Core 1:

- Rendering webpage
    

Core 2:

- Downloading images
    

Core 3:

- Running JavaScript
    

Core 4:

- Audio playback
    

---

### Characteristics

- Different instructions
    
- Independent tasks
    
- Workload distribution
    

---

### Applications

- Operating Systems
    
- Web servers
    
- Databases
    
- Distributed applications
    

---

### Advantages

- Better CPU utilization
    
- Flexible execution
    
- Reduced idle time
    

---

# [[Instruction Level Parallelism]]

Instruction Level Parallelism (ILP) executes multiple CPU instructions simultaneously.

Implemented inside modern processors.

---

## Techniques

### Instruction Pipelining

Different stages execute simultaneously.

Example:

- Fetch
    
- Decode
    
- Execute
    
- Memory Access
    
- Write Back
    

Multiple instructions occupy different stages at the same time.

---

### Superscalar Execution

CPU executes multiple instructions per clock cycle.

---

### Out-of-Order Execution

CPU rearranges independent instructions to improve performance.

---

### Speculative Execution

Processor predicts branch outcomes before they occur.

---

### Advantages

- Faster execution
    
- Better CPU utilization
    
- No programmer intervention
    

---

# [[Multicore and Manycore Processors]]

Modern processors contain multiple processing cores.

---

# [[Multicore Processor]]

Contains a small number of powerful CPU cores.

Usually:

- 2 cores
    
- 4 cores
    
- 8 cores
    
- 16 cores
    
- 32 cores
    

---

### Characteristics

- High clock speed
    
- Complex cores
    
- Shared cache
    

---

### Applications

- Personal computers
    
- Laptops
    
- Servers
    

---

# [[Manycore Processor]]

Contains dozens, hundreds, or even thousands of simpler cores.

---

### Characteristics

- Massive parallelism
    
- Lower power per core
    
- Optimized for throughput
    

---

### Examples

- NVIDIA GPUs
    
- AMD GPUs
    
- Intel Xeon Phi (legacy)
    
- AI accelerators
    

---

## Multicore vs Manycore

|Feature|Multicore|Manycore|
|---|---|---|
|Number of cores|Few|Hundreds/Thousands|
|Core complexity|Powerful|Simpler|
|Best for|General computing|Parallel workloads|
|Examples|Intel Core, AMD Ryzen|NVIDIA GPU|

---

# [[Memory Hierarchy]]

Memory hierarchy organizes storage based on speed, size, and cost.

As speed increases:

- Capacity decreases
    
- Cost per bit increases
    

---

## Levels

```
CPU Registers
        ↓
L1 Cache
        ↓
L2 Cache
        ↓
L3 Cache
        ↓
Main Memory (RAM)
        ↓
SSD/HDD
```

---

## Importance

Memory hierarchy reduces average memory access time.

Programs run faster because frequently accessed data stays close to the processor.

---

# [[Cache Memory]]

Cache is a small, extremely fast memory between CPU and RAM.

---

## Purpose

Reduce memory access latency.

---

## Cache Levels

### L1 Cache

- Fastest
    
- Smallest
    
- Private to each core
    

---

### L2 Cache

- Larger
    
- Slightly slower
    

---

### L3 Cache

- Shared among CPU cores
    
- Much larger
    

---

## Cache Concepts

### Cache Hit

Requested data is found in cache.

Fast access.

---

### Cache Miss

Requested data is absent.

CPU must fetch from RAM.

Higher latency.

---

### Locality of Reference

#### Temporal Locality

Recently used data is likely to be used again.

---

#### Spatial Locality

Nearby memory locations are likely to be accessed soon.

---

# [[Shared Memory Systems]]

All processors access the same physical memory.

```
CPU1
CPU2
CPU3
   |
Shared RAM
```

---

## Advantages

- Easy programming
    
- Fast communication
    
- Shared variables
    

---

## Disadvantages

- Limited scalability
    
- Memory contention
    
- Synchronization issues
    

---

## Examples

- Multicore processors
    
- Symmetric Multiprocessing (SMP)
    

---

# [[Distributed Memory Systems]]

Each processor has its own private memory.

Processors communicate through a network.

```
CPU1 → Memory1

CPU2 → Memory2

CPU3 → Memory3
```

Communication occurs using message passing.

---

## Advantages

- Excellent scalability
    
- Large memory capacity
    
- High performance
    

---

## Disadvantages

- Programming complexity
    
- Communication overhead
    

---

## Communication Library

MPI (Message Passing Interface)

---

# [[Shared Memory vs Distributed Memory]]

|Feature|Shared Memory|Distributed Memory|
|---|---|---|
|Memory|Common|Separate|
|Communication|Shared variables|Message passing|
|Scalability|Limited|Very high|
|Complexity|Easier|Harder|
|Example|Multicore CPU|HPC Cluster|

---

# [[Interconnection Networks]]

Interconnection networks connect processors and memory in parallel systems.

Their purpose is to enable fast data transfer.

---

## Characteristics

- Low latency
    
- High bandwidth
    
- Reliability
    
- Scalability
    

---

## Common Network Topologies

### Bus

- Simple
    
- Low cost
    
- Limited scalability
    

---

### Ring

Each processor connects to two neighbors.

Advantages:

- Simple implementation
    

Disadvantages:

- Higher communication delay
    

---

### Star

Central switch connects every node.

Advantages:

- Easy management
    

Disadvantages:

- Single point of failure
    

---

### Mesh

Processors arranged in a grid.

Advantages:

- Scalable
    
- Fault tolerant
    

Applications:

- Supercomputers
    

---

### Torus

Similar to mesh but edge nodes wrap around.

Advantages:

- Lower communication latency
    

---

### Hypercube

Nodes connected in multiple dimensions.

Advantages:

- Excellent scalability
    

Used in early parallel computers.

---

# [[Overview of Supercomputers]]

Supercomputers are the world's fastest computers designed for extremely demanding computational tasks.

Performance is measured in:

**FLOPS**

(Floating Point Operations Per Second)

Examples:

- GFLOPS = 10⁹ FLOPS
    
- TFLOPS = 10¹² FLOPS
    
- PFLOPS = 10¹⁵ FLOPS
    
- EFLOPS = 10¹⁸ FLOPS
    

---

## Characteristics

- Millions of processor cores
    
- Massive memory
    
- High-speed interconnects
    
- Parallel file systems
    
- Efficient cooling
    
- Huge power consumption
    

---

## Applications

- Weather prediction
    
- AI model training
    
- Drug discovery
    
- Nuclear simulations
    
- Astrophysics
    
- Quantum simulations
    
- National security
    
- Space research
    

---

## Components

- Compute Nodes
    
- Login Nodes
    
- Storage Nodes
    
- High-speed Network
    
- Job Scheduler
    
- Parallel File System
    

---

## Programming Models

- MPI
    
- OpenMP
    
- CUDA
    
- OpenCL
    
- OpenACC
    

---

# [[Top500 Systems]]

The **Top500** is a globally recognized ranking of the world's 500 fastest supercomputers.

The list is published **twice each year**:

- June
    
- November
    

---

## Benchmark Used

The primary benchmark is **LINPACK**, which measures floating-point computation performance.

Performance is reported in FLOPS.

---

## Evaluation Criteria

- LINPACK performance
    
- Peak performance
    
- Number of processors
    
- Memory
    
- Energy efficiency
    
- Network architecture
    

---

## Importance of the Top500 List

- Tracks advances in HPC technology
    
- Encourages innovation in processor and interconnect design
    
- Helps governments and research institutions compare computational capability
    
- Highlights trends such as GPU acceleration and exascale computing
    

---

## Examples of Modern Top500 Systems

- El Capitan (USA)
    
- Frontier (USA)
    
- Aurora (USA)
    
- Fugaku (Japan)
    

_(The exact rankings change over time as new Top500 lists are released.)_

---

# [[Key Terms]]

|Term|Meaning|
|---|---|
|HPC|High Performance Computing|
|CPU|Central Processing Unit|
|GPU|Graphics Processing Unit|
|FLOPS|Floating Point Operations Per Second|
|MPI|Message Passing Interface|
|OpenMP|Shared-memory parallel programming API|
|SIMD|Single Instruction Multiple Data|
|MIMD|Multiple Instruction Multiple Data|
|Cache Hit|Requested data found in cache|
|Cache Miss|Requested data not found in cache|
|Multicore|Processor with a small number of powerful cores|
|Manycore|Processor with hundreds or thousands of simpler cores|
|ILP|Instruction Level Parallelism|
|Top500|Ranking of the world's 500 fastest supercomputers|

---

# [[Exam Tips]]

### Frequently Asked Theory Questions

1. Define High Performance Computing (HPC).
    
2. Explain the need for HPC in modern computing.
    
3. Describe Flynn's Classification with suitable examples.
    
4. Differentiate between SISD, SIMD, MISD, and MIMD architectures.
    
5. Explain Data Parallelism, Task Parallelism, and Instruction Level Parallelism.
    
6. Compare Multicore and Manycore processors.
    
7. Explain the Memory Hierarchy with a neat diagram.
    
8. Define Cache Memory and explain cache hits, misses, and locality of reference.
    
9. Differentiate Shared Memory and Distributed Memory systems.
    
10. Explain common Interconnection Network topologies.
    
11. Describe the architecture and applications of supercomputers.
    
12. What is the Top500 list? Explain its purpose and benchmarking methodology.