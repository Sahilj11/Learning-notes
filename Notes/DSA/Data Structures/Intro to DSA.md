### What is Data 
- quantities , character or symbols on which operation are performed by computer , which may be stored 
### Diff b/w data and info
- Info means , data is arranged in systematic way then its gets a structure and become meaningful

### What is DSA
- To provide an appropriate way to structure the data we need to know about DSA
- systematic way to organise data so that it can be used efficiently (both in terms of time and space)
- arrays are example of a data structure
- Some real life example like using stack DSA for creating undo and redo feature or image stored using array of pixels 

## Data types vs Abstract Data types 

### What is data type 
- two imp things 
	- Define certain domain of values
	- Define operation allowed on those values 
	- Eg : int  type 
		- Takes only integer values 
		- Operation : addition , subtraction , multiplication 

### Primitive Data types
Primitive data types are the most basic building blocks for representing simple values in computer programming languages. These data types are predefined by the programming language and have fixed sizes, which allows the computer to allocate memory efficiently. Most programming languages support several common primitive data types. Here are some examples:

1. Integer: Represents whole numbers without a fractional component. It can be signed (both positive and negative values) or unsigned (only positive values). Examples include `int` (commonly 32 bits) and `long` (often 64 bits).

2. Floating-point: Represents numbers with a fractional component. It can be a single-precision floating-point number (`float`), typically 32 bits, or a double-precision floating-point number (`double`), usually 64 bits. These data types are used for handling real numbers and are subject to floating-point arithmetic limitations.

3. Character: Represents a single character, such as a letter, digit, or symbol. In most languages, it's denoted by the `char` data type, which typically uses 8 bits of memory to store one character.

4. Boolean: Represents a binary value that can be either true or false. In many languages, the `bool` data type is used to store Boolean values, with the value `true` representing true and `false` representing false.

5. Byte: Represents a group of 8 bits and is commonly used for memory-efficient storage of small integers or raw data. Some languages have specific `byte` data types, while others represent bytes as small integers.

These primitive data types are directly supported by the hardware and are usually the fastest and most efficient way to store and manipulate simple values. In addition to these standard data types, some programming languages may provide additional data types like `short` and `char` to cater to specific requirements or hardware constraints. It's essential to understand these primitive data types and their properties when working with programming languages, as they form the foundation for more complex data structures and user-defined data types in the language.

### User Defined Data types 
User-defined data types (UDTs) allow programmers to create custom data structures in programming languages. Unlike primitive data types, which are built into the language and have fixed representations and operations, user-defined data types can be tailored to specific requirements and encapsulate multiple data elements into a single entity. These data types are created by the programmer and offer greater flexibility and expressiveness when designing complex data structures.

There are two primary ways to create user-defined data types:

1. Structures: A structure is a composite data type that groups together different variables of different types under a single name. Each variable within the structure is called a "member" or "field." Structs (short for structures) are particularly useful when you need to store related data items with different data types. For example, consider a Point structure that represents a point in a 2D space with x and y coordinates:

```c
struct Point {
    int x;
    int y;
};
```

2. Classes: In object-oriented programming languages, classes are used to create user-defined data types. A class is a blueprint that defines the properties and behaviors of objects. Objects are instances of the class, and they encapsulate data (attributes or properties) and methods (functions or behaviors) that operate on that data. Classes allow you to create more sophisticated data types with data abstraction and encapsulation. Here's an example of a simple class in Python representing a car:

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def get_info(self):
        return f"{self.year} {self.make} {self.model}"
```

In this example, `Car` is a user-defined data type, and objects of the `Car` class can store information about a specific car and provide methods to access and manipulate that data.

User-defined data types are powerful because they allow programmers to model complex real-world entities and their relationships in the code. By encapsulating related data and behaviors into a single entity, UDTs make code more organized, maintainable, and easier to understand. These data types play a fundamental role in object-oriented programming and are essential for building large-scale applications with well-defined structures and data abstractions.

### Abstract data type

Sure! Imagine you have a special box called an "Abstract Data Type" (ADT) that can store different types of toys and has some cool buttons on it. This box works in a special way, and you can only interact with it using those buttons. You don't know what's inside the box or how it's made, but you know it can do some fun things!

The "Abstract Data Type" box has three important parts:

1. **What toys it can store**: This is like the box's rulebook that says, "Hey, I can store toy cars, action figures, and puzzle pieces." So you can't put anything else inside this box.

2. **The cool buttons**: The box has special buttons with labels like "Add a toy," "Take out a toy," and "Look at the top toy." These buttons are the only way you can interact with the toys inside the box.

3. **How the box works**: Now, you don't know exactly how the box stores and organizes the toys inside, but you know that when you press the "Add a toy" button, you can put a toy inside. When you press the "Take out a toy" button, you can remove a toy from the box. And when you press the "Look at the top toy" button, you can see what toy is on top without knowing what other toys are inside.

That's an "Abstract Data Type" for you! It's like having a magical toy box with some buttons, but you only know what the buttons do, not how the box is made or what's inside. It helps you keep your toys organized and allows you to play with them in a specific way.

An Abstract Data Type (ADT) is a theoretical concept in computer science that describes a set of data values and a set of operations that can be performed on those values. It emphasizes the behavior and characteristics of data, rather than the specific implementation details. In other words, an ADT defines what the data type does, not how it does it.

ADTs are a way of defining data structures in a high-level and abstract manner, allowing for better understanding and separation of concerns in software design. They provide a blueprint for creating data types and their associated operations, serving as a contract or interface between the data and the functions that manipulate it.

The primary characteristics of an Abstract Data Type are:

1. Data Representation: ADTs define the data that the data type can hold or represent. This includes the various attributes and properties that make up the data structure.

2. Operations: ADTs specify the operations or functions that can be performed on the data type. These operations define how the data can be manipulated or interacted with.

3. Encapsulation: ADTs encapsulate the data and operations, hiding the implementation details from the outside world. This allows for information hiding and protects the data from direct access or modification.

4. Well-Defined Interface: ADTs have a well-defined interface that separates the external view of the data type from its internal workings. Users of the ADT only need to know how to use the provided operations and don't need to understand how those operations are implemented.

5. Instantiation: ADTs can be instantiated to create concrete objects with specific values. Each instance of an ADT represents a unique occurrence of the data type, and the operations can be performed on these instances.

A classic example of an Abstract Data Type is the Stack. A stack is an ordered collection of elements that follows the Last-In-First-Out (LIFO) principle. The ADT definition for a stack would include the data representation (elements), the operations (push, pop, peek), and the rules that govern its behavior (e.g., the stack cannot be accessed in the middle; elements can only be added or removed from the top).

It's important to note that ADTs are not tied to any specific programming language or implementation. They are a conceptual model that can be implemented in various ways in different programming languages, depending on the specific requirements and performance considerations. In practice, programming languages provide mechanisms, such as classes and interfaces, to create and work with ADTs, allowing developers to apply the principles of abstraction in their software design and development process.

![[Pasted image 20230720112207.png]]
## Why ADT 
![[Pasted image 20230720112348.png]]

### Difference b/w DS and ADT
An Abstract Data Type (ADT) and a data structure are related concepts in computer science, but they have distinct meanings and purposes:

1. **Abstract Data Type (ADT)**:

   - ADT is a theoretical concept or a high-level description of a data type, specifying what data it can hold and what operations can be performed on that data.
   - It defines the behavior and characteristics of the data type without specifying the implementation details.
   - ADTs provide a blueprint for creating data types, encapsulating data and operations, and defining a well-defined interface for interacting with the data type.
   - ADTs are independent of programming languages and can be considered as a mathematical model or a concept that can be implemented in various ways.

2. **Data Structure**:

   - A data structure is a concrete implementation of an ADT in a specific programming language.
   - It involves the actual representation of data in memory and the algorithms used to perform the operations specified in the ADT.
   - Data structures provide the physical realization of the ADT's interface, allowing us to store and organize data efficiently in memory.
   - Examples of data structures include arrays, linked lists, stacks, queues, trees, graphs, and hash tables.

In summary, an ADT is a conceptual description of a data type, focusing on the behavior and interface, while a data structure is the tangible implementation of that ADT in a programming language, dealing with the actual storage and manipulation of data. ADTs provide a high-level view of what a data type should do, while data structures provide the low-level details of how it is achieved in a particular programming environment.

## Advantages of DS
Data structures offer several advantages that make them crucial in computer programming and software development:

1. **Efficient Data Organization**: Data structures allow for efficient organization and storage of data, enabling fast access, retrieval, and manipulation of information. Different data structures are designed to handle specific operations efficiently, leading to improved performance in algorithms and applications.

2. **Optimized Search and Retrieval**: Data structures like binary search trees and hash tables provide fast search and retrieval operations. This is particularly useful when dealing with large datasets or when frequently searching for specific elements.

3. **Memory Management**: Data structures facilitate efficient memory usage. They enable the allocation and deallocation of memory in an organized manner, preventing wastage and fragmentation, which can help improve a program's performance and reduce memory-related errors.

4. **Abstraction and Encapsulation**: Data structures encapsulate data and operations, providing a clear interface for interacting with the data. This abstraction simplifies the code and shields users from the implementation details, making it easier to understand, use, and maintain.

5. **Modularity and Code Reusability**: By using data structures, developers can create reusable components that can be integrated into different parts of the program. This modularity reduces redundant code and promotes code reusability, saving time and effort in the development process.

6. **Scalability and Performance**: Well-designed data structures can handle large and growing datasets efficiently. They enable algorithms to scale better and perform optimally as the data size increases, ensuring that applications can handle real-world scenarios.

7. **Algorithm Design and Analysis**: Data structures play a central role in algorithm design and analysis. They are fundamental building blocks for solving complex computational problems, allowing programmers to devise efficient algorithms for various tasks.

8. **Data Integrity and Security**: Data structures can help maintain data integrity by enforcing certain constraints or rules on the data. For example, a stack ensures that elements are added and removed in a specific order (LIFO), reducing the likelihood of data corruption.

9. **Integration with Libraries and APIs**: Data structures are integrated into many programming libraries and APIs, making it easier for developers to leverage their functionality without having to implement everything from scratch.

10. **Data Visualization and Analysis**: Certain data structures, such as graphs and trees, are used to represent relationships and hierarchical structures in various applications, making data visualization and analysis more intuitive and effective.

In summary, data structures provide a foundation for efficient data management and algorithm design, offering benefits such as improved performance, code reusability, and better organization of data. They are essential tools for any programmer working on developing efficient and scalable software solutions.