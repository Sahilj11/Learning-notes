## Types of variable in JAVA

In Java, variables can be categorized into several types based on their scope, usage, and declaration. Here are the main types of variables in Java:

1. **Local Variables**:

   - Declared within a method, constructor, or block.
   - Have limited scope, existing only within the block they are declared in.
   - Must be initialized before use.
   - Example:

   ```java
   public void someMethod() {
       int localVar = 10; // local variable
       // localVar is accessible only within this method
   }
   ```

2. **Instance Variables (Non-Static Variables)**:

   - Belong to an instance of a class and are declared within the class but outside any method, constructor, or block.
   - They are initialized with default values if not explicitly initialized.
   - Exist as long as the object exists.
   - Example:

   ```java
   public class MyClass {
       int instanceVar; // instance variable
       // instanceVar is accessible within any method in this class
   }
   ```

3. **Static Variables (Class Variables)**:

   - Belong to the class rather than any particular instance.
   - Declared with the `static` keyword.
   - Initialized with default values if not explicitly initialized.
   - Commonly used to represent constants or values shared by all instances of the class.
   - Example:

   ```java
   public class MyClass {
       static int staticVar; // static variable
       // staticVar is accessible and shared by all instances of this class
   }
   ```

4. **Final Variables**:

   - Declared using the `final` keyword and can be a local, instance, or static variable.
   - Once initialized, their value cannot be changed.
   - Should be assigned a value either during declaration or within the constructor.
   - Example:

   ```java
   public class MyClass {
       final int finalVar = 100; // final variable
       // finalVar's value cannot be changed once assigned
   }
   ```

5. **Parameters**:
   - Variables that are listed as part of a method's declaration.
   - They receive values when the method is called and act as placeholders for the arguments passed.
   - Local to the method and initialized with the values passed during the method call.
   - Example:
   ```java
   public void someMethod(int parameter) {
       // parameter is a method parameter
       // parameter is accessible and holds the value passed during method invocation
   }
   ```

#### Global variable

In Java, the term "global variable" is often used informally to describe variables that seem to be accessible from anywhere within the program. However, in strict Java terminology, there are no true "global variables" like in some other programming languages. Instead, Java has class-level variables, which can be mistaken for global variables due to their wider accessibility.

NOTE: FOR EXAM DO NOT WRITE THIS , this is just for concept clarity . use keyword global variable here

Class-level variables in Java can be both static and non-static (instance variables). They might be perceived as global within the context of a class because they are accessible to all the methods within that class.

1. **Instance Variables (Non-Static Variables)**:

   - Belong to an instance of a class and are accessible to all non-static methods of that class.
   - Exist as long as the object exists.
   - Example:

   ```java
   public class MyClass {
       int instanceVar; // instance variable
       // instanceVar is accessible within any non-static method in this class
   }
   ```

2. **Static Variables (Class Variables)**:
   - Belong to the class and are shared among all instances (objects) of the class.
   - Accessible by any method in the class, whether static or non-static.
   - Initialized once, and changes made by one instance are reflected in other instances.
   - Example:
   ```java
   public class MyClass {
       static int staticVar; // static variable
       // staticVar is accessible by any method in this class, regardless of being static or non-static
   }
   ```

While these variables might seem globally accessible within the scope of the class, they are not accessible outside the class without an instance of the class (for non-static variables) or without proper access (through the class name) for static variables. This is unlike some languages where global variables can be accessed from any part of the program.

Understanding the scope and accessibility of class-level variables is crucial in Java programming, as it helps maintain data encapsulation and ensures variables are used appropriately within the defined context of a class.

## Object oriented technology

Object-oriented technology (OOT) is a software development paradigm that organizes code and data into reusable and modular structures called objects. It's a widely used approach in modern software development due to its ability to model real-world entities and promote code reusability. Here are some key notes on object-oriented technology:

**Objects and Classes:**

- Objects are instances of classes and represent real-world entities or concepts.
- Classes define the blueprint for creating objects. They specify attributes (data members) and behaviors (methods) that objects of that class will have.

**Encapsulation:**
It is a key concept that emphasizes the bundling of data (attributes or properties) and methods (functions or procedures) that operate on that data into a single unit known as an object. Encapsulation is often described by the phrase "data hiding" and serves several important purposes in OOP:
![](../../../statics/Pasted%20image%2020231106065524.png)

1. **Data Protection:** Encapsulation protects the internal state (data) of an object by making it private or restricted access. This means that the data can only be accessed or modified through well-defined methods, preventing unauthorized or unintended changes to the object's state.

2. **Abstraction:** Encapsulation abstracts the complexities of an object's internal implementation. External code interacting with the object doesn't need to know how the data is stored or manipulated; it only needs to use the provided methods. This simplifies the interaction with objects, making code more understandable and maintainable.

3. **Control and Validation:** By encapsulating data with setter methods, you can control the values assigned to object attributes. This allows you to enforce validation rules and business logic, ensuring that only valid data is stored in the object.

4. **Flexibility and Evolution:** Encapsulation enables you to change the internal implementation of an object without affecting the external code that uses the object's interface. This promotes flexibility and makes it easier to adapt and evolve the software over time.

```java
public class encap {
	public static void main(String[] args) {
		int num1 = 10;
		int num2 = 20;
		System.out.println(sum(num1,num2));
	}
}
static int sum(int num1,int num2){
	return num1 + num2;
}
```

This encapsulation ensures that the internal state of a bank account is protected, abstracted from external code, and controlled through well-defined methods, aligning with the principles of OOP.

**Inheritance:**
Inheritance is another fundamental principle of object-oriented programming (OOP). It enables one class (the subclass or derived class) to inherit the properties (fields and methods) of another class (the superclass or base class). Inheritance allows for the creation of a new class that is a specialized version of an existing class. Here's an explanation of inheritance:

1. **Base and Derived Classes:** Inheritance involves the creation of a relationship between two classes: the base class and the derived class. The base class is the existing class from which properties are inherited, and the derived class is the new class that inherits those properties.

2. **Code Reusability:** Inheritance promotes code reuse by allowing the derived class to inherit and reuse the attributes and behaviors (fields and methods) of the base class. This eliminates the need to redefine common attributes and behaviors in each new class.

3. **Specialization:** The derived class can extend the functionality of the base class by adding new attributes and methods or by modifying existing ones. This allows you to create specialized classes that inherit a common set of features but also have their unique characteristics.

4. **"IS-A" Relationship:** Inheritance represents an "IS-A" relationship between the base and derived classes. For example, if you have a base class called `Vehicle`, a derived class called `Car` "IS-A" vehicle, indicating that a car shares characteristics with a vehicle but may have additional features specific to cars.

5. **Method Overriding:** Inheritance allows the derived class to override (provide its implementation for) methods inherited from the base class. This enables polymorphism, where objects of the derived class can be used interchangeably with objects of the base class.

```java
public class inheritance {
	public static void main(String[] args) {
		Animal.eat();
		Dog.eat();
		Dog.bark();
	}
}
class Animal{
	static void eat(){
		System.out.println("Animal eat");
	}
}
class Dog extends Animal{
	static void bark(){
		System.out.println("Dog barking..");
	}
}
```

**Polymorphism:**
Polymorphism (from Greek, meaning “many forms”) is a feature that allows one interface
to be used for a general class of actions. The specific action is determined by the exact
nature of the situation. Consider a stack (which is a last-in, first-out list). You might have
a program that requires three types of stacks. One stack is used for integer values, one for
floatingpoint values, and one for characters
![](../../../statics/Pasted%20image%2020231106065718.png)

1. **Dynamic Binding:** Polymorphism involves the ability to determine the appropriate method or behavior to execute at runtime rather than at compile time. This is known as dynamic binding or late binding. It allows you to write more flexible and adaptable code.

2. **"Many Forms":** The term "polymorphism" literally means "many forms." It allows objects of different classes that share a common superclass or interface to respond to the same method call in a way that is appropriate for their specific class.

3. **Method Overriding:** In polymorphism, you often use method overriding. This means that a subclass can provide its implementation for a method that is already defined in its superclass. When you call that method on an object of the subclass, the overridden version of the method in the subclass is executed.

4. **"IS-A" Relationship:** Polymorphism is closely related to inheritance. It relies on the "IS-A" relationship between a derived class and its base class. When a class inherits from another class, it "IS-A" type of that superclass, and this allows polymorphic behavior.

5. **Example:** Consider a scenario where you have a base class `Shape` with a method `calculateArea()`. You can have derived classes like `Circle` and `Rectangle` that inherit from `Shape` and override the `calculateArea()` method. When you call `calculateArea()` on a `Shape` object, the appropriate version of the method for the actual object's type (e.g., `Circle` or `Rectangle`) will be executed.

```java

```

**Abstraction:**
Abstraction is a fundamental concept in object-oriented programming (OOP) that focuses on simplifying complex systems by modeling classes, objects, and their behaviors in a way that hides unnecessary details while emphasizing the essential features. Abstraction allows developers to create a high-level view of a system, making it easier to understand, maintain, and work with. Here's an explanation of abstraction:

1. **Hiding Complexity:** Abstraction involves the process of hiding the intricate, lower-level implementation details of an object or class, exposing only the relevant and essential features to the outside world. This simplifies the usage of the object or class, as users don't need to concern themselves with the inner workings.

2. **Creating Models:** Abstraction encourages the creation of abstract models of real-world entities. These models focus on what an object does rather than how it does it. For example, an abstract `Car` class might have methods like `start()`, `stop()`, and `accelerate()`, without detailing the engine or transmission mechanisms.

3. **Defining Interfaces:** Abstraction often involves defining interfaces or abstract classes that specify a set of methods without providing the actual implementation. These interfaces or abstract classes serve as blueprints for concrete classes, ensuring consistency in behavior.

4. **Useful in Large Systems:** In large software systems, abstraction is critical for managing complexity. It allows developers to break down the system into manageable components (classes and objects) that communicate through well-defined interfaces.

5. **Extensibility:** Abstraction facilitates the addition of new features or functionality to a system without affecting existing code. By adhering to a well-defined interface, new classes can be created and integrated seamlessly.

6. **Example:** Consider a banking application. The concept of a bank account can be abstracted as a class with methods like `deposit()`, `withdraw()`, and `getBalance()`. The implementation details of how these methods interact with databases, transactions, and security measures are hidden from the user of the class.

## Diff b/w java and c++

Here's the information presented in a markdown table format for better readability:

| Comparison Index         | C++                                                   | Java                                                                                         |
| ------------------------ | ----------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Platform                 | C++ is platform-dependent.                            | Java is platform-independent.                                                                |
| Mainly used for          | C++ is mainly used for system programming.            | Java is mainly used for application programming.                                             |
| Design Goal              | Designed for systems and applications programming.    | Designed with a goal of being easy to use and accessible to a broader audience.              |
| Goto                     | Supports the goto statement.                          | Java doesn't support the goto statement.                                                     |
| Multiple Inheritance     | Supports inheritance.                                 | Doesn't support inheritance through class but can be achieved by interfaces.                 |
| Operator Overloading     | Supports operator overloading.                        | Doesn't support operator overloading.                                                        |
| Pointers                 | Supports pointers.                                    | Doesn't support pointer internally.                                                          |
| Compiler and Interpreter | Uses compiler only.                                   | Uses both compiler and interpreter.                                                          |
| Call by Value/Reference  | Supports both call by value and call by reference.    | Supports only call by value.                                                                 |
| Structure/Union          | Supports structures and unions.                       | Doesn't support structures and unions.                                                       |
| Thread Support           | Doesn't have built-in support for threads.            | Has built-in thread support.                                                                 |
| Virtual Keyword          | Supports the virtual keyword for function overriding. | Doesn't have a virtual keyword; methods are virtual by default.                              |
| Inheritance Tree         | Creates a new inheritance tree always.                | Uses a single inheritance tree with all classes derived from `Object` class.                 |
| Hardware                 | Nearer to hardware.                                   | Not as interactive with hardware.                                                            |
| Object-oriented          | Object-oriented language.                             | Also an object-oriented language, following a single root hierarchy from `java.lang.Object`. |

The above table summarizes the key differences between C++ and Java in various aspects such as platform support, language features, design goals, and more.

## Message Passing in java

Message Passing in terms of computers is communication between processes. It is a form
of communication used in object-oriented programming as well as parallel programming.
Message passing in Java is like sending an object i.e. message from one thread to another
thread. It is used when threads do not have shared memory and are unable to share monitors
or semaphores or any other shared variables to communicate.

We mostly use Queue to implement communication
between threads.

![](../../../statics/Pasted%20image%2020231106072514.png)

## Binding

- Linking b/w method call and method definition
- Static binding
  - binding which can be resolved at compile time by compiler
  - Also called early binding
  - binding happens before the program actually run
  - eg. Method overloading

```java
class Parent {
    void display() {
        System.out.println("Inside Parent class");
    }
}

class Child extends Parent {
    void display() {
        System.out.println("Inside Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent obj = new Child(); // Parent reference but Child object
        obj.display(); // Static binding - method call is resolved at compile time
    }
}

```

- Dynamic binding
  - When compiler is not able to resolve binding at compile time
  - Also called late binding
  - Binding happens during run time
  - Eg. Method overiding
  -

```java
class Parent {
    void display() {
        System.out.println("Inside Parent class");
    }
}

class Child extends Parent {
    void display() {
        System.out.println("Inside Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent obj = new Child(); // Parent reference but Child object
        obj.display(); // Dynamic binding - method call is resolved at runtime
    }
}

```

## Benefits of OOPS

1. Simplicity: software objects model real world objects, so the complexity is reduced and the program structure is very clear;
2. Modularity: each object forms a separate entity whose internal workings are decoupled from other parts of the system;
3. Modifiability: it is easy to make minor changes in the data representation or theprocedures in an OO program. Changes inside a class do not affect any other part of a program, since the only public interface that the external world has to a class is through the use of methods;
4. Extensibility: adding new features or responding to changing operating environments can be solved by introducing a few new objects and modifying some existing ones;
5. Maintainability: objects can be maintained separately, making locating and fixing problems easier;
6. Re-usability: objects can be reused in different programs

## Application of OOPS

- User interface design such as windows, menu.
- Real Time Systems
- Simulation and Modeling
- Object oriented databases
- AI and Expert System
- Neural Networks and parallel programming

## Data type

![](../../../statics/Pasted%20image%2020231106072634.png)
A variable of primitive type contains a single value of the appropriate size and format for
its type: a number, a character, or a boolean value.

- Integer
  - Java supports four types of integer types: byte, short, int and long. It does not support unsigned types and thereforeall Java values are signed types. This means that they can be positive or negative.

there are also three kinds of non-primitive types in JAVA. They are also termed as reference or derived types. The non-primitive types are: arrays, classes and interfaces. The value of a non-primitive type variable, in contrast to
that of a primitive type, is a reference to (an address of) the value or set of values represented by the variable.

## Java Tokens

The smallest individual units in a program are known as tokens

- Keywords:- Keywords are some reserved words which have some definite meaning. They cannot be used as variable name and they are written in lower-case letter . eg like abstract, new , for , int ,if etc.
- Identifiers :- Java Identifiers are used for naming classes, methods, variables, objects, labels in a program.
- Literals:- Literals are constant value appears directly in the program. Types like string literals , character , bool, int, float etc.

```java
String a = "hello"; // this is a string literal
char b = 'F'; // this is a char literal
```

- Operators
- Separators:- Separators are symbols used to indicate where groups of code are arranged and divided.

```java
{ } Braces
( ) Parentheses
[ ] Brackets
; Semicolon
, Comma
. Period
```

## Operators in java

Operators in Java are special symbols and keywords used to perform operations on variables and values. They are fundamental to any programming language and play a crucial role in Java as well. Here are some common categories of operators in Java:

1. **Arithmetic Operators:**

   - `+` (Addition): Adds two numbers.
   - `-` (Subtraction): Subtracts the right operand from the left operand.
   - `*` (Multiplication): Multiplies two numbers.
   - `/` (Division): Divides the left operand by the right operand.
   - `%` (Modulus): Computes the remainder of dividing the left operand by the right operand.

2. **Relational Operators:**

   - `==` (Equal to): Checks if two values are equal.
   - `!=` (Not equal to): Checks if two values are not equal.
   - `<` (Less than): Checks if the left operand is less than the right operand.
   - `>` (Greater than): Checks if the left operand is greater than the right operand.
   - `<=` (Less than or equal to): Checks if the left operand is less than or equal to the right operand.
   - `>=` (Greater than or equal to): Checks if the left operand is greater than or equal to the right operand.

3. **Logical Operators:**

   - `&&` (Logical AND): Returns true if both operands are true.
   - `||` (Logical OR): Returns true if at least one operand is true.
   - `!` (Logical NOT): Negates the value of the operand.

4. **Assignment Operators:**

   - `=` (Assignment): Assigns the value on the right to the variable on the left.
   - `+=`, `-=`, `*=`, `/=`, `%=` (Compound Assignment): Performs an operation and assigns the result to the left operand.

5. **Increment and Decrement Operators:**

   - `++` (Increment): Increases the value of a variable by 1.
   - `--` (Decrement): Decreases the value of a variable by 1.
   - Can be used as either a prefix (`++i`) or postfix (`i++`) operation, with a difference in behavior when used in expressions.

6. **Bitwise Operators:**

   - `&` (Bitwise AND): Performs a bitwise AND operation.
   - `|` (Bitwise OR): Performs a bitwise OR operation.
   - `^` (Bitwise XOR): Performs a bitwise XOR (exclusive OR) operation.
   - `~` (Bitwise NOT): Inverts the bits of the operand.
   - `<<` (Left Shift): Shifts the bits of the left operand to the left by a specified number of positions.
   - `>>` (Right Shift): Shifts the bits of the left operand to the right by a specified number of positions.

7. **Conditional (Ternary) Operator:**
   - `? :` (Conditional Operator): Evaluates a boolean expression and returns one of two values based on the result.

These are the most commonly used operators in Java. They are essential for performing various operations in Java programs, from simple arithmetic calculations to complex logical and bitwise manipulations

## Java run-time environment

- the Java Runtime Environment (JRE) is a crucial component of the Java platform that enables the execution of Java applications and applets. It provides the necessary runtime support to interpret and execute Java bytecode. Here are key aspects of the Java Runtime Environment:
- java The loader for Java applications. This tool is an interpreter and can interpret the class
  files generated by the javac compiler.
- javac The compiler, which converts source code into Java bytecode
- jar The archiver, which packages related class libraries into a single JAR file.
- javadoc The documentation generator, which automatically generates documentation from
  source code comments
- jdb The Java debugger
- jps The process status tool, which displays process information for current Java processes
- javap The class file disassembler
- jppletviewer This tool can be used to run and debug Java applets without a web browser.
- javah The C header and stub generator, used to write native methods
  In summary, the Java Runtime Environment (JRE) is a critical component of the Java platform that provides the runtime environment and resources necessary for executing Java applications. It ensures platform independence, security, and efficient execution of Java code. Users and developers benefit from the JRE's ability to run Java applications on various systems without modification.

## API

An application programming interface (API) is a computing interface which defines
interactions between multiple software intermediaries. It defines the kinds of calls or
requests that can be made, how to make them, the data formats that should be used, the
conventions to follow, etc.

## casting

- Casting means converting one data type to another
- type
  - Implicit casting:- Happens automatically when converting from a narrower range data type to wide range data type
    - eg. Converting an int to double/float
    - Converting float to double
    - ![](../../../statics/Pasted%20image%2020231106080024.png)
    - ![](../../../statics/Pasted%20image%2020231106080342.png)
    -
  - Explicit casting:- Does not happens automatically , should be done by programmer when converting from wider range data type to narrower range data type
    - Converting from Double to int
    - Converting from double to float
    - ![](../../../statics/Pasted%20image%2020231106080024.png)

## Control statements

Control statements in Java are used to manage the flow of a program's execution. They allow you to make decisions, repeat actions, and execute code conditionally. Java provides several types of control statements:

1. **Conditional Statements:**

   - **if Statement:** Executes a block of code if a specified condition is true. Optionally, an `else` block can be used to specify code to execute when the condition is false.

     ```java
     if (condition) {
         // Code to execute if condition is true
     } else {
         // Code to execute if condition is false
     }
     ```

   - **switch Statement:** Evaluates a variable or expression and allows the program to execute different code blocks based on the value of the variable.
     ```java
     switch (variable) {
         case value1:
             // Code to execute if variable equals value1
             break;
         case value2:
             // Code to execute if variable equals value2
             break;
         // ...
         default:
             // Code to execute if none of the cases match
     }
     ```

2. **Looping Statements:**

   - **for Loop:** Repeats a block of code a specified number of times.

     ```java
     for (initialization; condition; update) {
         // Code to repeat
     }
     ```

   - **while Loop:** Repeats a block of code while a specified condition is true.

     ```java
     while (condition) {
         // Code to repeat
     }
     ```

   - **do-while Loop:** Similar to a `while` loop, but it guarantees that the block of code will execute at least once, as the condition is checked after the block is executed.
     ```java
     do {
         // Code to repeat
     } while (condition);
     ```

3. **Jump Statements:**

   - **break Statement:** Used to exit a loop or switch statement prematurely.

     ```java
     for (int i = 0; i < 5; i++) {
         if (i == 3) {
             break; // Exit the loop when i equals 3
         }
     }
     ```

   - **continue Statement:** Used to skip the current iteration of a loop and proceed to the next iteration.

     ```java
     for (int i = 0; i < 5; i++) {
         if (i == 2) {
             continue; // Skip the iteration when i equals 2
         }
         // Code here is executed for all iterations except when i equals 2
     }
     ```

   - **return Statement:** Exits a method and optionally returns a value to the calling code.
     ```java
     public int add(int a, int b) {
         return a + b; // Exits the method and returns the result
     }
     ```

These control statements in Java allow you to create programs with branching logic, repetition, and the ability to make decisions based on conditions. They are essential for writing complex and flexible software.

## Data types

Java has a rich set of data types that can be categorized into two main categories: primitive data types and reference data types. Here's an overview of the commonly used data types in Java:

**Primitive Data Types:**

1. **byte:** This is an 8-bit signed integer type. It can store values from -128 to 127.

2. **short:** A 16-bit signed integer type with a range from -32,768 to 32,767.

3. **int:** A 32-bit signed integer type. It's commonly used for most integer values in Java.

4. **long:** A 64-bit signed integer type. Use it for very large integer values that cannot be represented by an `int`.

5. **float:** A 32-bit floating-point type. It's suitable for representing decimal numbers with limited precision.

6. **double:** A 64-bit floating-point type. It provides higher precision for floating-point numbers and is commonly used for most decimal values.

7. **char:** A 16-bit Unicode character type. It can store single characters like 'A', '5', or '€'.

8. **boolean:** Represents true or false values. It's used for boolean logic and conditions.

**Reference Data Types:**

9. **Classes:** User-defined data types that represent objects. Objects can have attributes (fields) and methods.

10. **Interfaces:** Similar to classes but represent a contract that classes can implement. They define a set of methods that implementing classes must provide.

11. **Arrays:** Ordered collections of elements of the same type. Arrays can be of primitive types or reference types.
12. **Strings:** Strings in Java are objects, not primitive data types. They represent sequences of characters and are widely used for text manipulation.

Java's strong typing ensures type safety and helps catch type-related errors at compile time. Additionally, Java provides automatic type conversion for some data types (e.g., widening conversions), but explicit casting may be required for others (e.g., narrowing conversions).

## Visibility controls

In Java, access modifiers are used to set the accessibility (visibility) of classes, interfaces, variables, methods, constructors, data members, and the setter methods.

#### Types

- Public
- Private
- Protected
- Default :- declaration visible only within package only
  ![](../../../statics/Pasted%20image%2020230913173824.png)

In Java, accessibility controls or access modifiers are used to specify the visibility or accessibility of classes, methods, fields, and other members within a Java program. There are four main access modifiers in Java:

1. **Public (`public`):** Members marked as `public` are accessible from any other class. There are no restrictions on accessing public members from any package or class.

```java
public class MyClass {
    public int myField;

    public void myMethod() {
        // ...
    }
}
```

2. **Private (`private`):** Members marked as `private` are only accessible within the same class. They cannot be accessed from outside the class, even within the same package.

```java
public class MyClass {
    private int myField;

    private void myMethod() {
        // ...
    }
}
```

3. **Protected (`protected`):** Members marked as `protected` are accessible within the same package and subclasses (even if they are in different packages). However, they are not accessible from unrelated classes outside the package.

```java
package mypackage;

public class MyClass {
    protected int myField;

    protected void myMethod() {
        // ...
    }
}
```

```java
package mypackage;

public class SubClass extends MyClass {
    // Access to protected members is allowed here.
    void anotherMethod() {
        int value = myField; // Accessing the protected field
        myMethod(); // Accessing the protected method
    }
}
```

4. **Default (Package-Private):** If no access modifier is specified (also known as "package-private"), the member is accessible only within the same package. It cannot be accessed from classes outside the package.

```java
package mypackage;

class MyClass {
    int myField;

    void myMethod() {
        // ...
    }
}
```

```java
package anotherpackage;

public class AnotherClass {
    // Cannot access myField or myMethod from MyClass, as they are package-private.
}
```

These access modifiers help you control the visibility and encapsulation of your classes and their members, which is a fundamental aspect of object-oriented programming. They allow you to restrict or expose certain parts of your code to maintain encapsulation, data integrity, and security.

## Class and methods in java

In Java, classes and methods are fundamental building blocks of object-oriented programming. They are used to define the structure and behavior of objects within your program. Let's dive into each concept:

### Classes in Java:

1. **Class Declaration:** A class in Java is a blueprint or template for creating objects. It defines the attributes (fields/variables) and methods (functions) that objects of the class will have.

   ```java
   public class MyClass {
       // Fields (instance variables)
       private int myField;
       private String myString;

       // Constructor
       public MyClass(int field, String string) {
           this.myField = field;
           this.myString = string;
       }

       // Methods
       public void doSomething() {
           System.out.println("Doing something...");
       }
   }
   ```

2. **Fields (Instance Variables):** Fields represent the state or data of an object. They are declared within the class and define the characteristics of objects created from that class.

3. **Constructor:** Constructors are special methods used to initialize objects when they are created. They have the same name as the class and are invoked using the `new` keyword.

4. **Methods:** Methods define the behavior of objects. They can perform various actions and manipulate the object's state. In the example above, `doSomething()` is a method that performs a simple action.

### Methods in Java:

1. **Method Declaration:** A method in Java is defined within a class and specifies its behavior. Methods are invoked on objects of the class.

   ```java
   public void methodName(parameter1Type parameter1, parameter2Type parameter2) {
       // Method body
   }
   ```

   - `public`: Access modifier indicating the method's visibility.
   - `void`: Return type (void means the method doesn't return a value).
   - `methodName`: Name of the method.
   - `parameter1Type`, `parameter2Type`: Parameter types that the method accepts.

2. **Method Parameters:** Methods can accept zero or more parameters, which are values passed into the method for processing.

   ```java
   public void add(int num1, int num2) {
       int result = num1 + num2;
       System.out.println("Sum: " + result);
   }
   ```

3. **Return Type:** Methods may or may not return a value. If they return a value, you specify the data type in place of `void`.

   ```java
   public int multiply(int num1, int num2) {
       return num1 * num2;
   }
   ```

4. **Method Invocation:** To use a method, you invoke it on an object of the class. For example:

   ```java
   MyClass obj = new MyClass(42, "Hello");
   obj.doSomething(); // Invoking the doSomething() method
   int result = obj.multiply(5, 6); // Invoking the multiply() method
   ```

5. **Static Methods:** In addition to instance methods, Java supports static methods, which are associated with the class itself rather than with objects of the class. They are called using the class name.

   ```java
   public static int staticMethod(int num1, int num2) {
       return num1 + num2;
   }
   ```

   ```java
   int result = MyClass.staticMethod(10, 20); // Calling a static method
   ```

Classes and methods are essential for organizing and structuring your Java programs, promoting code reusability, and modeling real-world entities in your software.

## Constructor

In Java, a constructor is a special type of method that is used to initialize objects of a class. Constructors have the same name as the class in which they are defined, and they do not have a return type, not even `void`. They are called automatically when an object of the class is created using the `new` keyword. Constructors are primarily used to set initial values for the object's attributes (fields).

Here's how you declare and use constructors in Java:

```java
public class MyClass {
    // Fields
    private int myField;
    private String myString;

    // Constructor 1: No-argument constructor
    public MyClass() {
        // Initialize fields or perform other setup tasks
        myField = 0;
        myString = "Default";
    }

    // Constructor 2: Parameterized constructor
    public MyClass(int field, String string) {
        // Initialize fields using parameters
        this.myField = field;
        this.myString = string;
    }

    // Other methods and code can be here
}
```

In this example, we have two constructors:

1. **No-argument constructor:** It takes no parameters and is used to create an object with default values. In this case, it initializes `myField` to 0 and `myString` to "Default."

2. **Parameterized constructor:** It takes two parameters (`field` and `string`) and allows you to initialize the object's fields with specific values when you create an object.

You can create objects of the `MyClass` class and use these constructors as follows:

```java
MyClass obj1 = new MyClass();             // Calls the no-argument constructor
MyClass obj2 = new MyClass(42, "Hello");  // Calls the parameterized constructor

System.out.println(obj1.myField); // Outputs 0
System.out.println(obj1.myString); // Outputs "Default"

System.out.println(obj2.myField); // Outputs 42
System.out.println(obj2.myString); // Outputs "Hello"
```

Some important points to remember about constructors in Java:

- If you don't explicitly provide any constructors in your class, Java provides a default no-argument constructor for you. However, once you define any constructor, the default constructor is no longer provided automatically.

- You can overload constructors by defining multiple constructors with different parameter lists. Java will choose the appropriate constructor based on the arguments you provide when creating an object.

- Constructors can have access modifiers (e.g., `public`, `private`, `protected`, or package-private) just like other methods. The access modifier determines where the constructor can be called from.

- Constructors can contain initialization code, setup tasks, or any other logic required to prepare an object for use.

## Inheritance types

In Java, inheritance is a fundamental concept of object-oriented programming (OOP) that allows you to create new classes (derived or subclass) based on existing classes (base or superclass). Inheritance promotes code reusability and establishes a relationship between classes. There are several types of inheritance in Java:

1. **Single Inheritance:**
   Single inheritance refers to a scenario where a class can inherit from only one superclass. In other words, a subclass can have only one immediate parent class.

   ```java
   class Animal {
       void eat() {
           System.out.println("Animal is eating");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Dog is barking");
       }
   }
   ```

2. **Multiple Inheritance (Interface-based):**
   Java does not support multiple inheritance of classes, meaning a class cannot inherit from multiple classes simultaneously. However, Java supports multiple inheritance through interfaces, where a class can implement multiple interfaces.

   ```java
   interface Swimmer {
       void swim();
   }

   interface Flyer {
       void fly();
   }

   class Bird implements Swimmer, Flyer {
       public void swim() {
           System.out.println("Bird is swimming");
       }

       public void fly() {
           System.out.println("Bird is flying");
       }
   }
   ```

3. **Multilevel Inheritance:**
   Multilevel inheritance refers to a scenario where a class extends another class, which, in turn, extends another class, forming a chain of inheritance.

   ```java
   class Grandparent {
       void method1() {
           System.out.println("Grandparent's method");
       }
   }

   class Parent extends Grandparent {
       void method2() {
           System.out.println("Parent's method");
       }
   }

   class Child extends Parent {
       void method3() {
           System.out.println("Child's method");
       }
   }
   ```

4. **Hierarchical Inheritance:**
   Hierarchical inheritance occurs when multiple subclasses inherit from a single superclass. Each subclass has its own behavior and can add additional methods or properties to the inherited ones.

   ```java
   class Animal {
       void eat() {
           System.out.println("Animal is eating");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Dog is barking");
       }
   }

   class Cat extends Animal {
       void meow() {
           System.out.println("Cat is meowing");
       }
   }
   ```

5. **Hybrid Inheritance (Rare):**
   Hybrid inheritance is a combination of two or more types of inheritance mentioned above. It can be achieved by mixing single, multiple, multilevel, or hierarchical inheritance as needed. However, it's relatively complex and can lead to issues like the diamond problem in multiple inheritance scenarios.

   Java avoids the diamond problem by not allowing multiple inheritance of classes but permits it through interfaces.

6. **Cyclic Inheritance (Prohibited):**
   Cyclic inheritance occurs when classes form a circular reference in their inheritance hierarchy. Java prohibits cyclic inheritance as it leads to ambiguity and potential issues.

   ```java
   class A extends B {
       // ...
   }

   class B extends A {
       // ...
   }
   ```

Java's inheritance mechanism ensures code reusability while avoiding some of the complexities and ambiguities associated with multiple inheritance. Instead of multiple inheritance of classes, Java encourages the use of interfaces to achieve similar goals.

## Abstract class

In Java, an abstract class is a class that cannot be instantiated on its own(cannot make instance of it , meaning cant create a object) but serves as a blueprint for other classes. Abstract classes are used to define a common interface or structure that multiple related classes must adhere to. They allow you to declare methods that have no implementation in the abstract class, which must be implemented by concrete (non-abstract) subclasses. Abstract classes are defined using the `abstract` keyword.

Here are some key characteristics and uses of abstract classes in Java:

1. **Abstract Method:** An abstract class can declare abstract methods (methods without a body) by using the `abstract` keyword for the method declaration. Abstract methods define a contract that concrete subclasses must follow by providing an implementation for these methods.

   ```java
   abstract class Shape {
       abstract void draw(); // Abstract method with no implementation
   }
   ```

2. **Concrete Methods:** Abstract classes can also contain concrete methods (methods with an implementation) that can be inherited by concrete subclasses. These methods provide shared behavior that is common to all subclasses.

   ```java
   abstract class Animal {
       void eat() {
           System.out.println("Animal is eating");
       }
   }
   ```

3. **Cannot Be Instantiated:** Abstract classes cannot be instantiated directly with the `new` keyword. You must create concrete subclasses that provide implementations for the abstract methods to create objects.

   ```java
   class Circle extends Shape {
       void draw() {
           System.out.println("Drawing a circle");
       }
   }
   ```

4. **Inheritance:** Subclasses of abstract classes must implement all the abstract methods declared in the abstract class. Failing to do so will result in a compilation error.

   ```java
   class Rectangle extends Shape {
       void draw() {
           System.out.println("Drawing a rectangle");
       }
   }
   ```

5. **Useful for Creating Hierarchies:** Abstract classes are often used to create class hierarchies, where the abstract class defines common behavior and attributes, while concrete subclasses provide specific implementations.

6. **Mixing Abstract and Concrete Methods:** Abstract classes can contain a mix of abstract and concrete methods, allowing you to provide default implementations for some methods while requiring subclasses to implement others.

Here's an example of how you might use an abstract class in Java:

```java
abstract class Shape {
    abstract void draw(); // Abstract method

    void resize() {
        System.out.println("Resizing the shape");
    }
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle extends Shape {
    void draw() {
        System.out.println("Drawing a rectangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        Shape rectangle = new Rectangle();

        circle.draw(); // Calls the draw method in Circle
        circle.resize(); // Calls the resize method in Shape

        rectangle.draw(); // Calls the draw method in Rectangle
        rectangle.resize(); // Calls the resize method in Shape
    }
}
```

In this example, the `Shape` abstract class defines an abstract method `draw()` that both `Circle` and `Rectangle` concrete subclasses must implement. The `resize()` method provides a default implementation that can be inherited by subclasses.

## Interface in java

In Java, an interface is a blueprint for a class that defines a set of abstract methods that must be implemented by any concrete class (a class that is not abstract) that declares to implement the interface. An interface specifies a contract that the implementing class must adhere to, ensuring that certain methods are available for use in objects of that class. In addition to abstract methods, interfaces can also include constants (static final fields) and default methods with implementations.

Variables declared inside of interface declarations are implicitly final and static, meaning
they cannot be changed by the implementing class.

### Default methods in interface

A default method lets you define a default implementation for an interface method. In other words, by use of a default method, it is now possible for an interface method to provide a body, rather than being abstract. During its development, the default method was also referred to as an extension method, and you will likely see both terms used.

```java
public interface MyIF {
// This is a "normal" interface method declaration.
// It does NOT define a default implementation.
int getNumber();
// This is a default method. Notice that it provides
// a default implementation.
default String getString() {
      return "Default String";
  }
}
```

### Static methods in interface

JDK 8 added another new capability to interface: the ability to define one or more static
methods. Like static methods in a class, a static method defined by an interface can be
called independently of any object. Thus, no implementation of the interface is necessary,
and no instance of the interface is required, in order to call a static method. Instead, a static
method is called by specifying the interface name, followed by a period, followed by the
method name.

```java
public interface MyIF {
// This is a "normal" interface method declaration.
// It does NOT define a default implementation.
  int getNumber();
// This is a default method. Notice that it provides
// a default implementation.
  default String getString() {
     return "Default String";
  }
// This is a static interface method.
  static int getDefaultNumber() {
      return 0;
   }
}
```

InterfaceName.staticMethodName
`int defNum = MyIF.getDefaultNumber();`

### Here are the key features and uses of interfaces in Java:

1. **Declaring an Interface:**
   An interface is declared using the `interface` keyword, followed by the interface name.

   ```java
   interface MyInterface {
       void abstractMethod(); // Abstract method (no method body)
       int CONSTANT_VALUE = 42; // Constant (static final field)

       default void defaultMethod() {
           // Default method with an implementation
           System.out.println("Default implementation of defaultMethod");
       }
   }
   ```

2. **Implementing an Interface:**
   To implement an interface, a class uses the `implements` keyword in its class declaration and provides implementations for all the abstract methods declared in the interface.

   ```java
   class MyClass implements MyInterface {
       @Override
       public void abstractMethod() {
           // Implementation of abstractMethod
           System.out.println("Implementing abstractMethod");
       }
   }
   ```

3. **Multiple Interface Implementation:**
   A class can implement multiple interfaces, separated by commas, allowing it to inherit the abstract methods and constants from all the implemented interfaces.

   ```java
   class AnotherClass implements MyInterface, AnotherInterface {
       // Implement abstract methods from MyInterface and AnotherInterface
   }
   ```

4. **Using Constants:** Interfaces can define constants, which are implicitly `public`, `static`, and `final`. These constants can be accessed using the interface name.

   ```java
   int value = MyInterface.CONSTANT_VALUE;
   ```

5. **Marker Interfaces:** Some interfaces in Java do not declare any methods; they are known as marker interfaces. Marker interfaces are used to indicate a capability or property of an implementing class. For example, the `Serializable` interface is a marker interface in Java.

   ```java
   import java.io.Serializable;

   class MySerializableClass implements Serializable {
       // Class implementation
   }
   ```

Interfaces are an essential part of Java's design for achieving multiple inheritance-like behavior, encapsulating contracts, and enabling polymorphism through shared method signatures. They provide a powerful mechanism for defining common behavior that can be implemented by various classes.

#### Interface inheritance

In Java, interface inheritance refers to the ability of one interface to inherit or extend another interface. This allows you to create a new interface that builds upon the definitions in an existing interface, adding new method signatures or constants. Interface inheritance promotes code reuse and helps create a more organized and modular codebase. Java supports multiple interface inheritance, meaning a class can implement multiple interfaces.

Here's how interface inheritance works in Java:

### Extending Interfaces:

You can extend one interface from another using the `extends` keyword. The child interface inherits all the method signatures (abstract methods) and constants (static final fields) from the parent interface. The child interface can also declare additional methods or constants.

```java
interface ParentInterface {
    void method1();
    void method2();
}

interface ChildInterface extends ParentInterface {
    void method3(); // Additional abstract method
    int CONSTANT_VALUE = 42; // Additional constant
}
```

In this example, `ChildInterface` extends `ParentInterface`, inheriting `method1()` and `method2()` from the parent interface while adding `method3()` and a new constant `CONSTANT_VALUE`.

### Implementing Interfaces:

When a class implements an interface that extends another interface, it is required to provide implementations for all the methods declared in both the parent and child interfaces.

```java
class MyClass implements ChildInterface {
    @Override
    public void method1() {
        // Implementation for method1
    }

    @Override
    public void method2() {
        // Implementation for method2
    }

    @Override
    public void method3() {
        // Implementation for method3
    }
}
```

In this example, `MyClass` implements `ChildInterface`, so it must provide implementations for `method1()`, `method2()`, and `method3()`. If `ChildInterface` had inherited from multiple parent interfaces, `MyClass` would need to provide implementations for all the methods declared in those interfaces as well.

### Multiple Interface Inheritance:

Java allows a class to implement multiple interfaces, each of which can extend other interfaces. This provides a flexible way to build complex class hierarchies and reuse code from multiple sources.

```java
interface InterfaceA {
    void methodA();
}

interface InterfaceB {
    void methodB();
}

interface InterfaceC extends InterfaceA, InterfaceB {
    void methodC();
}

class MyClass implements InterfaceC {
    @Override
    public void methodA() {
        // Implementation for methodA
    }

    @Override
    public void methodB() {
        // Implementation for methodB
    }

    @Override
    public void methodC() {
        // Implementation for methodC
    }
}
```

In this example, `InterfaceC` extends both `InterfaceA` and `InterfaceB`, and `MyClass` implements `InterfaceC`. `MyClass` must provide implementations for all methods from all three interfaces.

Interface inheritance in Java helps you create modular and extensible code by allowing you to define new interfaces that build upon existing ones. It promotes code reuse and the implementation of common behaviors across classes.

### Difference b/w Interface and classes

You cannot instantiate an interface.
•An interface does not contain any constructors.
•All of the methods in an interface are abstract.
•An interface cannot contain instance fields. The only fields that can appear in an
interface must be declared both static and final.
•An interface is not extended by a class; it is implemented by a class.
•An interface can extend multiple interfaces.
to implement an interface, a class must create the complete set of methods
defined by the interface.

## Overriding and Overloading (example of polymorphism )

In Java, overloading and overriding are two fundamental concepts related to methods in object-oriented programming. They are used to define and manipulate behaviors of classes and their methods. Let's explore each concept:

### Method Overloading:

Method overloading refers to the ability to define multiple methods in the same class with the same name but different parameter lists (i.e., a different number or type of parameters). The compiler determines which method to call based on the method's signature, which includes the method name and parameter types.

Key points about method overloading:

1. Method overloading is determined at compile time, also known as compile-time polymorphism or static polymorphism.

2. Overloaded methods have the same name within the same class.

3. Overloaded methods must have different parameter lists, which can differ in the number, type, or order of parameters.

Here's an example of method overloading:

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

In this example, the `Calculator` class has two `add` methods with different parameter types (`int` and `double`). Depending on the argument types when calling the `add` method, the appropriate version will be executed.

### Method Overriding:

Method overriding is a concept used in inheritance when a subclass provides a specific implementation of a method that is already defined in its superclass. The overriding method in the subclass must have the same method signature (method name, return type, and parameter types) as the method in the superclass.

Key points about method overriding:

1. Method overriding is determined at runtime, also known as runtime polymorphism or dynamic polymorphism.

2. Overriding methods have the same name, return type, and parameter types as the method they override in the superclass.

3. The `@Override` annotation is used to indicate that a method is intended to override a superclass method. This annotation helps catch errors at compile time if there is a mismatch in method signatures.

Here's an example of method overriding:

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a generic sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}
```

In this example, the `Dog` class overrides the `makeSound` method inherited from the `Animal` class. When you call `makeSound` on a `Dog` object, the overridden method in the `Dog` class will execute, providing a specific implementation.

To summarize, overloading involves defining multiple methods with the same name in the same class but with different parameter lists, while overriding involves providing a specific implementation of a method in a subclass that has the same signature as the method in the superclass. Both concepts are essential for creating flexible and extensible object-oriented code.

## Using Final in context of overriding and Inheritance

In Java, the `final` keyword has different implications for classes and methods in the context of inheritance.

1. **Final Class**: When a class is declared as `final`, it means that it cannot be subclassed or extended. It prevents other classes from inheriting from it. For instance:

```java
final class Parent {
    // Class implementation
}
// This won't be allowed since Parent is final
class Child extends Parent {
    // Class implementation
}
```

2. **Final Method**: When a method is declared as `final` within a class, it means that the method cannot be overridden by any subclass that might inherit from this class. For example:

```java
class Parent {
    public final void display() {
        // Method implementation
    }
}

class Child extends Parent {
    // Trying to override the final method will result in a compilation error
    // This is not allowed because the display() method in Parent is final
    public void display() {
        // Method implementation
    }
}
```

In summary, the `final` keyword, when used with a class, prevents inheritance, while when used with a method, it prevents that particular method from being overridden in any subclass.

This is particularly useful when you want to ensure that a specific class should not be extended or when a method within a class should not be altered or customized by its subclasses, maintaining the intended functionality.
