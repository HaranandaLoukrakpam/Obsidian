## 1. Introduction to Accelerators in HPC

[[Accelerators]] are specialised hardware components designed to perform particular types of computations faster and more efficiently than general-purpose CPUs.

In [[High Performance Computing (HPC)]], accelerators are used to improve computational performance by handling large numbers of parallel operations.

### Why Are Accelerators Needed?

- CPUs are designed for general-purpose computing.
    
- Some applications require millions of similar calculations.
    
- Accelerators can execute many operations simultaneously.
    
- They improve computational speed and energy efficiency for suitable workloads.
    
- They are widely used in AI, scientific simulations, and data processing.
    

### Types of Accelerators

1. [[GPU]] – Graphics Processing Unit.
    
2. [[FPGA]] – Field Programmable Gate Array.
    
3. [[ASIC]] – Application-Specific Integrated Circuit.
    

### CPU vs Accelerator

|CPU|Accelerator|
|---|---|
|General-purpose processor|Specialised processing hardware|
|Usually has fewer powerful cores|Often contains many parallel processing elements|
|Suitable for sequential and varied tasks|Suitable for specific parallel workloads|
|Flexible instruction processing|Optimised for particular operations|
|Example: Intel Core, AMD Ryzen|Example: NVIDIA GPU, FPGA|

---

## 2. GPU Computing Fundamentals

[[GPU Computing]] is the use of Graphics Processing Units to perform general-purpose computations in addition to graphics processing.

A [[GPU]] contains many processing cores that can execute numerous operations in parallel.

GPUs are especially effective for tasks involving large datasets and repeated mathematical operations.

### CPU and GPU Architecture

A CPU generally contains a small number of powerful cores designed for complex tasks, while a GPU contains a large number of simpler processing units designed for parallel execution.

### Basic Architecture

```
              Computer System
                    |
          +---------+---------+
          |                   |
         CPU                 GPU
          |                   |
     Few powerful       Many processing
        cores                cores
          |                   |
   Sequential and       Massively parallel
   varied operations      computations
```

### Working of GPU Computing

1. The CPU executes the main application.
    
2. Data is transferred from system memory to GPU memory.
    
3. The CPU launches a GPU computation.
    
4. Thousands of GPU threads perform operations simultaneously.
    
5. Results are transferred back to the CPU when required.
    

### Applications of GPU Computing

- [[Artificial Intelligence]] and deep learning.
    
- Scientific simulations.
    
- Image and video processing.
    
- Weather forecasting.
    
- Molecular modelling.
    
- Financial calculations.
    
- Computer vision.
    

### Advantages

- High parallel processing capability.
    
- High memory bandwidth.
    
- Suitable for large-scale numerical computations.
    
- Can significantly reduce execution time for suitable workloads.
    

### Limitations

- Data transfer between CPU and GPU can introduce overhead.
    
- Not all programs can be parallelised efficiently.
    
- GPU programming is more complex than ordinary CPU programming.
    
- GPU memory may be limited compared with system RAM.
    

---

## 3. Parallel Processing Using NVIDIA CUDA Concepts

[[CUDA]] stands for **Compute Unified Device Architecture**.

It is a parallel computing platform and programming model developed by [[NVIDIA]] that allows developers to use NVIDIA GPUs for general-purpose computing.

CUDA enables programmers to write programs that execute computational tasks across multiple GPU threads.

### CUDA Architecture

CUDA applications generally involve two major components:

1. **Host:** The CPU and its memory.
    
2. **Device:** The GPU and its memory.
    

### CUDA Architecture Diagram

```
              Host (CPU)
                  |
          Launches CUDA Kernel
                  |
                  v
             Device (GPU)
                  |
          +-------+-------+
          |               |
        SM 1             SM 2
          |               |
      +---+---+       +---+---+
      |   |   |       |   |   |
     T1  T2  T3      T4  T5  T6

SM = Streaming Multiprocessor
T  = GPU Thread
```

### Important CUDA Components

#### 3.1 Host

[[Host]] refers to the CPU and system memory that control the CUDA application.

The host:

- Executes the main program.
    
- Allocates memory.
    
- Transfers data to the GPU.
    
- Launches GPU kernels.
    
- Retrieves computation results.
    

#### 3.2 Device

[[Device]] refers to the NVIDIA GPU that performs parallel computation.

It executes GPU kernels and manages GPU threads.

#### 3.3 Kernel

A [[CUDA Kernel]] is a function executed by multiple GPU threads in parallel.

Example:

```
__global__ void add(int *a, int *b, int *c) {
    int i = threadIdx.x;
    c[i] = a[i] + b[i];
}
```

Here:

- `__global__` identifies a CUDA kernel.
    
- `threadIdx.x` provides the thread's index.
    
- Each thread performs one addition.
    

#### 3.4 Thread

A [[CUDA Thread]] is the smallest execution unit in the CUDA programming model.

Each thread executes the same kernel code but may operate on different data.

#### 3.5 Thread Block

A [[Thread Block]] is a group of CUDA threads that can cooperate and share resources.

Threads within a block can:

- Share shared memory.
    
- Synchronise using barriers.
    
- Cooperate on a common task.
    

#### 3.6 Grid

A [[CUDA Grid]] is a collection of thread blocks launched to execute a kernel.

### CUDA Thread Hierarchy

```
               Grid
                 |
       +---------+---------+
       |                   |
    Block 1              Block 2
       |                   |
   +---+---+           +---+---+
   |   |   |           |   |   |
  T0  T1  T2          T0  T1  T2
```

The hierarchy is:

**Grid → Blocks → Threads**

### CUDA Memory Hierarchy

CUDA provides several types of memory:

|Memory Type|Location / Scope|Characteristics|
|---|---|---|
|Registers|Individual thread|Very fast, private|
|Local Memory|Individual thread|Private but stored in device memory|
|Shared Memory|Thread block|Fast, shared among block threads|
|Global Memory|Entire device|Large capacity, accessible by threads|
|Constant Memory|Entire device|Read-only and cached|
|Texture Memory|Entire device|Optimised for certain read access patterns|

### Advantages of CUDA

- Supports massive parallelism.
    
- Provides direct GPU programming capabilities.
    
- Suitable for scientific and AI workloads.
    
- Offers libraries for numerical computation and deep learning.
    

### Limitations of CUDA

- Primarily supports NVIDIA GPUs.
    
- Requires understanding of parallel programming.
    
- Data transfer can become a bottleneck.
    
- Performance depends on memory access and thread organisation.
    

---

## 4. Heterogeneous Computing

[[Heterogeneous Computing]] is a computing approach that uses different types of processing units together to perform a task efficiently.

A heterogeneous system may combine:

- CPU
    
- GPU
    
- FPGA
    
- Other specialised accelerators
    

### Architecture

```
             Heterogeneous System
                      |
             +--------+--------+
             |        |        |
            CPU      GPU      FPGA
             |        |        |
          Control   Parallel  Specialised
          Tasks    Computing  Operations
             |        |        |
             +--------+--------+
                      |
                  Final Result
```

### Working

1. The CPU manages the overall application.
    
2. Computationally intensive tasks are assigned to accelerators.
    
3. Different processing units execute suitable tasks.
    
4. Results are combined to produce the final output.
    

### Example

In an AI application:

- CPU handles data preparation and control.
    
- GPU performs neural network calculations.
    
- Storage and networking components provide data.
    

### Advantages

- Combines the strengths of different processors.
    
- Improves overall computational performance.
    
- Provides flexibility in task allocation.
    
- Can improve energy efficiency.
    

### Disadvantages

- Programming is more complex.
    
- Data movement between devices introduces overhead.
    
- Different hardware requires compatible software.
    
- Resource coordination can be difficult.
    

### Homogeneous vs Heterogeneous Computing

|Homogeneous Computing|Heterogeneous Computing|
|---|---|
|Uses similar processing units|Uses different processing units|
|Similar architecture|Different architectures|
|Easier to manage|More complex to manage|
|Example: CPU-only cluster|Example: CPU and GPU system|
|Less specialised|Can be highly specialised|

---

## 5. FPGA Basics in HPC

[[FPGA]] stands for **Field Programmable Gate Array**.

An FPGA is a programmable integrated circuit whose internal logic can be configured after manufacturing to perform specific digital operations.

Unlike a CPU or GPU, which execute instructions using fixed processing architectures, an FPGA can be configured to create specialised hardware circuits.

### Basic FPGA Architecture

An FPGA generally contains:

1. [[Configurable Logic Blocks (CLBs)]] – Perform logical operations.
    
2. [[Programmable Interconnects]] – Connect different logic blocks.
    
3. [[Input/Output Blocks (IOBs)]] – Connect the FPGA to external devices.
    
4. [[Block RAM]] – Provides on-chip memory.
    
5. [[DSP Blocks]] – Accelerate mathematical operations such as multiplication.
    

### Diagram

```
             FPGA Architecture
       +--------------------------+
       |                          |
       |  +------+    +------+    |
       |  | CLB  |----| CLB  |    |
       |  +------+    +------+    |
       |      |          |        |
       |  +------+    +------+    |
       |  | RAM  |----| DSP  |    |
       |  +------+    +------+    |
       |                          |
       |  Programmable Connections|
       +--------------------------+
```

### Working of FPGA

1. The developer designs a digital circuit.
    
2. The design is described using a hardware description language or supported development tools.
    
3. The design is synthesised into logic elements.
    
4. The FPGA is configured with the resulting hardware design.
    
5. The configured circuit performs the required operations.
    

### FPGA Programming Languages

- [[Verilog]]
    
- [[VHDL]]
    
- High-Level Synthesis (HLS) tools can also generate hardware from supported high-level code.
    

### Applications of FPGA in HPC

- Signal processing.
    
- Network acceleration.
    
- Financial computing.
    
- Real-time data processing.
    
- Scientific computation.
    
- Hardware acceleration.
    

### Advantages

- Reconfigurable hardware.
    
- Parallel execution through customised circuits.
    
- Low latency for suitable workloads.
    
- Potentially high energy efficiency.
    

### Disadvantages

- More difficult to program than conventional software.
    
- Hardware design requires specialised knowledge.
    
- Development and debugging can be time-consuming.
    
- Not ideal for every general-purpose workload.
    

### CPU vs GPU vs FPGA

|Feature|CPU|GPU|FPGA|
|---|---|---|---|
|Main purpose|General computing|Parallel computing|Custom hardware logic|
|Architecture|Few powerful cores|Many processing cores|Reconfigurable logic|
|Flexibility|High|Moderate|High at hardware-design level|
|Programming|Conventional languages|CUDA and other GPU models|Verilog, VHDL, HLS|
|Best suited for|General tasks|Massively parallel workloads|Specialised low-latency operations|

---

## 6. Cluster Computing Architecture

[[Cluster Computing]] is a computing model in which multiple independent computers, called nodes, are connected through a network and work together as a single computing system.

Each node has its own processor, memory, and operating system.

Clusters are widely used in HPC to perform large computational tasks.

### Components of a Cluster

1. **Compute Nodes:** Perform actual computations.
    
2. **Head Node:** Manages the cluster and accepts user jobs.
    
3. **Interconnection Network:** Allows nodes to communicate.
    
4. **Shared Storage:** Stores application data and files.
    
5. **Job Scheduler:** Allocates resources and manages jobs.
    

### Cluster Architecture

```
                 Users
                   |
                   v
               Head Node
                   |
             Job Scheduler
                   |
           High-Speed Network
                   |
       +-----------+-----------+
       |           |           |
    Node 1      Node 2      Node 3
       |           |           |
      CPU         CPU         CPU
      RAM         RAM         RAM
       |           |           |
       +-----------+-----------+
                   |
              Shared Storage
```

### Working of Cluster Computing

1. A user submits a computational job.
    
2. The head node receives the job.
    
3. The job scheduler selects available compute nodes.
    
4. The task is divided among the selected nodes.
    
5. Nodes perform computations and communicate when required.
    
6. Results are collected and returned to the user.
    

### Types of Clusters

#### 6.1 High-Performance Computing Cluster

[[HPC Cluster]] combines multiple computing nodes to execute computationally intensive applications in parallel.

Example: Scientific simulations and weather forecasting.

#### 6.2 High-Availability Cluster

[[High-Availability Cluster]] is designed to keep services running even when one or more nodes fail.

Example: Banking systems and critical servers.

#### 6.3 Load-Balancing Cluster

[[Load-Balancing Cluster]] distributes incoming workloads among multiple nodes to improve performance and availability.

Example: Web servers handling large numbers of requests.

### Advantages

- High computational power.
    
- Scalable architecture.
    
- Cost-effective compared with some specialised supercomputers.
    
- Fault tolerance can be implemented.
    
- Resources can be shared.
    

### Disadvantages

- Network communication introduces overhead.
    
- Cluster management is complex.
    
- Requires proper workload distribution.
    
- Hardware failures can affect performance.
    

### Cluster vs Supercomputer

|Cluster|Supercomputer|
|---|---|
|Built from connected independent nodes|Highly integrated large-scale computing system|
|Often uses commodity hardware|May use specialised high-performance hardware|
|Usually easier to expand incrementally|Expansion can be more complex|
|Connected through a network|Uses high-performance interconnects|
|Can be used for HPC workloads|Designed for extremely demanding workloads|

---

## 7. Job Scheduling and Resource Managers

[[Job Scheduling]] is the process of assigning computational jobs to available resources in a cluster or HPC system.

A [[Job Scheduler]] decides when and where a submitted job should execute.

### Need for Job Scheduling

- Manages multiple users and jobs.
    
- Allocates processors and memory.
    
- Prevents resource conflicts.
    
- Improves system utilisation.
    
- Controls job execution priority.
    
- Maintains fair resource distribution.
    

### Job Scheduling Process

```
             User Submits Job
                    |
                    v
             Job Scheduler
                    |
                    v
          Checks Available Resources
                    |
                    v
          Allocates Compute Nodes
                    |
                    v
               Executes Job
                    |
                    v
              Returns Result
```

### Common Scheduling Algorithms

#### 7.1 First Come First Served (FCFS)

[[First Come First Served]] executes jobs in the order they arrive.

Advantages:

- Simple to implement.
    
- Fair according to arrival order.
    

Disadvantages:

- Long jobs may delay short jobs.
    
- Can lead to inefficient resource utilisation.
    

#### 7.2 Shortest Job First (SJF)

[[Shortest Job First]] gives priority to jobs with the shortest expected execution time.

Advantages:

- Reduces average waiting time under suitable assumptions.
    

Disadvantages:

- Requires knowledge of job execution time.
    
- Long jobs may experience starvation.
    

#### 7.3 Priority Scheduling

[[Priority Scheduling]] executes jobs according to assigned priority levels.

Advantages:

- Important jobs can execute earlier.
    

Disadvantages:

- Low-priority jobs may experience starvation.
    

#### 7.4 Backfilling

[[Backfilling]] allows smaller jobs to use temporarily available resources while ensuring that previously scheduled high-priority jobs are not delayed beyond their reserved start times.

It is commonly used in HPC job scheduling.

### Resource Managers

A [[Resource Manager]] manages computing resources such as:

- CPUs.
    
- GPUs.
    
- Memory.
    
- Compute nodes.
    
- Storage allocations.
    

### Common HPC Job Schedulers

|Scheduler|Description|
|---|---|
|[[SLURM]]|Widely used open-source workload manager|
|[[PBS Professional]]|HPC workload and job scheduler|
|[[HTCondor]]|Manages distributed computing workloads|
|[[LSF]]|IBM workload management and scheduling system|

### Example: SLURM

[[SLURM]] stands for **Simple Linux Utility for Resource Management**.

It is widely used in Linux-based HPC clusters.

Common SLURM commands:

|Command|Purpose|
|---|---|
|`sbatch`|Submit a batch job|
|`srun`|Run a job or parallel task|
|`squeue`|View queued and running jobs|
|`scancel`|Cancel a job|
|`sinfo`|View cluster node information|

Example SLURM script:

```
#!/bin/bash
#SBATCH --job-name=my_job
#SBATCH --nodes=1
#SBATCH --ntasks=4
#SBATCH --time=00:10:00

srun ./my_program
```

This script requests one node and four tasks, with a maximum time limit of ten minutes.

---

## 8. HPC on Cloud Platforms

[[Cloud HPC]] refers to using cloud computing infrastructure to perform high-performance computing workloads.

Instead of purchasing and maintaining physical supercomputers or clusters, organisations rent computing resources from cloud providers.

### Architecture

```
                 User
                  |
                  v
             Cloud Platform
                  |
          +-------+-------+
          |               |
      Compute          Storage
      Instances         Services
          |
    +-----+-----+
    |     |     |
   CPU   GPU  Network
    |     |     |
    +-----+-----+
          |
     HPC Workload
```

### Features of Cloud HPC

- On-demand computing resources.
    
- Scalable infrastructure.
    
- Access to GPU and CPU instances.
    
- High-speed networking options.
    
- Flexible storage services.
    
- Pay-as-you-use pricing models.
    

### Advantages

1. **Scalability:** Resources can be increased or decreased when required.
    
2. **Cost Flexibility:** Users pay for resources according to the pricing model.
    
3. **Accessibility:** Computing resources can be accessed remotely.
    
4. **Reduced Maintenance:** Cloud providers manage much of the physical infrastructure.
    
5. **Rapid Deployment:** HPC environments can be created without purchasing hardware.
    

### Disadvantages

- High costs for continuous large-scale workloads.
    
- Network latency and data transfer charges.
    
- Dependence on internet connectivity.
    
- Data privacy and security concerns.
    
- Vendor dependency.
    

---

## 9. HPC Services on Amazon Web Services (AWS)

[[Amazon Web Services (AWS)]] is a cloud computing platform that provides infrastructure and services for HPC applications.

### Important AWS Services for HPC

#### 9.1 Amazon EC2

[[Amazon EC2]] provides virtual computing instances that can be configured for CPU-intensive and GPU-intensive workloads.

#### 9.2 AWS ParallelCluster

[[AWS ParallelCluster]] is an open-source cluster management tool that helps deploy and manage HPC clusters on AWS.

#### 9.3 Amazon FSx for Lustre

[[Amazon FSx for Lustre]] provides high-performance file storage designed for workloads requiring fast access to large datasets.

#### 9.4 Elastic Fabric Adapter (EFA)

[[Elastic Fabric Adapter]] provides low-latency, high-throughput networking for supported HPC and machine learning applications.

### Applications

- Scientific simulations.
    
- Computational fluid dynamics.
    
- Genomics.
    
- AI model training.
    
- Engineering workloads.
    

---

## 10. HPC Services on Microsoft Azure

[[Microsoft Azure]] is Microsoft's cloud computing platform that provides computing, storage, networking, and HPC services.

### Important Azure Services

#### 10.1 Azure Virtual Machines

[[Azure Virtual Machines]] provide scalable virtual machines for general-purpose, CPU-intensive, and GPU-intensive workloads.

#### 10.2 Azure CycleCloud

[[Azure CycleCloud]] is used to create, manage, and optimise HPC and big computing clusters on Azure.

#### 10.3 Azure Storage

[[Azure Storage]] provides scalable storage for HPC datasets and application files.

#### 10.4 Azure High-Performance Computing Infrastructure

Azure provides HPC-focused VM configurations and networking capabilities for parallel and scientific applications.

### Applications

- Engineering simulations.
    
- Weather modelling.
    
- AI and deep learning.
    
- Financial modelling.
    
- Scientific research.
    

---

## 11. HPC Services on Google Cloud

[[Google Cloud Platform (GCP)]] provides cloud infrastructure for large-scale computing and data-intensive applications.

### Important Google Cloud Services

#### 11.1 Compute Engine

[[Google Compute Engine]] provides virtual machines that can be configured for high-performance computing.

#### 11.2 Google Kubernetes Engine

[[Google Kubernetes Engine (GKE)]] manages containerised applications using Kubernetes.

#### 11.3 Cloud Storage

[[Google Cloud Storage]] provides scalable object storage for large datasets.

#### 11.4 Google Cloud Batch

[[Google Cloud Batch]] is a service for scheduling and executing batch processing workloads on Google Cloud.

### Applications

- AI and machine learning.
    
- Scientific computing.
    
- Data analytics.
    
- Large-scale simulations.
    
- Bioinformatics.
    

### AWS vs Azure vs Google Cloud

|Feature|AWS|Microsoft Azure|Google Cloud|
|---|---|---|---|
|Compute|Amazon EC2|Azure Virtual Machines|Compute Engine|
|Cluster Management|AWS ParallelCluster|Azure CycleCloud|Cloud Batch and other cluster tools|
|Container Management|Amazon EKS|Azure Kubernetes Service|Google Kubernetes Engine|
|Storage|Amazon FSx and S3|Azure Storage|Cloud Storage|
|Main Use|Broad cloud and HPC infrastructure|Enterprise and HPC workloads|Data analytics and AI workloads|

---

## 12. Containerized HPC Using Docker and Kubernetes

### 12.1 Containerization

[[Containerization]] is a technology that packages an application and its dependencies into an isolated, portable environment called a container.

Containers help applications run consistently across different computing environments.

### Docker

[[Docker]] is a platform used to build, package, distribute, and run containerised applications.

### Main Components of Docker

1. **Docker Image:** A read-only template used to create containers.
    
2. **Docker Container:** A running instance of an image.
    
3. **Dockerfile:** A text file containing instructions to build an image.
    
4. **Docker Engine:** The software responsible for building and running containers.
    
5. **Docker Registry:** A repository used to store and distribute images.
    

### Docker Architecture

```
              Docker Client
                    |
                    v
              Docker Engine
                    |
             +------+------+
             |             |
         Docker Image   Containers
             |             |
          Template     Running Apps
```

### Example Dockerfile

```
FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    build-essential

WORKDIR /app

COPY program.c .

RUN gcc program.c -o program

CMD ["./program"]
```

This Dockerfile creates an Ubuntu-based image, installs a C compiler, compiles a program, and executes it.

### Advantages of Docker

- Portability.
    
- Application isolation.
    
- Consistent environments.
    
- Easy deployment.
    
- Dependency management.
    

### Limitations in HPC

- Container configuration may require specialised tuning.
    
- Containers do not automatically improve computational performance.
    
- GPU and high-speed network access require appropriate configuration.
    
- Containers must be designed carefully for security and performance.
    

### 12.2 Kubernetes

[[Kubernetes]] is an open-source container orchestration platform used to deploy, manage, scale, and monitor containerised applications.

It automates the management of containers across multiple machines.

### Main Components of Kubernetes

1. **Cluster:** A group of machines managed by Kubernetes.
    
2. **Node:** A machine in the Kubernetes cluster.
    
3. **Pod:** The smallest deployable unit in Kubernetes.
    
4. **Deployment:** Manages application replicas and updates.
    
5. **Service:** Provides network access to applications.
    
6. **Control Plane:** Manages the overall cluster.
    
7. **Worker Node:** Runs application workloads.
    

### Kubernetes Architecture

```
               Kubernetes Cluster
                       |
               +-------+-------+
               |               |
          Control Plane     Worker Nodes
               |               |
          Scheduler         +--+--+
          API Server        |     |
          Controller       Pod   Pod
               |            |     |
               +------------+-----+
```

### Working of Kubernetes

1. The user defines the desired application configuration.
    
2. Kubernetes receives the deployment request.
    
3. The scheduler selects suitable worker nodes.
    
4. Containers are started inside pods.
    
5. Kubernetes monitors the application.
    
6. It can restart failed containers and scale workloads when configured.
    

### Advantages

- Automated deployment.
    
- Container orchestration.
    
- Application scaling.
    
- Fault recovery.
    
- Efficient resource management.
    

### Limitations

- Complex setup and administration.
    
- Requires knowledge of networking and container management.
    
- May introduce unnecessary overhead for small applications.
    
- Not every HPC workload benefits from Kubernetes orchestration.
    

### Docker vs Kubernetes

|Docker|Kubernetes|
|---|---|
|Container platform|Container orchestration platform|
|Builds and runs containers|Manages containers across clusters|
|Handles container packaging|Handles scheduling and scaling|
|Used for application isolation|Used for large-scale deployment|
|Example: Docker Engine|Example: Kubernetes cluster|

**Important:** Docker and Kubernetes are complementary technologies, not direct replacements for each other.

---

## 13. Energy Efficient Computing

[[Energy Efficient Computing]] is the design and operation of computing systems to minimise energy consumption while maintaining required performance.

Energy efficiency is important in HPC because large computing systems consume significant electrical power and produce substantial heat.

### Need for Energy Efficiency

- Reduces electricity costs.
    
- Reduces cooling requirements.
    
- Decreases environmental impact.
    
- Improves system sustainability.
    
- Enables more computation per unit of energy.
    

### Important Concepts

#### 13.1 Power Consumption

[[Power Consumption]] is the rate at which a computer system uses electrical energy.

It is measured in watts (W).

#### 13.2 Energy Consumption

[[Energy Consumption]] is the total electrical energy used over a period of time.

**Formula:**

$$$$Energy = Power \times Time$$$$

If a system consumes 500 watts for 2 hours:

$$$$Energy = 500 \times 2 = 1000\ Wh = 1\ kWh$$$$

#### 13.3 Performance per Watt

[[Performance per Watt]] measures how much computational performance a system delivers for each watt of electrical power consumed.

**Formula:**

$$$$Performance\ per\ Watt = \frac{Performance}{Power}$$$$

A higher value indicates better energy efficiency.

#### 13.4 Dynamic Voltage and Frequency Scaling (DVFS)

[[Dynamic Voltage and Frequency Scaling (DVFS)]] adjusts processor voltage and frequency according to workload requirements.

- Lower frequency and voltage can reduce power consumption.
    
- Higher frequency can improve performance when needed.
    

#### 13.5 Power Management

Power management techniques include:

- Turning off unused resources.
    
- Using efficient processors.
    
- Optimising cooling systems.
    
- Reducing unnecessary computation.
    
- Managing CPU and GPU power states.
    

### Energy Efficient HPC Techniques

1. Use energy-efficient processors.
    
2. Optimise algorithms to reduce computation.
    
3. Improve processor utilisation.
    
4. Use efficient cooling systems.
    
5. Apply DVFS where appropriate.
    
6. Monitor power consumption.
    
7. Reduce unnecessary data movement.
    

### Importance of Energy Efficiency in Supercomputers

Large supercomputers may contain thousands of processors and accelerators. Their energy consumption directly affects operational cost and environmental sustainability.

---

## 14. Important Comparisons for Examinations

### CPU vs GPU vs FPGA

|CPU|GPU|FPGA|
|---|---|---|
|General-purpose processing|Massively parallel processing|Reconfigurable hardware|
|Few powerful cores|Many processing cores|Custom logic circuits|
|Flexible instruction execution|High throughput for parallel tasks|Specialised low-latency operations|
|General applications|AI and scientific computing|Signal processing and acceleration|

### Shared Memory vs Distributed Memory

|Shared Memory|Distributed Memory|
|---|---|
|Processors access common memory|Each node has its own memory|
|Communication through shared variables|Communication through message passing|
|Easier data sharing|Requires explicit communication|
|Example: Multicore system|Example: HPC cluster|

### Cloud HPC vs Traditional HPC

|Cloud HPC|Traditional HPC|
|---|---|
|Resources rented from cloud providers|Physical infrastructure owned or managed locally|
|Flexible scaling|Scaling requires hardware procurement|
|Pay-as-you-use or other cloud pricing|High initial infrastructure cost|
|Less physical maintenance|Requires local maintenance|
|Depends on cloud network and service availability|Greater direct infrastructure control|

### Docker vs Kubernetes

|Docker|Kubernetes|
|---|---|
|Builds and runs containers|Orchestrates containers|
|Container lifecycle management|Cluster-wide workload management|
|Suitable for packaging applications|Suitable for deploying at scale|

---

## 15. Important Examination Questions

### 2-Mark Questions

1. Define GPU computing.
    
2. What is CUDA?
    
3. Define CUDA kernel.
    
4. What is a thread block?
    
5. What is heterogeneous computing?
    
6. Expand FPGA.
    
7. What is an HPC cluster?
    
8. Define job scheduling.
    
9. What is SLURM?
    
10. Define Cloud HPC.
    
11. Name two cloud platforms that provide HPC services.
    
12. What is Docker?
    
13. Define Kubernetes.
    
14. What is a container?
    
15. Define energy-efficient computing.
    
16. What is DVFS?
    
17. Define performance per watt.
    
18. What is an FPGA's configurable logic block?
    

### 5-Mark Questions

1. Explain GPU computing and its applications.
    
2. Explain the basic architecture of CUDA.
    
3. Describe the CUDA thread hierarchy.
    
4. Explain heterogeneous computing with a diagram.
    
5. Explain FPGA architecture and its applications.
    
6. Describe cluster computing architecture.
    
7. Explain different types of computing clusters.
    
8. Explain job scheduling and resource managers.
    
9. Describe SLURM and its important commands.
    
10. Explain the advantages and disadvantages of Cloud HPC.
    
11. Discuss HPC services provided by AWS.
    
12. Explain HPC services offered by Microsoft Azure and Google Cloud.
    
13. Explain Docker architecture and its components.
    
14. Explain Kubernetes architecture and its components.
    
15. Discuss techniques for energy-efficient computing.
    

### 10-Mark Questions

1. Explain GPU computing fundamentals and discuss the NVIDIA CUDA programming model with a suitable diagram.
    
2. Explain heterogeneous computing and compare CPU, GPU, and FPGA architectures.
    
3. Describe FPGA architecture, working principles, advantages, disadvantages, and applications in HPC.
    
4. Explain cluster computing architecture, its components, working, and types.
    
5. Discuss job scheduling algorithms and resource management in HPC systems.
    
6. Explain Cloud HPC and compare AWS, Microsoft Azure, and Google Cloud services.
    
7. Explain containerization using Docker and Kubernetes with their architectures and differences.
    
8. Discuss energy-efficient computing techniques and their importance in HPC systems.
    

---

## 16. Quick Revision

|Topic|Key Point|
|---|---|
|Accelerator|Specialised hardware for faster computation|
|GPU|Processor designed for massive parallelism|
|CUDA|NVIDIA parallel computing platform|
|Host|CPU and system memory|
|Device|GPU|
|Kernel|Function executed by GPU threads|
|Thread|Smallest CUDA execution unit|
|Thread Block|Group of CUDA threads|
|Grid|Collection of thread blocks|
|Heterogeneous Computing|Uses different processing units together|
|FPGA|Reconfigurable integrated circuit|
|Cluster Computing|Multiple connected computers work together|
|Compute Node|Performs computational tasks|
|Head Node|Manages cluster operations|
|Job Scheduler|Assigns jobs to computing resources|
|SLURM|HPC workload manager|
|Cloud HPC|HPC resources delivered through cloud infrastructure|
|AWS|Amazon cloud platform|
|Azure|Microsoft cloud platform|
|GCP|Google cloud platform|
|Docker|Builds and runs containers|
|Kubernetes|Orchestrates containers|
|Energy Efficiency|More performance with less energy|
|DVFS|Adjusts processor voltage and frequency|

## 17. Conclusion

Accelerators, clusters, and cloud platforms are important components of modern [[High Performance Computing]]. GPUs and FPGAs accelerate specialised computations, while heterogeneous systems combine different processing technologies.

Cluster computing connects multiple nodes to solve large computational problems. Job schedulers and resource managers coordinate these systems. Cloud platforms such as [[AWS]], [[Microsoft Azure]], and [[Google Cloud]] provide scalable HPC infrastructure.

Finally, [[Docker]] and [[Kubernetes]] support portable and manageable computing environments, while energy-efficient computing helps reduce power consumption and operational costs.