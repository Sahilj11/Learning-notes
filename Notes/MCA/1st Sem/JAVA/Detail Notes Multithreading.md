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

![](../../../statics/Pasted%20image%2020231107075610.png)

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

![](../../../statics/Pasted%20image%2020231108081327.png)

## Creating thread

### Two ways to create thread in java

![](../../../statics/Pasted%20image%2020231108085405.png)

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

## Multithreading

![](../../../statics/Pasted%20image%2020231109082813.png)

```java
/**
 * multithread
 */
public class multithread {

    public static void main(String[] args) {
        Thread1 t1 = new Thread1();
        Thread2 t2 = new Thread2();
        t1.start();
        t2.start();
    }

    static class Thread1 extends Thread {
        public void run() {
            for (int i = 0; i < 5; i++) {
                System.out.println("Thread1: " + i);
            }
        }

    }

    static class Thread2 extends Thread {
        public void run() {
            for (int i = 0; i < 5; i++) {
                System.out.println("Thread2: " + i);
            }
        }
    }
}
```

## Synchronisation

### What is it

- Process by which we control the accessibility of multiple threads to a particular resource
  ![](../../../statics/Pasted%20image%2020231109091140.png)
  to overcome synchronisation disadvantage java introduced java.util.concurrent package

```java
/**
 * sync
 */
public class sync extends Thread {
    static seatBooking b;
    int seats;

    public void run() {
        b.bookSeat(seats);
    }

    public static void main(String[] args) {
        b = new seatBooking();
        sync sahil = new sync();
        sahil.seats = 7;
        sync rahul = new sync();
        rahul.seats = 6;
        sahil.start();
        rahul.start();
    }

}

class seatBooking {
    int MAX_SEAT = 10;
    // using synchronized keyword
    synchronized void bookSeat(int seats) {
        if (seats <= MAX_SEAT) {
            System.out.println("seat booked");
            MAX_SEAT = MAX_SEAT - seats;
        } else {
            System.out.println("Not enough seats");
        }
    }
}
```

program of synchronized

![](../../../statics/Pasted%20image%2020231109105217.png)

In Java, synchronization is a technique used to control access to critical sections of code, particularly when multiple threads are involved. Synchronization ensures that only one thread can execute a synchronized block of code or method at a time, preventing interference and maintaining data integrity. There are several ways to achieve synchronization in Java:

1. **Synchronized Method:**
   In Java, you can declare a method as synchronized by using the `synchronized` keyword. When a method is declared as synchronized, only one thread can execute that method for a particular instance of the class at a time.

   ```java
   public synchronized void synchronizedMethod() {
       // Critical section of code
       // Access is synchronized for this method
   }
   ```

2. **Synchronized Block:**
   In cases where synchronizing an entire method is not necessary, you can use synchronized blocks. This allows more fine-grained control over the critical section of code by explicitly defining which part needs synchronization.

   ```java
   public void someMethod() {
       // Non-critical section of code

       synchronized (this) {
           // Critical section of code
           // Access is synchronized for the block inside the synchronized statement
       }

       // Non-critical section of code
   }
   ```

3. **Static Synchronization:**
   When dealing with static methods or data members, you might need to synchronize access across all instances of a class. To achieve this, you can use the `static` keyword with the `synchronized` keyword to synchronize static methods or a block.

   ```java
   public class MyClass {
       public static synchronized void staticSynchronizedMethod() {
           // Critical section of code for static method
           // Access is synchronized for all instances of the class
       }

       public void someMethod() {
           // Non-critical section of code

           synchronized (MyClass.class) {
               // Critical section of code for static block
               // Access is synchronized for all instances of the class
           }

           // Non-critical section of code
       }
   }
   ```

Using synchronization mechanisms is crucial for concurrent programming to prevent race conditions and maintain data consistency when multiple threads are working with shared resources. However, excessive synchronization might lead to performance issues, so it's essential to use it judiciously where necessary.

### Cooperation(InterThread communication)

![](../../../statics/Pasted%20image%2020231109110501.png)

### issue of interthread

```java
/**
 * interThread
 */
public class interThread {

    public static void main(String[] args) {
        Totalearnings te = new Totalearnings();
        te.start();
        System.out.println(te.total);
    }
}

class Totaleakrnings extends Thread {
    int total = 0;

    public void run() {
        for (int i = 0; i < 10; i++) {
            total += 100;
        }
    }
}
// here program is printing 0 instead of 1000. because main thread is not waiting for te thread to complete its work
```

Solved sol

```java
/**
 * interThread
 */
public class interThread {

    public static void main(String[] args) throws InterruptedException{
        Totalearnings te = new Totalearnings();
        te.start();
        synchronized (te) {
            te.wait();
            System.out.println(te.total);
        }
    }
}

class Totalearnings extends Thread {
    int total = 0;

    public void run() {
        synchronized (this) {
            for (int i = 0; i < 10; i++) {
                total += 100;
            }
            this.notify();
        }
    }
}
```
