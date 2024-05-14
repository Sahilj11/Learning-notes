# Unit 1
Here are some notes on the topics you mentioned:
testing 
1. **Features of Python**:
   - Interpreted: Python code is executed line by line, making debugging easier.
   - High-level Language: Python abstracts many low-level details, making it easy to read and write.
   - Dynamically Typed: Variables in Python do not require explicit declaration of data types.
   - Object-Oriented: Python supports object-oriented programming paradigms.
   - Extensive Standard Library: Python comes with a large set of modules and libraries for various tasks.
   - Portable: Python code can run on various platforms with minimal or no modifications.

2. **Python Identifiers**:
   - Identifiers are names given to entities like variables, functions, classes, etc.
   - Rules for naming identifiers:
     - Must start with a letter (a-z, A-Z) or underscore (_).
     - Can be followed by letters, digits (0-9), or underscores.
     - Case sensitive.

3. **Python Character Set**:
   - Python supports Unicode characters, allowing for internationalization and localization.

4. **Keywords and Indentation**:
   - Keywords are reserved words that have special meanings in Python.
   - Examples: `if`, `else`, `for`, `while`, `def`, `class`, etc.
   - Indentation is crucial in Python for defining code blocks.
   - Consistent indentation (usually four spaces) is used to define blocks of code.

5. **Comments**:
   - Comments in Python start with the `#` symbol and extend until the end of the line.
   - Used for documentation and making code more understandable.

6. **Command Line Arguments**:
   - Python provides access to command line arguments via the `sys.argv` list.
   - Modules like `argparse` can also be used for more complex argument parsing.

7. **Assignment Operator**:
   - The assignment operator (`=`) is used to assign a value to a variable.

8. **Operators and Expressions**:
   - Python supports various operators like arithmetic, logical, bitwise, etc.
   - Expressions are combinations of values and operators that can be evaluated to produce a result.

9. **print() Function**:
   - Used to display output to the console.
   - Accepts multiple arguments and can format output using string formatting.

10. **input() Function**:
    - Used to accept user input from the console.
    - Returns a string.

11. **eval() Function**:
    - Evaluates a Python expression from a string and returns the result.

12. **Python Data Types**:
    - Includes integer (`int`), floating-point (`float`), complex numbers (`complex`), etc.
    - Python supports dynamic typing, so variables can hold different types of data.

13. **Variables**:
    - Names given to memory locations to store values.
    - Variables can be reassigned to different data types.

14. **Mutable vs Immutable variables**:
    - Mutable objects can be changed after creation (e.g., lists).
    - Immutable objects cannot be changed after creation (e.g., tuples, strings).

15. **Namespaces**:
    - Containers for mapping names to objects.
    - Help avoid naming conflicts and provide modularity.

16. **Decision Statements**:
    - Boolean Type: Represents the two truth values `True` and `False`.
    - Boolean Operators: `and`, `or`, `not`.
    - if statement: Executes a block of code if a condition is true.
    - else statement: Executes a block of code if the `if` condition is false.
    - Nested Conditionals Statements: `if` statements inside other `if` or `else` blocks.
    - Multi-way Decision Statements (`elif` statement): Used when there are multiple conditions to check.
## Namespace and Operators
Certainly, here are more detailed notes on namespaces and operators:

### Namespaces:

- **Definition**:
  - A namespace is a container for mapping names to objects in Python.
  - It helps avoid naming conflicts and provides a way for organizing code in a hierarchical manner.

- **Types of Namespaces**:
  1. **Local Namespace**: Associated with a particular function or method. Created when the function is called and destroyed when the function exits.
  2. **Global Namespace**: Associated with the entire script or module. Created when the program starts and destroyed when it terminates.
  3. **Built-in Namespace**: Contains built-in functions and exceptions provided by Python.

- **Accessing Namespaces**:
  - Namespaces can be accessed using the dot (`.`) operator.
  - Example: `math.pi` accesses the `pi` constant from the `math` module.

- **Modifying Namespaces**:
  - Namespaces can be modified by adding, modifying, or deleting attributes.
  - Example: `namespace.attribute = value` adds an attribute to the namespace.

- **Importing Namespaces**:
  - `import` statement is used to import namespaces (modules) into the current namespace.
  - Example: `import math` imports the `math` module.

- **Scoping Rules**:
  - Python follows the LEGB (Local, Enclosing, Global, Built-in) rule for resolving names.
  - Names are searched in the local namespace first, then in enclosing functions, followed by global and built-in namespaces.

### Operators and Expressions:

- **Arithmetic Operators**:
  - Addition `+`, Subtraction `-`, Multiplication `*`, Division `/`, Floor Division `//`, Modulus `%`, Exponentiation `**`.

- **Comparison Operators**:
  - Equal to `==`, Not equal to `!=`, Greater than `>`, Less than `<`, Greater than or equal to `>=`, Less than or equal to `<=`.

- **Logical Operators**:
  - Logical AND `and`, Logical OR `or`, Logical NOT `not`.

- **Bitwise Operators**:
  - Bitwise AND `&`, Bitwise OR `|`, Bitwise XOR `^`, Bitwise NOT `~`, Left Shift `<<`, Right Shift `>>`.

- **Assignment Operators**:
  - Assign `=`, Add and Assign `+=`, Subtract and Assign `-=`, Multiply and Assign `*=`, etc.

- **Identity Operators**:
  - `is`: Returns `True` if both variables point to the same object.
  - `is not`: Returns `True` if both variables do not point to the same object.

- **Membership Operators**:
  - `in`: Returns `True` if a sequence contains a specified value.
  - `not in`: Returns `True` if a sequence does not contain a specified value.

- **Operator Precedence**:
  - Operators with higher precedence are evaluated first.
  - Parentheses `()` can be used to change the default precedence.

- **Expressions**:
  - A combination of values, variables, and operators that can be evaluated to produce a result.
  - Example: `2 + 3 * 4` is an expression that evaluates to `14`.

# Unit 2
Sure, here's a revision with code and definitions:

### While Loop:
```python
# While loop example
x = 0
while x < 5:  # Definition: Executes a block of code as long as the condition is True.
    print(x)
    x += 1
```

### range() Function:
```python
# Using range() function
for i in range(5):  # Definition: Generates a sequence of numbers.
    print(i)
```

### For Loop:
```python
# For loop example
for i in range(5):  # Definition: Iterates over a sequence (e.g., list, tuple) or other iterable objects.
    print(i)
```

### Nested Loops:
```python
# Nested loops example
for i in range(3):  # Definition: A loop inside another loop.
    for j in range(2):
        print(i, j)
```

### Infinite Loop:
```python
# Infinite loop example
while True:  # Definition: A loop that runs indefinitely until stopped manually or by a break statement.
    print("This is an infinite loop")
    break
```

### Break Statement:
```python
# Break statement example
for i in range(10):  # Definition: Terminates the loop prematurely.
    if i == 5:
        break
    print(i)
```

### Continue Statement:
```python
# Continue statement example
for i in range(5):  # Definition: Skips the rest of the code inside the loop for the current iteration.
    if i == 3:
        continue
    print(i)
```

### Pass Statement:
```python
# Pass statement example
for i in range(5):  # Definition: Placeholder statement that does nothing.
    pass  # Placeholder for future code
```

### Introduction to Strings:
```python
# String declaration
string_variable = "Hello, World!"  # Definition: A sequence of characters, enclosed within single (' ') or double (" ") quotes.
```

### String Operations: Indexing and Slicing:
```python
# String indexing
print(string_variable[0])  # Prints 'H'
# String slicing
print(string_variable[7:])  # Prints 'World!'
```

### Lists:
```python
# List declaration
my_list = [1, 2, 3, 4, 5]  # Definition: An ordered and mutable collection of items.
```

### Operations on List: Slicing:
```python
# List slicing
print(my_list[1:3])  # Prints [2, 3]
```

### In-built Functions for Lists:
```python
# List functions
print(len(my_list))  # Length of list
print(max(my_list))  # Maximum value in list
print(min(my_list))  # Minimum value in list
print(sum(my_list))  # Sum of values in list
```

### List Processing: Searching and Sorting:
```python
# Searching in list
if 3 in my_list:  # Definition: Checks if a value is present in the list.
    print("Found")
# Sorting list
my_list.sort()  # Definition: Sorts the elements of a list in ascending order.
print(my_list)
```

### Dictionaries: Need of Dictionary:
```python
# Dictionary declaration
my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}  # Definition: A collection of key-value pairs, where each key must be unique.
```

### Operations on Dictionaries: Creation, Addition, Retrieving Values, Deletion:
```python
# Accessing values in dictionary
print(my_dict['name'])  # Prints 'John'
# Adding new key-value pair
my_dict['gender'] = 'Male'  # Definition: Adds a new key-value pair to the dictionary.
# Deleting key-value pair
del my_dict['age']  # Definition: Removes a key-value pair from the dictionary.
```

### Tuples, operations on Tuples, Inbuilt Functions for Tuples:
```python
# Tuple declaration
my_tuple = (1, 2, 3, 4, 5)  # Definition: An ordered and immutable collection of items.
# Accessing values in tuple
print(my_tuple[2])  # Prints 3
# Tuple functions
print(len(my_tuple))  # Length of tuple
print(max(my_tuple))  # Maximum value in tuple
print(min(my_tuple))  # Minimum value in tuple
```

### Introduction to Sets, operations on sets:
```python
# Set declaration
my_set = {1, 2, 3, 4, 5}  # Definition: A collection of unique and unordered items.
# Set operations
print(3 in my_set)  # Checks if 3 is in the set
my_set.add(6)  # Adds 6 to the set
my_set.remove(2)  # Removes 2 from the set
```
## Some operations
Sure, here are 5 common operation methods for each data type:

### Set:
1. `add(element)`: Adds a single element to the set.
2. `remove(element)`: Removes the specified element. Raises an error if the element is not found.
3. `union(other_set)`: Returns a new set containing all unique elements from both sets.
4. `intersection(other_set)`: Returns a new set containing common elements from both sets.
5. `clear()`: Removes all elements from the set.

### Tuple:
1. `count(element)`: Returns the number of occurrences of `element` in the tuple.
2. `index(element)`: Returns the index of the first occurrence of `element` in the tuple.
3. No other methods can modify the tuple as tuples are immutable.
   
### List:
1. `append(element)`: Adds `element` to the end of the list.
2. `remove(element)`: Removes the first occurrence of `element`.
3. `sort()`: Sorts the list in ascending order.
4. `reverse()`: Reverses the order of elements in the list.
5. `pop([index])`: Removes and returns the element at `index`. If `index` is not provided, removes and returns the last element.

### Dictionary:
1. `keys()`: Returns a view object containing the keys of the dictionary.
2. `values()`: Returns a view object containing the values of the dictionary.
3. `items()`: Returns a view object containing the key-value pairs of the dictionary.
4. `update(other_dict)`: Updates the dictionary with key-value pairs from `other_dict`.
5. `clear()`: Removes all elements from the dictionary.

### String:
1. `upper()`: Converts all characters in the string to uppercase.
2. `lower()`: Converts all characters in the string to lowercase.
3. `replace(old, new)`: Replaces all occurrences of `old` with `new`.
4. `split(sep)`: Splits the string into a list of substrings using `sep` as the delimiter.
5. `join(iterable)`: Joins elements of `iterable` into a single string, using the string as the separator.

These methods represent common operations used with each data type in Python.

## Functions
function is a block of reusable code that performs a specific task. Functions allow you to break down your code into smaller, manageable units, making it easier to organize, maintain, and reuse your code
### Inbuilt 
1. **print()**: This function is used to print the specified message or variable to the standard output (usually the console).

```python
print("Hello, world!")
```

2. **len()**: This function returns the length (the number of items) of an object such as a string, list, tuple, dictionary, etc.

```python
my_list = [1, 2, 3, 4, 5]
print(len(my_list))  # Output: 5
```

3. **type()**: This function returns the type of the specified object.

```python
x = 5
print(type(x))  # Output: <class 'int'>
```

4. **abs()**: This function returns the absolute value of a number. For integers and floats, it returns the positive value without any sign.

```python
print(abs(-10))  # Output: 10
print(abs(-3.14))  # Output: 3.14
```

5. **range()**: This function generates a sequence of numbers within a specified range.

```python
print(list(range(5)))  # Output: [0, 1, 2, 3, 4]
print(list(range(1, 6)))  # Output: [1, 2, 3, 4, 5]
print(list(range(0, 10, 2)))  # Output: [0, 2, 4, 6, 8]
```

### Lambda 
A lambda function in Python is a small anonymous function that can have any number of arguments but only one expression. Lambda functions are often used when you need a short function for a short period of time, typically to be used as an argument to higher-order functions (functions that take other functions as arguments). 

Lambda functions are defined using the `lambda` keyword, followed by a comma-separated list of arguments (if any), then a colon `:`, and finally the expression to be evaluated. The result of the expression is implicitly returned.

Syntax:
```
lambda arguments: expression
```

Here's an example of a lambda function that calculates the square of a number:

```python
square = lambda x: x * x
print(square(5))  # Output: 25
```

Lambda functions are often used in conjunction with functions like `map()`, `filter()`, and `sorted()` to apply a simple operation to each element of a sequence or filter elements based on a condition.

Example using `map()` to apply the lambda function to a list of numbers:

```python
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x * x, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

Example using `filter()` to filter even numbers from a list:

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4, 6, 8, 10]
```

Lambda functions are particularly useful when you need to create simple functions on the fly without explicitly defining a named function. They are commonly used in functional programming paradigms and for writing concise code. However, they should be used judiciously to maintain code readability and clarity.

## Modules and Packages
Certainly! Here's an overview of modules, importing your own modules, and packages in Python:

### Modules:
- Modules are Python files containing Python code. They can define functions, classes, and variables.
- Modules help organize code into reusable units and provide a way to namespace functions and variables.
- You can create your own modules by simply writing Python code in a `.py` file.

Example module (`mymodule.py`):
```python
# mymodule.py

def greet(name):
    print("Hello, " + name + "!")
```

### Importing Own Module:
- Once you've created a module, you can import it into other Python scripts using the `import` statement followed by the module name (without the `.py` extension).
- After importing, you can access functions, classes, and variables defined in the module using dot notation (`module_name.function()`).

Example usage:
```python
# main.py

import mymodule

mymodule.greet("Alice")
```

### Packages:
- Packages are directories of Python modules with an additional `__init__.py` file.
- They provide a way to organize modules into a hierarchical structure.
- Packages can contain sub-packages, allowing for even more organization.

Example package structure:
```
my_package/
    __init__.py
    module1.py
    module2.py
    sub_package/
        __init__.py
        module3.py
```

### Importing Modules from Packages:
- To import modules from a package, you use dot notation, specifying the package name followed by the module name.
- If you want to import specific modules or sub-packages within a package, you can use the `from ... import ...` syntax.

Example:
```python
# Importing module from package
import my_package.module1

my_package.module1.some_function()

# Importing specific function from module
from my_package.module2 import another_function

another_function()

# Importing sub-package
import my_package.sub_package.module3

my_package.sub_package.module3.some_function()
```

### Importance:
- Modules and packages help in organizing and structuring Python code, making it more manageable and reusable.
- They facilitate code reuse by allowing you to import functionality from one module into another.
- Packages enable developers to create large-scale applications by breaking them down into smaller, more manageable components.
- Importing your own modules and packages allows you to leverage your own code across multiple projects, saving time and effort.
### Some example of modules
Python comes with a rich standard library that includes a wide range of modules for various tasks. Here are some commonly used inbuilt modules in Python:

1. **`os`**: Provides a portable way of interacting with the operating system. It allows you to perform file operations, directory operations, and process management.

2. **`sys`**: Provides access to some variables used or maintained by the Python interpreter and functions that interact with the interpreter. It's typically used for system-specific parameters and functions.

3. **`math`**: Contains mathematical functions and constants such as trigonometric functions, logarithmic functions, mathematical constants like π (pi), and more.

4. **`datetime`**: Provides classes for manipulating dates and times. It allows you to work with dates, times, time intervals, time zones, and more.

5. **`random`**: Allows you to generate pseudo-random numbers, shuffle sequences, and select random elements. It's commonly used for simulations, games, and statistical sampling.
# UNIT 3
## File Operations
Certainly! Here's an overview of reading and writing text files in Python, along with code examples for each operation:
```python
# this is a simple way to open the file
f = open("test.txt","r")
```
### Reading Text Files:
You can read text files in Python using various methods provided by the file object. Here are some commonly used methods:

1. **`read()`**: Reads the entire content of the file as a single string.

```python
with open("file.txt", "r") as file:
    content = file.read()
    print(content)
```

2. **`readline()`**: Reads a single line from the file.

```python
with open("file.txt", "r") as file:
    line = file.readline()
    print(line)
```

3. **`readlines()`**: Reads all lines from the file and returns them as a list.

```python
with open("file.txt", "r") as file:
    lines = file.readlines()
    for line in lines:
        print(line)
```

### Writing Text Files:
You can write to text files in Python using the `write()` and `writelines()` methods provided by the file object. Make sure to open the file in write mode ("w") or append mode ("a") as needed.

1. **`write()`**: Writes a string to the file.

```python
with open("output.txt", "w") as file:
    file.write("Hello, world!\n")
```

2. **`writelines()`**: Writes a list of strings to the file.

```python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
with open("output.txt", "w") as file:
    file.writelines(lines)
```

### Manipulating File Pointer using `seek()`:
The `seek()` method allows you to change the position of the file pointer within the file.

```python
with open("file.txt", "r") as file:
    # Move pointer to the beginning of the file
    file.seek(0)
    content = file.read()
    print(content)
```

### Appending to Files:
To append content to a file without overwriting existing content, open the file in append mode ("a").

```python
with open("file.txt", "a") as file:
    file.write("New line appended\n")
```

## OOP
Certainly! Here's an overview of object-oriented programming (OOP) concepts in Python, along with explanations and code examples for each topic:

### Overview of OOP:
Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects," which can contain data in the form of fields (attributes) and code in the form of procedures (methods). OOP focuses on organizing code into classes and objects, allowing for better code reuse, modularity, and scalability.
Sure! Here's an overview of object-oriented programming (OOP) concepts in Python:

### Object-Oriented Programming (OOP):
Object-oriented programming is a programming paradigm that focuses on modeling real-world entities as objects, which have attributes (data) and behaviors (methods). OOP enables modular, reusable, and maintainable code by organizing it into classes and objects.

### Key Concepts:

1. **Classes and Objects**:
   - **Class**: A blueprint or template for creating objects. It defines the attributes and methods that all objects of the class will have.
   - **Object**: An instance of a class. It represents a specific entity with its own state (attributes) and behavior (methods).

2. **Attributes and Methods**:
   - **Attributes**: Data associated with an object. Also known as properties or fields.
   - **Methods**: Functions defined within a class that perform specific actions or operations on the object's data.

3. **Encapsulation**:
   - Encapsulation is the bundling of data (attributes) and methods that operate on the data into a single unit (class).
   - It hides the internal implementation details of an object and exposes only the necessary interface to interact with it.

4. **Inheritance**:
   - Inheritance is a mechanism by which a class can inherit attributes and methods from another class (superclass).
   - It promotes code reuse and allows for the creation of hierarchical relationships between classes.

5. **Polymorphism**:
   - Polymorphism allows objects of different classes to be treated as objects of a common superclass.
   - It enables code reuse and flexibility by providing a way to use objects interchangeably based on their common interface.

6. **Abstraction**:
   - Abstraction is the process of simplifying complex systems by hiding unnecessary details and exposing only essential features.
   - It allows developers to focus on high-level concepts and ignore low-level implementation details.

### Benefits of OOP:
- **Modularity**: OOP promotes modular design, allowing you to break down complex systems into smaller, more manageable components (classes).
- **Reusability**: OOP facilitates code reuse through inheritance and composition, reducing redundancy and improving maintainability.
- **Scalability**: OOP supports building large-scale applications by providing a structured and organized way to manage code complexity.
- **Flexibility**: OOP promotes flexibility and extensibility, allowing you to easily modify and extend existing code to accommodate new requirements.

### Classes and Objects:
- **Class**: A class is a blueprint for creating objects. It defines the attributes (data) and methods (functions) that all objects of the class will have.
- **Object**: An object is an instance of a class. It represents a specific instance of the class, with its own unique attributes and behaviors.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

# Creating objects (instances) of the Car class
car1 = Car("Toyota", "Camry")
car2 = Car("Honda", "Civic")
```

### Accessing Attributes:
Attributes are accessed using dot notation (`object.attribute`). They can be accessed and modified both from within the class and outside the class.

```python
print(car1.make)  # Output: Toyota
car1.model = "Corolla"
print(car1.model)  # Output: Corolla
```

### Built-in Class Attributes:
Python provides several built-in class attributes that can be accessed using the `__class__` attribute.

```python
print(car1.__class__)  # Output: <class '__main__.Car'>
print(Car.__name__)  # Output: Car
```

### Methods:
Methods are functions defined within a class. They can access and modify class attributes and perform specific actions.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
    
    def display_info(self):
        print("Make:", self.make)
        print("Model:", self.model)

car1 = Car("Toyota", "Camry")
car1.display_info()  # Output: Make: Toyota, Model: Camry
```

### Class and Instance Variables:
- **Class Variables**: Variables that are shared among all instances of a class.
- **Instance Variables**: Variables that are unique to each instance of a class.

```python
class Circle:
    pi = 3.14  # Class variable
    
    def __init__(self, radius):
        self.radius = radius  # Instance variable
```

### Destroying Objects:
Python automatically handles memory management and object destruction using garbage collection. Objects are automatically


```python
del car1  # Delete car1 object
```

### Polymorphism:
Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables code reuse and flexibility.

```python
class Animal:
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        print("Woof!")

class Cat(Animal):
    def sound(self):
        print("Meow!")

def make_sound(animal):
    animal.sound()

dog = Dog()
cat = Cat()

make_sound(dog)  # Output: Woof!
make_sound(cat)  # Output: Meow!
```

### Overloading and Overriding of Operators:
Certainly! Let's distinguish between method overriding and method overloading in Python:

### Method Overriding:
Method overriding occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. The method in the subclass has the same name, signature, and return type as the method in the superclass.

```python
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def sound(self):  # Method overriding
        print("Dog barks")

dog = Dog()
dog.sound()  # Output: Dog barks
```

In this example, the `sound()` method in the `Dog` class overrides the `sound()` method defined in the `Animal` class. When you call `dog.sound()`, the overridden method in the `Dog` class is executed, producing the output "Dog barks".

### Method Overloading:
Method overloading refers to the ability to define multiple methods with the same name but different parameters or argument lists within the same class. Unlike some other programming languages, Python does not support method overloading by default. However, you can achieve similar behavior using default parameter values or variable-length argument lists.

```python
class Calculator:
    def add(self, a, b):  # Method with two parameters
        return a + b

    def add(self, a, b, c):  # Method with three parameters (overloading)
        return a + b + c

calc = Calculator()
print(calc.add(2, 3, 4))  # Output: 9
```

In this example, the `add()` method in the `Calculator` class is overloaded to accept either two or three parameters. When you call `calc.add(2, 3, 4)`, the method with three parameters is executed, adding all three numbers together.

However, note that in Python, only the latest definition of a method with a given name within a class is retained. Therefore, method overloading as seen in other languages is not directly supported. Instead, you can achieve similar functionality using different method names or by using default parameter values or variable-length argument lists.

### Key Differences:
- **Method Overriding**: Involves providing a specific implementation of a method in a subclass that is already defined in its superclass.
- **Method Overloading**: Involves defining multiple methods with the same name but different parameters within the same class. Python does not support method overloading directly, but you can achieve similar behavior using default parameter values or variable-length argument lists.

### Class Inheritance:
Inheritance allows a class (subclass) to inherit attributes and methods from another class (superclass). The `super()` function is used to call methods of the superclass.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):
        super().speak()
        print("Dog barks")

dog = Dog()
dog.speak()  # Output: Animal speaks, Dog barks
```

In Python, there are several types of inheritance that you can use to establish relationships between classes. Here are the main types of inheritance:

1. **Single Inheritance**:
   - In single inheritance, a subclass inherits from only one superclass.
   - This is the simplest form of inheritance.
   
   ```python
   class Parent:
       pass
   
   class Child(Parent):
       pass
   ```

2. **Multiple Inheritance**:
   - Multiple inheritance occurs when a class inherits from multiple superclasses.
   - The subclass inherits attributes and methods from all the superclasses.
   
   ```python
   class Parent1:
       pass
   
   class Parent2:
       pass
   
   class Child(Parent1, Parent2):
       pass
   ```

3. **Multilevel Inheritance**:
   - Multilevel inheritance involves a chain of inheritance where a subclass inherits from a superclass, and then another subclass inherits from that subclass.
   - It forms a hierarchical structure.
   
   ```python
   class Grandparent:
       pass
   
   class Parent(Grandparent):
       pass
   
   class Child(Parent):
       pass
   ```

4. **Hierarchical Inheritance**:
   - Hierarchical inheritance occurs when more than one subclass inherits from the same superclass.
   
   ```python
   class Parent:
       pass
   
   class Child1(Parent):
       pass
   
   class Child2(Parent):
       pass
   ```

5. **Hybrid Inheritance**:
   - Hybrid inheritance is a combination of two or more types of inheritance.
   - It can involve any combination of single, multiple, multilevel, or hierarchical inheritance.
   
   ```python
   class Parent1:
       pass
   
   class Parent2:
       pass
   
   class Child(Parent1, Parent2):
       pass
   ```

Certainly! Here's an overview of exception handling in Python:

### Exception Handling:
Exception handling is a mechanism in Python for gracefully handling errors and exceptions that may occur during program execution. It allows you to anticipate and respond to exceptional conditions, preventing your program from crashing or behaving unexpectedly.

### Try-Except Block:
The `try-except` block is used to catch and handle exceptions. It allows you to specify code that may raise exceptions and provide a fallback mechanism to handle those exceptions.

```python
try:
    # Code that may raise exceptions
    result = 10 / 0
except ZeroDivisionError:
    # Handle the ZeroDivisionError exception
    print("Error: Cannot divide by zero")
```

### Try-Except-Else Block:
You can use the `else` block along with the `try-except` block to execute code that should run only if no exceptions occur inside the `try` block.

```python
try:
    # Code that may raise exceptions
    result = 10 / 2
except ZeroDivisionError:
    # Handle the ZeroDivisionError exception
    print("Error: Cannot divide by zero")
else:
    # Code to execute if no exceptions occur
    print("Result:", result)
```

### Try-Except-Finally Block:
The `finally` block is used to execute cleanup code that should run regardless of whether an exception occurs or not. It's often used to release resources or perform cleanup operations.

```python
try:
    # Code that may raise exceptions
    result = 10 / 2
except ZeroDivisionError:
    # Handle the ZeroDivisionError exception
    print("Error: Cannot divide by zero")
finally:
    # Cleanup code
    print("Cleanup code")
```

### Multiple Except Blocks:
You can use multiple `except` blocks to handle different types of exceptions separately.

```python
try:
    # Code that may raise exceptions
    result = 10 / 0
except ZeroDivisionError:
    # Handle the ZeroDivisionError exception
    print("Error: Cannot divide by zero")
except ValueError:
    # Handle the ValueError exception
    print("Error: Invalid input")
```

### Accessing Exception Information:
You can access information about the exception using the `as` keyword followed by an identifier.

```python
try:
    # Code that may raise exceptions
    result = 10 / 0
except ZeroDivisionError as e:
    # Handle the ZeroDivisionError exception and access its information
    print("Error:", e)
```

### Raising Exceptions:
You can manually raise exceptions using the `raise` statement to indicate exceptional conditions in your code.

```python
x = -1
if x < 0:
    raise ValueError("x cannot be negative")
```

### Python Standard Exceptions:

Python provides a wide range of standard exceptions that cover various common errors and exceptional conditions that may occur during program execution. Here are some of the most commonly used types of standard exceptions:

1. **`Exception`**: The base class for all built-in exceptions. It is typically used as a catch-all for any exception that does not have a more specific class.

2. **`SyntaxError`**: Raised when the Python parser encounters a syntax error in the code, indicating an invalid syntax.

3. **`IndentationError`**: Raised when there is an incorrect indentation in the code, typically caused by mixing tabs and spaces or incorrect indentation levels.

4. **`NameError`**: Raised when a local or global name is not found. This typically occurs when trying to access a variable or function that has not been defined.

5. **`TypeError`**: Raised when an operation or function is applied to an object of inappropriate type.

6. **`ValueError`**: Raised when a built-in operation or function receives an argument that has the right type but an inappropriate value.

### User-Defined Exceptions:
User-defined exceptions in Python allow you to create custom exception classes to handle specific error conditions in your code. Here's how you can define and use user-defined exceptions:

### Creating a User-Defined Exception:
To create a user-defined exception, you need to define a new class that inherits from the built-in `Exception` class or one of its subclasses.

```python
class MyError(Exception):
    def __init__(self, message):
        super().__init__(message)
        self.message = message

    def __str__(self):
        return f"MyError: {self.message}"
```

In this example:
- We define a new exception class `MyError` that inherits from the `Exception` class.
- We override the `__init__` method to initialize the exception with a custom error message.
- We also override the `__str__` method to provide a string representation of the exception when it's printed.

### Raising a User-Defined Exception:
Once you have defined your custom exception class, you can raise instances of that exception when appropriate conditions are met in your code.

```python
def divide(x, y):
    if y == 0:
        raise MyError("Division by zero is not allowed")
    return x / y

try:
    result = divide(10, 0)
except MyError as e:
    print(e)  # Output: MyError: Division by zero is not allowed
```

In this example:
- We define a function `divide` that takes two numbers as input and performs division.
- If the second number is zero, we raise an instance of our custom `MyError` exception with an appropriate error message.
- We use a `try-except` block to catch the `MyError` exception and handle it gracefully.

### Benefits of User-Defined Exceptions:
- **Custom Error Messages**: You can provide meaningful error messages tailored to your application's specific error conditions.
- **Modular Error Handling**: User-defined exceptions allow you to modularize error handling code and encapsulate error-handling logic within exception classes.
- **Improved Debugging**: Using custom exception classes can make it easier to identify and debug errors in your code by providing more descriptive error messages.

# UNIT 4
## Panda
### Intro
Pandas is a Python library used for working with data sets.
It has functions for analyzing, cleaning, exploring, and manipulating data.
Pandas allows us to analyze big data and make conclusions based on statistical theories.

Pandas can clean messy data sets, and make them readable and relevant.
### Features
Pandas is a powerful and flexible Python library designed for data manipulation and analysis. It provides easy-to-use data structures and functions for handling structured data efficiently. Here are some of the key features of Pandas:

1. **Data Structures**:
   - Pandas provides two main data structures: Series and DataFrame.
   - Series: A one-dimensional labeled array capable of holding data of any type.
   - DataFrame: A two-dimensional labeled data structure with columns of potentially different types, similar to a spreadsheet or SQL table.

2. **Data Alignment and Indexing**:
   - Pandas aligns data based on label indexes, making it easy to perform operations on data with different indexes.
   - Indexing allows for fast and efficient access to data, enabling both row and column selection.

3. **Data Input/Output**:
   - Pandas supports reading and writing data from/to various file formats, including CSV, Excel, SQL databases, JSON, HTML, and more.
   - It provides functions like `read_csv()`, `read_excel()`, `to_csv()`, `to_excel()`, etc., for seamless data import and export.

4. **Data Manipulation**:
   - Pandas offers a rich set of functions for data manipulation, including merging, joining, reshaping, pivoting, grouping, and aggregation.
   - Operations can be performed on entire datasets or subsets of data, facilitating complex data transformations.

5. **Missing Data Handling**:
   - Pandas provides robust support for handling missing or NaN (Not a Number) values in datasets.
   - Functions like `isna()`, `fillna()`, `dropna()`, and `interpolate()` enable efficient handling of missing data, allowing for data cleaning and preprocessing.

6. **Time Series Analysis**:
   - Pandas offers specialized support for working with time series data, including date/time indexing, resampling, time zone handling, and date range generation.
   - It provides dedicated data structures like `Timestamp` and `DatetimeIndex` for representing and manipulating time-related data.
### Some methods
Certainly! Here are six important methods in Pandas:

1. **`read_csv()`**:
   - This method is used to read data from a CSV file into a DataFrame.
   - It supports various parameters to handle different file formats, data types, headers, indexes, and missing values.
   - Example: `df = pd.read_csv('file.csv')`

2. **`head()`** and **`tail()`**:
   - These methods are used to view the first or last few rows of a DataFrame, respectively.
   - They are useful for quickly inspecting the structure and contents of a DataFrame.
   - Example: `df.head()` or `df.tail(10)` (to view the last 10 rows)

3. **`info()`**:
   - This method provides a concise summary of a DataFrame, including column data types, non-null counts, and memory usage.
   - It helps in understanding the size, shape, and data types of the DataFrame.
   - Example: `df.info()`

4. **`describe()`**:
   - This method generates descriptive statistics for numerical columns in a DataFrame, such as count, mean, standard deviation, min, max, and percentiles.
   - It gives insights into the distribution and central tendency of numerical data.
   - Example: `df.describe()`

5. **`groupby()`**:
   - This method is used for grouping data in a DataFrame based on one or more columns.
   - It enables aggregation, transformation, and other operations on grouped data.
   - Example: `df.groupby('column').mean()` (to calculate the mean for each group)

6. **`to_csv()`**:
   - This method is used to write data from a DataFrame to a CSV file.
   - It allows customization of parameters such as file path, column names, index, and delimiter.
   - Example: `df.to_csv('output.csv', index=False)` (to save DataFrame to a CSV file without index)
### Series
Certainly! Here are some notes on Series in Pandas:

1. **Definition**:
   - A Series is a one-dimensional labeled array in Pandas capable of holding data of any type, including integers, floats, strings, and Python objects.
   - It consists of a sequence of values and associated index labels.

2. **Creation**:
   - Series can be created from Python lists, NumPy arrays, dictionaries, or scalar values.
   - The general syntax to create a Series is: `pd.Series(data, index=index)`, where `data` can be a list, array, dictionary, or scalar, and `index` is an optional parameter specifying custom index labels.

3. **Indexing**:
   - Series objects have both a data component (the array of values) and an index component.
   - Indexing allows for fast and efficient access to elements based on their label or position.
   - Elements can be accessed using square brackets (`[]`) with either the label or positional index.

4. **Labeling**:
   - Each element in a Series has an associated index label, which can be of any immutable data type, such as integers, strings, or dates.
   - Index labels provide a unique identifier for each element in the Series, enabling easy data alignment and manipulation.

5. **Attributes and Methods**:
   - Series objects have various attributes and methods for accessing and manipulating data.
   - Some common attributes include `values` (returns the array of values), `index` (returns the index labels), `dtype` (returns the data type of the values), and `size` (returns the number of elements).
   - Methods like `head()`, `tail()`, `describe()`, `unique()`, `value_counts()`, etc., provide useful summary statistics and insights about the data.

6. **Operations**:
   - Series support element-wise operations, broadcasting, and vectorized operations similar to NumPy arrays.
   - Arithmetic operations, boolean operations, and mathematical functions can be applied directly to Series objects.
   - Series can be combined, concatenated, and aligned based on their index labels.
### DataFrame
Here are some detailed notes on DataFrames in Pandas:

1. **Definition**:
   - A DataFrame is a two-dimensional labeled data structure in Pandas, resembling a spreadsheet or SQL table.
   - It consists of rows and columns, where each column can hold data of different types (e.g., integers, floats, strings, etc.).
   - Rows and columns are both labeled, allowing for intuitive indexing and alignment of data.

2. **Creation**:
   - DataFrames can be created from various sources, including Python dictionaries, lists, NumPy arrays, CSV files, Excel files, SQL databases, and JSON data.
   - The `pd.DataFrame()` constructor is used to create a DataFrame from different data sources, with options to specify column names, index labels, and other parameters.

3. **Attributes and Methods**:
   - DataFrames have numerous attributes and methods for accessing, manipulating, and analyzing data.
   - Attributes like `shape`, `columns`, `index`, `dtypes`, and `values` provide information about the DataFrame's structure and contents.
   - Methods such as `head()`, `tail()`, `info()`, `describe()`, `mean()`, `sum()`, `groupby()`, `sort_values()`, and `pivot_table()` enable various data manipulation and analysis operations.

4. **Indexing and Selection**:
   - DataFrames support both label-based and positional-based indexing for accessing rows and columns.
   - Individual columns can be accessed using dictionary-like notation (`df['column_name']`) or attribute access (`df.column_name`).
   - Rows can be selected using integer-based indexing (`.iloc[]`) or label-based indexing (`.loc[]`).
   - Boolean indexing allows for selecting rows based on conditions.

5. **Missing Values**:
   - DataFrames support missing or NaN (Not a Number) values, which can be introduced using the `None` Python object or NumPy's `np.nan`.
   - Pandas provides functions like `isna()`, `fillna()`, and `dropna()` for handling missing values in DataFrames.

6. **Merging and Concatenation**:
   - DataFrames can be combined through merging, joining, or concatenation operations.
   - The `merge()` function is used for combining DataFrames based on a common column or index.
   - The `concat()` function concatenates DataFrames along rows or columns.

7. **Grouping and Aggregation**:
   - DataFrames support grouping and aggregation operations using the `groupby()` method.
   - Grouping allows for splitting the data into groups based on one or more keys and then applying aggregation functions (e.g., sum, mean, count) to each group.
### Panel

1. **Definition**:
   - Panel is a three-dimensional labeled data structure in Pandas, capable of handling higher-dimensional data.
   - It can be thought of as a container for DataFrame objects, where each item in the Panel is a DataFrame representing a two-dimensional slice of data.
   - Panels have three axes: items, major_axis, and minor_axis, each with its associated labels.

2. **Creation**:
   - Panels can be created using the `pd.Panel()` constructor or by passing a dictionary of DataFrames to the `pd.Panel.from_dict()` method.
   - The `pd.Panel()` constructor takes data, items, major_axis, and minor_axis as arguments to create a Panel object.

3. **Accessing Data**:
   - Data within a Panel can be accessed using indexing along the three axes: items, major_axis, and minor_axis.
   - Indexing along the items axis returns a DataFrame corresponding to a particular item.
   - Indexing along the major_axis and minor_axis axes returns a slice of data corresponding to the specified row and column labels, respectively.

4. **Operations**:
   - Panels support various operations, including arithmetic operations, slicing, merging, and concatenation.
   - Arithmetic operations between Panel objects align data based on their axes labels, performing element-wise operations.
### Index objects
Index objects play a fundamental role in Pandas, providing labels for the rows and columns of Series and DataFrame objects. Here are some detailed notes on index objects in Pandas:

1. **Definition**:
   - An Index object is an immutable array-like structure that holds the axis labels for Series and DataFrame objects in Pandas.
   - Index objects can be thought of as an ordered set of labels, providing a unique identifier for each row or column in a Pandas data structure.

2. **Types of Index Objects**:
   - Pandas supports various types of index objects, each with its specific characteristics and use cases:
     - **`pd.Index`**: A basic index object representing a one-dimensional array of labels.
     - **`pd.RangeIndex`**: An index object representing a range of integer labels, commonly used for default indexing.
     - **`pd.MultiIndex`**: A hierarchical index object representing multiple levels of labels, used for multi-level indexing in Series and DataFrame objects.

3. **Creation**:
   - Index objects can be created using constructors like `pd.Index()`, `pd.RangeIndex()`, `pd.MultiIndex()`, or by extracting them from existing Pandas data structures.
   - Index objects can be specified explicitly during the creation of Series and DataFrame objects or inferred automatically based on the data.

4. **Properties**:
   - Index objects have several properties that provide information about the labels and characteristics of the index:
     - **`values`**: Returns the array of labels contained in the index.
     - **`dtype`**: Returns the data type of the index labels.
     - **`name`**: Returns the name of the index, if any.
     - **`nlevels`**: Returns the number of levels in a MultiIndex object.

5. **Alignment and Alignment**:
   - Index objects play a crucial role in aligning data during arithmetic operations, joining, and merging operations in Pandas.
   - Operations between Series or DataFrame objects align data based on their index labels, ensuring that corresponding elements are matched correctly.

6. **Operations**:
   - Index objects support various operations, including membership testing, intersection, union, difference, and sorting.
   - Methods like `isin()`, `intersection()`, `union()`, `difference()`, and `sort_values()` provide functionality for manipulating index labels.
### Reindex
Certainly! Here are some detailed notes on re-indexing in Pandas:

1. **Definition**:
   - Re-indexing is the process of conforming a DataFrame to a new index, either by adding missing values, removing excess values, or rearranging data to match the new index.
   - It allows for realignment of data along one or more axes based on a new set of labels.

2. **Purpose**:
   - Re-indexing is commonly used to align data from different sources or to prepare data for merging or joining operations.
   - It ensures that data is properly aligned across multiple DataFrames or Series objects, facilitating meaningful analysis and comparison.

3. **Method**:
   - Re-indexing in Pandas is performed using the `reindex()` method, which returns a new DataFrame or Series with the data conformed to the new index.
   - The `reindex()` method takes one or more parameters, including `index`, `columns`, `fill_value`, `method`, `limit`, `copy`, etc., to customize the re-indexing behavior.

4. **Handling Missing Values**:
   - When re-indexing, missing values can be introduced if the new index contains labels that were not present in the original index.
   - The `fill_value` parameter in the `reindex()` method allows for specifying a value to use when filling missing values.
   - Alternatively, missing values can be filled using interpolation methods provided by the `method` parameter (e.g., `ffill`, `bfill`, `nearest`).

5. **Changing Index Labels**:
   - Re-indexing can also be used to change the index labels of a DataFrame or Series, without changing the underlying data.
   - By passing a new list of index labels to the `index` parameter of the `reindex()` method, the index labels can be updated accordingly.

6. **Aligning Data**:
   - Re-indexing ensures that data is aligned along the specified index labels, allowing for consistent indexing and alignment across multiple data structures.
   - It is particularly useful when working with time series data or data from disparate sources that may have different indexes.

### Iteration
Iteration in Pandas involves traversing through the elements of a DataFrame or Series to perform operations. However, it is generally discouraged due to performance reasons, as Pandas provides optimized vectorized operations that are much faster. Despite this, there are several methods available for iterating over elements in Pandas objects. Here's a breakdown:

1. **Iteration Over Rows**:
   - The `iterrows()` method allows iteration over DataFrame rows as (index, Series) pairs.
   - It returns an iterator yielding index labels and Series objects representing rows.
   - Example:
     ```python
     for index, row in df.iterrows():
         print(index, row['column_name'])
     ```

2. **Iteration Over Columns**:
   - It's more efficient to iterate over DataFrame columns using dictionary-like indexing.
   - Example:
     ```python
     for column_name, column_values in df.items():
         print(column_name, column_values)
     ```

3. **Iteration Over Data**:
   - The `itertuples()` method iterates over DataFrame rows as namedtuples, providing a more efficient way to access row data compared to `iterrows()`.
   - Example:
     ```python
     for row in df.itertuples():
         print(row.Index, row.column_name)
     ```

4. **Applying Functions**:
   - Instead of direct iteration, Pandas encourages applying functions to columns or rows using built-in methods like `apply()`, `applymap()`, or `map()`.
   - These methods leverage optimized implementations and can significantly improve performance.
   - Example:
     ```python
     def func(row):
         return row['column_name'] * 2

     df['new_column'] = df.apply(func, axis=1)
     ```

5. **Conditional Iteration**:
   - You can also iterate conditionally over DataFrame rows or columns using boolean indexing.
   - Example:
     ```python
     for index, row in df[df['column_name'] > 0].iterrows():
         print(index, row['column_name'])
     ```

6. **Performance Considerations**:
   - Iterating over large datasets can be slow compared to vectorized operations.
   - Whenever possible, use vectorized operations or apply functions to improve performance.
   - If iteration is necessary, prefer more efficient methods like `itertuples()` over `iterrows()`.
### Sorting 
Sorting in Pandas involves arranging the rows or columns of a DataFrame or Series based on the values of one or more columns or index labels. Here are some detailed notes on sorting in Pandas:

1. **Sorting Columns**:
   - The `sort_values()` method is used to sort DataFrame rows based on the values of one or more columns.
   - It takes the `by` parameter, which specifies the column(s) to sort by, and the `ascending` parameter, which determines the sort order (default is ascending).
   - Example:
     ```python
     df_sorted = df.sort_values(by='column_name', ascending=True)
     ```

2. **Sorting Index**:
   - The `sort_index()` method is used to sort DataFrame rows based on the index labels.   - It takes the `axis` parameter to specify whether to sort rows (`axis=0`, default) or columns (`axis=1`).
   - Example:
     ```python
     df_sorted = df.sort_index(axis=0)
     ```

3. **Multi-level Index Sorting**:
   - For DataFrames with multi-level indexes (MultiIndex), sorting can be performed along specific levels using the `level` parameter in `sort_index()`.
   - Example:
     ```python
     df_sorted = df.sort_index(level='level_name', axis=0)
     ```

4. **Sorting Series**:
   - Series objects can be sorted using the `sort_values()` method, similar to DataFrames.
   - It arranges the elements of the Series in ascending or descending order based on their values.
   - Example:
     ```python
     series_sorted = series.sort_values(ascending=True)
     ```

5. **Stable Sorting**:
   - By default, sorting in Pandas is stable, meaning that the relative order of equal elements is preserved.
   - This ensures that the original order is maintained for elements with the same value during sorting.

6. **Handling Missing Values**:
   - Missing values (`NaN`) are sorted to the end of the DataFrame or Series by default.
   - You can control the placement of missing values using the `na_position` parameter in `sort_values()`.

## Matplotlib
Matplotlib is a powerful Python library for creating static, interactive, and animated visualizations. It provides a wide range of functions for generating various types of plots, including line plots, scatter plots, bar plots, histograms, pie charts, and more. Matplotlib is highly customizable, allowing users to control every aspect of a plot, such as colors, line styles, markers, fonts, axes, labels, and annotations. It follows an object-oriented approach, enabling users to create and manipulate plot elements using Python objects directly. Matplotlib seamlessly integrates with NumPy for efficient data visualization workflows and supports multiple backends for rendering plots in different environments and formats. With extensive documentation and a large community of users and developers, Matplotlib is a go-to tool for data visualization in Python, suitable for a wide range of scientific, engineering, statistical, and data analysis applications.

**Application**
1. **Data Exploration and Analysis**: Matplotlib is often used for exploring datasets and gaining insights through visualizations. It helps analysts and data scientists to understand the distribution, trends, and patterns in the data.
    
2. **Scientific Research**: In scientific research, Matplotlib is used to visualize experimental results, simulations, and numerical data. It helps researchers communicate their findings effectively and facilitates the understanding of complex phenomena.
    
3. **Statistical Analysis**: Matplotlib is used in statistical analysis to visualize distributions, correlations, and regression models. It helps in interpreting statistical findings and communicating results to stakeholders.
    
4. **Machine Learning and Data Mining**: Matplotlib is integrated into machine learning and data mining workflows for visualizing model performance, feature distributions, and decision boundaries. It aids in model evaluation and comparison.
    
5. **Business Analytics**: In business analytics, Matplotlib is used to create dashboards, reports, and visualizations for tracking key performance indicators (KPIs), market trends, and customer behavior. It supports data-driven decision-making and strategy development.
**Common Functions**
1. **plt.plot(x, y, 'format', label='label')**:
   - Description: This method is used to create line plots. It takes arrays or sequences of x and y values as input and plots them as connected line segments. The `'format'` parameter specifies the line style, marker, and color of the plot. It can include combinations of characters like 'b-' (blue solid line), 'ro' (red circles), etc. The `label` parameter is optional and is used to specify a label for the plot, which can be used in legends.
   
2. **plt.scatter(x, y, s=size, c=color, marker='marker_type', label='label')**:
   - Description: This method creates scatter plots, where each data point is represented as a marker on the plot. It takes arrays or sequences of x and y values as input. Additional parameters like `s` specify the size of the markers, `c` specifies the color of the markers, and `marker` specifies the type of marker to use. The `label` parameter, as in `plt.plot()`, is optional and specifies a label for the plot.

3. **plt.xlabel('xlabel')**, **plt.ylabel('ylabel')**:
   - Description: These methods are used to set labels for the x-axis and y-axis, respectively. They take strings as input and specify the labels for the corresponding axes.

4. **plt.title('title')**:
   - Description: This method sets the title of the plot. It takes a string as input and specifies the title to be displayed above the plot.

5. **plt.legend()**:
   - Description: This method adds a legend to the plot, providing information about the different elements represented in the plot. The legend is populated based on the `label` parameter provided in `plt.plot()` or `plt.scatter()` functions.

6. **plt.savefig('filename.png')**:
   - Description: This method saves the current figure to a file in a specified format, such as PNG, PDF, or SVG. It takes a filename (including the file extension) as input and saves the plot accordingly.
## Sklearn
1. **Introduction**:
   - Scikit-learn is a popular open-source machine learning library for Python.
   - It provides simple and efficient tools for data mining and data analysis, built on NumPy, SciPy, and matplotlib.

2. **Features**:
   - Scikit-learn offers a wide range of supervised and unsupervised learning algorithms for classification, regression, clustering, dimensionality reduction, and more.
   - It includes tools for model selection, evaluation, and validation, such as cross-validation, grid search, and performance metrics.
   - Scikit-learn supports data preprocessing techniques like feature scaling, dimensionality reduction, and handling missing values.
   - It provides utilities for working with text data, image data, and time series data, including feature extraction and transformation.

3. **Simple and Consistent API**:
   - Scikit-learn follows a consistent API design, making it easy to learn and use different algorithms interchangeably.
   - Models are implemented as Python classes with methods like `fit()`, `predict()`, `transform()`, and `score()`.

4. **Supported Algorithms**:
   - Scikit-learn provides implementations of various machine learning algorithms, including:
     - Classification: Logistic Regression, Decision Trees, Random Forests, Support Vector Machines (SVM), K-Nearest Neighbors (KNN), etc.
### More info
1. **Loading Datasets**:
   - Scikit-learn provides built-in datasets for experimentation and learning.
   - These datasets can be loaded using functions like `load_iris()`, `load_digits()`, `load_boston()`, `fetch_openml()`, etc.
   - Example:
     ```python
     from sklearn.datasets import load_iris

     iris = load_iris()
     X, y = iris.data, iris.target
     ```

2. **Learning and Predicting**:
   - Scikit-learn follows a consistent API for training models and making predictions.
   - Models are trained using the `fit()` method with training data, and predictions are made using the `predict()` method with new data.
   - Example:
     ```python
     from sklearn.linear_model import LogisticRegression

     model = LogisticRegression()
     model.fit(X_train, y_train)
     y_pred = model.predict(X_test)
     ```

3. **Model Persistence**:
   - Model persistence refers to the ability to save trained models to disk for later use.
   - Scikit-learn provides utilities for model persistence using the `joblib` library or the `pickle` module.
   - Models can be saved using the `dump()` function and loaded back into memory using the `load()` function.
   - Example:
     ```python
     from joblib import dump, load

     # Save trained model
     dump(model, 'model.joblib')

     # Load model from file
     model = load('model.joblib')
     ```

4. **Benefits of Model Persistence**:
   - Model persistence allows trained models to be reused without retraining, saving time and computational resources.
   - Saved models can be deployed in production environments for making predictions on new data.
   - Model persistence facilitates sharing trained models with collaborators or integrating them into other applications.

5. **Considerations**:
   - When saving models, it's important to include any preprocessing steps or feature transformations that were applied during training.
   - Ensure that the version of scikit-learn used for saving and loading models is compatible to prevent compatibility issues.

6. **Alternate Serialization Methods**:
   - While `joblib` is the preferred method for model persistence in scikit-learn due to its efficiency with large NumPy arrays, `pickle` can also be used.
   - However, `pickle` may have compatibility issues between different Python versions and may not be as efficient as `joblib`.
## Numpy
Here are detailed notes on NumPy, its features, and applications:

1. **Introduction**:
   - NumPy, short for Numerical Python, is a powerful library for numerical computing in Python.
   - It provides high-performance multidimensional array objects and tools for working with these arrays efficiently.

2. **Features**:
   - **Multidimensional Arrays**: NumPy provides the `ndarray` class for representing multidimensional arrays, which can have any number of dimensions.
   - **Universal Functions (ufuncs)**: NumPy offers a large collection of mathematical functions that operate element-wise on arrays, providing fast execution.
   - **Broadcasting**: NumPy automatically broadcasts arrays of different shapes during arithmetic operations, making it easy to perform operations on arrays of different shapes.
   - **Array Operations**: NumPy arrays support various operations, including slicing, indexing, reshaping, stacking, and concatenation.

3. **Applications**:
   - **Scientific Computing**: NumPy is widely used in scientific computing, including fields such as physics, chemistry, biology, astronomy, and geoscience.
   - **Data Analysis**: NumPy forms the foundation for data analysis and manipulation in Python, serving as the backbone for libraries like pandas.
   - **Machine Learning**: NumPy arrays are used to represent data in machine learning algorithms, and many machine learning frameworks in Python rely on NumPy for efficient computation.
   - **Signal Processing**: NumPy provides tools for processing and analyzing signals, such as digital signal processing (DSP), image processing, and audio processing.
### Lists vs numpy
Lists and NumPy arrays are both data structures in Python, but they have several differences in terms of functionality, performance, and usage. Here's a comparison:

1. **Functionality**:
   - **Lists**: Lists are a built-in data structure in Python and can contain elements of different data types. They are mutable, meaning that you can add, remove, or modify elements after the list is created. Lists are versatile and can be used for various purposes.
   - **NumPy Arrays**: NumPy arrays are homogeneous, meaning that all elements in the array must be of the same data type. They are designed for numerical computing and support vectorized operations and mathematical functions. NumPy arrays are fixed in size and cannot be resized once created.

2. **Performance**:
   - **Lists**: Lists are implemented as dynamic arrays in Python, which means that they may not perform efficiently for large datasets or numerical computations. Iterating over lists can be slower compared to NumPy arrays, especially for large datasets.
   - **NumPy Arrays**: NumPy arrays are implemented in C and are optimized for numerical computations. They use contiguous blocks of memory, allowing for efficient vectorized operations and mathematical computations. NumPy arrays typically offer better performance than lists, especially for numerical tasks.

3. **Memory Usage**:
   - **Lists**: Lists in Python store references to objects, which can result in higher memory usage compared to NumPy arrays. Lists also have additional memory overhead for storing metadata such as the size of the list and the references to objects.
   - **NumPy Arrays**: NumPy arrays store data in a contiguous block of memory, resulting in lower memory usage compared to lists. NumPy arrays do not have the overhead of storing references to objects, making them more memory efficient, especially for large datasets.

4. **Ease of Use**:
   - **Lists**: Lists are easy to use and understand, and they support a wide range of operations and methods for manipulating data. Lists are suitable for general-purpose programming tasks and are often used in Python code.
   - **NumPy Arrays**: NumPy arrays have a more specialized usage and are primarily designed for numerical computing. They offer a wide range of mathematical functions and operations optimized for numerical tasks. While NumPy arrays may have a steeper learning curve compared to lists, they provide powerful tools for numerical computation and data analysis.

5. **Usage**:
   - **Lists**: Lists are suitable for general-purpose programming tasks, such as storing collections of items, iterating over elements, and performing basic operations like appending, removing, or sorting elements.
   - **NumPy Arrays**: NumPy arrays are used for numerical computing tasks, such as scientific computing, data analysis, machine learning, and numerical simulations. They are commonly used for storing and manipulating numerical data, performing mathematical operations, and working with large datasets efficiently.
### Creating Array
Creating arrays in NumPy can be done using various methods. Here are some common ways to create NumPy arrays:

1. **From Python Lists or Tuples**:
   - You can create a NumPy array from a Python list or tuple using the `numpy.array()` function.
   - Example:
     ```python
     import numpy as np

     my_list = [1, 2, 3, 4, 5]
     arr_from_list = np.array(my_list)

     my_tuple = (1, 2, 3, 4, 5)
     arr_from_tuple = np.array(my_tuple)
     ```

2. **Using Built-in Functions**:
   - NumPy provides several built-in functions for creating arrays with specific properties.
   - Examples:
     ```python
     arr_zeros = np.zeros((3, 3))  # Array of zeros with shape (3, 3)
     arr_ones = np.ones((2, 4))    # Array of ones with shape (2, 4)
     arr_empty = np.empty((2, 2))  # Empty array (values uninitialized) with shape (2, 2)
     arr_range = np.arange(0, 10, 2)  # Array with values from 0 to 10 (exclusive) with step 2
     arr_linspace = np.linspace(0, 10, 5)  # Array with 5 evenly spaced values from 0 to 10
     ```

3. **Using Random Number Generators**:
   - NumPy provides functions for generating arrays with random values from various distributions.
   - Examples:
     ```python
     arr_random = np.random.random((2, 2))  # Array with random values from a uniform distribution
     arr_normal = np.random.normal(0, 1, (3, 3))  # Array with random values from a normal distribution
     ```

4. **From Existing Data**:
   - You can create a NumPy array from existing data structures like Python lists, tuples, or other NumPy arrays.
   - Example:
     ```python
     my_list = [1, 2, 3, 4, 5]
     arr_from_list = np.array(my_list)

     existing_array = np.array([[1, 2], [3, 4]])
     arr_from_array = np.array(existing_array)
     ```

5. **Using Specialized Functions**:
   - NumPy provides specialized functions for creating arrays with specific properties, such as diagonal arrays, identity arrays, and full arrays.
   - Examples:
     ```python
     arr_diag = np.diag([1, 2, 3])  # Diagonal array with specified values on the diagonal
     arr_identity = np.identity(3)  # Identity array with size 3x3
     arr_full = np.full((2, 2), 5)  # Array filled with a specified value (5) with shape (2, 2)
     ```

### Using Array and scalar
In NumPy, arrays and scalars can be combined in arithmetic operations, where the scalar is applied element-wise to the array. This feature, known as broadcasting, allows for efficient vectorized operations. Here's how you can use arrays and scalars together in NumPy:

```python
import numpy as np

# Create a NumPy array
arr = np.array([1, 2, 3, 4, 5])

# Perform arithmetic operations with a scalar
result1 = arr + 2  # Add 2 to each element of the array
result2 = arr * 3  # Multiply each element of the array by 3
result3 = arr ** 2  # Square each element of the array

print("Array:", arr)
print("Array + Scalar:", result1)
print("Array * Scalar:", result2)
print("Array ** Scalar:", result3)
```

Output:
```
Array: [1 2 3 4 5]
Array + Scalar: [3 4 5 6 7]
Array * Scalar: [ 3  6  9 12 15]
Array ** Scalar: [ 1  4  9 16 25]
```

In the example above, the scalar value `2` is added to each element of the array `arr`. Similarly, the scalar value `3` is multiplied with each element of the array, and each element of the array is squared using the `**` operator with the scalar value `2`.

This broadcasting behavior allows for concise and efficient computation without the need for explicit looping over array elements. It is one of the key features of NumPy that makes it suitable for numerical computing and array manipulation.

### Indexing 
Indexing arrays in NumPy allows you to access individual elements, subsets of elements, or specific slices of an array. Here's an overview of indexing arrays in NumPy:

1. **Single Element Access**:
   - You can access individual elements of a NumPy array using square brackets `[]` and providing the indices of the element.
   - Example:
     ```python
     import numpy as np

     arr = np.array([1, 2, 3, 4, 5])
     print(arr[0])  # Access the first element (index 0)
     ```

2. **Slicing**:
   - Slicing allows you to extract a subset of elements from an array by specifying a range of indices.
   - You can use the colon `:` operator to specify the start, stop, and step of the slice.
   - Example:
     ```python
     import numpy as np

     arr = np.array([1, 2, 3, 4, 5])
     print(arr[1:4])  # Extract elements from index 1 to 3
     ```

3. **Negative Indices**:
   - Negative indices can be used to access elements from the end of the array.
   - Example:
     ```python
     import numpy as np

     arr = np.array([1, 2, 3, 4, 5])
     print(arr[-1])  # Access the last element
     ```

4. **Multi-dimensional Arrays**:
   - For multi-dimensional arrays, you can use multiple indices or slices separated by commas to access elements.
   - Example:
     ```python
     import numpy as np

     arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
     print(arr[0, 1])  # Access element at row 0, column 1
     ```

5. **Boolean Indexing**:
   - Boolean indexing allows you to filter elements of an array based on a boolean condition.
   - You can use boolean arrays of the same shape as the original array to specify which elements to select.
   - Example:
     ```python
     import numpy as np

     arr = np.array([1, 2, 3, 4, 5])
     mask = arr > 2  # Boolean mask to select elements greater than 2
     print(arr[mask])  # Select elements greater than 2
     ```

### Array Transposition
Array transposition refers to the process of exchanging the rows and columns of a two-dimensional array. In other words, it flips the shape of the array along its diagonal. Transposing an array can be useful in various numerical computations and data manipulation tasks.

In NumPy, array transposition can be performed using the `transpose()` method or the `T` attribute of the array object. Both methods produce the same result, allowing you to transpose the rows and columns of a NumPy array. Here's how you can do it in NumPy:

1. **Using the `transpose()` Method**:
   - The `transpose()` method allows you to transpose the rows and columns of a two-dimensional array.
   - It takes an optional argument `axes` that specifies the new order of axes. By default, it reverses the order of axes.
   - Example:
     ```python
     import numpy as np

     arr = np.array([[1, 2, 3], [4, 5, 6]])
     transposed_arr = arr.transpose()
     ```

2. **Using the `T` Attribute**:
   - The `T` attribute is a shorthand for the `transpose()` method and performs the same operation.
   - It returns the transposed array without any additional arguments.
   - Example:
     ```python
     import numpy as np

     arr = np.array([[1, 2, 3], [4, 5, 6]])
     transposed_arr = arr.T
     ```

3. **Specifying Axes**:
   - You can specify the order of axes using the `axes` parameter in the `transpose()` method.
   - The `axes` parameter takes a tuple of integers specifying the new order of axes.
   - Example:
     ```python
     import numpy as np

     arr = np.array([[1, 2, 3], [4, 5, 6]])
     transposed_arr = arr.transpose(1, 0)  # Swap rows and columns
     ```

4. **In-Place Transposition**:
   - Both methods return a transposed view of the original array by default.
   - To perform transposition in-place (modify the original array), you can use the `transpose()` method with the `copy` parameter set to `False`.
   - Example:
     ```python
     import numpy as np

     arr = np.array([[1, 2, 3], [4, 5, 6]])
     arr.transpose(copy=False)  # Perform transposition in-place
     ```

### Universal function
Universal functions (ufuncs) in NumPy are functions that operate element-wise on arrays, meaning they perform a specific operation on each element of the array independently. Ufuncs allow for efficient vectorized operations on arrays, avoiding the need for explicit looping over array elements.


1. **Exponential and Logarithmic Functions**:
   - Exponential: `np.exp(x)` computes the exponential of each element in the array `x`.
   - Logarithm: `np.log(x)` computes the natural logarithm of each element in the array `x`.

   ```python
   import numpy as np

   arr = np.array([1, 2, 3])

   # Exponential
   result_exp = np.exp(arr)

   # Logarithm (natural logarithm)
   result_log = np.log(arr)
   ```

2. **Square Root**:
   - `np.sqrt(x)` computes the square root of each element in the array `x`.

   ```python
   import numpy as np

   arr = np.array([4, 9, 16])

   # Square root
   result_sqrt = np.sqrt(arr)
   ```

3. **Trigonometric Functions**:
   - Sine: `np.sin(x)` computes the sine of each element in the array `x`.
   - Cosine: `np.cos(x)` computes the cosine of each element in the array `x`.
   - Tangent: `np.tan(x)` computes the tangent of each element in the array `x`.

   ```python
   import numpy as np

   arr = np.array([0, np.pi/4, np.pi/2])

   # Sine
   result_sin = np.sin(arr)

   # Cosine
   result_cos = np.cos(arr)

   # Tangent
   result_tan = np.tan(arr)
   ```

4. **Rounding Functions**:
   - Round: `np.round(x)` rounds each element in the array `x` to the nearest integer.
   - Floor: `np.floor(x)` rounds each element in the array `x` to the nearest integer less than or equal to it.
   - Ceil: `np.ceil(x)` rounds each element in the array `x` to the nearest integer greater than or equal to it.

   ```python
   import numpy as np

   arr = np.array([1.2, 2.7, 3.5])

   # Round
   result_round = np.round(arr)

   # Floor
   result_floor = np.floor(arr)

   # Ceil
   result_ceil = np.ceil(arr)
   ```

5. **Absolute Value**:
   - `np.abs(x)` computes the absolute value of each element in the array `x`.

   ```python
   import numpy as np

   arr = np.array([-1, -2, 3])

   # Absolute value
   result_abs = np.abs(arr)
   ```

### Array Processing
Array processing in NumPy involves performing various operations and manipulations on arrays to analyze, transform, and manipulate data efficiently. Here are some key points about array processing in NumPy:

1. **Element-Wise Operations**:
   - NumPy supports element-wise operations, where an operation is applied to each element of an array independently.
   - Element-wise operations can be arithmetic, logical, trigonometric, or any other mathematical function.
   - These operations can be performed using universal functions (ufuncs) provided by NumPy.

2. **Array Manipulation**:
   - NumPy provides functions for manipulating the shape and structure of arrays.
   - Functions like `reshape()`, `resize()`, `flatten()`, `ravel()`, and `transpose()` allow you to change the dimensions, flatten, or transpose arrays as needed.
   - Array concatenation, splitting, stacking, and joining functions (`concatenate()`, `split()`, `stack()`, `hstack()`, `vstack()`, `column_stack()`, `row_stack()`) are also available for combining or dividing arrays.

3. **Array Iteration**:
   - You can iterate over the elements of a NumPy array using loops like `for` loops.
   - However, for large arrays, vectorized operations and ufuncs are preferred over explicit iteration for better performance.

4. **Array Sorting**:
   - NumPy provides functions for sorting arrays, both in-place and out-of-place.
   - Functions like `np.sort()` and `np.argsort()` allow you to sort arrays along specified axes or dimensions.
   - You can also use methods like `sort()` and `argsort()` directly on array objects.

5. **Array Reductions**:
   - Reduction operations compute summary statistics or aggregate values across arrays.
   - Common reduction operations include `sum()`, `mean()`, `std()`, `min()`, `max()`, `argmin()`, `argmax()`, `median()`, `var()`, `any()`, `all()`, etc.
   - Reductions can be performed along specified axes or dimensions using the `axis` parameter.

6. **Broadcasting**:
   - Broadcasting allows arrays of different shapes to be combined in arithmetic operations, provided they meet certain compatibility rules.
   - Broadcasting rules enable efficient computation by implicitly expanding or duplicating arrays to match shapes during operations.

7. **Masking and Filtering**:
   - NumPy supports masking and filtering of arrays based on boolean conditions.
   - You can create boolean masks to select or filter elements of an array based on specific criteria.

8. **Vectorized Computation**:
   - Vectorization refers to the process of performing operations on entire arrays rather than individual elements.
   - Vectorized operations are more efficient than explicit loops and are the preferred way of processing arrays in NumPy.
### Array I/O
Array input and output (IO) in NumPy involve reading and writing arrays from/to external sources such as files, databases, or network streams. NumPy provides functions for reading and writing arrays in various formats, including binary files, text files, and NumPy's own `.npy` format. Here are some key points about array input and output in NumPy:

1. **Text File Input and Output**:
   - NumPy provides functions for reading and writing arrays from/to text files using `np.loadtxt()` and `np.savetxt()` functions, respectively.
   - Text files can be in plain text format or delimited format (e.g., CSV files).
   - You can specify delimiter, data type, and other parameters when reading or writing text files.

2. **Binary File Input and Output**:
   - NumPy allows reading and writing arrays in binary format using `np.fromfile()` and `np.tofile()` functions.
   - Binary files are more space-efficient than text files and are suitable for storing large arrays.
   - You can specify data type and shape information when reading binary files.

3. **NumPy Binary Format (.npy)**:
   - NumPy provides its own binary format for storing arrays with the `.npy` file extension.
   - Arrays can be saved and loaded using `np.save()` and `np.load()` functions, respectively.
   - The `.npy` format preserves the data type, shape, and other metadata of the array.

4. **Compressed File Formats**:
   - NumPy supports reading and writing arrays from/to compressed file formats like `.npz` (compressed archive) using `np.savez()` and `np.load()` functions.
   - Compressed file formats reduce file size and storage requirements, especially for large datasets.

5. **Memory-Mapped Files**:
   - NumPy allows memory-mapped IO, where arrays are stored in a file on disk but can be accessed as if they were in memory.
   - Memory-mapped files enable efficient handling of large datasets without loading the entire array into memory.

6. **Database IO**:
   - NumPy does not directly support database IO, but you can use third-party libraries like Pandas or SQLAlchemy for reading and writing arrays from/to databases.

Here are code examples demonstrating array input and output in NumPy for different scenarios:

1. **Text File Input and Output**:
   
   ```python
   import numpy as np

   # Create an array
   arr = np.array([[1, 2, 3], [4, 5, 6]])

   # Save array to a text file (CSV format)
   np.savetxt('array_data.csv', arr, delimiter=',')

   # Load array from a text file
   loaded_arr = np.loadtxt('array_data.csv', delimiter=',')
   print(loaded_arr)
   ```

2. **Binary File Input and Output**:
   
   ```python
   import numpy as np

   # Create an array
   arr = np.array([[1, 2, 3], [4, 5, 6]])

   # Save array to a binary file
   arr.tofile('array_data.bin')

   # Load array from a binary file
   loaded_arr = np.fromfile('array_data.bin', dtype=np.int32).reshape((2, 3))
   print(loaded_arr)
   ```

3. **NumPy Binary Format (.npy)**:
   
   ```python
   import numpy as np

   # Create an array
   arr = np.array([[1, 2, 3], [4, 5, 6]])

   # Save array to a .npy file
   np.save('array_data.npy', arr)

   # Load array from a .npy file
   loaded_arr = np.load('array_data.npy')
   print(loaded_arr)
   ```

4. **Compressed File Formats**:
   
   ```python
   import numpy as np

   # Create arrays
   arr1 = np.array([1, 2, 3])
   arr2 = np.array([4, 5, 6])

   # Save multiple arrays to a compressed .npz file
   np.savez('arrays_compressed.npz', arr1=arr1, arr2=arr2)

   # Load arrays from a compressed .npz file
   loaded_data = np.load('arrays_compressed.npz')
   loaded_arr1 = loaded_data['arr1']
   loaded_arr2 = loaded_data['arr2']
   print(loaded_arr1)
   print(loaded_arr2)
   ```

5. **Memory-Mapped Files**:
   
   ```python
   import numpy as np

   # Create a memory-mapped array
   arr = np.memmap('memory_mapped.bin', dtype=np.float64, mode='w+', shape=(3, 3))

   # Modify array data
   arr[:] = np.random.rand(3, 3)

   # Read array data
   print(arr)

   # Close the memory-mapped file
   del arr
   ```

## Database in python
In Python, you can interact with databases using various libraries such as SQLite, MySQL, PostgreSQL, or SQLAlchemy. Here's an overview of performing basic database operations including creating a database connection, creating tables, inserting, reading, updating, and deleting data (DML operations), as well as performing Data Definition Language (DDL) operations like creating and dropping tables.

### Creating Database Connection:
```python
import sqlite3

# Connect to SQLite database (creates a new one if not exists)
conn = sqlite3.connect('example.db')
```

### Creating Tables (DDL Operation):
```python
# Create a cursor object to execute SQL commands
cursor = conn.cursor()

# Define SQL command to create a table
create_table_sql = '''
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
'''

# Execute SQL command to create the table
cursor.execute(create_table_sql)

# Commit changes to the database
conn.commit()
```

### Inserting Data (DML Operation):
```python
# Define data to insert
user_data = [
    ('Alice', 25),
    ('Bob', 30),
    ('Charlie', 35)
]

# Define SQL command to insert data
insert_sql = 'INSERT INTO users (name, age) VALUES (?, ?)'

# Execute SQL command to insert data
cursor.executemany(insert_sql, user_data)

# Commit changes to the database
conn.commit()
```

### Reading Data (DML Operation):
```python
# Execute SQL command to select data
cursor.execute('SELECT * FROM users')

# Fetch all rows
rows = cursor.fetchall()

# Print fetched rows
for row in rows:
    print(row)
```

### Updating Data (DML Operation):
```python
# Define SQL command to update data
update_sql = 'UPDATE users SET age = ? WHERE name = ?'

# Execute SQL command to update data
cursor.execute(update_sql, (28, 'Alice'))

# Commit changes to the database
conn.commit()
```

### Deleting Data (DML Operation):
```python
# Define SQL command to delete data
delete_sql = 'DELETE FROM users WHERE name = ?'

# Execute SQL command to delete data
cursor.execute(delete_sql, ('Bob',))

# Commit changes to the database
conn.commit()
```

### Closing Database Connection:
```python
# Close cursor and connection
cursor.close()
conn.close()
```
