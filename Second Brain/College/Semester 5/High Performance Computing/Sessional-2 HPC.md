---
course: "[[High-Performance Computing]]"
course_code: 24BCSM 3106R
exam: 2nd Sessional Examination (November 2026)
total_marks: 30
---

# High-Performance Computing — 2nd Sessional Examination

## Section 1 (2 × 4 = 8 Marks)

### 1. Apply Amdahl's Law to determine the maximum achievable speedup of a parallel program when a fraction of the code remains serial.
According to [[Amdahl's Law]], the [[Speedup]] of a program with a [[Serial Fraction]] $$s$$ and a [[Parallel Fraction]] $$1 - s$$ across $$N$$ processors is:
$$S(N) = \frac{1}{s + \frac{1 - s}{N}}$$

To determine the maximum achievable speedup, take the limit as the number of processors approaches infinity:
$$S_{\max} = \lim_{N \to \infty} \frac{1}{s + \frac{1 - s}{N}} = \frac{1}{s}$$

Thus, the maximum speedup is strictly bounded by the reciprocal of the serial fraction.

### 2. Calculate the speedup and efficiency of a parallel program given its serial execution time, parallel execution time, and number of processors.
Let $$T_s$$ be the [[Serial Execution Time]], $$T_p$$ be the [[Parallel Execution Time]], and $$N$$ be the number of processors.

- **[[Speedup]]:**
$$S = \frac{T_s}{T_p}$$

- **[[Parallel Efficiency]]:**
$$E = \frac{S}{N} = \frac{T_s}{N \cdot T_p}$$

### 3. Analyze the Cache optimization techniques in terms of HPC.
[[Cache Optimization]] bridges the speed gap between the CPU and main memory (the [[Memory Wall]]) by exploiting [[Spatial Locality]] and [[Temporal Locality]]:
- **[[Loop Tiling]] (Blocking):** Divides large arrays into smaller blocks that fit into the cache, reducing [[Capacity Misses]] in matrix operations.
- **[[Loop Interchange]]:** Reorders nested loops to match the memory layout (row-major vs. column-major), ensuring contiguous memory access and maximizing [[Cache Hits]].
- **[[Data Alignment]] and Padding:** Aligns data structures to cache line boundaries to prevent [[False Sharing]] in multi-threaded HPC workloads.

### 4. State the differences between shared-memory programming using OpenMP and distributed-memory programming using MPI, with suitable examples.

| Feature | [[OpenMP]] ([[Shared Memory]]) | [[MPI]] ([[Distributed Memory]]) |
| :--- | :--- | :--- |
| **Memory Model** | All threads access a single shared address space. | Each process has its own private address space. |
| **Communication** | Implicit via shared variables. | Explicit via message passing (`MPI_Send`, `MPI_Recv`). |
| **Scalability** | Limited to a single node (multi-core CPU). | Scales across thousands of nodes in a [[Compute Cluster]]. |
| **Example** | Parallelizing a loop on one server using `#pragma omp parallel for`. | Distributing a large weather simulation grid across multiple cluster nodes. |

---

## Section 2 (4 × 3 = 12 Marks)

### 5. Evaluate the suitability of LINPACK and SPEC HPC benchmarks for assessing the performance of high-performance computing systems.

- **[[LINPACK]] (HPL - High-Performance Linpack):**
  - **Mechanism:** Solves a dense system of linear equations ($$Ax = b$$) using [[LU Decomposition]] to measure sustained floating-point performance in [[FLOPS]].
  - **Suitability:** Ideal for ranking peak raw compute capability (used for the [[TOP500]] list) and verifying hardware stability.
  - **Limitation:** Heavily compute-bound with high data reuse; it fails to accurately reflect memory bandwidth, latency, or network interconnect bottlenecks found in real-world scientific applications.

- **[[SPEC HPC]]:**
  - **Mechanism:** A standardized suite of real-world scientific and engineering applications (e.g., climate modeling, molecular dynamics, seismic processing) utilizing [[MPI]], [[OpenMP]], and [[OpenACC]].
  - **Suitability:** Provides a realistic evaluation of overall system performance, capturing memory hierarchy efficiency, I/O, and inter-node communication overhead across diverse workloads.
  - **Limitation:** More complex to configure and run than LINPACK, and results are harder to condense into a single universal metric.

### 6. Explain the fundamental concepts of GPU computing and NVIDIA CUDA, and discuss their role in accelerating parallel applications.

- **[[GPU Computing]]:** Uses Graphics Processing Units to perform general-purpose computation ([[GPGPU]]) by leveraging thousands of lightweight cores designed for massive [[Data-Level Parallelism]] and high memory throughput.
- **[[NVIDIA CUDA]]:** A parallel computing platform and programming model for NVIDIA GPUs based on:
  - **[[Host-Device Model]]:** The CPU (Host) manages control flow and memory transfers, while the GPU (Device) executes parallel functions called [[CUDA Kernels]].
  - **[[Thread Hierarchy]]:** Execution is organized into lightweight [[Threads]], grouped into [[Thread Blocks]], which form a [[Grid]].
  - **[[SIMT]] (Single Instruction, Multiple Threads):** Threads are scheduled in groups of 32 called [[Warps]] that execute the same instruction simultaneously.
  - **[[Memory Hierarchy]]:** Includes fast per-thread [[Registers]], low-latency on-chip [[Shared Memory]] (per block), and high-capacity [[Global Memory]].

- **Role in Acceleration:** CUDA offloads compute-intensive, repetitive tasks (e.g., matrix multiplication, deep learning training, finite element analysis) from the CPU to the GPU, hiding memory latency through massive multithreading and delivering orders-of-magnitude speedups.

### 7. Analyze the architectural differences between CPU-based and GPU-based computing and evaluate their suitability for different HPC workloads.

| Architectural Feature | [[CPU]] (Latency-Optimized)                                    | [[GPU]] (Throughput-Optimized)                                   |
| :-------------------- | :------------------------------------------------------------- | :--------------------------------------------------------------- |
| **Core Design**       | Few complex, high-frequency cores.                             | Thousands of simpler, lower-frequency cores.                     |
| **Control Logic**     | Advanced [[Branch Prediction]] and [[Out-of-Order Execution]]. | Minimal control logic; relies on [[SIMT]] execution.             |
| **Cache & Memory**    | Large multi-level caches (L1/L2/L3) to minimize latency.       | Smaller caches; ultra-high [[Memory Bandwidth]] (e.g., [[HBM]]). |

- **Workload Suitability:**
  - **CPU-Based Computing:** Best suited for sequential tasks, irregular control flows, heavy branching, OS management, and latency-sensitive workloads (e.g., database transactions, graph traversal, job orchestration).
  - **GPU-Based Computing:** Best suited for massively parallel, regular, compute-bound workloads with high arithmetic intensity (e.g., [[Deep Learning]], molecular dynamics, fluid dynamics, and image/signal processing).

---

## Section 3 (10 × 1 = 10 Marks)

### 8. Design a suitable HPC solution for a computationally intensive application using clusters, cloud platforms, or heterogeneous computing. Justify your choice of architecture, resource scheduling, and energy efficiency considerations.

#### Target Application
**Global Climate Modeling and Weather Forecasting:** Requires solving coupled partial differential equations over massive 3D atmospheric/oceanic grids, involving both high-throughput matrix/stencil computations and heavy inter-node communication.

#### 1. Architecture Choice: [[Heterogeneous Computing]] Cluster
- **Design:** A multi-node on-premise cluster where each compute node combines multi-core [[CPUs]] with multiple high-memory [[GPUs]], interconnected via high-bandwidth, low-latency [[InfiniBand]] networking and backed by a [[Parallel File System]] (e.g., [[Lustre]]).
- **Programming Model:** Hybrid [[MPI]] (for inter-node domain decomposition) + [[CUDA]] / [[OpenMP]] (for intra-node GPU/CPU acceleration).
- **Justification:**
  - **Compute Efficiency:** CPUs handle I/O, grid partitioning, and irregular control logic, while GPUs accelerate the dense, data-parallel stencil and physics calculations.
  - **Network Performance:** On-premise [[InfiniBand]] with [[RDMA]] avoids the network latency and data egress costs associated with public cloud platforms for tightly coupled simulations.

#### 2. [[Resource Scheduling]]
- **Workload Manager:** Deploy [[Slurm]] (Simple Linux Utility for Resource Management).
- **Scheduling Policies:**
  - **[[Backfill Scheduling]]:** Allows smaller jobs to fill idle resource gaps without delaying high-priority, large-scale simulation jobs, maximizing cluster utilization.
  - **[[Topology-Aware Scheduling]]:** Allocates nodes that are physically close on the network switches to minimize communication hops and latency.
  - **[[GPU Affinity]] & Checkpointing:** Binds processes to specific CPU cores and local GPUs (respecting [[NUMA]] boundaries) and integrates periodic [[Checkpointing]] to recover from hardware faults during multi-day runs.

#### 3. [[Energy Efficiency]] Considerations
- **Higher [[FLOPS per Watt]]:** Using GPUs for the primary computational load delivers significantly higher energy efficiency compared to an equivalent CPU-only cluster.
- **[[DVFS]] (Dynamic Voltage and Frequency Scaling):** Automatically lowers CPU/GPU clock frequencies during memory-bound or communication-heavy phases to reduce dynamic power consumption.
- **[[Direct-to-Chip Liquid Cooling]]:** Replaces traditional air cooling to efficiently dissipate heat from high-TDP GPUs, lowering the data center's [[PUE]] (Power Usage Effectiveness).
- **Power-Aware Scheduling:** Configures [[Slurm]] to power down or suspend idle nodes during off-peak periods and schedule non-urgent batch jobs when renewable energy or lower electricity tariffs are available.