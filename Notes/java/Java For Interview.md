## JDK
Here are structured notes on **Java Architecture**:

## String

- **String** is an immutable class in Java (`java.lang.String`).    
- Once created, its value **cannot be changed**.

### String Pool
- Java maintains a special **memory area** called the **String Pool** inside the heap.
- When you create a string using **literals**, it is stored in the pool.
```java
String s1 = "hello"; // goes into the string pool
String s2 = "hello"; // refers to the same object in the pool
System.out.println(s1 == s2); // true
```
### 🔁 Using `new String()`
- Creates a **new object in heap** even if the same value exists in the pool.
```java
String s3 = new String("hello"); // new object in heap
System.out.println(s1 == s3); // false (different references)
```

### 🆚 `=` vs `new`:

| Way of Creating String          | Stored In   | Creates New Object | Uses Pool                                   |
| ------------------------------- | ----------- | ------------------ | ------------------------------------------- |
| `String s = "abc";`             | String Pool | No                 | Yes                                         |
| `String s = new String("abc");` | Heap        | Yes                | No (but refers to pooled string internally) |

### **Java Architecture**

Java architecture is designed to provide **platform independence**, **scalability**, and **security**. It consists of several key components:

### **1. Java Architecture Overview**

Java follows a **"Write Once, Run Anywhere" (WORA)** principle using the Java Virtual Machine (JVM). The architecture includes:

- **Java Source Code** → **Compiler (javac)** → **Bytecode** → **JVM** → **Machine Code**

### **2. Components of Java Architecture**

#### **a) Java Development Kit (JDK)**

- Contains tools to develop and run Java programs.
- Includes **compiler (javac)**, **JVM**, and **JRE**.
- Provides debugging tools, documentation, and libraries.

#### **b) Java Runtime Environment (JRE)**

- Provides libraries and JVM required to run Java applications    
- Does **not** include the compiler.
- Includes essential Java classes and runtime libraries.
#### **c) Java Virtual Machine (JVM)**

- Converts bytecode into machine code for execution.
    
- Ensures platform independence.
    
- Performs:
    
    - **Class Loading** (via ClassLoader)
        
    - **Bytecode Verification** (ensures security)
        
    - **Execution** (via Just-In-Time Compiler)
        

---

## **3. JVM Architecture**

### **a) ClassLoader**

- Loads Java classes into memory.
    
- Types:
    
    - **Bootstrap ClassLoader** (loads core Java classes)
        
    - **Extension ClassLoader** (loads `ext` directory classes)
        
    - **Application ClassLoader** (loads user-defined classes)
        

### **b) Runtime Data Areas**

1. **Method Area** → Stores class structure (fields, methods, constant pool).
    
2. **Heap** → Stores objects and instance variables.
    
3. **Stack** → Stores method execution, local variables, and partial results.
    
4. **PC Register** → Holds address of the next instruction.
    
5. **Native Method Stack** → Executes native (non-Java) code.
    

### **c) Execution Engine**

- **Interpreter** → Executes bytecode line-by-line.
    
- **JIT Compiler (Just-In-Time Compiler)** → Converts frequently used bytecode into machine code for faster execution.
    

### **d) Garbage Collector**

- Reclaims memory by removing unused objects.
    
- **Types of GC Algorithms**:
    
    - Serial GC
        
    - Parallel GC
        
    - CMS (Concurrent Mark-Sweep)
        
    - G1 (Garbage First)
        

---

## **4. Java Memory Management**

Java divides memory into:

1. **Young Generation** (Eden, Survivor Space)
    
2. **Old Generation** (Tenured Space)
    
3. **Permanent Generation / Metaspace** (Stores class metadata)
    

Garbage collection occurs in these areas based on object lifespan.

---

## **5. Java Execution Flow**

1. **Write Code** (`.java` file)
    
2. **Compile Code** (`javac` → Generates `.class` file with bytecode)
    
3. **Run Code** (`java` command → Loads bytecode into JVM)
    
4. **JVM Executes Bytecode** (via ClassLoader, Execution Engine, and Garbage Collector)
    

---

## **6. Java Application Architecture**

### **a) Standalone Applications**

- Desktop applications (Swing, JavaFX).
    
- Runs independently without a web browser.
    

### **b) Web Applications**

- Uses **Servlets, JSP, Spring Boot**.
    
- Deployed on servers like **Tomcat, Jetty**.
    

### **c) Enterprise Applications**

- Large-scale applications using **EJB, Spring, Microservices**.
    
- Handles transactions, security, and distributed computing.
    

### **d) Mobile Applications**

- Android apps use **Java (or Kotlin) with Android SDK**.
    

---

## **7. Java Frameworks & Tools**

- **Spring Boot** → Microservices, web apps.
    
- **Hibernate** → ORM for database handling.
    
- **JPA** → Java Persistence API for data storage.
    
- **JUnit, TestNG** → Testing frameworks.
    

---

This covers the core Java architecture, memory management, JVM internals, and application structures. Let me know if you need more details on any specific section. 🚀

## Strings
- Strings in Java are **immutable** objects, meaning once created, they cannot be changed.
    
- Strings are stored in the **string pool**, which optimizes memory by reusing instances.
    
- Strings can be created using **string literals** (`String s = "Hello";`) or the **`new` keyword** (`String s = new String("Hello");`).
    
- When using string literals, Java checks if the value already exists in the pool and reuses it.
    
- Using `new String("Hello")` creates a new object in the heap, even if `"Hello"` already exists in the pool.
    
- String methods include:
    
    - `.length()` → Returns the length of the string.
        
    - `.charAt(index)` → Retrieves a character at the given index.
        
    - `.substring(start, end)` → Extracts part of the string.
        
    - `.concat(str)` → Joins two strings.
        
    - `.equals(str)` → Checks for content equality.
        
    - `.equalsIgnoreCase(str)` → Ignores case while comparing.
        
    - `.compareTo(str)` → Compares lexicographically.
        
    - `.toUpperCase()` / `.toLowerCase()` → Changes case.
        
    - `.trim()` → Removes leading/trailing spaces.
        
    - `.split(delimiter)` → Splits a string into an array.
        
- Strings are often manipulated using `StringBuilder` or `StringBuffer` to improve performance when modifying strings frequently.
    
- `StringBuilder` is **faster** but **not thread-safe**, while `StringBuffer` is **thread-safe** but slightly slower.

## Classes
- A class is a blueprint for creating objects. It encapsulates data (fields/attributes) and methods (functions) that represent the properties and behaviors of the objects.

## Prints
- **`System.out.print()`**
    - Prints text on the same line.
    - Example: `System.out.print("Hello "); System.out.print("World");`
    - Output: `Hello World`
- **`System.out.println()`**
    - Prints text and moves to the next line.
    - Example: `System.out.println("Hello"); System.out.println("World");`
    - Output:
- **`System.out.printf()`**
    - Formats output similar to C’s `printf()`.
    - Example: `System.out.printf("Value: %.2f", 10.1234);`
    - Output: `Value: 10.12`
- **`System.out.format()`**
    
    - Works like `printf()`, used for formatting.
        
    - Example: `System.out.format("Hello, %s!", "John");`
        
    - Output: `Hello, John!`
        
- **`System.err.print()` & `System.err.println()`**
    
    - Prints error messages in red (console-dependent).
        
    - Example: `System.err.println("Error!");`
        
- **Using `toString()` in Objects**
    
    - If an object overrides `toString()`, `System.out.print(obj)` will print its string representation.
        
- **`print()` in GUI (Swing/AWT)**
    
    - `Graphics.drawString("Text", x, y);` prints text in a GUI component.
        
- **File Printing (`PrintWriter`)**
    
    - `PrintWriter writer = new PrintWriter("output.txt"); writer.print("Hello"); writer.close();`
        
    - Writes to a file instead of the console.

## Array
A **jagged array** in Java is an array of arrays where each **sub-array** can have a different length. Unlike a **2D array**, where all rows have the same length, a jagged array allows for **variable-sized** rows.

## Super 
- It is used to access parent class fields , constructor and methods in child class
```java
public class Test{
	int name;
	String type;
	public Test(int name,String type){
		this.name = name;
		this.type=type;
	}
}

class SubTest extends Test{

	String subType;	
	public Test(int name,String type,String subType){
		super(name,type);
		this.name = name;
		this.subType=subType;
	}	
	
}
```
- important , super() should be the first line in constructor 
- java by default calls default constructor of parent class
- access method using `super.parent()`
- cannot access private methods

## Inner class
- creating class inside a class , can also be inside a method
- types :- simple , static , inside method ( can be access only inside that method)
```java
class Test{
	String name;
	class InnerTest{
		int na;
	}
	
	static class StatTest{
		int na;
	}
}

Test t = new Test();
// non static class
Test.InnerTest st = t.new InnerTest();

// static class
Test.StatTest stc = new Test.StatTest();
```

## This keyword
- it refer to the current object 
- can be used in non static method
![](../statics/Pasted%20image%2020250405064926.png)
- calling current class constructor
- this call should be first line in constructor 
## Upcasting and Downcasting

### 🔼 Upcasting:
- Converting a **subclass** reference to a **superclass** reference.
- Happens **automatically** (implicit casting).
- Used for generalization and polymorphism.

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

Animal a = new Dog(); // Upcasting
a.sound();            // Works
// a.bark();         // Not accessible
```

### 🔽 Downcasting:
- Converting a **superclass** reference back to a **subclass** reference.
- Must be done **manually** (explicit casting).
- Can cause `ClassCastException` if the object is not actually of the subclass type.

```java
Dog d = (Dog) a;  // Downcasting
d.bark();         // Now accessible
```

✅ **Tip:** Always use `instanceof` before downcasting to avoid exceptions.

```java
if (a instanceof Dog) {
    Dog d = (Dog) a;
    d.bark();
}
```

## Inheritance

## Stream
### Lambda expression 
- Anonymous function, no name ,no return type , no access modifier
- It can be used in functional interface(only one abstract method)
### Predicate 
- It takes a arugment and return boolean . it has test function
### Function
- It takes a arugment and return it after applying it . it has apply method
- `Function<T,R> ft`
- here T is input and R is return.
### Consumer
- It takes argument and return nothing , It has accept method
- `Consumer<T> cn`
### Supplier
- it returns , and takes nothing . it has get method
### Bi
- BiPredicate, BiConsumer,BiFunction . all takes two input instead of one
### UnaryOperator
- It is a short form of writing a function where input and output is of same type `UnaryOperator<Integer>`

### BinaryOperator
- It is extends BiFunction . meaning when all three type are same it can be used.
- `BiFunction<Integer,Integer,Integer>` can be `BinaryOperator<Integer>`.
- 
### Method Reference 
- Use method without invoking and in place of lambda expression
- ![](../statics/Pasted%20image%2020250408194316.png)
### Constructor Reference
![](../statics/Pasted%20image%2020250408194417.png)
### Intro of Stream
- introduced in java 8 process collections of data in a functional and declarative manner 
- What is Stream:- sequence of elements supporting functional and declarative programming
![](../statics/Pasted%20image%2020250408195714.png)

- It has source , intermediate operation and terminal operations.
- ![](../statics/Pasted%20image%2020250408200128.png)

### Intermediate Operations

### 🔁 **Filtering and Slicing**

- **`filter(Predicate<T>)`**  
    Filters elements based on a condition.
    
    ```java
    stream.filter(x -> x > 10)
    ```
    
- **`distinct()`**  
    Removes duplicate elements (uses `.equals()`).
    
- **`limit(long maxSize)`**  
    Truncates the stream to a maximum number of elements.
    
- **`skip(long n)`**  
    Skips the first `n` elements.

### 🛠 **Mapping and Transforming**

- **`map(Function<T, R>)`**  
    Transforms each element to another form.
    
    ```java
    stream.map(String::toUpperCase)
    ```
    
- **`flatMap(Function<T, Stream<R>>)`**  
    Transforms each element into a stream and flattens them.
    
    ```java
    stream.flatMap(str -> Arrays.stream(str.split(" ")))
    ```

### 🔢 **Sorting**

- **`sorted()`**  
    Sorts elements in natural order.    
- **`sorted(Comparator<T>)`**  
    Sorts elements using a custom comparator.

### 🎯 **Peeking**

- **`peek(Consumer<T>)`**  
    Performs an action on each element (useful for debugging).
    
    ```java
    stream.peek(System.out::println)
    ```

### ⛓ **Chaining example**

```java
List<String> result = list.stream()
    .filter(s -> s.length() > 3)
    .map(String::toUpperCase)
    .sorted()
    .distinct()
    .collect(Collectors.toList());
```

### Terminal Operation
### 🔄 **Reduction Operations**

- **`collect()`**  
    Converts the stream into a collection or other format.in latest java we can directly use toList , toSet etc
    
    ```java
    list.stream().collect(Collectors.toList());
    ```
- **`reduce()`**  
    Combines elements into a single result , it takes binaryoperator
    
    ```java
    list.stream().reduce(0, Integer::sum);
    ```
### ✅ **Matching and Finding**

- **`anyMatch(Predicate)`**  
    Returns `true` if **any** element matches.
    
    ```java
    stream.anyMatch(x -> x > 10);
    ```
    
- **`allMatch(Predicate)`**  
    Returns `true` if **all** elements match.
- **`noneMatch(Predicate)`**  
    Returns `true` if **no** elements match.
- **`findFirst()`**  
    Returns the **first** element (as `Optional`).    
- **`findAny()`**  
    Returns **any** element (useful with parallel streams).

### 🔢 **Aggregation**

- **`count()`**  
    Returns the number of elements.
    
    ```java
    stream.count();
    ```
    
- **`min(Comparator)` / `max(Comparator)`**  
    Finds the min or max element.

### 🔁 **For-Each and Side Effects**

- **`forEach(Consumer)`**  
    Performs an action for each element.
    
    ```java
    stream.forEach(System.out::println);
    ```
    
- **`forEachOrdered(Consumer)`**  
    Same as `forEach` but maintains order (in parallel streams).

### ⚠️ Once a terminal operation is called, the stream is **consumed** and **can’t be reused**.

- Using string.chars() it returns a stream

### 🔀 What is a **Parallel Stream** in Java?

A **Parallel Stream** splits the data into **multiple threads** and processes them **concurrently**, using **multiple CPU cores** — leveraging **ForkJoinPool** under the hood.

---

### ✅ How to create a parallel stream

```java
list.parallelStream()
```

vs

```java
list.stream() // sequential
```

---

### ⚡ Example:

```java
list.parallelStream()
    .map(x -> heavyComputation(x))
    .collect(Collectors.toList());
    
```

This can be **faster** if `heavyComputation()` is CPU-intensive.

---

### 🧠 When to use `parallelStream()`

✅ **Use when:**

- Each element's processing is **independent**
    
- The operation is **CPU-bound** (not I/O-bound)
    
- Your dataset is **large** (thousands of items or more)
    
- You're not modifying shared mutable state
    
- You want to **speed up** processing with multi-core CPUs
    

❌ **Avoid when:**

- You’re working with **small collections**
    
- Your code modifies **shared variables** (risk of concurrency bugs)
    
- Order matters (unless you use `forEachOrdered()`)
    
- You're doing **I/O operations** (they block threads)
    
- Running in a **resource-limited environment** (e.g., server under load)
    

---

### ⚠️ Gotcha:

Parallelism adds **overhead**. For small lists, it can be **slower** than sequential streams.

---

Want a benchmark or example comparing performance?

#### Stream Questions
1. How do you find the sum of a list of integers using streams? 
2. How do you find the maximum and minimum values in a stream? 
3. How do you find the average of numbers in a list using streams? 
4. How do you concatenate multiple lists into a single stream? 
5. How do you group a list of numbers into even and odd using streams? 
6. How do you group a list of employees by department using streams?
7. How do you find the second highest number in a list using streams? 
8. How do you partition a list of numbers into two groups: greater than 10 and less than 10? 
9. How do you count occurrences of each word in a list using streams? 
10. How do you remove null values from a list using streams? 
11. How do you concatenate all strings in a list into a single string using streams? 
12. How do you flatten a list of lists into a single list using streams? 
13. How do you find duplicate elements in a list using streams? 
14. How do you get the top 3 highest numbers from a list using streams? 
15. How do you convert a list of strings into a map of string-length pairs? 
16. How do you find the longest word in a list using streams? 
17. How do you get distinct characters from a list of strings? 
18. How do you merge two maps using streams? 
19. How do you extract a sublist based on a condition using streams? 
20. How do you shuffle elements in a list using streams?

## Polymorphism
![](../statics/Pasted%20image%2020250417130541.png)
### Compile time 
- Method overloading as example
### Runtime 
- ![](../statics/Pasted%20image%2020250417131905.png)
- method overriding example of runtime polymorphism
- Dynamic method dispatch

## Static
- ![](../statics/Pasted%20image%2020250417132219.png)
- 