# Unit 1
Here are some notes on the topics you mentioned:

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
