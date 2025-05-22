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

## Collection
The **Collection Framework in Java** is a unified architecture for representing and manipulating collections of objects. It provides a set of interfaces and classes that make it easy to work with groups of data — such as lists, sets, and maps — in a consistent and efficient way.
![](../statics/Pasted%20image%2020250521144019.png)
![](../statics/Pasted%20image%2020250521144115.png)

### List Interface 

![](../statics/Pasted%20image%2020250521144158.png)
![](../statics/Pasted%20image%2020250521144331.png)
![](../statics/Pasted%20image%2020250521144311.png)
#### ArrayList

![](../statics/Pasted%20image%2020250521144403.png)
![](../statics/Pasted%20image%2020250521144959.png)
![](../statics/Pasted%20image%2020250521145042.png)
![](../statics/Pasted%20image%2020250521145154.png)
![](../statics/Pasted%20image%2020250521145305.png)
```java
List<Integer> ls = new ArrayList<>(initialCapacity: 11);
```

- We cannot have a method to know the capacity but we can use reflection
![](../statics/Pasted%20image%2020250521145744.png)
- here using Arrays.asList() do not allow for adding and deleting but replacing , class name is `java.util.Arrays$ArrayList`.
- in case of List.of() we cannot even do replace

| Method                            | Description                                  | Time Complexity              |
| --------------------------------- | -------------------------------------------- | ---------------------------- |
| `add(E e)`                        | Adds element to the end                      | O(1) amortized               |
| `add(int index, E element)`       | Inserts element at index                     | O(n)                         |
| `get(int index)`                  | Returns element at index                     | O(1)                         |
| `set(int index, E element)`       | Replaces element at index                    | O(1)                         |
| `remove(int index)`               | Removes element at index                     | O(n)                         |
| `remove(Object o)`                | Removes first occurrence                     | O(n)                         |
| `clear()`                         | Removes all elements                         | O(n)                         |
| `contains(Object o)`              | Checks if element exists                     | O(n)                         |
| `indexOf(Object o)`               | Returns index of first occurrence            | O(n)                         |
| `lastIndexOf(Object o)`           | Returns index of last occurrence             | O(n)                         |
| `size()`                          | Returns number of elements                   | O(1)                         |
| `isEmpty()`                       | Checks if list is empty                      | O(1)                         |
| `toArray()`                       | Converts list to array                       | O(n)                         |
| `ensureCapacity(int minCapacity)` | Ensures capacity without resizing frequently | O(n) worst case              |
| `trimToSize()`                    | Trims unused memory                          | O(n)                         |
| `clone()`                         | Creates shallow copy                         | O(n)                         |
| `iterator()`                      | Returns iterator                             | O(1)                         |
| `subList(int from, int to)`       | Creates a view of the portion of the list    | O(1) (but changes reflected) |

**Comparator**
- Interface allowing custom ordering
- ![](../statics/Pasted%20image%2020250521150646.png)
- contains compare method , it is a functional interface , compare two object of same type and decide its order
![](../statics/Pasted%20image%2020250521150922.png)
- if int is -ve then o1 comes before o2 , if 0 then they are equal , if +ve then o1 comes after o2.

![](../statics/Pasted%20image%2020250521152349.png)
this do not work, null tells that follow natural ordering , but here in custom object , natural ordering is not defined

![](../statics/Pasted%20image%2020250521152450.png)
in String class it implements Comparable that is why the sort function work on a String list
![](../statics/Pasted%20image%2020250521152915.png)


#### LinkedList
![](../statics/Pasted%20image%2020250521153212.png)
![](../statics/Pasted%20image%2020250521153327.png)
![](../statics/Pasted%20image%2020250521153444.png)

| Method                              | Description                        | Time Complexity |
| ----------------------------------- | ---------------------------------- | --------------- |
| `add(E e)`                          | Adds to end                        | O(1)            |
| `add(int index, E element)`         | Inserts at index                   | O(n)            |
| `get(int index)`                    | Gets element at index              | O(n)            |
| `set(int index, E element)`         | Replaces element at index          | O(n)            |
| `remove(int index)`                 | Removes element at index           | O(n)            |
| `remove(Object o)`                  | Removes first occurrence           | O(n)            |
| `clear()`                           | Removes all elements               | O(n)            |
| `contains(Object o)`                | Checks if list contains element    | O(n)            |
| `size()`                            | Returns number of elements         | O(1)            |
| `isEmpty()`                         | Checks if list is empty            | O(1)            |
| `indexOf(Object o)`                 | First occurrence index             | O(n)            |
| `lastIndexOf(Object o)`             | Last occurrence index              | O(n)            |
| `addFirst(E e)` / `offerFirst(E e)` | Adds to beginning                  | O(1)            |
| `addLast(E e)` / `offerLast(E e)`   | Adds to end                        | O(1)            |
| `removeFirst()` / `pollFirst()`     | Removes from beginning             | O(1)            |
| `removeLast()` / `pollLast()`       | Removes from end                   | O(1)            |
| `peekFirst()` / `getFirst()`        | Gets first element without removal | O(1)            |
| `peekLast()` / `getLast()`          | Gets last element without removal  | O(1)            |
| `iterator()`                        | Returns iterator                   | O(1)            |
| `descendingIterator()`              | Iterator from end to start         | O(1)            |
#### Vector
![](../statics/Pasted%20image%2020250521154108.png)
![](../statics/Pasted%20image%2020250521154129.png)
![](../statics/Pasted%20image%2020250521154532.png)

#### Stack
it do not implements List interface directly 
![](../statics/Pasted%20image%2020250521155106.png)
![](../statics/Pasted%20image%2020250521155119.png)

#### CopyOnWriteArrayList
- It **creates a new copy of the internal array** every time a write operation (like `add()`, `set()`, `remove()`) is performed.
- Read operations (like `get()`, `iterator()`) operate on a **stable, immutable snapshot** of the array.
- No need for external synchronization when iterating or accessing.
![](../statics/Pasted%20image%2020250521155832.png)

### Map

![](../statics/Pasted%20image%2020250521204632.png)

![](../statics/Pasted%20image%2020250521160301.png)
![](../statics/Pasted%20image%2020250521160726.png)
![](../statics/Pasted%20image%2020250521160736.png)
#### HashMap

![](../statics/Pasted%20image%2020250521161950.png)
![](../statics/Pasted%20image%2020250521162201.png)
![](../statics/Pasted%20image%2020250521162217.png)
![](../statics/Pasted%20image%2020250521162231.png)
![](../statics/Pasted%20image%2020250521162249.png)
![](../statics/Pasted%20image%2020250521162321.png)
![](../statics/Pasted%20image%2020250521162406.png)
![](../statics/Pasted%20image%2020250521162435.png)
![](../statics/Pasted%20image%2020250521162511.png)
![](../statics/Pasted%20image%2020250521162548.png)
![](../statics/Pasted%20image%2020250521162857.png)
- Red Black Tree used after java 8
![](../statics/Pasted%20image%2020250521163049.png)
- Size will get doubled
- ![](../statics/Pasted%20image%2020250521163441.png)
![](../statics/Pasted%20image%2020250521163503.png)
- It use balanced tree if it hits a threashold of a linked list which is 8 by default
- Important to note that equals method is called to search a linkedlist or tree , so if you create a Custom class for key ensure to implement equals method
- 
![](../statics/Pasted%20image%2020250521164716.png)

#### LinkedHashMap
![](../statics/Pasted%20image%2020250521165233.png)
![](../statics/Pasted%20image%2020250521173137.png)
- accessorder set true ensure that the key which is access get to last 
- this can be used for LRU cache


### Garbage Collection
- System.gc()

#### WeakHashMap

- A **Map** implementation where the **keys are stored using weak references**.
    
- If a key is no longer referenced elsewhere in the program (i.e., no strong references), it becomes **eligible for garbage collection**.
    
- When GC collects the key, the corresponding entry is **automatically removed** from the map.

### 🔑 Key Points:

|Feature|Details|
|---|---|
|Class Name|`java.util.WeakHashMap`|
|Implements|`Map<K, V>`|
|Key reference type|**Weak** reference|
|Value reference type|**Strong** reference|
|Garbage collected entries|✅ Yes, if key has no strong reference|
|Thread-safe?|❌ No (needs external sync)|

---

### 🧪 Example Code:

```java
import java.util.WeakHashMap;

public class Main {
    public static void main(String[] args) {
        WeakHashMap<Object, String> map = new WeakHashMap<>();
        Object key = new Object();

        map.put(key, "Value");

        System.out.println("Before GC: " + map);

        key = null;  // Remove strong reference to key
        System.gc(); // Suggest garbage collection

        try { Thread.sleep(100); } catch (Exception ignored) {}

        System.out.println("After GC: " + map);
    }
}
```

### 📤 Sample Output:

```
Before GC: {java.lang.Object@6bc7c054=Value}
After GC: {}
```

---

### 📋 Comparison with `HashMap`:

|Feature|`HashMap`|`WeakHashMap`|
|---|---|---|
|Key reference|Strong|Weak|
|Entry removal|Manual|Automatic (GC-based)|
|Memory leaks|Possible|Less likely|
|Use cases|General purpose|Caching, metadata|

---

### 🧠 When to Use `WeakHashMap`?

- When you want the **map entries to disappear automatically** when keys are no longer in use.
    
- For **caching**, **plugin managers**, or **metadata mapping** where retaining keys is not necessary.
    
- When avoiding **memory leaks** is important.
    

---

### ⚠️ Limitations:
- **Not thread-safe** → Use `Collections.synchronizedMap()` or a concurrent alternative.
- Garbage collection timing is **non-deterministic**.


#### IdentityHashMap

- `IdentityHashMap` is a special `Map` implementation that **compares keys using `==` (reference equality)** instead of `.equals()`.
    
- It’s part of the `java.util` package.
    

---

### 🔑 Key Characteristics:

| Feature              | Description                                                            |
| -------------------- | ---------------------------------------------------------------------- |
| Key comparison       | Uses `==` (identity comparison) instead of `.equals()`                 |
| Value comparison     | Uses `==` for keys only, values behave normally                        |
| Null keys/values     | ✅ Allows one `null` key and multiple `null` values                     |
| Underlying structure | Backed by a simple array, not a traditional hash bucket like `HashMap` |
| Thread-safe          | ❌ No, must be synchronized externally if used by multiple threads      |
| Performance          | Fast for small maps, no hashing based on `hashCode()`                  |

---

### 🧪 Example Code:

```java
import java.util.IdentityHashMap;

public class Main {
    public static void main(String[] args) {
        IdentityHashMap<String, String> map = new IdentityHashMap<>();

        String a = new String("key");
        String b = new String("key");

        map.put(a, "value1");
        map.put(b, "value2");

        System.out.println(map.size());  // Output: 2
    }
}
```

### ❓ Why size is 2?

- Because `a == b` is `false` (different objects), even though `a.equals(b)` is `true`.
    
- `IdentityHashMap` treats `a` and `b` as **different keys**.
    

---

### 📋 Comparison: `HashMap` vs `IdentityHashMap`

| Feature          | `HashMap`                   | `IdentityHashMap`                     |
| ---------------- | --------------------------- | ------------------------------------- |
| Key comparison   | `.equals()` + `.hashCode()` | `==` (reference equality)             |
| Use case         | General-purpose maps        | Object identity-based mappings        |
| Memory leak risk | Low                         | Higher (due to identity logic)        |
| Performance      | Optimized for general use   | Faster for small, identity-based maps |

### 🧠 When to Use `IdentityHashMap`?
- **Frameworks** or **tools** that need to **track object identity**, not just logical equality. 
- Example: Keeping metadata for specific object instances in a cache.

### ⚠️ Cautions:

- Don’t use `IdentityHashMap` where logical equality is expected.
- Not intuitive: Two logically equal keys may be treated as different.
- Not a replacement for `HashMap` in most everyday cases.
### Comparable 

- `Comparable` is an **interface** in `java.lang` used to define the **natural ordering** of objects.
    
- It is used when you want to **sort custom objects** using `Collections.sort()` or `Arrays.sort()`.
    

---

### 🔑 Key Points

|Feature|Description|
|---|---|
|Interface|`java.lang.Comparable<T>`|
|Method to implement|`int compareTo(T o)`|
|Purpose|Defines **natural order** of class instances|
|Sorting usage|Used by sorting methods like `Collections.sort()`|
|Modifies original class|✅ Yes – implements in the class itself|

---

### 🧪 Syntax:

```java
public class Student implements Comparable<Student> {
    int marks;

    public Student(int marks) {
        this.marks = marks;
    }

    @Override
    public int compareTo(Student other) {
        return this.marks - other.marks; // ascending order
    }
}
```

---

### 📊 Return Values of `compareTo()`:

|Return Value|Meaning|
|---|---|
|Negative|`this < other`|
|Zero|`this == other`|
|Positive|`this > other`|

---

### 🧪 Usage Example:

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        List<Student> list = new ArrayList<>();
        list.add(new Student(85));
        list.add(new Student(75));
        list.add(new Student(95));

        Collections.sort(list); // uses compareTo internally
    }
}
```

---

### 📋 `Comparable` vs `Comparator`

|Feature|`Comparable`|`Comparator`|
|---|---|---|
|Defined in|The class itself|A separate class (or lambda)|
|Method|`compareTo(T o)`|`compare(T o1, T o2)`|
|Sorting flexibility|Only one natural order|Can define multiple sort logics|
|Modifies class?|✅ Yes|❌ No (external)|

---

### 📌 Use Cases:

- Sorting a list of custom objects (e.g., Students by marks).
    
- Used in **TreeSet**, **TreeMap**, and other sorted collections.
    
- When a **default/natural** order is required.
    

#### Sorted Map
![](../statics/Pasted%20image%2020250521202923.png)
![](../statics/Pasted%20image%2020250521203207.png)
Treemap using red black tree
![](../statics/Pasted%20image%2020250521203535.png)
![](../statics/Pasted%20image%2020250521203554.png)
![](../statics/Pasted%20image%2020250521203606.png)


### HashTable
- Legacy 
- it is synchronized, now use ConcurrentHashMap
- no null key or value

### ConcurrentHashMap
- In java 7 it is using segment based locking , hashmap is divided into 16 segments 
- Only the segment been written or read from is locked not the entire map
- In java 8 , compare and swap approach , no locking except resizing or collision 
**CAS** is a low-level atomic instruction used in concurrent programming to achieve **lock-free thread-safe operations**.
- It does not allow null as key
It works like this:

> "If the value at a memory location is equal to an expected value, update it to a new value. Otherwise, do nothing."

- `ConcurrentHashMap` is a thread-safe implementation of `Map` in `java.util.concurrent` package.
    
- Unlike `HashMap`, it allows **concurrent access** from multiple threads **without explicit synchronization**

- **No segments**.
    
- It uses **fine-grained locking at the bucket/bin level**, and **CAS (Compare-And-Swap)** for non-blocking reads and some updates.
    
- Locking occurs:
    
    - When **resizing the map**
        
    - When **multiple threads try to update the same bin**
        
    - When bins turn into **tree nodes** (for collision handling)

#### ConcurrentSkipListMap
- It is a Thread safe tree map
- Use SkipList
- ![](../statics/Pasted%20image%2020250521222057.png)
- ![](../statics/Pasted%20image%2020250521222219.png)

#### EnumMap
- If you are using enum as a key , and key belong to single enum , then we can use the EnumMap , here advantage is the map knows the keys in advance
- So resizing is not required here 
- Order is same as of enum
- no hashing

#### ImmutableMap
![](../statics/Pasted%20image%2020250521223026.png)

## Set


### Queue
- adding element called enqueue , and removing it is called dequeue
- Interface
![](../statics/Pasted%20image%2020250521231428.png)
#### Priority Queue
- Order element based on their natural ordering
- Does not allow null element
- Implemented using heap
- Delete , insert (logn) 

### Deque
- Double ended queue
- ![](../statics/Pasted%20image%2020250521232454.png)
- ArrayDeque , no null allowed , fast iteration
- Here in ArrayDeque , circular array is been used


### BlockingQueue
- Thread safe queue
- It is a interface , using implementation like ArrayBlockingQueue
- wait for queue to become non-empty / wait for space
- ![](../statics/Pasted%20image%2020250521235849.png)


## MultiThreading
![](../statics/Pasted%20image%2020250522072823.png)
![](../statics/Pasted%20image%2020250522072837.png)
![](../statics/Pasted%20image%2020250522072941.png)
![](../statics/Pasted%20image%2020250522073137.png)
![](../statics/Pasted%20image%2020250522073251.png)
![](../statics/Pasted%20image%2020250522073316.png)
![](../statics/Pasted%20image%2020250522073958.png)
![](../statics/Pasted%20image%2020250522074110.png)
- Extends Thread class and override run method
- 
### Creating Thread 
![](../statics/Pasted%20image%2020250522074654.png)
- Using Runnable 
- ![](../statics/Pasted%20image%2020250522074802.png)
- ![](../statics/Pasted%20image%2020250522074817.png)
### Lifecycle of thread
![](../statics/Pasted%20image%2020250522075012.png)
 In Java multithreading, `sleep()`, `start()`, and `join()` are fundamental methods for managing thread execution. Let's break down each one:

### 1. `Thread.sleep(long milliseconds)`

- **Purpose:** The `sleep()` method is used to pause the execution of the _currently executing thread_ for a specified duration in milliseconds.
- **Behavior:**
    - When a thread calls `sleep()`, it temporarily stops its execution and moves from the `Running` state to the `Timed Waiting` state.
    - It doesn't release any monitors (locks) it might be holding. This is a crucial distinction from `wait()`.
    - After the specified time elapses, the thread moves back to the `Runnable` state (ready to be picked up by the scheduler), but there's no guarantee it will immediately start running again. The scheduler decides when it gets CPU time.
    - `sleep()` is a static method, meaning it always affects the thread that is currently executing the `sleep()` call, not necessarily the `Thread` object on which it's invoked (though it's usually called as `Thread.sleep()`).
- **Signature:** `public static native void sleep(long millis) throws InterruptedException`
- **Exception Handling:** It throws an `InterruptedException` if another thread interrupts the current thread while it is sleeping. You must handle this exception (usually by catching it and deciding how to respond, e.g., cleaning up or logging).
- **Use Cases:**
    - To slow down operations.
    - To give other threads a chance to execute.
    - To simulate real-world delays.
    - In situations where you need to periodically check for a condition.

**Example:**

Java

```java
public class SleepExample extends Thread {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getName() + ": " + i);
            try {
                Thread.sleep(1000); // Pause for 1 second
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + " was interrupted.");
                Thread.currentThread().interrupt(); // Restore the interrupted status
            }
        }
    }

    public static void main(String[] args) {
        SleepExample t1 = new SleepExample();
        SleepExample t2 = new SleepExample();

        t1.start();
        t2.start();
    }
}
```

### 2. `Thread.start()`

- **Purpose:** The `start()` method is used to begin the execution of a thread. It's the entry point for a new thread's execution.
- **Behavior:**
    - When `start()` is called on a `Thread` object, the Java Virtual Machine (JVM) creates a new execution stack for that thread.
    - It then calls the `run()` method of that `Thread` object (or the `run()` method of the `Runnable` object if the `Thread` was constructed with a `Runnable`).
    - It's important to note that `start()` itself doesn't directly execute the `run()` method. Instead, it makes the thread eligible to be run by the thread scheduler.
    - Calling `start()` more than once on the same thread object will result in an `IllegalThreadStateException`.
- **Lifecycle:** `start()` moves a thread from the `New` state to the `Runnable` state.
- **Use Cases:** Essential for initiating any new thread of execution in Java.

**Example:**

Java

```java
public class StartExample extends Thread {
    public void run() {
        System.out.println(Thread.currentThread().getName() + " is running.");
    }

    public static void main(String[] args) {
        StartExample t1 = new StartExample();
        StartExample t2 = new StartExample();

        t1.start(); // This will call the run() method of t1 in a new thread
        t2.start(); // This will call the run() method of t2 in another new thread

        // If you mistakenly call run() directly, it won't create a new thread:
        // t1.run(); // This would execute run() in the main thread
    }
}
```

### 3. `Thread.join()`

- **Purpose:** The `join()` method allows one thread to wait for the completion of another thread. When `join()` is called on a thread object, the calling thread will pause its execution until the thread on which `join()` was called finishes its execution.
- **Behavior:**
    - If thread A calls `t.join()`, where `t` is another thread, then thread A will block (go into the `Waiting` or `Timed Waiting` state) until thread `t` completes its execution.
    - `join()` has overloaded versions:
        - `join()`: Waits indefinitely until the thread dies.
        - `join(long millis)`: Waits for a maximum of `millis` milliseconds. If the thread doesn't die within that time, the calling thread resumes.
        - `join(long millis, int nanos)`: Waits for a maximum of `millis` milliseconds plus `nanos` nanoseconds.
- **Exception Handling:** Like `sleep()`, `join()` can throw an `InterruptedException` if the waiting thread is interrupted while it's waiting for the target thread to die.
- **Use Cases:**
    - When you need to ensure that a set of threads have completed their tasks before proceeding with further operations (e.g., aggregating results from multiple threads).
    - To maintain execution order or dependencies between threads.

**Example:**

Java

```java
public class JoinExample extends Thread {
    public void run() {
        for (int i = 1; i <= 3; i++) {
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + " was interrupted.");
                Thread.currentThread().interrupt();
            }
            System.out.println(Thread.currentThread().getName() + " is running: " + i);
        }
    }

    public static void main(String[] args) {
        JoinExample t1 = new JoinExample();
        JoinExample t2 = new JoinExample();
        JoinExample t3 = new JoinExample();

        t1.start();

        try {
            t1.join(); // Main thread waits for t1 to complete
        } catch (InterruptedException e) {
            System.out.println("Main thread interrupted while waiting for t1.");
            Thread.currentThread().interrupt();
        }

        t2.start();
        t3.start();

        System.out.println("Main thread finished.");
    }
}
```

**Output of `JoinExample` (approximate):**

```
Thread-0 is running: 1
Thread-0 is running: 2
Thread-0 is running: 3
Thread-1 is running: 1
Thread-2 is running: 1
Main thread finished.
Thread-1 is running: 2
Thread-2 is running: 2
Thread-1 is running: 3
Thread-2 is running: 3
```

Notice how "Main thread finished." only prints after `Thread-0` completes because of `t1.join()`. If `t1.join()` were removed, "Main thread finished." could print much earlier.

### Key Differences and Relationships:

|   |   |   |   |
|---|---|---|---|
|**Feature**|**start()**|**sleep()**|**join()**|
|**Purpose**|Initiates a new thread's execution|Pauses the _current_ thread for a duration|Makes _one_ thread wait for _another_ to complete|
|**Caller**|The thread that wants to create/run a new thread|The thread that wants to pause itself|The thread that wants to wait for another thread|
|**Effect**|Creates a new call stack, calls `run()`|Puts the current thread in `Timed Waiting`|Puts the calling thread in `Waiting`/`Timed Waiting`|
|**Lock**|No direct lock involvement|Does NOT release acquired locks|Releases the lock on the `Thread` object if used with `wait()` (though usually `join()` is used directly)|
|**State**|`New` -> `Runnable`|`Running` -> `Timed Waiting` -> `Runnable`|`Running` -> `Waiting`/`Timed Waiting` -> `Runnable`|
|**Exception**|`IllegalThreadStateException` if called twice|`InterruptedException`|`InterruptedException`|


```java
class MyThread extends Thread{
	public MyThread(String name){
		super(name);
	}
	@Override
	public void run(){
	}
}
class Main{
	public static void main(String[] arg){
		MyThread t1 = new MyThread("My Thread");
		t1.setPriority(Thread.MAX_PRIORITY); // Thread.MIN_PRIORITY(1) , NORM_PRIORITY (5)
		
	}
}
```
![](../statics/Pasted%20image%2020250522083105.png)

- these are not strict , it is a hint to jvm

### 4. `Thread.setDaemon(boolean on)`

- **Purpose:** This method is used to mark a thread as either a daemon thread or a user thread.
- **Daemon Thread Explained:**
    - **Definition:** A daemon thread is a low-priority thread that runs in the background to provide services to user threads. Its life depends on the mercy of user threads.
    - **JVM Termination:** The Java Virtual Machine (JVM) will exit when all _non-daemon (user) threads_ have completed their execution. If there are only daemon threads running, the JVM will terminate, regardless of whether the daemon threads have finished their tasks.
    - **Purpose:** Daemon threads are typically used for background tasks like garbage collection (the GC thread is a daemon thread), finalization, logging, or monitoring, where it's not critical for them to complete their execution if the main application (user threads) shuts down.
    - **Inheritance:** A thread inherits its daemon status from its parent thread. The `main` thread is always a user thread by default.
    - **Caution:** Daemon threads are automatically terminated by the JVM without any graceful shutdown mechanism. This means `finally` blocks in daemon threads might not always execute, which can lead to resource leaks if not handled carefully (e.g., if you're dealing with I/O streams).
- **Behavior of `setDaemon()`:**
    - You **must** call `setDaemon()` _before_ the thread is started (i.e., before calling `thread.start()`). If you try to call it after `start()`, it will throw an `IllegalThreadStateException`.
    - `public final void setDaemon(boolean on)`
    - You can check if a thread is a daemon thread using `public final boolean isDaemon()`.
- **Use Cases:**
    - Background tasks that are not essential for the application's core functionality.
    - Support services that should automatically stop when the main application ends.

**Example:**

Java

```
public class DaemonThreadExample extends Thread {
    public void run() {
        if (Thread.currentThread().isDaemon()) {
            System.out.println(Thread.currentThread().getName() + " is a DAEMON thread.");
        } else {
            System.out.println(Thread.currentThread().getName() + " is a USER thread.");
        }

        try {
            for (int i = 0; i < 5; i++) {
                System.out.println(Thread.currentThread().getName() + " running: " + i);
                Thread.sleep(500);
            }
        } catch (InterruptedException e) {
            System.out.println(Thread.currentThread().getName() + " interrupted.");
            Thread.currentThread().interrupt();
        } finally {
            // This finally block might not execute for daemon threads if JVM exits
            if (Thread.currentThread().isDaemon()) {
                System.out.println(Thread.currentThread().getName() + " (Daemon) finally block executed.");
            } else {
                System.out.println(Thread.currentThread().getName() + " (User) finally block executed.");
            }
        }
    }

    public static void main(String[] args) throws InterruptedException {
        DaemonThreadExample userThread = new DaemonThreadExample();
        DaemonThreadExample daemonThread = new DaemonThreadExample();

        daemonThread.setDaemon(true); // Mark as daemon before starting

        userThread.setName("UserThread");
        daemonThread.setName("DaemonThread");

        userThread.start();
        daemonThread.start();

        // Let main thread run for a bit to allow daemon thread to show some output
        Thread.sleep(1500);
        System.out.println("Main thread finished. JVM will exit if only daemon threads remain.");
        // The JVM will likely exit here, even if DaemonThread hasn't completed its loop.
    }
}
```

### 5. `Thread.interrupt()`

- **Purpose:** The `interrupt()` method is used to request a thread to stop what it is doing. It's a way for one thread to signal to another thread that it should interrupt its current activity.
- **Behavior:**
    - **Not a termination method:** `interrupt()` does not forcibly stop a thread. It's a cooperative mechanism. The interrupted thread is responsible for checking its interrupted status and responding appropriately.
    - **Interrupted Status:** Calling `interrupt()` sets an internal "interrupted" flag of the target thread to `true`.
    - **Blocked States:** If the target thread is currently blocked in methods like `sleep()`, `wait()`, or `join()`, calling `interrupt()` on it will cause these methods to throw an `InterruptedException`. When `InterruptedException` is thrown, the interrupted status of the thread is **cleared** (set back to `false`).
    - **Polling the Status:** If the thread is not in a blocked state, the `interrupt()` call merely sets the flag. The thread can then check this flag using:
        - `public boolean isInterrupted()`: Returns the interrupted status of the thread. This method **does not** clear the interrupted status.
        - `public static boolean interrupted()`: A static method that tests whether the _current_ thread has been interrupted. This method **clears** the interrupted status (sets it back to `false`).
- **Use Cases:**
    - To gracefully shut down long-running tasks or background threads.
    - To signal a thread to stop waiting on a condition.
    - To cancel an ongoing operation.

**Example:**

Java

```
public class InterruptExample extends Thread {
    public void run() {
        while (!Thread.currentThread().isInterrupted()) { // Check interrupted status
            System.out.println(Thread.currentThread().getName() + " is working...");
            try {
                Thread.sleep(1000); // Thread might be interrupted here
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + " was interrupted while sleeping!");
                // Crucial: Re-interrupt the thread to set the flag again
                // so the while loop condition can catch it, or break the loop.
                Thread.currentThread().interrupt();
                break; // Exit the loop on interruption
            }
        }
        System.out.println(Thread.currentThread().getName() + " has stopped working.");
    }

    public static void main(String[] args) throws InterruptedException {
        InterruptExample worker = new InterruptExample();
        worker.setName("WorkerThread");
        worker.start();

        Thread.sleep(3000); // Let the worker thread run for 3 seconds
        worker.interrupt(); // Interrupt the worker thread
    }
}
```

### 6. `Thread.yield()`

- **Purpose:** The `yield()` method is a static method that provides a hint to the thread scheduler that the _current thread_ is willing to yield its current use of a processor. It suggests that the current thread is not doing anything critical at the moment and other threads of the same or higher priority might want to run.
- **Behavior:**
    - When `yield()` is called, the currently executing thread moves from the `Running` state to the `Runnable` (ready) state.
    - The thread scheduler is **free to ignore this hint**. There's no guarantee that another thread will immediately start running, or that the yielded thread won't be immediately re-scheduled.
    - `yield()` does not cause the thread to release any monitors (locks) it holds.
    - It is platform-dependent and its behavior can vary significantly across different JVM implementations and operating systems.
- **Use Cases:**
    - Primarily for debugging or testing purposes to help reproduce race conditions.
    - Occasionally in highly specialized performance tuning where you want to explicitly give other threads a chance, but it's generally discouraged due to its unpredictable nature. Most modern JVMs and operating systems have sophisticated schedulers that make manual `yield()` calls rarely beneficial.

**Example:**

Java

```
public class YieldExample extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println(Thread.currentThread().getName() + " is running: " + i);
            if (i == 2) {
                System.out.println(Thread.currentThread().getName() + " yielding...");
                Thread.yield(); // Hint to yield CPU
            }
        }
    }

    public static void main(String[] args) {
        YieldExample t1 = new YieldExample();
        YieldExample t2 = new YieldExample();

        t1.setName("Thread-A");
        t2.setName("Thread-B");

        t1.start();
        t2.start();
    }
}
```

**Note:** The output of `YieldExample` can be highly unpredictable due to `yield()`'s non-deterministic nature. You might see interleaving of "Thread-A" and "Thread-B" differently with each run.

### 7. `Object.wait()`

- **Purpose:** The `wait()` method is used for inter-thread communication. It causes the _current thread_ to wait indefinitely (or for a specified time) until another thread calls `notify()` or `notifyAll()` on the _same object_.
    
- **Crucial Difference from `sleep()` and `join()`:** `wait()` **releases the lock (monitor)** on the object it's called on. This is its key distinction and makes it fundamental for synchronized communication. `sleep()` and `join()` do not release locks.
    
- **Behavior:**
    
    - **Must be called from a `synchronized` block/method:** `wait()` (and `notify()`, `notifyAll()`) can only be called from within a synchronized method or synchronized block. If called outside, it throws an `IllegalMonitorStateException`. This is because a thread must own the object's monitor to wait on it or notify other threads.
    - **Releases Lock:** When `wait()` is called, the current thread gives up the lock on the object and enters the `Waiting` (or `Timed Waiting`) state.
    - **Awaiting Notification:** The thread remains in the waiting state until one of the following occurs:
        - Another thread calls `notify()` on the same object (waking up one waiting thread).
        - Another thread calls `notifyAll()` on the same object (waking up all waiting threads).
        - The specified timeout period (if `wait(long timeout)` or `wait(long timeout, int nanos)` is used) elapses.
        - The thread is interrupted (throws `InterruptedException`).
    - **Re-acquires Lock:** When a thread is notified and wakes up, it re-acquires the lock on the object before it can resume execution.
    - **Spurious Wakeups:** A thread can sometimes wake up from `wait()` without being notified or interrupted (a "spurious wakeup"). Therefore, `wait()` should always be called inside a `while` loop that checks the condition it's waiting for.
- **Signatures:**
    
    - `public final void wait() throws InterruptedException`
    - `public final void wait(long timeout) throws InterruptedException`
    - `public final void wait(long timeout, int nanos) throws InterruptedException`1
- **Use Cases:**
    
    - Implementing producer-consumer patterns.
    - Any scenario where threads need to coordinate their actions based on certain conditions or shared resources.
    - Building custom concurrency utilities.

**Example (Producer-Consumer using `wait()` and `notifyAll()`):**

Java

```
import java.util.LinkedList;
import java.util.Queue;

class Buffer {
    private Queue<Integer> list = new LinkedList<>();
    private int capacity = 5;

    public void produce(int value) throws InterruptedException {
        synchronized (this) {
            while (list.size() == capacity) {
                System.out.println("Buffer is full. Producer waiting...");
                wait(); // Release lock and wait
            }
            list.add(value);
            System.out.println("Produced: " + value);
            notifyAll(); // Notify consumers that buffer is not empty
        }
    }

    public int consume() throws InterruptedException {
        synchronized (this) {
            while (list.isEmpty()) {
                System.out.println("Buffer is empty. Consumer waiting...");
                wait(); // Release lock and wait
            }
            int value = list.remove();
            System.out.println("Consumed: " + value);
            notifyAll(); // Notify producers that buffer is not full
            return value;
        }
    }
}

class Producer extends Thread {
    Buffer buffer;
    public Producer(Buffer buffer) {
        this.buffer = buffer;
    }
    public void run() {
        for (int i = 0; i < 10; i++) {
            try {
                buffer.produce(i);
                Thread.sleep(100);
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
                System.out.println("Producer interrupted.");
                break;
            }
        }
    }
}

class Consumer extends Thread {
    Buffer buffer;
    public Consumer(Buffer buffer) {
        this.buffer = buffer;
    }
    public void run() {
        for (int i = 0; i < 10; i++) {
            try {
                buffer.consume();
                Thread.sleep(200);
            } catch (InterruptedException e) {
                Thread.currentThread().interrupt();
                System.out.println("Consumer interrupted.");
                break;
            }
        }
    }
}

public class WaitNotifyExample {
    public static void main(String[] args) {
        Buffer sharedBuffer = new Buffer();

        Producer producer = new Producer(sharedBuffer);
        Consumer consumer = new Consumer(sharedBuffer);

        producer.setName("Producer");
        consumer.setName("Consumer");

        producer.start();
        consumer.start();
    }
}
```


### 8. `Object.notify()`

- **Purpose:** The `notify()` method is used to wake up _a single thread_ that is waiting on the object's monitor (i.e., a thread that has called `wait()` on that same object).
- **Behavior:**
    - **Must be called from a `synchronized` block/method:** Just like `wait()`, `notify()` must be invoked within a synchronized method or a synchronized block. The calling thread must own the monitor of the object on which `notify()` is called. If not, an `IllegalMonitorStateException` is thrown.
    - **Wakes up one thread:** If there are multiple threads waiting on the same object, `notify()` wakes up only one of them. The choice of which thread gets woken up is non-deterministic and depends on the JVM's implementation, often based on thread priority or the order in which they entered the waiting set.
    - **Doesn't immediately release lock:** The thread that called `notify()` does _not_ immediately release the object's monitor. It only releases the monitor when it exits the synchronized block/method. The woken-up thread then tries to re-acquire the monitor before it can resume execution.
    - **If no threads are waiting:** If `notify()` is called and no threads are currently waiting on that object's monitor, the call has no effect.
- **Use Cases:**
    - When you have a condition that has changed, and only one waiting thread needs to be informed (e.g., a single item has been produced in a buffer where only one consumer can process it at a time).
    - However, due to its non-deterministic nature, `notifyAll()` is often preferred to avoid deadlocks or missed signals, especially in complex scenarios.

**Signature:** `public final native void notify()`

### 9. `Object.notifyAll()`

- **Purpose:** The `notifyAll()` method is used to wake up _all threads_ that are waiting on the object's monitor.
- **Behavior:**
    - **Must be called from a `synchronized` block/method:** Similar to `wait()` and `notify()`, `notifyAll()` must be invoked within a synchronized method or a synchronized block. The calling thread must own the monitor.
    - **Wakes up all threads:** When `notifyAll()` is called, all threads that are currently in the `Waiting` or `Timed Waiting` state on that particular object's monitor are moved to the `Runnable` state (ready to be scheduled).
    - **Doesn't immediately release lock:** The thread that called `notifyAll()` does _not_ immediately release the object's monitor. It releases the monitor only when it exits the synchronized block/method.
    - **Contention for lock:** Once the monitor is released, the awakened threads will then contend for the monitor. Only one of them will succeed in acquiring it and resuming execution at a time. The others will remain in the `Blocked` state (waiting for the lock) until they can acquire it.
    - **Safer choice:** `notifyAll()` is generally the safer choice than `notify()` because it avoids the risk of "lost notifications" or "deadlock" where the "wrong" thread is woken up, or a needed thread is never woken up. Although it might seem less efficient to wake up all threads, the overhead is usually minimal, and it significantly improves the correctness of concurrent applications.
- **Use Cases:**
    - Producer-Consumer problems where multiple consumers might be waiting for data, or multiple producers waiting for buffer space.
    - Any scenario where a change in condition might satisfy multiple waiting threads.
    - When you want to be certain that all relevant waiting threads are given a chance to check the condition and potentially proceed.

**Signature:** `public final native void notifyAll()`

### Key Differences and Relationships between `wait()`, `notify()`, and `notifyAll()`:

|   |   |   |   |
|---|---|---|---|
|**Feature**|**wait()**|**notify()**|**notifyAll()**|
|**Purpose**|Causes current thread to release lock and wait|Wakes up one waiting thread on the object's monitor|Wakes up all waiting threads on the object's monitor|
|**Lock**|**Releases the monitor** of the object|**Does NOT release the monitor** immediately|**Does NOT release the monitor** immediately|
|**Caller**|A thread that needs to wait for a condition to change|A thread that has changed a condition|A thread that has changed a condition|
|**Context**|Must be called inside a `synchronized` block/method|Must be called inside a `synchronized` block/method|Must be called inside a `synchronized` block/method|
|**State Change**|`Running` -> `Waiting`/`Timed Waiting`|(No direct state change for the notifying thread)|(No direct state change for the notifying thread)|
|**Usage**|Always in a `while` loop to guard against spurious wakeups|Use with caution, can lead to deadlocks if not careful|Generally preferred for correctness and robustness|

### Example (Revisiting Producer-Consumer with `notifyAll()` as shown previously):

As demonstrated in the `Object.wait()` section, the `Buffer` class correctly uses `notifyAll()`:

Java

```
import java.util.LinkedList;
import java.util.Queue;

class Buffer {
    private Queue<Integer> list = new LinkedList<>();
    private int capacity = 5;

    public void produce(int value) throws InterruptedException {
        synchronized (this) { // Acquire lock on 'this' (Buffer object)
            while (list.size() == capacity) {
                System.out.println("Buffer is full. Producer waiting...");
                wait(); // Producer releases lock and waits
            }
            list.add(value);
            System.out.println("Produced: " + value);
            notifyAll(); // Notify all waiting threads (consumers and potentially other producers)
        } // Producer releases lock here
    }

    public int consume() throws InterruptedException {
        synchronized (this) { // Acquire lock on 'this' (Buffer object)
            while (list.isEmpty()) {
                System.out.println("Buffer is empty. Consumer waiting...");
                wait(); // Consumer releases lock and waits
            }
            int value = list.remove();
            System.out.println("Consumed: " + value);
            notifyAll(); // Notify all waiting threads (producers and potentially other consumers)
            return value;
        } // Consumer releases lock here
    }
}

// Producer and Consumer classes as defined previously...
class Producer extends Thread { /* ... */ }
class Consumer extends Thread { /* ... */ }

public class WaitNotifyAllExample {
    public static void main(String[] args) {
        Buffer sharedBuffer = new Buffer();

        Producer producer = new Producer(sharedBuffer);
        Consumer consumer = new Consumer(sharedBuffer);
        // You could add multiple producers and consumers here to see notifyAll in action
        // Consumer consumer2 = new Consumer(sharedBuffer);

        producer.setName("Producer");
        consumer.setName("Consumer");
        // consumer2.setName("Consumer-2");

        producer.start();
        consumer.start();
        // consumer2.start();
    }
}
```

In this example, when a producer adds an item, it calls `notifyAll()` to wake up any waiting consumers. When a consumer removes an item, it calls `notifyAll()` to wake up any waiting producers. This ensures that regardless of how many producers or consumers are waiting, they all get a chance to re-evaluate the buffer's state.


## Enum
- ![](../statics/Pasted%20image%2020250522103127.png)
- each field is an instance of the DAY class
- ![](../statics/Pasted%20image%2020250522103221.png)
- after compile it looks like this
- ordinal is index
- .values() return array of enum filed
- .name() give string 
- as enum gets converted to class , we can write method , fields etc


## Wrapper class
- Convert primitive value into objects
- Process of converting primitive to object is boxing and java do that automatically hence autoboxing