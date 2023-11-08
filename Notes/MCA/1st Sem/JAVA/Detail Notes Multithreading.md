# Intro
## Difference b/w Multitasking , Multiprocessing and Multithreading
- Multitasking:- Performing multiple task at a single time
	- types
		- Multi Processing
		- Multi Threading
- Multi processing:- When one system is connected to multiple processors in order to complete a task
- Multi Threading:- Executing multiple threads (Sub-process, small task) at a single time
	- For eg. when we launch VLC . VLC itself is a process , small task inside vlc like progress bar , timer , audio etc are small task . when these small task are executing simultaneously it is an example of multi threading

## Difference b/w process and Thread
![[Pasted image 20231107075610.png]]

Context Switching:- Context switching is a crucial operation performed by an operating system to switch the CPU (Central Processing Unit) from executing one process or thread to another. It's a fundamental aspect of multitasking and allows the CPU to handle multiple processes concurrently.

In computing, especially in the context of operating systems and concurrent programming, the concepts of processes and threads are fundamental but have distinct characteristics:

**Process**:
- A process is an executing instance of a program managed by the operating system.
- It consists of an executable program, the associated data, and resources (like memory, open files, etc.).
- Each process has its own memory space, file handles, and other resources.
- Processes are independent of each other and cannot directly access each other's memory.
- Communication between processes typically requires inter-process communication (IPC) mechanisms.
- Creation of a process is more resource-intensive (due to its own memory space and system resources).
- Processes are heavyweight in terms of resources and management overhead.

**Thread**:
- A thread is a subset of a process. It represents an independent flow of execution within a process.
- Threads within the same process share the same memory space and resources.
- Threads can directly communicate with other threads in the same process using shared memory.
- Creation of a thread is less resource-intensive compared to creating a process.
- Threads are lightweight in terms of resources and management overhead.
- Multithreading allows multiple threads within a single process to execute concurrently.
- Threads in a process share resources and can communicate more efficiently than processes.

**Key Differences**:

1. **Resource Usage**: Processes have their own memory space and resources, whereas threads share the same memory space and resources within a process.

2. **Communication and Synchronization**: Inter-process communication is more complex, often requiring specific mechanisms, whereas threads in the same process can communicate directly through shared memory.

3. **Creation Overhead**: Creating a process is more resource-intensive compared to creating a thread.

4. **Independence**: Processes are independent entities, while threads share resources and are part of the same entity (the process).

5. **Execution**: Threads within the same process can execute concurrently, allowing for more efficient utilization of resources compared to processes.

In summary, processes and threads are both mechanisms for concurrent execution but differ in terms of resource utilization, communication, and independence. Threads allow for more lightweight concurrent execution within a process and can communicate more efficiently due to their shared resources, while processes are independent and require more overhead due to their separate memory space.

## Life cycle of thread
![[Pasted image 20231108081327.png]]


## Creating thread
### Two ways to create thread in java
![[Pasted image 20231108085405.png]]

1. Using Runnable interface :- this is present in java.lang package . this interface only contains one method which is run
2. Thread class:- this is a class given by java , it implements runnable interface , and contains constructors , methods (like run , start etc)

```java
/**
 * thread
 */
public class thread {

    public static void main(String[] args) {
       Test t = new Test(); 
       Test2 t2 = new Test2();
       Thread th = new Thread(t2);
       t.start();
       th.start();
    }
    static class Test extends Thread{
        @Override
        public void run(){
            for (int i = 0; i < 6; i++) {
               System.out.println("Thread " + i); 
            }
        }

    }
    // using runnable interface
    static class Test2 implements Runnable{
        @Override
        public void run(){
            for (int i = 0; i < 6; i++) {
               System.out.println("Thread2 " + i); 
            }
        }
    }

}
```

It is good to use runnable interface method to create thread as if we have a class A extending Class B , and now we want to make Class A thread it would not be possible as java do not support multiple inheritance