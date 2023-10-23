## Multi threading
Multithreading in Java is a technique that allows a Java program to execute multiple threads simultaneously. A thread is a lightweight sub-process that shares the same memory space and resources as the main program but can execute independently. Multithreading is commonly used to improve the performance and responsiveness of Java applications, especially in scenarios where tasks can be executed concurrently.

Here's a detailed explanation of multithreading in Java:

1. **Thread Class and Runnable Interface**:
   In Java, multithreading can be achieved in two ways:

   - **Extending the `Thread` class:** You can create a new class that extends the `Thread` class and override the `run()` method to define the code to be executed in the new thread.

   ```java
   class MyThread extends Thread {
       public void run() {
           // Code to be executed in the new thread
       }
   }
   ```

   - **Implementing the `Runnable` interface:** You can create a class that implements the `Runnable` interface and override the `run()` method. This class can then be used to create a `Thread` object.

   ```java
   class MyRunnable implements Runnable {
       public void run() {
           // Code to be executed in the new thread
       }
   }
   ```

2. **Creating and Starting Threads**:
   Once you've defined a thread using either of the above approaches, you can create thread instances and start them. To create and start a thread, you can use the following:

   - Extending `Thread` class:

   ```java
   MyThread thread = new MyThread();
   thread.start();
   ```

   - Implementing `Runnable` interface:

   ```java
   MyRunnable myRunnable = new MyRunnable();
   Thread thread = new Thread(myRunnable);
   thread.start();
   ```

3. **Thread Synchronization**:
   When multiple threads access shared resources, you need to ensure proper synchronization to prevent data corruption and race conditions. Java provides mechanisms like `synchronized` blocks and methods, as well as the `Lock` interface to handle synchronization.

4. **Thread Lifecycle**:
   Threads in Java go through several states during their lifecycle, including:
   - New: The thread is created but not yet started.
   - Runnable: The thread is executing or is eligible to run.
   - Blocked/Waiting: The thread is temporarily inactive, waiting for a resource or another event.
   - Timed Waiting: The thread is in a waiting state for a specified time.
   - Terminated: The thread has completed its execution and is no longer active.

5. **Thread Priorities**:
   Threads in Java can have priorities, ranging from 1 (lowest) to 10 (highest). You can set thread priorities using the `setPriority()` method. However, thread priorities are only hints to the JVM, and they don't guarantee precise execution order.

6. **Thread Groups**:
   Thread groups are used to manage and categorize threads. They provide a way to handle multiple threads collectively, making it easier to manage and control them.

7. **Daemon Threads**:
   Daemon threads are threads that run in the background, providing services to other threads. They automatically terminate when no non-daemon threads are running.

8. **Thread Pools**:
   Creating and managing threads individually can be inefficient. Java provides the `Executor` framework, which includes thread pools for managing a group of worker threads, which are reused to execute tasks.

9. **Concurrency Utilities**:
   Java offers a range of high-level concurrency utilities in the `java.util.concurrent` package, including `ExecutorService`, `ThreadPoolExecutor`, `CountDownLatch`, `CyclicBarrier`, and others, which make managing and synchronizing threads easier.

10. **Java's `synchronized` Keyword**:
    The `synchronized` keyword can be used to synchronize methods or blocks of code, ensuring that only one thread can execute a synchronized block at a time. This is crucial for avoiding data race conditions.

In summary, multithreading in Java allows you to create and manage multiple threads within a single program, enabling concurrent execution of tasks. However, it's essential to be mindful of synchronization, thread lifecycle, and other considerations to write safe and efficient multithreaded code.

### Life cycle of thread 
In Java, threads go through several states during their lifecycle. Understanding the thread lifecycle is important when working with multithreaded applications. The thread states in Java are typically represented by the `Thread.State` enumeration, and they include the following states:

1. **New**: 
   - A thread is in the "New" state when it has been created but has not yet been started using the `start()` method.
   - The thread has been created but hasn't started its execution.

2. **Runnable**: 
   - A thread is in the "Runnable" state when it's eligible to run but may not be currently executing.
   - It can be in the runnable state while waiting for its turn to execute on the CPU.

3. **Blocked**:
   - A thread is in the "Blocked" state when it's waiting for a monitor lock to enter a synchronized block or method.
   - Threads enter this state when they are trying to access a resource that is currently locked by another thread. They remain in this state until the resource becomes available.

4. **Waiting**:
   - A thread enters the "Waiting" state when it's waiting indefinitely for another thread to perform a particular action.
   - Threads can be in this state when they call methods like `wait()`, `join()`, or `park()`.

5. **Timed Waiting**:
   - A thread is in the "Timed Waiting" state when it's waiting for a specified period.
   - Threads enter this state when they call methods like `sleep()`, `wait(timeout)`, or other time-limited operations.

6. **Terminated**: 
   - A thread enters the "Terminated" state when it has completed its execution or has been explicitly terminated.
   - Once a thread reaches this state, it cannot be restarted.

Here's a diagram that illustrates the thread lifecycle:

```
New --(start())--> Runnable --(Blocked/Waiting/Timed Waiting)--> Terminated
                          ^                       |
                          |                       |
                          |                       v
                          +---> Blocked --(resource available)--> Runnable
```

- Threads usually start in the "New" state, then transition to the "Runnable" state when `start()` is called, making them eligible for execution.
- From the "Runnable" state, threads can transition to the "Blocked," "Waiting," or "Timed Waiting" states as necessary based on their actions or the availability of resources.
- Once a thread has finished executing its task, it enters the "Terminated" state.

It's important to manage thread states properly in multithreaded applications to ensure that threads are synchronized and resources are accessed safely. The use of synchronization mechanisms like `synchronized` blocks and the `wait()` and `notify()` methods is essential for managing thread state transitions effectively.


## Package
**java package** is a group of similar types of classes, interfaces and sub-packages.

![[Pasted image 20231023084035.png]]
#### Creating package
The **package keyword** is used to create a package in java.
```java
- //save as Simple.java  
- package mypack;  
- public class Simple{  
-  public static void main(String args[]){  
-     System.out.println("Welcome to package");  
-    }  
- }
```
#### Compile package
```java
javac -d directory javafilename
javac -d . Simple.java
```
The -d switch specifies the destination where to put the generated class file. You can use any directory name like /home (in case of Linux), d:/abc (in case of windows) etc. If you want to keep the package within the same directory, you can use . (dot).

You need to use fully qualified name e.g. mypack.Simple etc to run the class.
**To Compile:** javac -d . Simple.java
**To Run:** java mypack.Simple
#### How to access package from another package?
There are three ways to access the package from outside the package.

1. import package.`*`;
![[Pasted image 20231023084442.png]]
3. import package.classname;
![[Pasted image 20231023084520.png]]

5. fully qualified name.
![[Pasted image 20231023084537.png]]

#### Subpackage
Package inside the package is called the **subpackage**. It should be created **to categorize the package further**.

Package in java can be categorized in two form, built-in package and user-defined package.
In Java, a package is a mechanism for organizing related classes and interfaces into a single, coherent namespace. Packages provide a way to structure your code, avoid naming conflicts, and make your code more maintainable and modular. They are essential for organizing and managing larger Java applications. Here's a detailed explanation of packages in Java:

1. **What is a Package?**  
   A package is a directory that contains a group of related Java classes and interfaces. It provides a hierarchical way to organize your Java code. Packages are used to avoid naming conflicts and to create a modular, well-organized codebase.

2. **Why Use Packages?**  
   - **Organization:** Packages help you organize your classes logically. You can group related classes and interfaces together within a package.
   - **Access Control:** Packages can control the access to classes and their members (fields and methods). You can specify the access level using the `public`, `private`, `protected`, and default (no modifier) access modifiers.
   - **Naming Conflicts:** Packages help avoid naming conflicts. If two classes with the same name exist in different packages, there won't be a conflict as long as you use the fully qualified name (package name + class name) to refer to them.

3. **Package Naming Convention:**  
   - Package names are typically written in lowercase letters to distinguish them from class names, which usually start with an uppercase letter.
   - Package names usually follow the reverse domain name convention to ensure uniqueness. For example, if your domain is `example.com`, you might create a package named `com.example.myapp`.

4. **Creating Packages:**  
   To create a package, you need to do the following:
   - Include a `package` declaration at the top of your Java source file. For example:
     ```java
     package com.example.myapp;
     ```
   - Save the Java source file in a directory structure that matches the package name. For the example above, you'd save the file in a directory like `com/example/myapp`.

5. **Accessing Classes in Packages:**  
   To access a class or interface from a package, you can use the `import` statement in your Java source code. For example:
   ```java
   import com.example.myapp.MyClass;
   ```
   You can then use `MyClass` in your code without specifying the full package name each time.

6. **Classpath:**  
   When compiling or running Java code, the Java classpath needs to include the root directory where your package directory structure resides. This enables the Java compiler and runtime to find your classes. You can set the classpath using the `-cp` or `-classpath` option.

7. **Standard Java Packages:**  
   Java provides a set of standard packages, such as `java.util`, `java.io`, and `java.lang`, which contain classes and interfaces that are fundamental to the Java language.

8. **Nested Packages:**  
   You can also create nested packages within packages. For example, if you have a package `com.example.myapp`, you can create a subpackage `com.example.myapp.util` to further organize your code.

9. **Package Visibility:**
   - Classes with default (package-private) access can be accessed only within the same package.
   - Classes with `public` access can be accessed from anywhere.

10. **Jar Files:**  
    You can package classes from multiple packages into a JAR (Java Archive) file. This makes it easy to distribute and share libraries or applications.

In summary, packages in Java provide a way to structure, organize, and manage your code, prevent naming conflicts, and control access to classes and their members. They are an essential part of writing modular and maintainable Java applications.

### Creating package and accessing it 
Creating a package and accessing it in Java involves a series of steps. I'll explain the process in detail:

**Creating a Package:**

1. **Package Structure:** To create a package, you need to decide on a package name and organize your source code accordingly. The package name should follow the naming conventions, typically in reverse domain name style, such as `com.example.myapp`.

2. **Directory Structure:** The directory structure should match the package name. For example, if your package is named `com.example.myapp`, you would create a directory structure like this:

   ```
   project_root
   └── com
       └── example
           └── myapp
   ```

   Inside the `myapp` directory, you'll place your Java source files.

3. **Package Declaration:** In your Java source files, you need to include a `package` declaration at the top of each file. The `package` declaration specifies the package name for the classes in that file. For example:

   ```java
   package com.example.myapp;
   ```

   Place this declaration at the very top of each `.java` file.

4. **Compile Source Files:** Compile your Java source files using the `javac` command. Make sure that your class files are generated in the correct directory structure, matching the package name. For example:

   ```
   javac -d project_root src/com/example/myapp/MyClass.java
   ```

   This will compile `MyClass.java` and place the resulting `.class` file in the appropriate directory structure.

**Accessing a Package:**

Once you have created a package, you can access it in other classes or packages using the `import` statement. Here's how you can access classes and interfaces from a package:

1. **Import Statement:** To access a class or interface from a package, you can use the `import` statement. This statement informs the Java compiler that you want to use a class from a specific package. You can place `import` statements at the top of your Java source file, below the package declaration (if there is one) and above the class declaration.

   ```java
   import com.example.myapp.MyClass;
   ```

   In this example, we're importing the `MyClass` class from the `com.example.myapp` package.

2. **Using Classes:** After importing the class, you can use it in your code without specifying the full package name each time. For example, you can create an instance of `MyClass`:

   ```java
   MyClass myObject = new MyClass();
   ```

   Since you've imported `MyClass`, you don't need to use the full package name when creating objects or invoking methods on this class.

3. **Accessing Nested Packages:** If you have nested packages within your package, you can import classes from these nested packages in a similar way. For instance, if you have a nested package `com.example.myapp.util`, you can import a class from this nested package as follows:

   ```java
   import com.example.myapp.util.UtilityClass;
   ```

   Then you can use `UtilityClass` in your code as needed.

4. **Access Modifier:** The access modifier of a class (e.g., `public`, `private`, `protected`, default) in a package affects how it can be accessed from other classes and packages. For example, if a class is declared as `public`, it can be accessed from any package. If it has default (package-private) access, it can only be accessed within the same package.

In summary, creating and accessing packages in Java involves organizing your source code in a directory structure that matches the package name, including a `package` declaration in your source files, and using `import` statements to access classes from other packages. This helps you structure your code, avoid naming conflicts, and make your Java application more modular and organized.
### Advantage of Java Package

1) Java package is used to categorize the classes and interfaces so that they can be easily maintained.

2) Java package provides access protection.

3) Java package removes naming collision.

