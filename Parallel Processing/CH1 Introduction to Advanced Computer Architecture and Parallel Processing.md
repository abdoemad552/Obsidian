High performance in computer systems may come from:
1. Fast dense circuitry.
2. Packaging technology.
3. Parallelism.

# What are parallel processors?
Parallel processors are:
* Computer systems
* Consisting of multiple processing units
* Connected together via some interconnection network
* With the existence of a software that **manages the communication between them**.

# Parallel processors computer systems are categorized according to two factors:
1. Processing units themselves.
2. The interconnection network that ties them together.

# How can processing units communicate together?
We are concerned with two methods:
1. **Shared memory**: Shared memory is a communication paradigm in parallel processing in which multiple processors share a common memory space. The shared memory can be accessed by all processors allowing them to read and write from the same memory locations.
	* The interconnection for shared memory can be classified as **bus-based** and **switch-based**.
2. Message passing: message passing is a communication paradigm in parallel processing in which the processing units communicate together by sending and receiving messages.
	* The interconnection in message passing can **static connection** or **dynamic connection**.

# What is the difference between Bus-based and Switch-based interconnection in case of shared memory?
Bus-based and switch-based interconnection networks are both common architectures used in parallel computing systems, but they have different characteristics and trade-offs.
- **Bus-based**: In a bus-based network, all nodes are connected to a shared communication bus. Nodes communicate by broadcasting messages onto the bus, and all nodes can listen to messages on the bus. It forms a single shared communication medium.
- **Switch-based**: Switch-based networks use switches or routers to connect nodes in a point-to-point or mesh topology. Each node is typically connected to one or more switches, and communication between nodes involves routing through these switches.

# What is the difference between static and dynamic interconnection in case of message passing?
Static and dynamic connections in message passing refer to the way in which processes establish communication channels for exchanging messages.
* In **static connections**, the communication channels between processes are established before execution begins and remain fixed throughout the execution of the program. Once established, processes communicate exclusively through these predetermined channels.
* In **dynamic connections**, processes establish communication channels as needed during program execution. Processes can create, modify, and close communication channels dynamically based on runtime conditions and requirements.

# What is the purpose of using multiprocessors in computer systems?
1. Creating high performance computer systems.
2. Multiprocessor computer systems are expected to reach faster speeds than the fastest single processor computer system.
3. Cost effective.
4. Fault tolerance; If a processor fails, the remaining processors should be able to provide continued service (even if the performance is degraded).

A **cluster** is a collection of stand-alone computers connected using some interconnection network.

The pervasiveness إنتشار of the Internet created interest in **network computing** and more recently in grid computing. Grids are geographically distributed platforms of computation. They should provide **dependable**, **consistent**, **pervasive**, and **inexpensive** access to high-end computational facilities.
# What is the basis of Flynn's taxonomy?
Flynn based his classification on the notion of a stream of information. Two types of information flow into the processor: Instruction stream and Data stream.
# Compare between Instruction stream and Data stream.
**Instruction stream** is defined as the sequence of instructions performed or executed by the processing unit.
**Data stream** is defined as the data traffic being exchanged between the memory unit an the processing unit.
# What are the four categories of computer architecture?
Flynn categorized computer architecture into four categories:
1. Single Instruction Single Data (SISD).
2. Single Instruction Multiple Data (SIMD).
3. Multiple Instruction Single Data (MISD).
4. Multiple Instruction Multiple Data (MIMD).
# Which of these categories are considered to achieve parallelism?
SIMD and MIMD.
# Give an example on SISD systems.
Conventional single-processor von Neumann computers.
# Compare between SIMD and MIMD.
In SIMD all processors have the same control unit which makes them execute the same instruction in a **synchronized** fashion.
In MIMD each processor has its own control unit and can execute different instructions on different data.
![[Pasted image 20240219074527.png]]
![[Pasted image 20240219074626.png]]
![[Pasted image 20240219074756.png]]

In SIMD:
* The processor array is a set of identical synchronized processing elements capable of simultaneously performing the same operation on **different data**.
* A program can be developed and executed on the front end using a traditional serial programming language.
* Processors either do nothing or exactly the same operations at the same time.
* This paradigm is most useful for solving problems that have lots of data that need to be updated on a **wholesale basis**.

In SIMD there are two main configurations:
1. In the first scheme each processor has its own local memory. Processors can communicate with each other through the interconnection network. If the interconnection network does not provide direct connection between a given pair of processors, then this pair can exchange data via an **intermediate** processor.
![[Pasted image 20240219214534.png]]
2. In the second scheme the processors communicate with memories via interconnection network. Two processors can transfer data between each other via intermediate memory module(s) or possibly via intermediate processor(s).
![[Pasted image 20240219214600.png]]

In MIMD there are two categories: shared memory or message passing.
* Processors exchange information through their central shared memory in shared memory systems, and exchange information through their interconnection network in message passing systems.
* A **shared memory** system typically accomplishes inter-processor coordination through a global memory shared by all processors. Because access to shared memory is **balanced**, these systems are also called SMP (**symmetric multiprocessor**) systems. Each processor has equal opportunity to read/write to memory, including equal access speed.
* A message passing system (also referred to as **distributed memory**) typically combines the local memory and processor at each node of the interconnection network. There is no global memory, so *it is necessary to move data from one local memory to another by means of message passing*. This is typically done by a Send/Receive pair of commands, which must be written into the application software by a programmer.

Programming in the shared memory model was easier, and designing systems in the message passing model provided scalability.

A hybrid configuration of these two is the Distributed Shared Memory architecture (memory is physically distributed but the programming model follows the shared memory school of thought).

# Shared Memory Organization
A shared memory model is one in which processors communicate by reading and writing locations in a shared memory that is equally accessible by all processors.

The issues related to shared memory organization:
1. **Access control**: Access control determines which process accesses are possible to which resources.
2. **Synchronization**: Synchronization constraints limit the time of accesses from sharing processes to shared resources.
3. **Protection**: Protection is a system feature that prevents processes from making arbitrary access to resources belonging to other processes.
4. **Security**.

## What is the purpose of access control table?
Access control table contains flags that determine the legality of each access attempts.

**Cache Coherence**: Cache coherence protocols are employed to ensure that the data stored in the private caches remains consistent with the data in the shared memory. When a processor reads from or writes to a memory location, the coherence protocol ensures that all copies of that data in other caches are updated accordingly. This coherence is essential for maintaining the illusion of a single, unified shared memory space across all processors.

Shared memory systems can be classified as:
1. Uniform Memory Access (**UMA**): In the UMA system, a shared memory is accessible by all processors through an interconnection network in the same way a single processor accesses its memory. Therefore, **all processors have equal access time to any memory location**.
2. Non-Uniform Memory Access (**NUMA**): In the NUMA system, each processor has part of the shared memory attached. The memory has a single address space. Therefore, any processor could access any memory location directly using its real address. However, the access time to modules depends on the distance to the processor. This results in a nonuniform memory access time.
3. Cache Only Memory Access (**COMA**).

# Message Passing Organization
* Communications in message passing systems are performed via send and receive operations.
* Processors do not share a global memory and each processor has access to its own address space.
* The message passing approach is, in principle, scalable to large proportions.
* Two important design factors must be considered in designing interconnection networks for message passing systems. These are the link ***bandwidth*** and the network ***latency***. The link bandwidth is defined as the number of bits that can be transmitted per unit time (bits/s). The network latency is defined as the time to complete a message transfer.

Network interconnection can be classified according to:
1. Mode of operation (Synchronous vs Asynchronous).
2. Control strategy (Centralized vs Decentralized).
3. Switching techniques (Circuit vs Packet).
4. Topology (Static vs Dynamic).

# Compare between synchronous and asynchronous mode of operation.
* In **synchronous** mode of operation,  single global clock is used by all components of the system such that the whole system is operation in a lock-step manner.
* In **asynchronous** mode of operation, doesn't require a global clock. Instead, a handshaking technique is used in order to coordinate the operations the system.

Synchronous systems tend to be slower compared to asynchronous systems, they are race and hazard-free.

Synchronous systems can be slower compared to asynchronous systems because they often operate at the speed of the clock. If any operation takes longer than a single clock cycle, the system must wait until the next clock cycle to proceed, leading to potential idle time.

# Compare between centralized and decentralized control systems.
* In **centralized** control system, a single centralized control unit controls the operation of all other components on the system.
* In **decentralized** control system, the control function is distributed among different components in the system.

The function and reliability of the central control unit can become the bottleneck in a centralized control system.

# Compare between circuit switching and packet switching mechanism.
* In the **circuit switching** mechanism, a complete path has to be established prior to the start of communication between a source and a destination. The established path will remain in existence during the whole communication period.
* In a **packet switching** mechanism, communication between a source and destination takes place via messages that are divided into smaller entities, called packets. On their way to the destination, packets can be sent from a node to another in a store-and-forward manner until they reach their destination.

While packet switching tends to use the network resources more efficiently compared to circuit switching, it suffers from variable packet delays.

Popular Static topologies include:
* Linear
* Ring
* Mesh
* Tree
* Hypercube

