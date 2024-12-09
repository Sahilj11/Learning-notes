

#### **Why Java is Not 100% Object-Oriented?**

- Java uses **primitive data types** (e.g., `int`, `boolean`, `float`) that are not objects.
- Wrapper classes (e.g., `Integer`, `Boolean`) can "wrap" these primitives into objects.

#### **Why Pointers Are Not Used in Java?**

1. **Safety:** Direct memory access using pointers can lead to errors or security vulnerabilities.
2. **Simplicity:** Pointers add complexity, contradicting Java’s design principle of simplicity.
3. **Memory Management:** JVM handles memory allocation, avoiding direct access by the user.
#### **What is the JIT Compiler in Java?**

- The **Just-In-Time (JIT) compiler** converts frequently used bytecode into native machine code during runtime, enhancing performance.
- It optimizes "hotspots" (frequently executed code) dynamically.
#### **Why is String Immutable in Java?**

1. **String Pool Efficiency:** If strings were mutable, changes in one reference would affect others.
2. **Security:** Immutable strings ensure integrity in sensitive areas like networking or file operations.
3. **Thread-Safety:** Immutable objects can be shared safely across threads without synchronization.
#### **What is a Marker Interface?**

- An **empty interface** without methods or fields.
- Examples: `Serializable`, `Cloneable`.
- Used to convey metadata or behavior to the JVM or frameworks.
#### **Can You Override a Private or Static Method?**

1. **Private Methods:**
    - Cannot be overridden because they are not visible in child classes.
    - Creating a method with the same name in the child class is considered a **new method**, not overriding.
2. **Static Methods:**
    - Cannot be overridden but can be **hidden** (method hiding) by declaring a static method with the same signature in the child class.
#### **Does `finally` Always Execute?**

- **No**, in cases like:
    - `System.exit()` is called.
    - System crash occurs.
#### **Methods in `java.lang.Object` Class**

1. `clone()`: Creates and returns a copy of this object.
2. `equals(Object obj)`: Compares two objects for equality.
3. `finalize()`: Called by garbage collector before object destruction.
4. `getClass()`: Returns the runtime class of the object.
5. `hashCode()`: Returns a hash code value for the object.
6. `toString()`: Returns a string representation of the object.
#### **How Can You Make a Class Immutable?**

To make a class immutable:

1. Declare the class as `final` so it cannot be extended.
2. Make all fields `private` and `final`.
3. Avoid setter methods.
4. Initialize all fields via the constructor.
5. Return deep copies of mutable fields in getter methods.
#### **What is a Singleton Class and How to Create One?**

- **Singleton Class:** A class that allows only one instance to be created.

**Steps to Create a Singleton Class:**

1. Make the constructor `private` to prevent instantiation from other classes.
2. Create a `static` method to provide access to the instance.
3. Use a `static` variable to hold the single instance.

**Example:**

```java
public class Singleton {
    private static Singleton instance;

    private Singleton() {
        // Private constructor
    }

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

## Java Collection
![](../statics/Pasted%20image%2020241205220800.png)
![](../statics/Pasted%20image%2020241205220813.png)
![](../statics/Pasted%20image%2020241205220829.png)
![](../statics/Pasted%20image%2020241205220856.png)
![](../statics/Pasted%20image%2020241205220903.png)
![](../statics/Pasted%20image%2020241205220955.png)
![](../statics/Pasted%20image%2020241205221001.png)
![](../statics/Pasted%20image%2020241205221033.png)
![](../statics/Pasted%20image%2020241205221132.png)
![](../statics/Pasted%20image%2020241205221209.png)
![](../statics/Pasted%20image%2020241205221224.png)
![](../statics/Pasted%20image%2020241205221245.png)
![](../statics/Pasted%20image%2020241205221312.png)
![](../statics/Pasted%20image%2020241205221458.png)

![](../statics/Pasted%20image%2020241205221445.png)
![](../statics/Pasted%20image%2020241205221536.png)
![](../statics/Pasted%20image%2020241205221602.png)
![](../statics/Pasted%20image%2020241205221620.png)

![](../statics/Pasted%20image%2020241205221626.png)
![](../statics/Pasted%20image%2020241205221850.png)
![](../statics/Pasted%20image%2020241205222011.png)

### **Difference Between Concurrent and Synchronized Collections in Java**
#### **Synchronized Collections**

1. **Definition:**
    
    - These are thread-safe collections provided in the `java.util` package using synchronized methods or blocks.
2. **Implementation:**
    
    - Achieved by wrapping collections using `Collections.synchronizedXXX()` methods.
        - Examples:
            - `Collections.synchronizedList(new ArrayList<>())`
            - `Collections.synchronizedMap(new HashMap<>())`
3. **Thread-Safety Mechanism:**
    
    - Entire methods or blocks are synchronized, meaning only one thread can access them at a time.
4. **Performance:**
    
    - Relatively slower because of high contention due to the locking mechanism.
5. **Examples:**
    
    - `Vector`
    - `Hashtable`
    - `Collections.synchronizedList()`
    - `Collections.synchronizedMap()`
6. **Iteration:**
    
    - Needs explicit synchronization to avoid `ConcurrentModificationException`.  
        Example:
        
        ```java
        synchronized (list) {
            Iterator<Integer> it = list.iterator();
            while (it.hasNext()) {
                System.out.println(it.next());
            }
        }
        ```
        
#### **Concurrent Collections**

1. **Definition:**
    
    - These are thread-safe collections designed specifically for concurrent access by multiple threads.
2. **Implementation:**
    
    - Provides more fine-grained control with internal optimizations to reduce contention.
3. **Thread-Safety Mechanism:**
    
    - Uses non-blocking algorithms or fine-grained locking mechanisms like segment locking.
4. **Performance:**
    
    - Faster due to reduced contention and better scalability in multi-threaded environments.
5. **Examples:**
    
    - `ConcurrentHashMap`
    - `CopyOnWriteArrayList`
    - `ConcurrentLinkedQueue`
6. **Iteration:**
    
    - Does not require explicit synchronization. Uses fail-safe iterators that allow safe traversal even if the collection is modified during iteration.

---

#### **Key Differences**

| **Feature**                 | **Synchronized Collections**                    | **Concurrent Collections**                        |
| --------------------------- | ----------------------------------------------- | ------------------------------------------------- |
| **Thread-Safety Mechanism** | Locks entire methods or blocks                  | Fine-grained locks or non-blocking mechanisms     |
| **Performance**             | Slower due to high contention                   | Faster and more scalable                          |
| **Iteration**               | Requires manual synchronization                 | Fail-safe iterators for safe concurrent traversal |
| **Examples**                | `Vector`, `Hashtable`, `synchronizedList`, etc. | `ConcurrentHashMap`, `CopyOnWriteArrayList`, etc. |

#### **When to Use:**

- **Synchronized Collections:**  
    Suitable for small-scale applications with simpler synchronization requirements.
    
- **Concurrent Collections:**  
    Ideal for high-concurrency applications where multiple threads need to access and modify the collections simultaneously.
![](../statics/Pasted%20image%2020241205222645.png)
### **Comparable and Comparator in Java**

---

#### **Comparable**

1. **Definition:**
    
    - A built-in interface in Java (`java.lang.Comparable`) used to define the **natural ordering** of objects.
    - The class whose objects are to be compared must implement the `Comparable` interface.
2. **Method:**
    
    - Implements the method:
        
        ```java
        int compareTo(T o);
        ```
        
        Returns:
        - `0` if the objects are equal.
        - Negative value if the current object is less than the specified object.
        - Positive value if the current object is greater than the specified object.
3. **Example:**
    
    ```java
    import java.util.*;
    
    class Student implements Comparable<Student> {
        int id;
        String name;
    
        public Student(int id, String name) {
            this.id = id;
            this.name = name;
        }
    
        @Override
        public int compareTo(Student other) {
            return this.id - other.id; // Sort by id in ascending order
        }
    
        @Override
        public String toString() {
            return id + " - " + name;
        }
    }
    
    public class Main {
        public static void main(String[] args) {
            List<Student> students = new ArrayList<>();
            students.add(new Student(3, "Alice"));
            students.add(new Student(1, "Bob"));
            students.add(new Student(2, "Charlie"));
    
            Collections.sort(students); // Sort using Comparable
            System.out.println(students);
        }
    }
    ```
    

---

#### **Comparator**

1. **Definition:**
    
    - An interface in `java.util` used to define **custom ordering** of objects.
    - The class whose objects are being compared does **not need to implement** this interface. The logic is externalized.
2. **Method:**
    
    - Implements the method:
        
        ```java
        int compare(T o1, T o2);
        ```
        
        Returns:
        - Negative value if `o1` is less than `o2`.
        - Zero if `o1` is equal to `o2`.
        - Positive value if `o1` is greater than `o2`.
3. **Example:**
    
    ```java
    import java.util.*;
    
    class Student {
        int id;
        String name;
    
        public Student(int id, String name) {
            this.id = id;
            this.name = name;
        }
    
        @Override
        public String toString() {
            return id + " - " + name;
        }
    }
    
    public class Main {
        public static void main(String[] args) {
            List<Student> students = new ArrayList<>();
            students.add(new Student(3, "Alice"));
            students.add(new Student(1, "Bob"));
            students.add(new Student(2, "Charlie"));
    
            // Sort by name using Comparator
            Comparator<Student> nameComparator = (s1, s2) -> s1.name.compareTo(s2.name);
    
            Collections.sort(students, nameComparator);
            System.out.println(students);
        }
    }
    ```
    

---

### **Key Differences**

|**Feature**|**Comparable**|**Comparator**|
|---|---|---|
|**Location of Sorting Logic**|Defined within the class itself|Defined externally in a separate class or lambda|
|**Interface Package**|`java.lang.Comparable`|`java.util.Comparator`|
|**Single or Multiple Orders**|Can define only one natural ordering|Can define multiple custom orderings|
|**Method**|`compareTo(Object o)`|`compare(Object o1, Object o2)`|
|**Example Usage**|`Collections.sort(list)`|`Collections.sort(list, comparator)`|

---

#### **When to Use:**

- **Comparable:** Use when a class has a **single natural ordering** (e.g., sorting by `id` in `Student`).
- **Comparator:** Use when you need **multiple sorting criteria** (e.g., sorting by `name`, then by `id`).


![](../statics/Pasted%20image%2020241205230241.png)


## you **cannot reduce the visibility** of a method in a subclass when overriding it in Java. This is because Java enforces the **Liskov Substitution Principle**, ensuring that a subclass can always replace its superclass without breaking functionality.


### **Rules of Visibility in Overriding:**

1. **Visibility Can Be Maintained or Broadened:**
    
    - A subclass can keep the same visibility (`protected`, `public`) or make it more permissive.
    - Example:
        - From `protected` in the parent class to `public` in the child class.
2. **Visibility Cannot Be Reduced:**
    
    - Reducing visibility (e.g., from `public` to `protected` or `private`) is not allowed.
    - Doing so will result in a **compile-time error**.
### **Example of Visibility Rules**

#### Parent Class:

```java
class Parent {
    public void display() {
        System.out.println("Parent display()");
    }
}
```

#### Valid Override (Maintaining or Increasing Visibility):

```java
class Child extends Parent {
    @Override
    public void display() { // Same visibility
        System.out.println("Child display()");
    }
}
```

#### Invalid Override (Reducing Visibility):

```java
class Child extends Parent {
    @Override
    protected void display() { // Compiler Error: Cannot reduce visibility
        System.out.println("Child display()");
    }
}
```

### **Why This Restriction Exists:**

1. **Polymorphism:**
    
    - If a subclass method reduces visibility, it would break polymorphism because the overridden method in the superclass might not be accessible through a superclass reference.
2. **Code Safety:**
    
    - Ensures that subclasses do not accidentally hide functionality that clients of the superclass depend on.

## Variable shadowing
Variable shadowing happens when a **local variable** (inside a method, constructor, or inner class) has the **same name** as a variable in the **outer scope** (like a class field or static variable). The local variable "hides" the outer variable in that specific scope, so when you use the variable's name, it refers to the **local one** instead of the outer one.
```java
class Example {
    int number = 10; // Class variable (outer)

    void show(int number) { // Method parameter shadows the class variable
        System.out.println("Local number: " + number); // Refers to the method parameter
        System.out.println("Outer number: " + this.number); // Refers to the class variable
    }

    public static void main(String[] args) {
        Example obj = new Example();
        obj.show(20); // Passes 20 as the method parameter
    }
}

```


![](../statics/Pasted%20image%2020241206071941.png)
![](../statics/Pasted%20image%2020241206072123.png)
![](../statics/Pasted%20image%2020241206072155.png)

## Covariant types in java
- return type of child class should be same as of parent class or child class of return type of parent class.


![](../statics/Pasted%20image%2020241206073412.png)
![](../statics/Pasted%20image%2020241206073455.png)
![](../statics/Pasted%20image%2020241206073540.png)
![](../statics/Pasted%20image%2020241206073645.png)
![](../statics/Pasted%20image%2020241206073719.png)
![](../statics/Pasted%20image%2020241206073837.png)
![](../statics/Pasted%20image%2020241206073850.png)
![](../statics/Pasted%20image%2020241206073930.png)
![](../statics/Pasted%20image%2020241206074040.png)
![](../statics/Pasted%20image%2020241206074625.png)
![](../statics/Pasted%20image%2020241206074647.png)
![](../statics/Pasted%20image%2020241206074711.png)
![](../statics/Pasted%20image%2020241206075112.png)
### **Method Referencing in Java**

**Method referencing** is a feature introduced in Java 8 that allows you to use methods or constructors as arguments to functional interfaces. It provides a cleaner and more concise way to write lambda expressions when the lambda simply calls an existing method.

---

### **Syntax of Method Reference**

```java
ClassName::methodName
```

Types of method references:

1. **Static method reference** (`ClassName::staticMethod`).
2. **Instance method reference** (`instance::instanceMethod`).
3. **Instance method of an arbitrary object of a particular type** (`ClassName::instanceMethod`).
4. **Constructor reference** (`ClassName::new`).

### **Functional Interfaces**

A **functional interface** in Java is an interface with exactly one abstract method. These are used as the target for lambda expressions and method references.

- Common examples: `Runnable`, `Callable`, `Comparator`, and custom interfaces annotated with `@FunctionalInterface`.

### **Examples**

#### **1. Static Method Reference**

```java
import java.util.function.BiFunction;

class MathUtils {
    public static int add(int a, int b) {
        return a + b;
    }
}

class StaticMethodReference {
    public static void main(String[] args) {
        // Using a lambda expression
        BiFunction<Integer, Integer, Integer> lambdaAdd = (a, b) -> MathUtils.add(a, b);

        // Using a method reference
        BiFunction<Integer, Integer, Integer> methodRefAdd = MathUtils::add;

        System.out.println("Lambda Result: " + lambdaAdd.apply(5, 3)); // Output: 8
        System.out.println("Method Reference Result: " + methodRefAdd.apply(5, 3)); // Output: 8
    }
}
```

---

#### **2. Instance Method Reference**

```java
import java.util.function.Function;

class Greeter {
    public String sayHello(String name) {
        return "Hello, " + name;
    }
}

class InstanceMethodReference {
    public static void main(String[] args) {
        Greeter greeter = new Greeter();

        // Using a lambda expression
        Function<String, String> lambdaGreet = (name) -> greeter.sayHello(name);

        // Using a method reference
        Function<String, String> methodRefGreet = greeter::sayHello;

        System.out.println("Lambda Greeting: " + lambdaGreet.apply("Alice")); // Output: Hello, Alice
        System.out.println("Method Reference Greeting: " + methodRefGreet.apply("Alice")); // Output: Hello, Alice
    }
}
```

---

#### **3. Instance Method of an Arbitrary Object**

```java
import java.util.function.Function;
import java.util.Arrays;

class ArbitraryInstanceMethod {
    public static void main(String[] args) {
        String[] names = {"Charlie", "Alice", "Bob"};

        // Using a lambda expression
        Arrays.sort(names, (a, b) -> a.compareToIgnoreCase(b));

        // Using a method reference
        Arrays.sort(names, String::compareToIgnoreCase);

        System.out.println("Sorted Names: " + Arrays.toString(names)); // Output: [Alice, Bob, Charlie]
    }
}
```

---

#### **4. Constructor Reference**

```java
import java.util.function.Supplier;

class Example {
    public Example() {
        System.out.println("Example instance created!");
    }
}

class ConstructorReference {
    public static void main(String[] args) {
        // Using a lambda expression
        Supplier<Example> lambdaInstance = () -> new Example();

        // Using a constructor reference
        Supplier<Example> constructorRefInstance = Example::new;

        lambdaInstance.get(); // Output: Example instance created!
        constructorRefInstance.get(); // Output: Example instance created!
    }
}
```

---

### **Combining Functional Interface and Method Reference**

```java
@FunctionalInterface
interface Greeting {
    void say(String message);
}

class GreetingUtils {
    public static void greet(String message) {
        System.out.println("Greeting: " + message);
    }
}

class FunctionalInterfaceWithMethodReference {
    public static void main(String[] args) {
        // Using a lambda expression
        Greeting lambdaGreet = (message) -> GreetingUtils.greet(message);

        // Using a method reference
        Greeting methodRefGreet = GreetingUtils::greet;

        lambdaGreet.say("Hello, Lambda!"); // Output: Greeting: Hello, Lambda!
        methodRefGreet.say("Hello, Method Reference!"); // Output: Greeting: Hello, Method Reference!
    }
}
```

![](../statics/Pasted%20image%2020241206075556.png)
![](../statics/Pasted%20image%2020241206080911.png)

![](../statics/Pasted%20image%2020241206081115.png)
![](../statics/Pasted%20image%2020241206081238.png)
![](../statics/Pasted%20image%2020241206081325.png)
![](../statics/Pasted%20image%2020241206081403.png)
![](../statics/Pasted%20image%2020241206081501.png)

## Diamond problem

The **diamond problem** occurs in object-oriented programming when a class inherits from multiple classes (or interfaces) that have methods with the same name, leading to ambiguity about which method the subclass should inherit or invoke. This problem is prominent in languages with multiple inheritance (e.g., C++)

In **Java**, the diamond problem specifically arises in the context of **interfaces with default methods** (introduced in Java 8). Unlike classes, interfaces in Java can now provide a method implementation using the `default` keyword.



![](../statics/Pasted%20image%2020241206081837.png)
![](../statics/Pasted%20image%2020241206081904.png)

![](../statics/Pasted%20image%2020241206082108.png)
![](../statics/Pasted%20image%2020241206082151.png)
![](../statics/Pasted%20image%2020241206082438.png)
![](../statics/Pasted%20image%2020241206082950.png)
 ![](../statics/Pasted%20image%2020241206083212.png)
 ![](../statics/Pasted%20image%2020241206083221.png)
 ![](../statics/Pasted%20image%2020241206083320.png)
 ![](../statics/Pasted%20image%2020241206083527.png)
 T is type of input and R is type of output
![](../statics/Pasted%20image%2020241206083604.png)
![](../statics/Pasted%20image%2020241206083752.png)
![](../statics/Pasted%20image%2020241206083921.png)
![](../statics/Pasted%20image%2020241206083945.png)
no chaining in supplier

## Stream and parallel stream
![](../statics/Pasted%20image%2020241209080251.png)
![](../statics/Pasted%20image%2020241209080539.png)
![](../statics/Pasted%20image%2020241209080644.png)
![](../statics/Pasted%20image%2020241209080659.png)
![](../statics/Pasted%20image%2020241209081014.png)

## Dynamic polymorphism
Dynamic polymorphism in Java is a concept where the method that is going to be executed is determined at **runtime**. It is also known as **runtime polymorphism** or **method overriding**.

### Key Characteristics:

1. **Method Overriding**:
    
    - Occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.
    - The overridden method in the subclass has the same name, return type, and parameters as the method in the superclass.
2. **Decided at Runtime**:
    
    - The method that gets invoked is determined based on the **object type** (not the reference type) at runtime.
3. **Achieved Using Inheritance**:
    
    - Dynamic polymorphism requires a parent-child relationship between classes.
4. **Example**:
    

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal;

        myAnimal = new Dog();
        myAnimal.sound(); // Output: Dog barks

        myAnimal = new Cat();
        myAnimal.sound(); // Output: Cat meows
    }
}
```

### How It Works:

- The reference type (`Animal`) points to different object types (`Dog`, `Cat`).
- At runtime, the JVM determines which method to call based on the actual object type.

### Benefits:

- Promotes flexibility and reusability of code.
- Helps implement **polymorphic behavior**, which is central to object-oriented design.

Cannot implement dynamic polymorphism with instance variable

### **Method Overloading in Java**

**Method overloading** is a feature in Java where multiple methods in the same class have the **same name** but **different parameters**. It is a type of **compile-time polymorphism**, where the method to be called is determined at compile-time.

---

### **Key Characteristics**

1. **Same Name, Different Parameters**:
    
    - Methods must have the same name.
    - Methods must differ in one or more of the following:
        - **Number of parameters**.
        - **Data type of parameters**.
        - **Order of parameters**.
2. **Cannot Differ by Return Type Alone**:
    
    - Changing only the return type is not sufficient for overloading; the parameter list must be different.
3. **Happens in the Same Class**:
    
    - Overloaded methods must belong to the same class or inherit from a superclass.

---

### **Example**

```java
class Calculator {

    // Method with two integer parameters
    int add(int a, int b) {
        return a + b;
    }

    // Method with three integer parameters
    int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method with double parameters
    double add(double a, double b) {
        return a + b;
    }

    // Method with different parameter order
    String add(String a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();

        System.out.println(calc.add(5, 10));         // Output: 15
        System.out.println(calc.add(1, 2, 3));      // Output: 6
        System.out.println(calc.add(2.5, 3.5));     // Output: 6.0
        System.out.println(calc.add("Sum: ", 10));  // Output: Sum: 10
    }
}
```

---

### **Why Use Method Overloading?**

- **Readability**: Methods with the same purpose but different input types can share the same name, improving readability.
- **Code Reusability**: Avoids creating multiple unrelated method names for similar actions.
- **Flexibility**: Allows handling different types and numbers of inputs with the same method name.

---

### **Rules for Method Overloading**

1. The parameter list must be different.
2. Overloading can happen in the same class or in a subclass (via inheritance).
3. Return type alone cannot distinguish overloaded methods.

### **Benefits**

- Enhances code clarity.
- Reduces redundancy by allowing methods to handle different types or numbers of inputs seamlessly.

## Multithreading
![](../statics/Pasted%20image%2020241209082306.png)

![](../statics/Pasted%20image%2020241209082537.png)

## Inner class
![](../statics/Pasted%20image%2020241209083652.png)
### **Inner Classes in Java**

An **inner class** is a class defined **inside another class**. It has access to the members (including private ones) of the outer class. Inner classes are primarily used for logical grouping of classes and better encapsulation.

---

### **Types of Inner Classes**

#### 1. **Member Inner Class**

- A non-static class defined within a class.
- Treated like a member of the outer class, meaning:
    - It can access all members of the outer class (including private).
    - It requires an instance of the outer class to be instantiated.

**Example**:

```java
class OuterClass {
    private String message = "Hello from OuterClass";

    class MemberInnerClass {
        void display() {
            System.out.println(message); // Accessing outer class's private field
        }
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass outer = new OuterClass();
        OuterClass.MemberInnerClass inner = outer.new MemberInnerClass();
        inner.display(); // Output: Hello from OuterClass
    }
}
```

---

#### 2. **Static Nested Class**

- A **static** class defined within a class.
- Behaves like a static member of the outer class:
    - Does not require an instance of the outer class to be instantiated.
    - Cannot access non-static members of the outer class directly.

**Example**:

```java
class OuterClass {
    private static String message = "Hello from Static Nested Class";

    static class StaticNestedClass {
        void display() {
            System.out.println(message); // Accessing static field
        }
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass.StaticNestedClass nested = new OuterClass.StaticNestedClass();
        nested.display(); // Output: Hello from Static Nested Class
    }
}
```

---

#### 3. **Local Inner Class**

- A class defined **inside a method**, **constructor**, or **block**.
- Has access to local variables and parameters of the enclosing method, but only if they are declared as **final** or **effectively final**.
- Useful when the class is needed only within the scope of the method.

**Example**:

```java
class OuterClass {
    void outerMethod() {
        final String message = "Hello from Local Inner Class";

        class LocalInnerClass {
            void display() {
                System.out.println(message); // Accessing final local variable
            }
        }

        LocalInnerClass localInner = new LocalInnerClass();
        localInner.display();
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass outer = new OuterClass();
        outer.outerMethod(); // Output: Hello from Local Inner Class
    }
}
```

---

#### 4. **Anonymous Inner Class**

- A **class without a name**, defined and instantiated in a single step.
- Commonly used when extending a class or implementing an interface for short-term use.
- Ideal for creating simple event listeners or callbacks.

**Example (Interface Implementation)**:

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greeting greet = new Greeting() {
            @Override
            public void sayHello() {
                System.out.println("Hello from Anonymous Inner Class");
            }
        };
        greet.sayHello(); // Output: Hello from Anonymous Inner Class
    }
}
```

**Example (Extending a Class)**:

```java
class Animal {
    void makeSound() {
        System.out.println("Some generic animal sound");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Animal() {
            @Override
            void makeSound() {
                System.out.println("Dog barks");
            }
        };
        dog.makeSound(); // Output: Dog barks
    }
}
```

---

### **Summary Table**

| Type                | Defined Where                    | Access to Outer Class Members | Static Allowed | When to Use                            |
| ------------------- | -------------------------------- | ----------------------------- | -------------- | -------------------------------------- |
| **Member Inner**    | Directly in outer class          | Yes                           | No             | Logical grouping, need outer instance. |
| **Static Nested**   | Directly in outer class          | Only static members           | Yes            | When outer instance is not needed.     |
| **Local Inner**     | Inside a method/block            | Yes (final/effectively final) | No             | Temporary use within a method/block.   |
| **Anonymous Inner** | Inline (usually in method/block) | Yes                           | No             | Quick extension of class/interface.    |

### **`static` Keyword in Java**

The `static` keyword in Java is used for memory management and to define entities that belong to a **class** rather than an instance of the class. It can be applied to **variables**, **methods**, **blocks**, and **nested classes**.

---

### **Features of `static` Keyword**

1. **Class-Level Association**:
    
    - Static members belong to the **class** rather than any specific object.
    - Accessed using the class name directly (though accessing via an object is also possible).
2. **Memory Optimization**:
    
    - A static member is shared among all instances of the class, saving memory.
3. **No Need for Object Creation**:
    
    - Static methods and variables can be accessed without creating an object of the class.

---

### **Usage of `static` Keyword**

#### 1. **Static Variables**

- Also called **class variables**.
- Shared across all objects of the class.
- Changes made to a static variable by one object are visible to all other objects.

**Example**:

```java
class Counter {
    static int count = 0; // Static variable

    Counter() {
        count++; // Increment static variable
    }

    static int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        new Counter();
        new Counter();
        new Counter();
        System.out.println(Counter.getCount()); // Output: 3
    }
}
```

---

#### 2. **Static Methods**

- Belong to the class and can be called without creating an object.
- Cannot access **non-static** members (variables/methods) directly.
- Used for utility or helper methods (e.g., `Math.max()`).

**Example**:

```java
class Utility {
    static int square(int number) {
        return number * number; // Static method
    }
}

public class Main {
    public static void main(String[] args) {
        int result = Utility.square(5); // Call static method without creating an object
        System.out.println(result); // Output: 25
    }
}
```

---

#### 3. **Static Block**

- Used for **initialization** of static variables or any static setup logic.
- Executes **once** when the class is loaded into memory.
- Runs **before the main method**.

**Example**:

```java
class Example {
    static int value;

    static { // Static block
        value = 42; // Initialize static variable
        System.out.println("Static block executed!");
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println("Value: " + Example.value); // Output: Static block executed! Value: 42
    }
}
```

---

#### 4. **Static Nested Class**

- A **static nested class** is a class defined inside another class and marked as `static`.
- It does not require an instance of the outer class to be instantiated.
- Can only access the static members of the outer class.

**Example**:

```java
class Outer {
    static String message = "Hello from Outer";

    static class StaticNested {
        void display() {
            System.out.println(message); // Access static member of outer class
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer.StaticNested nested = new Outer.StaticNested(); // Create instance of static nested class
        nested.display(); // Output: Hello from Outer
    }
}
```

---

### **Key Points to Remember**

1. **Static Variables**:
    
    - Shared among all instances of a class.
    - Initialized only once, at class loading.
2. **Static Methods**:
    
    - Can access only static variables and call other static methods.
    - Cannot use `this` or `super` (since they are related to instance context).
3. **Static Block**:
    
    - Executes once, during class loading.
    - Useful for static initialization.
4. **Static Nested Class**:
    
    - Can access only static members of the enclosing class.
    - Useful when the nested class is logically related to the outer class but does not depend on its instance.

---

### **When to Use `static`**

- When a member logically belongs to the class rather than an instance.
- For utility methods (e.g., `Math` methods, `Collections` methods).
- When you want to share data across all instances of a class (e.g., counters, configuration constants).
In Java, you cannot declare a **top-level class** as `static`. However, you can declare a **nested class** as `static`. Such a class is called a **static nested class**.

### **`abstract` Keyword in Java**

The `abstract` keyword in Java is used to define classes and methods that are **incomplete** or meant to be **implemented later** by subclasses. It provides a way to enforce a blueprint for child classes while allowing polymorphism and shared structure.

---

### **Usage of `abstract` Keyword**

1. **Abstract Classes**:
    
    - Declared with the `abstract` keyword.
    - Cannot be instantiated.
    - Can contain **abstract methods** (methods without a body) and **concrete methods** (methods with a body).
2. **Abstract Methods**:
    
    - Declared with the `abstract` keyword.
    - Does not have a body (implementation).
    - Must be overridden by subclasses.

---

### **Abstract Class**

An **abstract class** serves as a **base class** and may provide:

1. Common functionality (via concrete methods).
2. A contract that must be followed by subclasses (via abstract methods).

**Example**:

```java
abstract class Animal {
    abstract void makeSound(); // Abstract method

    void sleep() { // Concrete method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.makeSound(); // Output: Woof! Woof!
        dog.sleep();     // Output: Sleeping...
    }
}
```

---

### **Abstract Methods**

- Abstract methods define a method signature but no implementation.
- Declared in abstract classes.
- Must be implemented by all non-abstract subclasses.

**Example**:

```java
abstract class Shape {
    abstract void draw(); // Abstract method
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Rectangle();
        shape1.draw(); // Output: Drawing a Circle
        shape2.draw(); // Output: Drawing a Rectangle
    }
}
```

---

### **Key Rules for `abstract`**

1. **Abstract Classes**:
    
    - Cannot be instantiated directly.
    - Can contain both abstract and concrete methods.
    - Can have constructors, static methods, and final methods.
    - Can contain instance variables and static variables.
2. **Abstract Methods**:
    
    - Cannot have a body (no `{}` block).
    - Must be overridden in the first concrete subclass.
    - Can only be declared inside abstract classes.
3. **Subclasses**:
    
    - A subclass must implement all abstract methods of its abstract parent class unless it is also declared abstract.

---

### **Practical Scenarios for `abstract`**

1. **Common Functionality**: Use an abstract class to define common behavior and require specific details from subclasses.
    
2. **Polymorphism**: Abstract classes allow polymorphic behavior where the specific implementation depends on the object type at runtime.
    
3. **Blueprints**: Abstract classes serve as blueprints for related classes with a shared contract.
    

---

### **Difference Between Abstract Class and Interface**

|Feature|Abstract Class|Interface|
|---|---|---|
|**Methods**|Can have abstract and concrete methods|All methods are abstract (before Java 8); can have default and static methods (since Java 8).|
|**Inheritance**|A class can extend only one abstract class|A class can implement multiple interfaces.|
|**Access Modifiers**|Can have any access modifier for methods and fields|All methods are implicitly `public`.|
|**Variables**|Can have instance variables|Can only have `public static final` constants.|
|**Constructor**|Can have constructors|Cannot have constructors.|

---

### **Advantages of `abstract`**

1. **Code Reusability**:
    
    - Common methods in abstract classes reduce code duplication.
2. **Enforce a Contract**:
    
    - Subclasses must follow the rules and implement abstract methods.
3. **Polymorphism**:
    
    - Abstract classes allow dynamic method binding at runtime.
4. **Encapsulation**:
    
    - Abstract classes encapsulate shared functionality.

---

### **Limitations**

1. **Single Inheritance**:
    
    - A class can only extend one abstract class, limiting flexibility compared to interfaces.
2. **Cannot Be Instantiated**:
    
    - Direct use of abstract classes is not possible; they are always meant to be extended.
3. **Complexity**:
    
    - Overuse of abstract classes can make code more complicated and harder to follow.

---

### **When to Use Abstract Classes**

- When you want to provide a **base class** with **common implementation**.
- When you want to enforce a **specific contract** for subclasses while providing some default behavior.
- When single inheritance is sufficient, and the use of multiple inheritance (via interfaces) is not required.
