## what is it 
- System calls provide an interface to the service made available by an OS
- Usermode and kernel mode 
	- When a program is run on kernel mode it has direct access to memory , other hardware and if program crash it can affect the whole system
	- whereas user mode is much safer :- when program been run on user mode needs some memory it ask the OS for that , when OS allows , program for some time switch from user mode to kernel mode . this is called context switching
	- the calls in above example made by program is called system call
- System call is a programmatic way in which a computer program request a service from kernel of OS 
- These calls are generally available as routines written in C , C++
- ![[Pasted image 20230609122411.png]]
- ![[Pasted image 20230609122530.png]]
- all above example of system calls

## Types of system calls
- Process control:- 
	- ![[Pasted image 20230609122805.png]]
- ![[Pasted image 20230609122919.png]]
- **![[Pasted image 20230609122928.png]]
- ![[Pasted image 20230609122939.png]]
- ![[Pasted image 20230609122946.png]]
- 