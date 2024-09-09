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
- common approach is to partition the tasks into small components , or modules , rather than have one monolithic system 

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

