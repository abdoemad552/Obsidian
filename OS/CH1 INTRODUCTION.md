An **operating system** is a program that manages a computer’s hardware. It also provides a basis for application programs and acts as an intermediary between the **computer user** and the **computer hardware**.

Some operating systems are designed to be convenient, others to be efficient, and others to be some combination of the two.

A **computer system** can be divided roughly into four components:
1. **Hardware**
		Hardware components include CPU, memory, and I/O devices.
		Provides the basic computing resources for the computer system.
2. **Operating system**
		Operating system controls the hardware and coordinates its use for various application programs.
3. **Application programs**
		Defines the ways in which the resources are being used to solve users' computing problems.
		Application programs such as word processors, compilers, and web browsers.
4. **Users**
		Users include people, machines, and other computers.

We can view a computer system as consisting of hardware, software, and data.

Resource allocation is the process of managing system resources and share them with users and application programs in a way that provides efficiency and fairness.

Operating system can be thought as a **resource allocator** and **control program**.

A **control program** manages the execution of user programs to prevent errors and improper use of the computer. It is especially concerned with the operation and control of I/O devices.

The fundamental goal of computer systems is to execute user programs and to make solving user problems easier.

The operating system is the one program running at all times on the computer—usually called
the **kernel**.

Along with the kernel, there are two other types of programs:
	**System programs**, which are associated with the operating system but are not necessarily part of the kernel.
	**Application programs**, which include all programs not associated with the operation of the system.

In many systems, duplication of resources is used to ensure fault tolerance. For example HP Non-Stop system use multiple pairs of CPUs. A pair of CPUs is used for executing the same instructions and the result of each CPU is compared. If there is a difference, then one of the pair is fault, and both are halted. The process that was being executed is then moved to another pair of CPU.

There are two types of multiprocessor systems:
1. Symmetric Multiprocessing (**SMP**): each processor performs all tasks within the operating system. SMP means that all processors are peers; no boss–worker relationship exists between processors.
2. Asymmetric Multiprocessing: A boss processor controls the system; the other processors either look to the boss for instruction or have predefined tasks.

There are two types of memory access:
1. Uniform Memory Access (**UMA**): In this type, the time taken to access any memory from and processor takes the same amount of time.
2. Non-uniform Memory Access (**NUMA**): In this type, some parts of some memories takes longer time for access than other parts.

Operating systems can minimize the NUMA penalty through resource management.

On-chip communication happens between components of the same chip. For example if we have multicore processor, the communication between these cores is called On-chip communication.

Between-chip communication happens between different chips on the board. For example between multiple processors.

