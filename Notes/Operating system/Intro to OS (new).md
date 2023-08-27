## Main functionality of OS is resource allocation

## Process of executing program
- first loaded in RAM , then CPU read the code line by line and execute
- access time of RAM million time faster than HDD. 
- time taken by CPU to access data from HDD is very slow as compared to RAM , that is why data copied into RAM and thereon the CPU reads the data from RAM

## How hardware devices work together
- CPU cannot understand high level programming. through compiler it is converted to machine code (.exe , or executable code)
- this machine code is placed in hard disk
- CPU cannot directly access HDD directly 
- lets see CPU requesting of program 1 , CPU will look for it in RAM . if present in RAM CPU will fetch the program and execute it . if p1 not in RAM , copy of p1 from hardisk is placed in RAM, this happens when we execute (double clicked) it 

## Role of operating system in loading program
- Lets say RAM has capacity to load 50 programs , and HDD has cappacity to load 500 programs . how will the system know which 50 program to load in RAM first , one approach is to load programs which are more often used . certain algo can be written to tackle this issue
- This algo is written in OS:- It is also called a job scheduler. A long-term scheduler **determines which programs are admitted to the system for processing**. It selects processes from the queue (which are present in HDD )and loads them into memory (RAM) for execution. Process loads into the memory for CPU scheduling.
- Again the issue , lets say P1 and P2 program are loaded in RAM , how will CPU decide which program to execute first . again we need an algo , which is written in OS code 
- various approach can be taken to decide program, 1. by size , 2. by time it has been on RAM
- name of algo which handles this task is called short term scheduler

## How I/O device works
- when OS is started the code of OS is loaded into RAM , the space occupied by OS is called OS space
- remaining space called user space
- Every device will have buffer associated with it. 
- Understand this with an example 
	- Opening Calculator :-  doing 2 + 3 = 5 (now the program is waiting for I/O event)
		- first we press key 2 , this 2 will get stored in binary format in buffer. from buffer it gets moved into RAM. now when i press Key 3 , binary of 3 will overwrite 2 in buffer of keyboard and thereafter 3 binary gets moved to RAM
		- Now CPU will store those binarys of 2 and 3 in its registers or buffer. now the operation (which is adding) by CPU. 
		- the answer will be placed in register , from there it goes to RAM
		- Now the result will be placed in monitor buffer
		- in CPU there is Arethmetic logical unit
		- 
- Another example
	- wants to edit text file
		- note pad program and file copy will be loaded into RAM 
		- after the changes we need to save this. 
		- from this we can say HDD can read as well as write . so it is Input and output
- Turn around time = waiting time + burst time(executing time) + I/O time