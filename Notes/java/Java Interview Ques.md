

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

