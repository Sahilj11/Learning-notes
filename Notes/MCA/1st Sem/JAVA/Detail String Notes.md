## Intro
- String is a non-primitive data-type
- String is a sequence of character (Array of characters)
- String is a class 
```java
public final String extends Object implements CharSequence,Serializable,Comparable{

}
```
- String is a immutable object
- There are 3 class to create String
	- String
	- StringBuffer
	- StringBuilder
## String Constant pool(String Literal pool)
- It is an area in heap memory where java stores String literal values
- ![[Pasted image 20231109122612.png]]
- if using constructor for string creation then 2 object is created 
- where as if using literal then only one object is created

## StringBuffer
In Java, both `String` and `StringBuffer` are classes used to work with strings, but they have differences in terms of mutability, performance, and usage.

### String

- **Immutable:** Strings in Java are immutable, meaning once a `String` object is created, its value cannot be changed. Any operation that seems to modify a `String` actually creates a new `String` object.
- **Performance:** Since `String` objects are immutable, performing operations like concatenation or substring creation results in the creation of new `String` objects, which can be inefficient in terms of memory usage and performance, especially when dealing with a large number of string manipulations.
- **Usage:** Strings are commonly used when you don't expect the value to change frequently, like representing fixed values such as names, addresses, etc.

Example:

```java
String str = "Hello";
str = str + " World"; // This creates a new String object
```

### StringBuffer

- **Mutable:** `StringBuffer` is mutable, allowing the content of the string to be changed after it's created without creating a new object. This means you can modify the content of a `StringBuffer` without creating new instances.
- **Performance:** Due to its mutability, `StringBuffer` is more efficient when performing a large number of string manipulations because it avoids creating new objects. It's optimized for concatenation and modification operations.
- **Usage:** `StringBuffer` is preferred when you need to perform a lot of string manipulations in scenarios where the value of the string might change frequently.

Example:

```java
StringBuffer stringBuffer = new StringBuffer("Hello");
stringBuffer.append(" World"); // Modifies the existing StringBuffer object
```

### Differences Summary

- `String` objects are immutable and cannot be changed once created. Operations on `String` create new objects.
- `StringBuffer` objects are mutable and can be changed without creating new objects. It's more efficient when dealing with frequent string modifications.

In modern Java, `StringBuffer` has been largely replaced by `StringBuilder`, which is similar in behavior but is not thread-safe. `StringBuilder` offers better performance in scenarios where thread safety is not a concern.

### Methods in StringBuffer
![[Pasted image 20231109123435.png]]

## StringBuilder
In Java, `StringBuilder` is another class used to work with strings, similar to `StringBuffer`. Both `StringBuilder` and `StringBuffer` have similarities, but they differ primarily in terms of synchronization and thread safety.

### StringBuilder

- **Mutable:** Like `StringBuffer`, `StringBuilder` is mutable, allowing the content of the string to be changed after it's created without creating a new object.
- **Performance:** `StringBuilder` is designed for single-threaded environments. It is not synchronized, which means it's not thread-safe. Therefore, it typically offers better performance in scenarios where thread safety is not a concern.
- **Usage:** `StringBuilder` is commonly used when you need a mutable sequence of characters in a single-threaded environment, and performance is a priority.

Example:

```java
StringBuilder stringBuilder = new StringBuilder("Hello");
stringBuilder.append(" World"); // Modifies the existing StringBuilder object
```

### StringBuffer

- **Mutable:** Similar to `StringBuilder`, `StringBuffer` is mutable, allowing changes to the string content without creating new objects.
- **Performance:** `StringBuffer` is designed for multi-threaded environments and is synchronized, making it thread-safe. Synchronization adds overhead, which might impact performance when compared to `StringBuilder`.
- **Usage:** `StringBuffer` is preferred in multi-threaded scenarios where multiple threads might access or modify the same string concurrently.

Example:

```java
StringBuffer stringBuffer = new StringBuffer("Hello");
stringBuffer.append(" World"); // Modifies the existing StringBuffer object
```

### Differences Summary

- `StringBuilder` is not thread-safe and provides better performance in single-threaded environments.
- `StringBuffer` is thread-safe due to its synchronized nature, making it suitable for multi-threaded environments but potentially impacting performance due to synchronization overhead.

Both `StringBuilder` and `StringBuffer` provide similar functionalities for manipulating strings. The choice between them depends on whether thread safety is necessary and the performance requirements of the specific application. In scenarios where thread safety isn't a concern, `StringBuilder` is generally preferred due to its better performance.