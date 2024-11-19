# UNIT 1
## INTRO
OS is a program that act as a intermediary b/w computer user and computer.
OS provides an environment to run various application program.
OS is a program that manages computer hardware
OS provides convinence to its users and provides efficient resource allocation and act as good resource manager.
![](../../statics/Pasted%20image%2020240909172132.png)

### Goals 
- Primary Goal (convinence / userfriendly)
- Secondary Goal (efficiency (Using resource in efficient manner) Reliability /maintainability)

### Functions
- Process management:- invole handling the creation ,scheduling and termination of process which are executing program.
- Memory management:- manages allocation and deallocation of physical and virtual Memory
- I/O management:- handles I/O operations of peripheral devices
- File management:- manages files on storage devices , including their information , naming permissions etc.
- Network management:- manages network protocoles and functions , enabling the OS to establish network connection.
- Security and protection

## Structure of OS

### INTRO
- common approach is to partition the tasks into small components , or modules , rather than have one monolithic system.

#### Simple Structure
- many OS do not have well-defined structures. initially started as simple ,small and limited system and then grew beyond their original scope. MS-DOS
- not divided into modules. its interface , levels and functionality are not well separated.

#### Layered approach
![](../../statics/Pasted%20image%2020240909183111.png)

#### Micro-kernel approach
- this method structures the OS by removing all nonessential component from kernel and implementing them as system and user-level program. the result is small kernel.
![](../../statics/Pasted%20image%2020240909183324.png)
- Mach OS used Micro-kernel approach.
- benefit is , it makes extending the OS easier. All services are added to user space and consequently do not require modification of kernel.

## System Calls
- provides means for a user program to ask the OS to perform tasks reserved for OS on the user program behalf.
![](../../statics/Pasted%20image%2020240909183847.png)
- it provides a interface to the services made available by OS. these calls are generally available as routines written in C and C++.
- API specifies a set of functions that are available to an application programmer, including the parameters that are passed to each function and the return values the programmer can except.

## Types of OS 

### Batch OS
A Batch Operating System is one of the earliest types of operating systems designed for managing jobs (tasks) in batches.

![](../../statics/Pasted%20image%2020240909173859.png)

#### Key Concepts:
1. **Batch Processing**:
   - Jobs are grouped into batches and processed sequentially.
   - Users submit jobs to a central place (often to an operator).
   - The operating system processes the jobs one after another without user intervention.
2. **Job Queue**:
   - Jobs are collected and placed in a queue.
   - The system executes jobs automatically in the order they are submitted or based on priority.
3. **Non-interactive System**:
   - Once jobs are submitted, there is no direct interaction between the user and the computer.
   - Users only get the results after the entire batch of jobs has been processed.
4. **Job Control Language (JCL)**:
   - Early batch systems used a scripting language, like **Job Control Language (JCL)**, to define job commands, including input/output instructions.

#### Characteristics of Batch Operating Systems:
1. **Automatic Job Execution**:
   - The system automatically selects and runs jobs from the batch queue in sequence.
2. **Efficient for Large Jobs**:
   - Suitable for repetitive, large-scale jobs (e.g., payroll systems, data processing).
3. **Minimal User Interaction**:
   - Users submit jobs and only receive output after job completion, with no real-time input required.
4. **Resource Sharing**:
   - The system efficiently shares CPU, memory, and other resources among multiple jobs, reducing idle time.
5. **Job Scheduling**:
   - Batch systems typically include job scheduling mechanisms to prioritize jobs and allocate resources efficiently.
6. **Sequential Job Execution**:
   - Jobs are executed one after the other, usually in the order of submission, unless job prioritization is implemented.

#### Advantages of Batch Operating Systems:
1. **Increased Throughput**:
   - By processing jobs in batches, system utilization is maximized, and more jobs are completed in a shorter time.
2. **Efficient for Long Jobs**:
   - Large and time-consuming jobs can be processed without user interaction, making it efficient for background tasks.
3. **Reduces Setup Time**:
   - Jobs are processed in batches, minimizing the setup time required for each individual job.
4. **Simplicity**:
   - The system automates job execution, making it easier for users to submit large tasks without worrying about real-time interaction.

#### Disadvantages of Batch Operating Systems:
1. **No Real-Time Interaction**:
   - Users must wait until the entire batch is processed to receive their results, which can be inefficient for time-sensitive tasks.
2. **Debugging Difficulty**:
   - Debugging errors can be challenging because there is no immediate feedback. Users only discover errors after the job is processed, requiring resubmission.
3. **Idle Time**:
   - If there are no jobs in the queue, system resources (like CPU) may sit idle until new jobs are submitted.
4. **Delayed Execution**:
   - Low-priority jobs may experience long delays as they wait in the queue, particularly if higher-priority jobs are added continuously.
5. **Rigid Scheduling**:
   - Without real-time user control, scheduling is rigid, and long jobs can block the queue for an extended period.

#### Examples of Batch Operating Systems:
1. **Unix Batch Processing**:
   - Unix-like systems (e.g., Linux) still allow for batch processing using commands like `batch`, `cron`, or `at` for scheduling jobs.

#### Applications of Batch Operating Systems:
1. **Payroll Processing**:
   - Payroll systems that process salary data, generate paychecks, and calculate taxes are typically processed in batches.
2. **Billing Systems**:
   - Utility companies process billing information in large batches at the end of each billing cycle.

### Multiprogramming OS

![](../../statics/Pasted%20image%2020240909174552.png)

- Multiple Jobs:- keeps several jobs in main memory simultaneously , allowing more efficient use of CPU.
- Job execution:- OS picks and begins to execute one of the jobs in memory. 
- waiting jobs:- eventually a job need to wait for a task like I/O operation to complete.
- Non-multiprogrammed:- CPU sits idle while waiting for a job to get completed.
- multiprogrammed:- OS switch to and execute another job if the current job need to wait, utilizing the CPU effectively.

Conclusion:- Efficient utilization.

#### +ves 
- high cpu utilization
- less waiting time
- multi-task handling 
- shared CPU time.

#### -ves 
- complex scheduling
- complex memory management

### Multitasking OS / time sharing / multi programming with round robin / fair share
- It is a logical extension of multi programming , it allows many users to share computer simultaneously. the CPU execute multiple jobs by switching among them. but the switch occurs so rapidly that it give user impression of parallelism. 
- For Multitasking to take place , firstly there should be multi-programming i.e presence of multiple program ready for execution. and secondly the concept of time sharing.

![](../../statics/Pasted%20image%2020240909180044.png)

### Multi processing OS / tightly coupled system
- multiprocessor OS refers to the use of two or more CPU within a single computer system. these multiple cpu share system bus , memory and other peripheral devices.
- multiple concurrent processes each can run on a separate CPU, here achieving a true parallelism.

![](../../statics/Pasted%20image%2020240909180519.png)
![](../../statics/Pasted%20image%2020240909180603.png)
![](../../statics/Pasted%20image%2020240909180651.png)

### Real time OS
- special purpose OS which has well defined time constraints. Processing must be done within the defined time limit or system will fail.
- valued more quickly or how predictably it can respond, without buffer delays than for the amount of work it can perform in a given time period.
- For eg: Air traffic control system , petroleum refinery.
![](../../statics/Pasted%20image%2020240909181137.png)
![](../../statics/Pasted%20image%2020240909181150.png)

### Distributed OS
- It is a software over a collection of independent, networked, communicating, loosely coupled nodes and physically separate computational nodes.
- nodes communicate with one another through various network such as internet. they handle jobs which are serviced by multiple CPUs. Each individual node holds a specific software subset of the global aggregate OS.
- Suitable when :- resource sharing, computation speedup,Reliability, communication.

![](../../statics/Pasted%20image%2020240909181638.png)


# UNIT 2

## Process
- It is a program in execution.
- A program is not a process by default. program is a passive entity i.e a file containing a list of instructions stored on disk.
- program becomes process when an executable file is loaded into main memory and when its PCB is created.
- A process on the other hand is an active entity , which requires resources like main memory, CPU time, register , system buses etc.
![](../../statics/Pasted%20image%2020240909190011.png)
![](../../statics/Pasted%20image%2020240909190140.png)
![](../../statics/Pasted%20image%2020240909190224.png)

### PCB (Process control block)
- each process is represented in OS by PCB also called task control block.
- PCB simply serves as a repository for any information that may vary from process to process. It contains many piecies of information
- process state:- the state may be new , ready , running , waiting , halted and so on.
- program counter:- contains address of next instruction to be executed for this process.
- CPU register:- the register vary in number and type , depending on computer architecture. like accumulators etc.
- CPU scheduling information:- includes process priority, pointers to scheduling queues, and any other scheduling parameters.
- memory management information:- 

### Process State
![](../../statics/Pasted%20image%2020240909190825.png)
![](../../statics/Pasted%20image%2020240909190931.png)


## Scheduling 
#### Intro
- Scheduling :- process of determining which process in ready queue is allocated to CPU
- Types
	- Non-pre-emptive:- once CPU has been allocated to process , the process keep the CPU until it release the CPU willingly
	- ![](../../statics/Pasted%20image%2020241111174405.png)
	- ![](../../statics/Pasted%20image%2020241111174429.png)
	- ![](../../statics/Pasted%20image%2020241111174516.png)
	- ![](../../statics/Pasted%20image%2020241111180212.png)
#### Scheduling Performance criteria
- CPU Utilisation
- Throughput:- number of process per unit time.
- Waiting time
- Response time:- time takes to start responding , not the time takes to output response

#### Terms 
![](../../statics/Pasted%20image%2020241111174819.png)
- Convey effect:- if smaller process has to wait more for the CPU because of Larger process then this effect is called convey effect , it result in more avg waiting time. Solution. smaller process have to be executed before longer process.

#### Multilevel scheduling
![](../../statics/Pasted%20image%2020241111181225.png)
![](../../statics/Pasted%20image%2020241111181404.png)
## Deadlock
![](../../statics/Pasted%20image%2020241111181834.png)
![](../../statics/Pasted%20image%2020241111182017.png)
![](../../statics/Pasted%20image%2020241111182150.png)
![](../../statics/Pasted%20image%2020241111182205.png)
![](../../statics/Pasted%20image%2020241111182317.png)
![](../../statics/Pasted%20image%2020241111182454.png)

## Deadlock handling 
![](../../statics/Pasted%20image%2020241112075301.png)
![](../../statics/Pasted%20image%2020241112075322.png)
![](../../statics/Pasted%20image%2020241112075339.png)
![](../../statics/Pasted%20image%2020241112075419.png)
![](../../statics/Pasted%20image%2020241112075451.png)
![](../../statics/Pasted%20image%2020241112075520.png)
Deadlock avoidance is a strategy in operating systems to prevent situations where processes become indefinitely blocked, waiting for resources held by each other. Unlike deadlock prevention, which limits resource allocation to avoid circular waiting, deadlock avoidance dynamically examines resource allocation to ensure safe states.

### Key Concepts of Deadlock Avoidance

1. **Deadlock Conditions**:
   - Deadlock occurs when the following four conditions hold simultaneously:
     - **Mutual Exclusion**: Only one process can use a resource at a time.
     - **Hold and Wait**: Processes holding resources can request additional ones.
     - **No Preemption**: Resources cannot be forcibly taken; they must be released by the process.
     - **Circular Wait**: A closed chain of processes exists where each process holds resources requested by the next.
   - Deadlock avoidance aims to prevent circular wait through careful resource allocation.

2. **Safe and Unsafe States**:
   - A **safe state** is one in which the system can allocate resources without leading to a deadlock, as it can guarantee each process will eventually finish.
   - An **unsafe state** doesn’t mean a deadlock occurs immediately, but it has a potential for deadlock if resource requests are handled poorly.
   - Deadlock avoidance algorithms ensure the system remains in a safe state.

3. **Banker’s Algorithm**:
   - One of the most well-known deadlock avoidance algorithms.
   - Works by analyzing the maximum resources each process might need and ensuring that resources are only allocated if they keep the system in a safe state.
   - **Algorithm steps**:
     - Check if enough resources are available to fulfill the request.
     - Pretend to allocate the resources and test if the system remains in a safe state.
     - If safe, allocate resources; otherwise, deny the request.

4. **Resource Allocation Graph (RAG)**:
   - A graphical approach to model resource allocation and detect potential deadlocks.
   - **Claim Edges**: Show potential future requests (dotted lines).
   - If all requests can be resolved without forming a cycle, the allocation is safe; if a cycle forms, a deadlock risk exists.
   
5. **Advantages of Deadlock Avoidance**:
   - Prevents deadlocks by maintaining safe states and carefully granting resource requests.
   - More flexible than deadlock prevention since it doesn’t impose strict rules on resource allocation and usage.

6. **Challenges of Deadlock Avoidance**:
   - Requires knowledge of maximum resource requirements, which can be difficult to predict.
   - May involve complex calculations, especially in systems with multiple resources and processes.
   - Inefficient for high-load systems, as it may delay processes to avoid entering an unsafe state.

### When to Use Deadlock Avoidance
- Suitable for systems where resource usage is predictable.
- Common in databases, real-time systems, and operating systems where resources are managed and predictable constraints are in place.
## Memory 
![](../../statics/Pasted%20image%2020241112063441.png)
![](../../statics/Pasted%20image%2020241112063909.png)
![](../../statics/Pasted%20image%2020241112064028.png)
![](../../statics/Pasted%20image%2020241112064109.png)
![](../../statics/Pasted%20image%2020241112065239.png)
![](../../statics/Pasted%20image%2020241112065425.png)


![](../../statics/Pasted%20image%2020241112065638.png)
![](../../statics/Pasted%20image%2020241112065732.png)![](../../statics/Pasted%20image%2020241112070035.png)
![](../../statics/Pasted%20image%2020241112070126.png)
![](../../statics/Pasted%20image%2020241112070243.png)
![](../../statics/Pasted%20image%2020241112070329.png)
![](../../statics/Pasted%20image%2020241112070458.png)
In operating systems, paging is a memory management technique that allows processes to use more memory than physically available by dividing memory into fixed-size blocks, or pages. This helps in efficiently managing and allocating memory while supporting multi-programming. Here’s an overview:

### 1. **Paging Basics**
   - Physical memory (RAM) is divided into fixed-size blocks called **frames**.
   - Logical memory (address space of a process) is divided into equally sized **pages**.
   - Pages of a process are mapped to frames in physical memory through a **page table**.

### 2. **Page Table**
   - Each process has a page table that keeps track of where its pages are stored in physical memory.
   - The page table maps each page in virtual memory to a frame in physical memory.
   - **Page table entries (PTEs)** typically contain the frame number, protection bits (read/write), and a valid/invalid bit.

### 3. **Page Faults**
   - A **page fault** occurs when a process tries to access a page not currently in physical memory.
   - The OS handles a page fault by loading the missing page from secondary storage (e.g., disk) into a free frame in RAM.
   - This may involve **page replacement** if no free frames are available, where the OS swaps out a page from RAM to disk.

### 4. **Page Replacement Algorithms**
   - To manage limited physical memory, the OS may need to replace pages in memory with pages from disk.
   - Common algorithms include:
     - **FIFO (First-In, First-Out)**: Replaces the oldest page in memory.
     - **LRU (Least Recently Used)**: Replaces the page that hasn't been used for the longest time.
     - **Optimal**: Replaces the page that won’t be used for the longest time in the future (theoretical).

### 5. **Benefits of Paging**
   - **Eliminates External Fragmentation**: Pages are of a fixed size, so there’s no external fragmentation.
   - **Efficient Memory Use**: Processes can use non-contiguous memory, allowing better use of available memory.
   - **Virtual Memory**: Enables processes to use more memory than is physically available.

### 6. **Challenges**
   - **Page Table Overhead**: Page tables can become large, especially with large virtual address spaces.
   - **TLB (Translation Lookaside Buffer)**: A cache used to speed up virtual-to-physical address translation by storing recent translations.
   - **Swapping Overhead**: Frequent page faults and swaps can slow down the system.

Paging thus enables efficient memory management, supporting virtual memory and multi-programming but requires effective page replacement strategies to maintain performance.

![](../../statics/Pasted%20image%2020241112071531.png)
The **Translation Lookaside Buffer (TLB)** is a specialized, high-speed cache in a computer’s memory management unit (MMU) that stores recent translations of virtual memory addresses to physical memory addresses. The TLB is essential for speeding up the virtual memory process by reducing the time it takes to translate virtual addresses to physical addresses.

1. **Purpose of the TLB**:
   - Every time a program accesses memory, the virtual address it uses must be translated to a physical address in RAM. This is done by looking up page tables, which can be a slow process.
   - The TLB stores recent address translations, allowing the system to skip the page table lookup for frequently accessed addresses and directly retrieve the physical address.
   - By caching these translations, the TLB significantly speeds up memory access for the CPU.

2. **Structure of the TLB**:
   - A TLB is a small associative memory or content-addressable memory, meaning it can quickly match virtual addresses to physical addresses.
   - Each TLB entry holds a **virtual page number** and the corresponding **physical frame number**.
   - Additional information, such as access permissions, is often stored in each TLB entry.

3. **TLB Hit and Miss**:
   - **TLB Hit**: When a virtual address has a matching entry in the TLB, the physical address is retrieved directly, avoiding a time-consuming page table lookup.
   - **TLB Miss**: If there’s no matching entry in the TLB, the system performs a page table lookup to get the physical address. This is slower, but once retrieved, the translation is stored in the TLB for future use.

4. **Replacement Policies**:
   - Since the TLB has limited space, it cannot store all address translations, so older entries must be replaced.
   - Common replacement policies include **Least Recently Used (LRU)**, **First-In-First-Out (FIFO)**, or **Random Replacement**.

5. **Benefits of TLB**:
   - **Reduced Latency**: TLB significantly lowers the time required for address translation, which is essential for system performance, especially in multitasking environments.
   - **Higher CPU Efficiency**: By minimizing time spent on address translation, the TLB allows the CPU to execute instructions more efficiently.
   
6. **TLB and Context Switching**:
   - During a **context switch** (switching between processes), the TLB entries might become invalid since the new process has its own virtual-to-physical address mappings.
   - Some systems **flush the TLB** on every context switch, while others use **process-specific tags** (ASIDs or Address Space Identifiers) to retain entries between context switches.

7. **TLB in Multi-Level Paging**:
   - In systems with multi-level paging, the TLB is even more critical because multi-level page tables involve multiple memory accesses for each translation.
   - TLB entries help bypass these repeated lookups, making memory access quicker and more efficient.
The TLB is a small, fast cache for storing recent virtual-to-physical address translations, reducing the need for repeated page table lookups. Its presence is vital for efficient memory management, improving overall system performance by allowing quicker memory access.
## Segmentation 

![](../../statics/Pasted%20image%2020241112073504.png)

![](../../statics/Pasted%20image%2020241112073619.png)

| Feature                | Paging                                                             | Segmentation                                                                                                            |
| ---------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| **Division of Memory** | Divides memory into fixed-size pages.                              | Divides memory into variable-sized segments.                                                                            |
| **Logical Unit**       | Pages have no inherent meaning; they’re arbitrary units of memory. | Segments correspond to logical parts of a program (e.g., functions, arrays).                                            |
| **Size**               | Pages are typically a fixed size (e.g., 4 KB).                     | Segments vary in size based on the program’s structure.                                                                 |
| **Address Structure**  | Logical address is split into a page number and offset.            | Logical address has a segment number and offset.                                                                        |
| **Memory Table**       | Uses a page table to map pages to physical memory.                 | Uses a segment table to map segments to physical memory.                                                                |
| **Fragmentation**      | Leads to internal fragmentation (unused space within pages).       | Leads to external fragmentation (scattered free spaces between segments).                                               |
| **Protection**         | Typically less granular protection per page.                       | Allows fine-grained protection per segment.                                                                             |
| **Usage**              | Suitable for systems emphasizing efficient memory use.             | Suitable for systems that require modular programming.                                                                  |
| **Example Use Cases**  | Common in virtual memory systems like Linux or Windows.            | Used in modular programming or systems that need logical separation, sometimes combined with paging for modern systems. |
