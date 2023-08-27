- Process control block and attributes collectively called as context
-  ![[Pasted image 20230609110606.png]]
- In the above pic processes are given prirority number , higher number executed first. you can see no space in RAM , but p5 has the highest priority , so one of the process needs to be remove from RAM and come back to HDD for making space in RAM 
- This is decided by medium term scheduler
- this going out and bringing in called swapping
- Context switching is a fundamental concept in operating systems (OS) that refers to the process of saving and restoring the state of a running process or thread so that another process or thread can be executed. It involves switching the CPU from one process to another, allowing multiple processes to share the CPU's time and resources efficiently. ^bedcda
- When a context switch occurs, the OS saves the current execution context, which typically includes the values of the CPU registers, program counter, and stack pointer, among other important data. This saved context is stored in a data structure known as the process control block (PCB) or thread control block (TCB), which contains all the necessary information to resume the process or thread at a later point

## Various time of process
- Arrival time :- time at which process arrived at RAM from HDD
- ![[Pasted image 20230609112319.png]]
- Burst time also called execution time

## Scheduling Algo
- Non Preemptive SA:-  process in execution not stooped even if high priority process comes in RAM
- Preemptive SA :- opposite of Non P
- CPU scheduling algo applied only to process which are in ready state
- ![[Pasted image 20230609113326.png]]
- after CPU done with execution of P1 , which of the p will it be given . although P4 has highest priority , still P3 will be execute as scheduling apply to ready state
- Process which are in I/O state will be blocked and so those processes will not be considered by scheduling algorithms while scheduling. this is the reason why I/O state also called blocked state

### Shortest Job first algo
- Among the arrived process , process with the least burst time be given preference
- It is a non preemptive algo . Also it is a priority based 

### FCFS

### SRTF
