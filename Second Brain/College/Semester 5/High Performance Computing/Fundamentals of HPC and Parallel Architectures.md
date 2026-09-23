# [[High Performance Computing (HPC)]] — Unit Notes

## 1. [[Introduction to High Performance Computing]]

**[[High Performance Computing]] (HPC)** refers to the practice of aggregating computing power to perform complex computational tasks at significantly higher speeds than traditional standalone systems. Instead of relying on a single processing unit, HPC architectures coordinate multiple processors or cores running concurrently.
### Core Characteristics of HPC

- **High Computational Throughput:** Massive raw floating-point calculation performance.
    
- **[[Parallel Processing]]:** Dividing tasks across multiple compute engines.
    
- **High Memory Bandwidth & Capacity:** Substantial main and distributed memory spaces.
    
- **Low-Latency Interconnects:** Specialized high-speed communication buses between nodes.
    
- **Large-Scale Data Handling:** Efficient processing of terabyte- to petabyte-scale datasets.
    
- **Target Workloads:** Highly compute-intensive and simulation-heavy workloads.
### Primary Application Domains

- **[[Weather Forecasting]] & [[Climate Modelling]]:** Atmospheric fluid dynamics, global circulation tracking.
    
- **[[Artificial Intelligence]] & [[Machine Learning]]:** Distributed deep neural network training.
    
- **Computational Biology & Drug Discovery:** Molecular dynamics, protein folding simulations.
    
- **Astrophysics & Space Exploration:** N-body cosmological simulations.
    
- **[[Computational Fluid Dynamics]] (CFD):** Aerodynamic modeling for aerospace and automotive systems.
    
- **Geophysics & Seismic Analysis:** Subsurface imaging and resource detection.
    
- **Nuclear Physics:** Fission and fusion plasma modeling.
    
- **Big Data Analytics:** High-throughput streaming and graph analysis.

## 2. [[Need for HPC in Modern Computing]]

Conventional sequential computing is bounded by execution time and physical architectural ceilings (such as power and memory walls). HPC circumvents these limits by breaking monolithic computing tasks into concurrent sub-problems.
### Primary Drivers

- **Compute Acceleration:** Concurrent instruction execution across multiple hardware units.
    
- **Scalable Data Capacity:** Processing datasets exceeding single-system memory architectures.
    
- **High-Fidelity Physical Simulations:** Enabling realistic numerical resolutions.
    
- **Model Training for AI:** Scaling parameter optimization across large compute clusters.
    
- **Near-Real-Time Constraints:** Timely generation of mission-critical insights (e.g., severe weather tracking).
### Architectural Execution Flow

#### Sequential Computing Model

Plaintext

```
Problem
   ↓
Single Processor
   ↓
Result
```

#### HPC Parallel Computing Model

Plaintext

```
             ┌─ Processor 1 ─┐
             ├─ Processor 2 ─┤
Problem ────→├─ Processor 3 ─┤────→ Result
             ├─ Processor 4 ─┤
             └───────────────┘
```

## 3. [[Flynn's Classification]]

Proposed by Michael J. Flynn in 1966, this taxonomy categorizes computer architectures based on the concurrency of **Instruction Streams** and **Data Streams**.

|**Category**|**Full Form**|**Instruction Streams**|**Data Streams**|**Typical Implementation**|
|---|---|---|---|---|
|**[[SISD]]**|Single Instruction, Single Data|Single (1)|Single (1)|Classical Von Neumann architecture, single-core CPUs|
|**[[SIMD]]**|Single Instruction, Multiple Data|Single (1)|Multiple|Vector processors, CPU SIMD extensions, GPUs|
|**[[MISD]]**|Multiple Instruction, Single Data|Multiple|Single (1)|Fault-tolerant redundant systems, systolic arrays|
|**[[MIMD]]**|Multiple Instruction, Multiple Data|Multiple|Multiple|Multicore CPUs, distributed HPC clusters|

## 4. [[SISD|SISD (Single Instruction, Single Data)]]

A single processing unit executes a single instruction stream sequentially against a single memory stream.
### Structural Flow

```
Instruction Stream
       ↓
   Processor
       ↓
  Data Stream
```

### Characteristics

- One instruction executed per cycle (in non-pipelined implementations).
    
- Strictly sequential execution pipeline.
    
- Standard model of early computing architectures.
### Algorithmic Example

```
A = 5
B = 10
C = A + B   // Executed strictly in chronological sequence
```

- **Advantages:** Straightforward hardware design; deterministic execution; no concurrency or synchronization bugs.
    
- **Disadvantages:** Performance is bounded by single-thread CPU clock frequencies.

## 5. [[SIMD|SIMD (Single Instruction, Multiple Data)]]

A single control unit dispatches one instruction to multiple arithmetic logic units (ALUs), which execute the operation simultaneously across distinct data elements.
### Structural Flow

```
                 Instruction
                      ↓
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
      Data 1        Data 2        Data 3
        ↓             ↓             ↓
     ALU / PE      ALU / PE      ALU / PE
        ↓             ↓             ↓
     Result 1      Result 2      Result 3
```

### Vector Operation Example

Given vectors $A = [1, 2, 3, 4]$ and $B = [5, 6, 7, 8]$:

A single `VADD` (Vector Add) instruction executes concurrently:

  

$$[1+5, \; 2+6, \; 3+7, \; 4+8] \longrightarrow [6, 8, 10, 12]$$

### Primary Applications

- Image and digital signal processing (DSP).
       
- Multimedia vector acceleration (e.g., AVX-512, ARM Neon).
    
- Massively parallel rendering and tensor operations via [[GPU Computing]].
## 6. [[MISD|MISD (Multiple Instruction, Single Data)]]

Multiple processing units receive different instructions, but all operate simultaneously on the exact same data stream.
### Structural Flow

```
                  Data Stream
                       ↓
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
  Instruction 1  Instruction 2  Instruction 3
        ↓              ↓              ↓
   Processor 1    Processor 2    Processor 3
        ↓              ↓              ↓
        └──────────────┬──────────────┘
                       ↓
                     Result
```

### Characteristics & Applications

- Rare in general-purpose computing.
    
- Used primarily in **Fault-Tolerant Redundant Systems** (e.g., aerospace flight control computers verifying identical data against multiple distinct algorithms) and systolic array pipelines.
## 7. [[MIMD|MIMD (Multiple Instruction, Multiple Data)]]

Multiple independent processors execute distinct instruction streams on distinct data sets simultaneously. This is the foundation of modern high-performance systems.
### Structural Flow

```
Instruction 1 ──→ Processor 1 ──→ Data 1
Instruction 2 ──→ Processor 2 ──→ Data 2
Instruction 3 ──→ Processor 3 ──→ Data 3
Instruction 4 ──→ Processor 4 ──→ Data 4
```

### Characteristics & Implementations

- High architectural flexibility and task independence.
    
- Cores can operate asynchronously or synchronously.
    
- Implemented in modern multi-core processors, symmetric multiprocessing (SMP) nodes, and distributed computing clusters.
## 8. [[Types of Parallelism]]

### 8.1 [[Data Parallelism]]

The same computation is mapped across different partitions of an aggregate dataset simultaneously.
- **Core Principle:** Uniform operation applied to partitioned data segments.
    
- **Example:** Multiplying every element of an array by a scalar constant across 4 dedicated cores.
    
- **Primary Domains:** Dense linear algebra, image convolution, deep learning batch passes.
### 8.2 [[Task Parallelism]]

Distinct logical tasks or functional subroutines are dispatched to separate processors concurrently.
- **Core Principle:** Different operations running concurrently; may consume the same or different data.
    
- **Example:** Core 1 handles network ingestion, Core 2 parses data packets, Core 3 performs database writes.
    
- **Primary Domains:** Asynchronous microservices, multithreaded runtime engines, pipeline rendering.
### 8.3 [[Instruction-Level Parallelism]] (ILP)

Microarchitectural concurrency that enables a processor to execute multiple independent assembly instructions within a single program thread simultaneously.
- **Key Mechanisms:**
    - **[[Pipelining]]:** Overlapping the execution stages (Fetch, Decode, Execute, Writeback) of subsequent instructions.
        
    - **[[Superscalar Execution]]:** Equipping the CPU core with multiple parallel execution units (ALUs, FPUs) to issue multiple instructions per clock cycle.
        
    - **[[Out-of-Order Execution]] (OoO):** Dynamically reordering independent instructions around cache misses or pipeline stalls.
        
    - **[[Branch Prediction]]:** Speculatively executing potential conditional instruction paths using speculative execution hardware.

## 9. [[Multicore and Manycore Processors]]

```
       Multicore (e.g., General CPU)               Manycore (e.g., Modern GPU)
┌───────────────────────────────────────────┐    ┌───────────────────────────────────────────┐
│  ┌─────────────┐       ┌─────────────┐   │    │ [c][c][c][c][c][c][c][c][c][c][c][c][c]   │
│  │   Core 1    │       │   Core 2    │   │    │ [c][c][c][c][c][c][c][c][c][c][c][c][c]   │
│  │ Large Cache │       │ Large Cache │   │    │ [c][c][c][c][c][c][c][c][c][c][c][c][c]   │
│  └─────────────┘       └─────────────┘   │    │ [c][c][c][c][c][c][c][c][c][c][c][c][c]   │
│  ┌─────────────┐       ┌─────────────┐   │    │                                           │
│  │   Core 3    │       │   Core 4    │   │    │ Hundreds/Thousands of Small Cores         │
│  │ Large Cache │       │ Large Cache │   │    │ Optimized for Mass Data Throughput        │
│  └─────────────┘       └─────────────┘   │    │                                           │
└───────────────────────────────────────────┘    └───────────────────────────────────────────┘
```

### Architectural Comparison

|**Dimension**|**[[Multicore Processors]]**|**[[Manycore Processors]]**|
|---|---|---|
|**Core Count**|Low to moderate (4 to 128 large cores)|Very high (hundreds to tens of thousands)|
|**Core Architecture**|Complex, heavy out-of-order execution, branch prediction|Simpler, energy-efficient, throughput-focused in-order pipelines|
|**Workload Focus**|Latency-optimized, complex sequential or light multithreaded logic|Throughput-optimized, massively parallel SIMD/SIMT data sets|
|**Primary Domain**|Operating systems, web servers, general compute|Matrix multiplication, physics simulation, graphics rendering|

## 10. [[Memory Hierarchy]]

Balancing latency, bandwidth, capacity, and manufacturing costs requires hierarchical data staging:

```
              ▲  Faster, Lower Latency, Lower Capacity, Higher Cost
              │
         [Registers]
              │
          [L1 Cache]
              │
          [L2 Cache]
              │
          [L3 Cache]
              │
          [Main Memory (DRAM)]
              │
        [Non-Volatile Storage (NVMe / SSD)]
              │
        [Cold Storage (HDD / Magnetic Tape)]
              │
              ▼  Slower, Higher Latency, Higher Capacity, Lower Cost
```

## 11. [[Cache Concepts|Cache Memory Concepts]]

Caches bridge the performance gap (the **Memory Wall**) between high-frequency CPU cores and comparatively high-latency DRAM.
### Multi-Level Cache Organization

- **L1 Cache:** Dedicated private cache per core; partitioned into L1-Instruction (L1i) and L1-Data (L1d). Operates at core clock frequency (1–4 cycle latency).
    
- **L2 Cache:** Larger private or shared cache per core; slightly higher latency (10–14 cycles).
    
- **L3 Cache:** Massive Last-Level Cache (LLC), typically unified and shared across all cores on a die (40–75 cycle latency).

```
CPU Core ──→ L1 Cache ──→ L2 Cache ──→ L3 Cache (Shared) ──→ Main Memory (RAM)
```

### Cache Hit vs. Cache Miss

- **Cache Hit:** The requested cache line is resident in cache memory; serviced with minimal clock cycle penalties.
    
- **Cache Miss:** The requested memory block is absent, requiring eviction passes and retrieval from lower memory levels or DRAM.
### Cache Hit Rate Metric

$$\text{Hit Rate} = \frac{\text{Cache Hits}}{\text{Total Memory Accesses}}$$

## 12. [[Shared Memory Systems]]

All processing units communicate via loads and stores to a globally shared physical address space.

```
CPU 1 ──┐
CPU 2 ──┼── High-Speed System Bus / Crossbar ──→ [[Shared Memory]]
CPU 3 ──┘
```

- **Advantages:** Simple programming model; zero-copy communication through memory pointer references.
    
- **Disadvantages:** [[Cache Coherence]] traffic (e.g., MESI protocol overhead); memory bus contention; strictly limited physical scalability (Symmetric Multiprocessing limits).
## 13. [[Distributed Memory Systems]]

Each node acts as an autonomous computing unit with its own private processor and local address space. Nodes communicate exclusively through explicit message packets over an interconnection network.

```
┌─────────────────┐             ┌─────────────────┐
│ Node 1          │             │ Node 2          │
│ [CPU] ↔ [Memory]│             │ [CPU] ↔ [Memory]│
└────────┬────────┘             └────────┬────────┘
         │                               │
         └───── [[Interconnection Networks]] ─────┘
```

- **Advantages:** Highly scalable; total memory aggregates linearly with node count; free from global memory bus bottlenecks.
    
- **Disadvantages:** High communication latency; requires explicit data serialization and partitioning.
    
- **Standard Programming Paradigm:** **[[MPI|MPI (Message Passing Interface)]]**.
## 14. [[Shared vs Distributed Memory]]

|**Architectural Feature**|**[[Shared Memory Systems]]**|**[[Distributed Memory Systems]]**|
|---|---|---|
|**Address Space**|Unified global address space|Separate, isolated address space per node|
|**Inter-Process Communication**|Shared memory reads/writes, pointers|Explicit packetized network messaging|
|**Programming Model**|Threads (OpenMP, POSIX pthreads)|Message Passing (MPI)|
|**Scalability**|Limited (typically up to ~64–128 sockets)|Massive (thousands of nodes)|
|**Data Synchronization**|Locks, semaphores, mutexes, atomic ops|Message send/receive, barriers, reductions|
|**Hardware Example**|Multi-socket server motherboards|Multi-rack Supercomputer clusters|

> **Note on Hybrid Architectures:** Modern HPC systems use a **hybrid model**: shared memory within a single node (using OpenMP/threads) combined with distributed memory across nodes (using MPI).

## 15. [[Interconnection Networks]]
The topology of the interconnect determines the bandwidth, latency, and routing diameter between compute nodes.
### Common Topologies

#### 1. Bus Topology

All nodes attach to a single shared physical medium.
- _Characteristics:_ Simplest design; low cost; severe contention at scale.

```
Node 1 ─┐
Node 2 ─┼── Common Bus Link
Node 3 ─┤
Node 4 ─┘
```
#### 2. Ring Topology

Each node is connected to exactly two neighboring nodes, forming an unbroken circular pathway.
- _Characteristics:_ Low pin count; latency scales linearly $O(N)$ with network size.

```
Node 1 ──── Node 2
  │           │
Node 4 ──── Node 3
```

#### 3. Star Topology

All peripheral nodes connect directly to a centralized network switch or router.
- _Characteristics:_ Single hop between any two nodes; switch represents a central point of failure and potential throughput bottleneck.

```
       Node 1
         │
Node 2 ─ Switch ─ Node 3
         │
       Node 4
```

#### 4. Mesh Topology

Nodes are arranged in a multi-dimensional lattice where internal nodes connect to orthogonal neighbors.
- _Characteristics:_ Highly scalable; predictable localized routing paths.

```
Node ── Node ── Node
 │        │        │
Node ── Node ── Node
 │        │        │
Node ── Node ── Node
```

#### 5. Torus Topology

A mesh topology augmented with wrap-around perimeter connections across dimensions.
- _Characteristics:_ Eliminates boundary edge constraints; halves the maximum network diameter compared to a standard mesh.
## 16. [[Supercomputers]]

A supercomputer aggregates thousands of compute nodes linked by low-latency interconnects (such as InfiniBand or custom proprietary fabrics), operating as a unified resource.
### Node Architecture Breakdown

```
                      [[Supercomputer]] Cluster
                                 │
     ┌───────────────────────────┼───────────────────────────┐
     ↓                           ↓                           ↓
 [Node 1]                    [Node 2]                    [Node 3]
  ├── Host CPU                ├── Host CPU                ├── Host CPU
  ├── GPU/Accelerator         ├── GPU/Accelerator         ├── GPU/Accelerator
  └── High-Speed Memory       └── High-Speed Memory       └── High-Speed Memory
     │                           │                           │
     └───────────────────────────┼───────────────────────────┘
                                 ↓
                 [[Interconnection Networks|Low-Latency Fabric Interconnect]]
```
## 17. [[TOP500 Systems]]

The **[[TOP500]]** project ranks the 500 most powerful non-distributed computing systems globally twice a year, based on the **[[LINPACK Benchmark]]** (solving a dense system of linear equations, measured in High-Performance Linpack / HPL)
### Computational Scale Units

$$\text{FLOPS} = \text{Floating-Point Operations Per Second}$$

- **$1\text{ GFLOPS}$ (GigaFLOPS):** $10^9\text{ FLOPS}$
    
- **$1\text{ TFLOPS}$ (TeraFLOPS):** $10^{12}\text{ FLOPS}$
    
- **$1\text{ PFLOPS}$ (PetaFLOPS):** $10^{15}\text{ FLOPS}$
    
- **$1\text{ EFLOPS}$ (ExaFLOPS):** $10^{18}\text{ FLOPS}$
### Additional Industry Metrics

- **[[Green500]]:** Evaluates energy efficiency by measuring performance-per-watt ($\text{GFLOPS/Watt}$).
    
- **HPCG Benchmark:** High-Performance Conjugate Gradients, designed to complement LINPACK by testing memory-bandwidth-bound scientific workloads.
## [[Quick Revision]]

```
[[High Performance Computing (HPC)]]
│
├── [[Flynn's Classification]]
│   ├── [[SISD]]  → 1 Instruction, 1 Data
│   ├── [[SIMD]]  → 1 Instruction, Multiple Data
│   ├── [[MISD]]  → Multiple Instructions, 1 Data
│   └── [[MIMD]]  → Multiple Instructions, Multiple Data
│
├── [[Types of Parallelism]]
│   ├── [[Data Parallelism]]            → Same task, partitioned data
│   ├── [[Task Parallelism]]            → Distinct tasks, parallel execution
│   └── [[Instruction-Level Parallelism]] → Pipelining, Superscalar, Out-of-Order
│
├── [[Multicore and Manycore Processors]]
│   ├── [[Multicore Processors]]        → Few, latency-optimized complex cores
│   └── [[Manycore Processors]]         → Massive arrays of throughput cores
│
├── [[Memory Hierarchy]]
│   └── Registers → L1/L2/L3 Caches → DRAM → Non-Volatile Storage
│
├── [[Memory Architectures]]
│   ├── [[Shared Memory Systems]]       → Uniform memory address space
│   └── [[Distributed Memory Systems]]  → Private memory per node + [[MPI]]
│
├── [[Interconnection Networks]]
│   └── Bus, Ring, Star, Mesh, Torus
│
└── [[Supercomputers]]
    └── [[TOP500 Systems]] (Measured via HPL / [[LINPACK Benchmark]] in FLOPS)
```
## [[Key Exam Definitions]]

- **[[High Performance Computing|HPC]]:** The use of aggregated, parallel computing clusters to solve complex computational problems at high speeds.
    
- **[[SISD]]:** Single instruction stream executing against a single data stream sequentially.
    
- **[[SIMD]]:** A single instruction applied simultaneously across multiple distinct data points.
    
- **[[MISD]]:** Multiple independent instructions concurrently evaluating the same data stream.
    
- **[[MIMD]]:** Multiple concurrent processors running different instructions on separate data sets.
    
- **[[Data Parallelism]]:** Distributing disjoint data segments across multiple processing units to execute the same operation simultaneously.
    
- **[[Task Parallelism]]:** Executing distinct functional tasks or threads concurrently on separate processing units.
    
- **[[Instruction-Level Parallelism|ILP]]:** Overlapping or executing independent machine instructions concurrently within a single processing core.
    
- **[[Multicore Processors]]:** A single physical die packaging multiple general-purpose, high-clock CPU cores.
    
- **[[Manycore Processors]]:** Specialized processors housing large arrays of simpler cores optimized for high-throughput, parallel tasks.
    
- **[[Cache Memory]]:** High-speed static memory placed directly adjacent to processor execution units to mitigate main-memory latency.
    
- **[[Shared Memory Systems]]:** Architecture where all processors read and write to a single, global address space.
    
- **[[Distributed Memory Systems]]:** Multi-node systems where each compute element accesses only its local memory and communicates via explicit network messages.
    
- **[[Interconnection Networks]]:** Dedicated physical and logical fabrics enabling communication and data exchange among processing nodes.
    
- **[[Supercomputers]]:** Scaled computing clusters consisting of thousands of interconnected, heterogeneous compute nodes.
    
- **[[TOP500]]:** Biannual performance ranking of world supercomputers evaluated via the High-Performance [[LINPACK Benchmark]] in FLOPS.