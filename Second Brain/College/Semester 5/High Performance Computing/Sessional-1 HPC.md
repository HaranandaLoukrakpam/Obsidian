---
course: "[[High-Performance Computing]]"
course_code: 24BCSM 3106R
exam: 1st Sessional Examination (September 2026)
total_marks: 30
---

# High-Performance Computing — 1st Sessional Examination

## Section 1 (2 × 4 = 8 Marks)

### 1. What is High-Performance Computing (HPC)? Mention any two applications of HPC.
[[High-Performance Computing]] (HPC) is the aggregation of computing power using [[Supercomputers]], [[Compute Clusters]], and [[Parallel Processing]] techniques to solve complex computational problems at high speeds.

- **Applications:** Weather forecasting and climate modeling; genomic sequencing and drug discovery.

### 2. Differentiate between SISD and SIMD architectures according to Flynn's classification.
According to [[Flynn's Classification]]:

| Feature | [[SISD]] (Single Instruction, Single Data) | [[SIMD]] (Single Instruction, Multiple Data) |
| :--- | :--- | :--- |
| **Execution** | Executes one instruction on a single data stream at a time (sequential). | Executes the same instruction simultaneously across multiple data streams (parallel). |
| **Hardware** | Traditional uniprocessor / single-core CPUs. | [[Vector Processors]], [[GPUs]], and CPU SIMD extensions (e.g., [[AVX]]). |

### 3. Define speedup and efficiency in parallel computing.
- **[[Speedup]]:** The ratio of execution time on a single processor to the execution time on multiple parallel processors.
$$S = \frac{T_s}{T_p}$$
- **[[Parallel Efficiency]]:** The ratio of speedup to the number of processors used, measuring how effectively the processors are utilized.
$$E = \frac{S}{N}$$

### 4. What is cache optimization? Why is it important in HPC applications?
[[Cache Optimization]] is the process of structuring data and algorithms to maximize [[Cache Hits]] and minimize main memory accesses by exploiting [[Spatial Locality]] and [[Temporal Locality]]. It is critical in HPC because main memory latency is significantly slower than CPU processing speed; minimizing [[Cache Misses]] prevents processor stalls and maximizes computational throughput.

---

## Section 2 (4 × 3 = 12 Marks)

### 5. Explain the MIMD architecture with a suitable example. How does it differ from SIMD architecture?
[[MIMD]] (Multiple Instruction, Multiple Data) is a parallel architecture where multiple autonomous processors simultaneously execute different instructions on different data sets. Processors operate asynchronously and can use either [[Shared Memory]] or [[Distributed Memory]].

- **Example:** Modern [[Multi-Core CPUs]] and distributed [[Compute Clusters]].

**Differences between [[MIMD]] and [[SIMD]]:**
- **Instruction Stream:** MIMD processors execute independent instruction streams; SIMD units execute a single synchronized instruction stream.
- **Synchronization:** MIMD operates asynchronously; SIMD operates synchronously in lockstep.
- **Flexibility:** MIMD handles both [[Task-Level Parallelism]] and [[Data-Level Parallelism]]; SIMD is restricted to data-level parallelism (e.g., matrix/vector operations).
- **Hardware Complexity:** MIMD requires complex control logic and synchronization mechanisms, whereas SIMD has simpler control hardware.

### 6. A program takes 80 seconds to execute on a single processor and 25 seconds on a parallel system using multiple processors. Calculate the speedup and parallel efficiency if 4 processors are used.
- **Given:**
$$T_s = 80\text{ s}, \quad T_p = 25\text{ s}, \quad N = 4$$

- **[[Speedup]]:**
$$S = \frac{T_s}{T_p} = \frac{80}{25} = 3.2$$

- **[[Parallel Efficiency]]:**
$$E = \frac{S}{N} = \frac{3.2}{4} = 0.8 \text{ (or } 80\%)$$

### 7. Explain Amdahl's Law and discuss how the serial portion of a program limits the achievable speedup in a parallel system.
[[Amdahl's Law]] defines the theoretical maximum [[Speedup]] of a fixed-size task when a portion of it is parallelized across multiple processors:
$$S(N) = \frac{1}{s + \frac{1 - s}{N}}$$
where $$s$$ is the [[Serial Fraction]] and $$1 - s$$ is the [[Parallel Fraction]].

**Limitation by the Serial Portion:**
As the number of processors $$N$$ approaches infinity, the parallel execution term $$\frac{1 - s}{N}$$ approaches zero, leaving:
$$S_{\max} = \frac{1}{s}$$
Because the serial portion must execute sequentially on a single processor regardless of how many cores are added, it creates a strict upper bound on speedup. Even a small serial fraction (e.g., 10%) caps the maximum possible speedup at 10x, leading to diminishing returns as processor count increases.

---

## Section 3 (10 × 1 = 10 Marks)

### 8. A parallel HPC application has a serial fraction of 20% and a parallel fraction of 80%.

**Given:**
$$s = 0.20, \quad p = 1 - s = 0.80$$

#### a) Calculate the theoretical speedup using Amdahl's Law for 2, 4, 8, and 16 processors.
Using [[Amdahl's Law]]:
$$S(N) = \frac{1}{0.20 + \frac{0.80}{N}}$$

- **For 2 processors:**
$$S(2) = \frac{1}{0.20 + \frac{0.80}{2}} = \frac{1}{0.60} \approx 1.67$$

- **For 4 processors:**
$$S(4) = \frac{1}{0.20 + \frac{0.80}{4}} = \frac{1}{0.40} = 2.50$$

- **For 8 processors:**
$$S(8) = \frac{1}{0.20 + \frac{0.80}{8}} = \frac{1}{0.30} \approx 3.33$$

- **For 16 processors:**
$$S(16) = \frac{1}{0.20 + \frac{0.80}{16}} = \frac{1}{0.25} = 4.00$$

#### b) Calculate the corresponding parallel efficiency for each case.
Using [[Parallel Efficiency]]:
$$E(N) = \frac{S(N)}{N}$$

- **For 2 processors:**
$$E(2) = \frac{1.67}{2} \approx 0.833 \text{ (or } 83.33\%)$$

- **For 4 processors:**
$$E(4) = \frac{2.50}{4} = 0.625 \text{ (or } 62.50\%)$$

- **For 8 processors:**
$$E(8) = \frac{3.33}{8} \approx 0.417 \text{ (or } 41.67\%)$$

- **For 16 processors:**
$$E(16) = \frac{4.00}{16} = 0.250 \text{ (or } 25.00\%)$$

#### c) Explain the trend in speedup and efficiency as the number of processors increases.
- **[[Speedup]]:** Increases sub-linearly with diminishing returns, asymptotically approaching the theoretical maximum:
$$S_{\max} = \frac{1}{0.20} = 5$$
- **[[Parallel Efficiency]]:** Decreases steadily as processor count increases (from 83.33% down to 25%) because more processors remain idle during the 20% serial execution phase, resulting in lower hardware utilization.

#### d) Discuss how Gustafson's Law provides a different perspective on scalability for this application.
While [[Amdahl's Law]] assumes a fixed problem size ([[Strong Scaling]]), [[Gustafson's Law]] assumes a fixed execution time where the problem size scales proportionally with the number of processors ([[Weak Scaling]]):
$$S(N) = s + N(1 - s) = N - s(N - 1)$$
For this application, as processor count grows, the parallel workload expands while the serial overhead remains relatively constant in time. This yields a linear scaled speedup:
$$S(16) = 0.20 + 16(0.80) = 13$$
This demonstrates that large-scale HPC systems remain effective when tackling larger datasets rather than trying to speed up a fixed, small problem.

#### e) Suggest two optimization techniques that could improve the performance of the application.
1. **Reducing the [[Serial Fraction]] (Algorithmic Refactoring):** Identify bottlenecks in the 20% serial code (such as I/O operations, [[Lock Contention]], or sequential initialization) and replace them with [[Parallel I/O]], [[Lock-Free Data Structures]], or parallel algorithms to raise the [[Amdahl's Law]] ceiling.
2. **[[Load Balancing]] and [[Communication Optimization]]:** Distribute parallel workloads evenly across processors to prevent stragglers, and overlap computation with inter-processor communication (e.g., using non-blocking [[MPI]] calls) to hide latency.