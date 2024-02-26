# Parallel computing can be in two forms:
1. **Shared memory** (load): in which a large piece of memory is shared between processors and hence more synchronization and less communication is needed.
2. **Distributed memory**: in which each processor has its own piece of memory which is smaller. In this we need more communication between processors.

# The overheads which are related with parallel computing are:
* Synchronization
* Distribution
* Communication.

**What are the elementary steps in parallel computing?**
* Degree of parallelism
* Initialization
* Work distribution
* Data I/O access
* Communication
* Synchronization

**Mention some APIs that are used in parallel computing.**
* MPI: Message Passing Interface
* OpenMP: Open Multi-Processing
* CUDA


# Increasing the degree of parallelism in parallel computing can have several advantages and disadvantages:

**Pros**:
1. **Improved Performance**: One of the primary advantages is the potential for increased computational speed and throughput. With more tasks executing simultaneously, the overall processing time can be significantly reduced.

2. **Scalability**: Higher degree of parallelism often leads to better scalability, allowing systems to handle larger workloads without sacrificing performance. This is particularly beneficial in environments where the workload may vary over time.

3. **Resource Utilization**: Increased parallelism can help in better utilization of available computational resources. Idle resources can be effectively utilized by distributing tasks across multiple processors or nodes.

4. **Fault Tolerance**: Parallel systems can often be designed with redundancy and fault tolerance in mind. If one processing unit fails, others can continue to work, reducing the impact of hardware failures on overall system operation.

5. **Flexibility**: Parallelism allows for greater flexibility in designing algorithms and applications. Tasks can be divided into smaller units, making it easier to adapt to different hardware configurations and optimize performance.

**Cons**:
1. **Complexity**: Parallel programming and system design are inherently more complex than sequential counterparts. Coordinating tasks, managing communication between processes, and ensuring data consistency can be challenging and error-prone.

2. **Overhead**: Parallelism introduces overhead in terms of communication and synchronization between parallel tasks. This overhead can sometimes outweigh the benefits of parallel execution, especially for fine-grained parallelism.

3. **Load Balancing**: Ensuring that work is evenly distributed across processing units can be difficult, especially if the workload is dynamic or heterogeneous. Load imbalance can lead to underutilization of some resources and decreased overall performance.

4. **Concurrency Issues**: Parallelism can introduce concurrency issues such as race conditions, deadlocks, and data inconsistencies. These issues can be difficult to debug and may require sophisticated synchronization mechanisms to resolve.

5. **Cost**: Building and maintaining parallel computing systems can be expensive, both in terms of hardware infrastructure and development effort. Specialized hardware, software tools, and skilled personnel may be required, increasing the overall cost of deployment.

# What Is High-Performance Computing (HPC)?
High-performance computing refers to the capacity of a system to process an *enormous amount of data and run complex models rapidly*. HPC programs, therefore, require a huge compute power to process terabytes, petabytes, or **even zettabytes** of data in real-time.
Thus, HPC relies on the principle of computing, networking, and data storage.

# Mention some application of HPC.
* Predictive Cardiovascular Health
* Understanding the Viral Genome
* Autonomous Driving Technology
* Augmented Reality
* NASA's Solar Weather Monitoring
* Aircraft Production and Aerodynamics

# Why using high clock speeds became more difficult?
* High power consumption
* Heating
* Increased current leakage

# **[Differences Between Core and CPU](https://www.baeldung.com/cs/core-vs-cpu#:~:text=It%20is%20responsible%20for%20executing,%2Dlogic%20unit%2C%20and%20memory.)**
[Click here for more about the difference between core and CPU](https://www.baeldung.com/cs/core-vs-cpu#:~:text=It%20is%20responsible%20for%20executing,%2Dlogic%20unit%2C%20and%20memory.)
![[Pasted image 20240222135703.png]]
The above image is a diagram of a dual-core and quad-core processor, which are two types of multi-core processors. Multi-core processors are processors that have multiple processing cores, which allows them to execute multiple instructions simultaneously. This can improve the performance of computers, especially for tasks that can be parallelized.

The diagram shows that each core has its own cache, which is a small amount of high-speed memory that stores frequently accessed data and instructions. The cores also share access to a larger main memory. The cores communicate with each other and with the main memory through an on-chip interconnect.

Dual-core processors have two cores, while quad-core processors have four cores. This means that quad-core processors can potentially execute up to four instructions at the same time, while dual-core processors can only execute up to two instructions at the same time.

However, it is important to note that not all tasks can be parallelized. For tasks that cannot be parallelized, a quad-core processor will not offer any performance advantage over a dual-core processor. Additionally, even for tasks that can be parallelized, there may be overhead associated with dividing the task up into multiple subtasks and coordinating the execution of those subtasks on different cores.

Overall, multi-core processors can improve the performance of computers for tasks that can be parallelized. However, it is important to consider the specific task at hand and the potential overhead of using multiple cores before deciding whether a multi-core processor is right for you.