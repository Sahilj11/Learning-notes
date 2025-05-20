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

## Final
### 📘 **`final` Keyword in Java – Quick Notes**

---

### 🔍 **What is `final` in Java?**

The `final` keyword in Java is used to **restrict modification**. It can be applied to:

1. Variables
    
2. Methods
    
3. Classes
    

---

### 1. 🔒 **Final Variable**

- **Value cannot be changed** once assigned.
    
- Must be initialized **once** (either during declaration or in the constructor).
    

```java
final int MAX_VALUE = 100;
// MAX_VALUE = 200; ❌ Error
```

📌 **For objects**: You cannot reassign the object reference, but you **can change the object’s internal state**.

```java
final List<String> list = new ArrayList<>();
list.add("Hello");        // ✅ allowed
list = new ArrayList<>(); // ❌ Error
```

---

### 2. 🚫 **Final Method**

- A method marked `final` **cannot be overridden** by subclasses.
    

```java
class Parent {
    final void show() {
        System.out.println("Parent method");
    }
}

class Child extends Parent {
    // void show() { } ❌ Error: Cannot override final method
}
```

---

### 3. 🧱 **Final Class**

- A `final` class **cannot be subclassed (inherited)**.
    
- Commonly used for security and immutability (e.g., `String` class).
    

```java
final class Vehicle {
    void run() {
        System.out.println("Running...");
    }
}

// class Car extends Vehicle {} ❌ Error: Cannot subclass final class
```

---

### ⚠️ **Important Notes**

- You can declare a **blank final variable** and initialize it in the constructor.
    
- `final` is **not the same as `const`** in other languages — Java does not have a `const` keyword.
    
- Use `final` for constants (often with `static`) → `static final`.
    

```java
static final double PI = 3.14159;
```

---

### ✅ **When to Use `final`**

- To create constants (`static final`)
    
- To prevent method overriding
    
- To prevent inheritance
    
- To make your variables safe from re-assignment
    
In Java, **you cannot use `final` and `abstract` together** on a class or method. These two keywords are **mutually exclusive** because their meanings **contradict** each other.

---

### ❌ **Why `final abstract` or `abstract final` is illegal**

|Keyword|Meaning|
|---|---|
|`abstract`|Method/class **must be overridden/extended** (it's incomplete).|
|`final`|Method/class **cannot be overridden/extended** (it's complete and locked).|

So trying to combine them:

```java
abstract final class Test {}       // ❌ Error
final abstract void show();        // ❌ Error
```

Is **logically contradictory** — you’re saying:

- "`abstract`: Please override this!"
    
- "`final`: You’re not allowed to override this!"
    

---

### ✅ Valid Use Examples

```java
abstract class Animal {
    abstract void sound(); // Must be overridden
}

final class MathUtils {
    // Cannot be extended
    public static final double PI = 3.14;
}
```

---

### ✅ Summary

|Combination|Valid?|Why|
|---|---|---|
|`abstract final`|❌|Can't be overridden AND must be? ❌ Logic clash|
|`final abstract`|❌|Same as above, reversed order|
|`abstract` only|✅|For base classes/methods|
|`final` only|✅|For sealing methods or utility classes|

## Static
- ![](../statics/Pasted%20image%2020250417132219.png)

### 📘 **`static` Keyword in Java – Quick Notes**

### 🔍 **What is `static` in Java?**

The `static` keyword is used to indicate that **a field, method, block, or nested class belongs to the class itself**, rather than to instances of the class.

---

### 🧱 **Where Can We Use `static`?**

|Use Case|Meaning|
|---|---|
|`static` variable|Shared by all objects of the class (class-level variable)|
|`static` method|Belongs to class; can be called without creating an object|
|`static` block|Executes once when the class is loaded (used for static initialization)|
|`static` class|Inner class that does not need outer class reference|

---

### 1. 🧮 **Static Variable (Class Variable)**

- Only one copy exists, shared across all instances.
    
- Good for constants or counters.
    

```java
class Student {
    static String college = "ABC University"; // shared by all students
    String name;

    Student(String name) {
        this.name = name;
    }
}
```

---

### 2. 🛠️ **Static Method**

- Can be called without creating an object.
    
- **Cannot access non-static (instance) variables or methods** directly.
    
- Often used for utility/helper methods.
    

```java
class MathUtil {
    static int square(int x) {
        return x * x;
    }
}

// Usage
int result = MathUtil.square(5);
```

---

### 3. 🧱 **Static Block**

- Used to initialize static variables.
    
- Runs only once when the class is loaded.
    

```java
class Test {
    static int value;

    static {
        value = 10;
        System.out.println("Static block executed");
    }
}
```

---

### 4. 🧩 **Static Nested Class**

- A static class inside another class.
    
- Can be instantiated without an outer class object.
    

```java
class Outer {
    static class Inner {
        void show() {
            System.out.println("Static inner class");
        }
    }
}

// Usage
Outer.Inner obj = new Outer.Inner();
obj.show();
```

---

### ⚠️ **Rules and Key Points**

- `static` methods **cannot use `this` or `super`**.
    
- A static method **cannot directly access** non-static members.
    
- You can call static members using the **class name** (preferred).
    

```java
ClassName.staticMethod();
```

---

### 🔚 **Use Cases for `static`**

- Constants (`static final`)
    
- Utility methods (e.g., `Math`, `Collections`)
    
- Counter shared across all objects
    
- Singleton instance
    
- Static factory methods

## Exceptions 
### Type of error 
- Syntax error :- cannot be compiled
- Logical error
- Runtime error:- will compiled 

![](../statics/Pasted%20image%2020250519212511.png)
![](../statics/Pasted%20image%2020250519212619.png)
![](../statics/Pasted%20image%2020250519213140.png)

### Checked Vs Unchecked

### ✅ **Checked Exceptions**

- **Checked at compile-time**.
    
- Must be **handled using `try-catch`** or declared using `throws`.
    
- Used for **recoverable conditions** (e.g., file not found, network issues).
    
- **Examples**:
    
    - `IOException`
        
    - `SQLException`
        
    - `FileNotFoundException`
        

```java
try {
    FileReader fr = new FileReader("file.txt");
} catch (FileNotFoundException e) {
    e.printStackTrace();
}
```

---

### ⚠️ **Unchecked Exceptions**

- **Not checked at compile-time**.
    
- Occur due to **programming errors** (e.g., logic flaws).
    
- Inherit from `RuntimeException`.
    
- Handling is **optional**.
    
- **Examples**:
    
    - `NullPointerException`
        
    - `ArrayIndexOutOfBoundsException`
        
    - `ArithmeticException`
        

```java
int[] arr = new int[3];
System.out.println(arr[5]); // ArrayIndexOutOfBoundsException
```

---

### 🔁 Summary Table

|Feature|Checked Exception|Unchecked Exception|
|---|---|---|
|Checked by compiler|Yes|No|
|Must be handled|Yes|No|
|Inherits from|`Exception`|`RuntimeException`|
|Type|Recoverable|Programming bug|

## Throws vs Throw
### 🚀 `throw`

- Used to **actually throw** an exception.
    
- Used **inside a method** or block.
    
- Only **one exception** can be thrown at a time.
    

#### 🧾 Syntax:

```java
throw new ExceptionType("Error message");
```

#### ✅ Example:

```java
if(age < 18) {
    throw new ArithmeticException("Not eligible to vote");
}
```

---

### 📌 `throws`

- Used to **declare** exceptions a method **might throw**.
    
- Used in **method signature**.
    
- Can declare **multiple exceptions** separated by commas.
    

#### 🧾 Syntax:

```java
returnType methodName() throws Exception1, Exception2 { }
```

#### ✅ Example:

```java
public void readFile() throws IOException {
    FileReader fr = new FileReader("file.txt");
}
```

---

### 🔁 Summary Table

|Feature|`throw`|`throws`|
|---|---|---|
|Purpose|To **throw** an exception|To **declare** potential exceptions|
|Usage|Inside method/block|In method signature|
|How many?|Only one exception|Can declare multiple exceptions|
|Timing|Runtime|Compile-time declaration|


### Try with resources
In **Java**, a class can be used in a **try-with-resources** statement **only if it implements** the `AutoCloseable` interface (or its subinterface `Closeable`).

### ✅ **Requirements**:

- The class **must implement `AutoCloseable` or `Closeable`**.
    
- This ensures the resource is **automatically closed** after the `try` block.
    

---

### 🔧 Common Classes Used in Try-with-Resources:

|Class|Package|Interface Implemented|
|---|---|---|
|`FileInputStream`|`java.io`|`Closeable`|
|`FileOutputStream`|`java.io`|`Closeable`|
|`BufferedReader`|`java.io`|`Closeable`|
|`BufferedWriter`|`java.io`|`Closeable`|
|`FileReader`|`java.io`|`Closeable`|
|`FileWriter`|`java.io`|`Closeable`|
|`Scanner`|`java.util`|`Closeable`|
|`Connection`|`java.sql`|`AutoCloseable`|
|`PreparedStatement` / `Statement`|`java.sql`|`AutoCloseable`|
|`ResultSet`|`java.sql`|`AutoCloseable`|
|`ZipFile`|`java.util.zip`|`Closeable`|

---

### ✅ Example:

```java
try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {
    String line;
    while ((line = br.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

---

### 🛠️ Custom Resource:

You can also create your own class that implements `AutoCloseable`:

```java
class MyResource implements AutoCloseable {
    public void doSomething() {
        System.out.println("Using resource");
    }
    public void close() {
        System.out.println("Closing resource");
    }
}
```

---

### 🔁 Summary:

|Interface|Introduced In|Used By|
|---|---|---|
|`Closeable`|Java 1.5|Mostly `java.io`|
|`AutoCloseable`|Java 1.7|More general|

### ✅ **Steps to Create a Custom Exception**

1. **Extend** the `Exception` class (for checked exceptions)  
    **or** `RuntimeException` (for unchecked exceptions).
    
2. Define constructors (default and with message).
    

---

### 🔹 **Checked Custom Exception**

```java
class MyCheckedException extends Exception {
    public MyCheckedException(String message) {
        super(message);
    }
}
```

🔸 **Usage:**

```java
public void test() throws MyCheckedException {
    throw new MyCheckedException("This is a checked exception");
}
```

---

### 🔹 **Unchecked Custom Exception**

```java
class MyUncheckedException extends RuntimeException {
    public MyUncheckedException(String message) {
        super(message);
    }
}
```

🔸 **Usage:**

```java
public void test() {
    throw new MyUncheckedException("This is an unchecked exception");
}
```

---

### ✅ Summary

|Exception Type|Extend From|Must Declare with `throws`?|
|---|---|---|
|Checked Exception|`Exception`|✅ Yes|
|Unchecked Exception|`RuntimeException`|❌ No|

## Abstraction

### ✅ **What is Abstraction?**

Abstraction is the process of hiding **internal implementation details** and showing only **essential features** to the user.

> Think of using a mobile phone – you interact with the screen and buttons, but don't need to know how the internal electronics work.

---

### 🎯 **Why Use Abstraction?**

- To reduce complexity
    
- To increase reusability
    
- To achieve loose coupling
    
- To improve maintainability
    

---

### 🛠️ **How Can We Achieve Abstraction in Java?**

Java provides **two main ways** to achieve abstraction:

---

#### 1. **Abstract Classes**

- Declared using the `abstract` keyword.
    
- Can have both **abstract methods** (without body) and **concrete methods** (with body).
    
- Cannot be instantiated.
    

```java
abstract class Animal {
    abstract void sound();  // abstract method

    void sleep() {          // concrete method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Barks");
    }
}
```

---

#### 2. **Interfaces**

- Fully abstract by default (in Java 8 and earlier).
    
- Can have **abstract methods**, **default methods**, and **static methods**.
    
- Achieves **multiple inheritance**.
    
- All methods are `public` and `abstract` by default (except static and default).
    

```java
interface Vehicle {
    void start();           // abstract method
    default void stop() {   // default method
        System.out.println("Stopping...");
    }
}

class Car implements Vehicle {
    public void start() {
        System.out.println("Car starting");
    }
}
```

---

### 💡 **Key Differences: Abstract Class vs Interface**

|Feature|Abstract Class|Interface|
|---|---|---|
|Inheritance Type|Single inheritance|Multiple inheritance|
|Methods|Abstract + Concrete|Mostly abstract (can have default)|
|Fields|Can have variables|Only `public static final` constants|
|Constructor|Can have constructors|Cannot have constructors|
|Use Case|Common base class|Common capabilities|

---

### 🔚 **Conclusion**

- Use **abstract classes** when there is a "is-a" relationship with some default behavior.
    
- Use **interfaces** when you want to define a contract for capabilities without implementation dependency.
    

Let me know if you want visual diagrams or MCQs to practice this concept.

## 📘 **Java Access Modifiers – Quick Notes**

Access modifiers in Java determine the **visibility/scope** of classes, methods, and variables. They control **who can access what** in your code.

---

### 🔐 **Types of Access Modifiers in Java**

|Modifier|Class|Package|Subclass|World|
|---|---|---|---|---|
|`private`|✅|❌|❌|❌|
|(default)|✅|✅|❌|❌|
|`protected`|✅|✅|✅|❌|
|`public`|✅|✅|✅|✅|

---

### 1. 🔒 `private`

- **Visible only within the same class**.
    
- Not accessible outside the class (not even in subclasses).
    

```java
class Person {
    private String name;

    private void showName() {
        System.out.println(name);
    }
}
```

---

### 2. 📦 **Default** (no modifier)

- Also called **package-private**.
    
- Accessible **only within the same package**.
    
- If no access modifier is specified, this is the default.
    

```java
class Employee {
    int empId; // default access
}
```

---

### 3. 🔐 `protected`

- Accessible **within the same package** and **in subclasses** (even if in different packages).
    

```java
class Animal {
    protected void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void bark() {
        sound();  // Accessible here
    }
}
```

---

### 4. 🌐 `public`

- Accessible from **anywhere**.
    
- Used for APIs, main methods, and globally accessible classes.
    

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```

---

### 📌 **Important Points**

- **Classes** can only be `public` or **default** (cannot be `private` or `protected`).
    
- Use **`private`** to enforce encapsulation.
    
- Use **`protected`** when you want controlled access in subclasses.
    
- Use **`public`** for open API features.
    
- Use **default** when you want access only within the same package.
    

## Interface 
- Blueprint of class
- Have absctract method and static constant
- meaning writing abstract keyword on method in interface is redundant and also writing static final on variable is also redundant
- from java 8 interface can have default and static method
### 📘 **Java Interfaces – Notes + Java 8 Enhancements**

---

### 🔍 **What is an Interface in Java?**

- An **interface** is a blueprint for a class.
    
- It can have **abstract methods**, **constants**, and **default/static methods** (since Java 8).
    
- Used to **achieve abstraction** and **multiple inheritance** in Java.
    

```java
interface Animal {
    void makeSound();  // abstract method
}
```

---

### ✅ **Key Properties of Interfaces**

- All methods were **abstract and public** by default (before Java 8).
    
- All variables are **public static final** by default.
    
- A class **implements** an interface, not extends it.
    
- Interfaces support **multiple inheritance** (unlike classes).
    

---

### 🆕 **Java 8 New Features in Interfaces**

|Feature|Syntax & Example|Why Introduced|
|---|---|---|
|`default` methods|Provide method implementation inside interface|To avoid breaking old implementations|
|`static` methods|Define utility/helper methods directly in interface|For better cohesion & reuse|
|`Functional Interface`|`@FunctionalInterface` annotation and lambda support|For functional programming in Java 8|

---

### 1. 🔁 **Default Methods**

Introduced to allow interfaces to have method **implementations**.

```java
interface MyInterface {
    default void greet() {
        System.out.println("Hello from default method!");
    }
}
```

#### ✅ **Why?**

- To add new methods to existing interfaces **without breaking** classes that implement them.
    
- Solves the **"diamond problem"** more gracefully than classes.
    

---

### 2. ⚙️ **Static Methods in Interfaces**

```java
interface Utils {
    static void print(String msg) {
        System.out.println(msg);
    }
}
```

#### ✅ **Why?**

- To provide **utility methods** related to the interface.
    
- No need for external utility classes.
    

---

### 3. 🧩 **Functional Interfaces**

- An interface with **exactly one abstract method**.
    
- Used in **lambda expressions** and **streams API**.
    

```java
@FunctionalInterface
interface Calculator {
    int operation(int a, int b);
}
```

```java
Calculator add = (a, b) -> a + b;
System.out.println(add.operation(5, 3)); // Output: 8
```

#### ✅ **Why?**

- Enables **functional programming** in Java 8.
    
- Makes code more concise, expressive.
    

---

### 🚫 What You _Still Can't_ Do in Interfaces

- You can't have constructors.
    
- Cannot maintain instance state (no instance variables).
    

---

### ✅ **Interface vs Abstract Class (Quick Comparison)**

|Feature|Interface|Abstract Class|
|---|---|---|
|Multiple Inheritance|✅ Yes|❌ No|
|Constructors|❌ No|✅ Yes|
|Instance Variables|❌ No|✅ Yes|
|Method Implementation|✅ (from Java 8)|✅ Yes|

---

### 📝 Summary

- Java 8 enhanced interfaces with **default**, **static**, and **functional** features.
    
- These changes made interfaces more **flexible** and **modern**.
    
- The goal was to evolve the language **without breaking** existing codebases.

### ⚖️ **`default` vs `static` Methods in Interfaces**

|Feature|`default` Method|`static` Method|
|---|---|---|
|**Definition**|Method with a body inside an interface using `default` keyword|Method with a body using `static` keyword|
|**Invocation**|Called using **object reference**|Called using **interface name**|
|**Inheritance**|✅ Inherited by implementing class|❌ Not inherited by implementing class|
|**Overridable?**|✅ Can be **overridden** in implementing class|❌ Cannot be overridden|
|**Access to instance data?**|✅ Can access instance methods (via object)|❌ Cannot access instance members|
|**Purpose**|To add new behavior without breaking old code|To add **utility/helper** methods|

---

### 🔧 **Example: `default` Method**

```java
interface Vehicle {
    default void start() {
        System.out.println("Vehicle is starting");
    }
}

class Car implements Vehicle {}

Car c = new Car();
c.start();  // Output: Vehicle is starting
```

---

### ⚙️ **Example: `static` Method**

```java
interface MathUtil {
    static int square(int x) {
        return x * x;
    }
}

int result = MathUtil.square(4);  // Output: 16
```

---

### 💡 **Why Both Were Introduced in Java 8?**

|Method Type|Motivation|
|---|---|
|`default`|Enable backward-compatible evolution of interfaces (e.g., adding methods without forcing changes in all implementing classes).|
|`static`|Encourage grouping related utility methods within interfaces instead of external utility classes.|

---

### 📝 Summary

- Use **`default`** when you want to provide **optional behavior** that can be overridden.
    
- Use **`static`** when you want to provide **common helper methods** that don't depend on object state.


## Inner class
![](../statics/Pasted%20image%2020250520085020.png)


### 📘 **What is a Member Inner Class?**

A **member inner class** is a **non-static class** defined **inside another class**, but **outside any method**.

```java
class Outer {
    class Inner {
        void show() {
            System.out.println("Inside Inner Class");
        }
    }
}
```

---

### 🧠 **Key Points**

|Feature|Description|
|---|---|
|Belongs to|Instance of the outer class|
|Can access|All **members** (including private) of the outer class|
|Cannot have|`static` declarations (unless it's a constant)|
|Instantiated using|An **instance of the outer class**|

---

### ✅ **How to Create an Object of Member Inner Class**

```java
Outer outer = new Outer();
Outer.Inner inner = outer.new Inner();
inner.show();
```

---

### 🔄 **Accessing Outer Class Members**

```java
class Outer {
    int x = 10;
    
    class Inner {
        void display() {
            System.out.println("x = " + x); // Access outer member
        }
    }
}
```

---

### 🚫 **Rules and Restrictions**

- Cannot have `static` methods or fields.
    
- Cannot be instantiated without an instance of the outer class.
    
- It is compiled to a separate `.class` file: `Outer$Inner.class`.
    

---

### 🎯 **When to Use Member Inner Class**

- When inner class **logically belongs** to outer class.
    
- When inner class needs **access to outer class’s instance members**.
    
- Useful in **encapsulation** and **helper class scenarios**.
    

---

### 📝 **Example**

```java
class Laptop {
    private String brand = "Dell";

    class Battery {
        void show() {
            System.out.println("Laptop Brand: " + brand);
        }
    }
}

class Main {
    public static void main(String[] args) {
        Laptop laptop = new Laptop();
        Laptop.Battery battery = laptop.new Battery();
        battery.show();  // Output: Laptop Brand: Dell
    }
}
```

---

### 📌 Summary

- Member inner class is a **non-static inner class**.
    
- It is associated with the **instance of the outer class**.
    
- Can access **all members** of the outer class.
    
- Helps in grouping **logically related classes** together.




### 📘 **What is a Static Nested Class?**

A **static nested class** is a **static class defined inside another class**.

```java
class Outer {
    static class Nested {
        void display() {
            System.out.println("Inside static nested class");
        }
    }
}
```

---

### 🧠 **Key Characteristics**

|Feature|Description|
|---|---|
|**Declared as**|`static class` inside another class|
|**Can access**|Only **static members** of the outer class directly|
|**Doesn't need**|An object of outer class to be instantiated|
|**Can have**|Both static and non-static members|
|**Is like**|A top-level class, but scoped within another class|

---

### ✅ **How to Create a Static Nested Class Object**

```java
Outer.Nested obj = new Outer.Nested();
obj.display();
```

---

### 🔄 **Accessing Outer Class Members**

```java
class Outer {
    static int data = 50;

    static class Nested {
        void show() {
            System.out.println("Data: " + data);
        }
    }
}
```

> ❗ A static nested class **cannot** access non-static members of the outer class directly.

---

### 📌 **Use Cases**

- When the nested class **does not require access** to instance members of the outer class.
    
- Useful for **grouping classes logically** that are only used by the outer class.
    
- Often used in **utility/helper classes**, like `Map.Entry`, `Thread.State`.
    

---

### 📝 Example

```java
class University {
    static String name = "ABC University";

    static class Department {
        void info() {
            System.out.println("Department of CSE at " + name);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        University.Department d = new University.Department();
        d.info();  // Output: Department of CSE at ABC University
    }
}
```

---

### ⚖️ **Member Inner Class vs Static Nested Class**

|Feature|Member Inner Class|Static Nested Class|
|---|---|---|
|Requires outer object|✅ Yes|❌ No|
|Can access|All members (even private)|Only static members|
|Static allowed inside|❌ No|✅ Yes|

---

### ✅ Summary

- Static nested class is like a **static member** of the outer class.
    
- It does **not need** an instance of the outer class.
    
- Best used when there's **no dependency on outer class instance**.


### 📘 **What is a Local Inner Class?**

- A **local inner class** is a class **defined inside a method, constructor, or block**.
    
- It is **local to the block** where it is defined, so its scope is limited.
    
- Not visible outside the method/block.
    

```java
void myMethod() {
    class LocalClass {
        void display() {
            System.out.println("Inside Local Inner Class");
        }
    }
    LocalClass obj = new LocalClass();
    obj.display();
}
```

---

### 🧠 **Key Points**

|Feature|Description|
|---|---|
|Defined inside|Method, constructor, or block|
|Scope|Only within the method/block|
|Can access|Final or effectively final local variables from the method|
|Can access outer class members|Yes, including private members|
|Cannot have|Access modifiers (like `public`, `private`)|
|Instantiated within|The method or block where it is defined|

---

### ✅ **Example**

```java
class Outer {
    void method() {
        int num = 10;  // effectively final variable

        class LocalInner {
            void print() {
                System.out.println("num = " + num);
            }
        }

        LocalInner local = new LocalInner();
        local.print();
    }
}
```

---

### 🔄 **Accessing Variables**

- Local inner class **can access**:
    
    - All members of outer class.
        
    - **Final or effectively final** local variables of the enclosing method.
        

---

### ⚠️ **Important Notes**

- The local variable accessed inside the local inner class **must be final or effectively final** (not modified after initialization).
    
- Local inner classes **cannot declare static members**.
    

---

### 📝 **When to Use?**

- When you need a class that is **used only within a single method**.
    
- To logically group code that belongs only in the method context.
    
- For better encapsulation and clarity.
    

---

### Summary:

|Aspect|Local Inner Class|
|---|---|
|Defined inside|Method/block/constructor|
|Scope|Only inside the method/block|
|Access to outer members|Yes|
|Access to local variables|Only final or effectively final|
|Static members allowed|No|
