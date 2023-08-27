## What is an object 
  
In other words, an object is a software construct that represents a real-world entity, concept, or thing and includes the data associated with it as well as the actions that can be performed on that data. Objects are created based on a blueprint called a class, which defines the structure and behavior of the object.
## Byte code 
- it is cross platform and ends with .class extension 
- ensure cross platform compatibility 
- you can send byte code to a mac and then there JVM can be used to convert it into machine code
## JDK
- java development kit , dev tools that helps us code in java
- it contains 
	- JRE(java runtime env)- contains libraries and toolkits 
		- it contains 
			- JVM(java virtual machine):- runs java program , that convert source code to machine code

## First code 
``` java
public class first {

    public static void main(String[] args){

    }

}
```
- inside first class is main method
```java
System.out.print("Heelo");
```
- for printing on console
- use `println` or `\n` for simulate enter after line
``` java
System.out.print("\Hello\")
```
- to print double quotes
- using `\` for escape character

## Primitive vs reference data type 
In programming, especially in languages like Java, data types can be categorized into two main groups: primitive data types and reference (or non-primitive) data types. These categories dictate how data is stored, accessed, and manipulated in memory.

1. **Primitive Data Types:**
Primitive data types represent basic values and are built into the programming language. They are usually simple, atomic values that directly map to a specific amount of memory. In most programming languages, primitive data types are limited in terms of the range of values they can hold and the operations that can be performed on them. Common primitive data types include:

   - `int`: Represents integer values.
   - `double` and `float`: Represent floating-point (decimal) numbers.
   - `char`: Represents a single character.
   - `boolean`: Represents true or false values.
   - `byte`, `short`, `long`: Different integer types with varying ranges.

Primitive data types are usually stored directly in memory, and operations involving them are often simple and efficient. They have a fixed size, which makes them memory-efficient but limits the range of values they can hold.

Example in Java:
```java
int age = 25;
double pi = 3.14159;
char initial = 'J';
boolean isTrue = true;
```

2. **Reference (Non-Primitive) Data Types:**
Reference data types represent objects or complex data structures that are not stored directly in memory but are instead accessed through references or pointers. These data types can hold a reference to an object's memory location. They include:

   - Objects of classes (instances of user-defined classes).
   - Arrays.
   - Interfaces.
   - Strings (in languages like Java, strings are reference types, not primitives).

Reference data types allow for more complex data structures and can store a wide variety of data. They can be dynamic in size and offer a wider range of operations through methods provided by classes or interfaces.

Example in Java:
```java
String name = "Alice"; // String is a reference data type
int[] numbers = {1, 2, 3, 4}; // Array is a reference data type
ArrayList<String> list = new ArrayList<>(); // ArrayList is a reference data type
```

One key distinction between these two types lies in how they are stored in memory. Primitive data types store the actual value, while reference data types store a reference to the value's location in memory. This difference has implications for memory management, pass-by-value/reference behavior, and the operations that can be performed on the data.

In summary, primitive data types are simple, atomic values with limited operations, while reference data types are used to create complex data structures and objects with more flexibility and functionality.