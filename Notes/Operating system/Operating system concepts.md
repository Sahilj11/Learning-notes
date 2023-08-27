## Program vs Process
- lets say you want to open google chrome , but initally it is not opened in RAM , now in HDD , copy of the program will be created 
- this copy is called process (it is important to note that multiple process can be craeted for a single program)
- Execution and I/O cannot be done at same time for a single process
### states of process
- New State :- when the process is created , it is in new state
- Ready state:- when the process is ready for execution or I/O event and waiting in RAM either for CPU or I/O
- Running State:- 
- I/O state :- interacting with I/O . also called blocked state
- terminated state:- once completed , removed from RAM
- Suspend Ready state:- 

## Degree of multiprogramming
- Maximum processes which can be placed in our RAM

## Types of Operating system 
- Batch OS :- degree of multiprogramming is 1 , only one process can be placed inside the RAM
- [[Operating system structure#^768556]]
- Multiprogramming OS:- multiple process happening in RAM
- Multiprocessing OS:- multiple core in CPU is example of multipleprocessing
- Parallel processing(multiple tasks been done parallel by CPU) vs concurrent processing(CPU swtiching b/w process)

## Process control block, attributes of process
- program from which a process is created is called passive entity
- whereas the process itself is called active entity
- All the called function goes in Stack. Heap is used for dynamic memory 
- Block created for process where the memory for the process is been managed called process control block
- The Process Control Block (PCB) is a data structure used by operating systems to manage and store information about a specific process. Each process in an operating system has an associated PCB that contains crucial information required for the management and execution of the process. The PCB is typically created when a process is created and is updated as the process executes and interacts with the operating system.
- The PCB contains various pieces of information about a process, including:
	1. Process state: This field indicates the current state of the process, such as running, ready, blocked, or terminated. The OS uses this information to determine which processes are eligible for execution and which processes are waiting for certain events to occur.	    
	2. Program counter (PC): The PC represents the memory address of the next instruction to be executed in the process. When a context switch occurs [[CPU scheduling algo#^bedcda]], the PC value is saved in the PCB of the currently running process and later restored when the process resumes execution.	    
	3. CPU registers: The PCB stores the values of CPU registers for the process, including general-purpose registers, stack pointer, and other architecture-specific registers. Saving and restoring these register values during a context switch ensures that the process can resume execution seamlessly.	    
	4. Process identification: The PCB contains a unique identifier for the process, such as a process ID (PID), which helps the operating system distinguish between different processes.	    
	5. Memory management information: This section of the PCB holds information about the process's memory allocation, such as the base address and size of its memory segments or pages. It allows the OS to manage the process's memory resources effectively.	    
	6. Resource ownership and utilization: The PCB maintains information about the resources allocated to the process, including open files, I/O devices, and other system resources. This data is crucial for managing resource sharing and enforcing resource allocation policies.	    
	7. Process scheduling information: The PCB may include scheduling-related information, such as the priority of the process, the amount of CPU time used by the process, and the scheduling algorithm-specific data. These details aid the OS in making scheduling decisions and determining the order in which processes should be executed   
- The PCB serves as a central repository of process-related information, enabling the operating system to manage and control processes effectively. When a process is not in execution, its PCB provides the necessary data for the OS to schedule, allocate resources, and resume execution when appropriate.
- Process attributes:- 
	- CPU scheduling(part of OS code) :- Done by scheduler , which decide which of the program loaded in RAM should be executed first (which one should be executed first depends on type of algo in scheduler , first come first serve , or fastest first). Importance of these attributes, lets say scheduler give CPU the process which execute the fastest first , CPU is executing a process , while execution a new process enter the RAM which can be executed much faster than process whcih is currently been executed . so the CPU will leave the current process and take the faster one and start executing . after finishing execution , CPU will take up previous process from where it left off. but how will it know where is that left off point in code . this is where these attributes come in handy 
	- process ID
	- Program counter:- also a register , tells from where code line in a process CPU  need to continue the execution
	- General purpose register
	- Priority 
	- List of open files
	- List of open devices 
	- Protection