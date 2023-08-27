- ![[Pasted image 20230609065229.png]]
- ![[Pasted image 20230609065501.png]]
- here the job(task) is loaded in RAM , if the OS was not multiprogramming:- CPU starts job 1 after some time it(job1) needs to use I/O . now the CPU is idle , this is inefficient so in multiprogramming instead of staying idle CPU starts executing job2
- ![[Pasted image 20230609065824.png]]
- ![[Pasted image 20230609070146.png]]
- ![[Pasted image 20230609070155.png]]
- lets say user 1 opens a program now CPU is doing task for it , user1 starts giving input , during that time CPU shift to user2  (this happens so fast that the user1 dont even realise that CPU has shifted its focus on user2 program, and when user1 needs the CPU it will be back ) ^768556
- ![[Pasted image 20230609070408.png]]

## kernel
- The kernel is a critical component of an operating system (OS). It is a software layer that acts as a bridge between applications and the computer's hardware, providing essential services and managing system resources. The kernel is loaded into memory when the system boots up and remains resident throughout the computer's operation.

## Simple structure
- ![[Pasted image 20230609124108.png]]
- issue with this is that all layers have access to lowest layer , making it vulernable

## Monolithic structure

## layered structure
- ![[Pasted image 20230609124658.png]]
- every service given seperate layers

## Micro kernels
- ![[Pasted image 20230609124815.png]]
- reducing the services from kernel and adding it to user mode

## Modules
- ![[Pasted image 20230609125038.png]]
- involve object oriented programming technique to create modular kernel
- other functionality will be loaded to kernel either at boot time or at run time
- resemble to layer structure in a way that each kernel section has defined protected interface .   protected from the things we dont want them to access
- here each of modules can communicate with any other module directly through core kernel