In Java, a wrapper class is a class that allows you to encapsulate primitive data types (such as int, char, boolean, etc.) into objects. These wrapper classes provide a way to work with primitive data types as if they were objects, which is useful in situations where objects are required, such as when using certain Java libraries or working with collections.

Java provides a set of predefined wrapper classes for each primitive data type. Here are the primitive data types and their corresponding wrapper classes:

1. `int` - `Integer`
2. `char` - `Character`
3. `boolean` - `Boolean`
4. `double` - `Double`
5. `float` - `Float`
6. `long` - `Long`
7. `short` - `Short`
8. `byte` - `Byte`

For example, if you need to store an integer in a collection like an ArrayList, you would use the `Integer` wrapper class instead of the primitive `int` type. Here's a simple example:

```java
import java.util.ArrayList;

public class WrapperExample {
    public static void main(String[] args) {
        // Using the Integer wrapper class
        Integer num = new Integer(42); // Wrapping the primitive int
        ArrayList<Integer> numList = new ArrayList<>();
        numList.add(num);

        // Autoboxing: Automatically converting int to Integer
        int value = 17;
        Integer wrappedValue = value; // Automatically wrapped (autoboxed)

        // Unboxing: Converting Integer back to int
        int unwrappedValue = wrappedValue; // Automatically unwrapped (unboxed)
    }
}
```

In modern Java, there's a concept called "autoboxing" and "unboxing" that simplifies the conversion between primitive types and their corresponding wrapper classes. With autoboxing, you can assign a primitive value to a wrapper class instance without explicitly creating the instance. Similarly, with unboxing, you can extract the primitive value from a wrapper class instance without explicitly calling a method.

Wrapper classes also provide various methods for converting, comparing, and manipulating primitive values. They are particularly useful when working with Java collections, generics, and libraries that expect objects rather than primitive types.

## Autoboxing and unboxing 
Autoboxing and unboxing are Java language features introduced in Java 5 that simplify the process of converting between primitive data types and their corresponding wrapper classes (reference types). They make code more concise and reduce the need for explicit conversions, making it easier to work with collections and other APIs that expect objects. Let's explore these concepts with examples and also discuss the paradigm before their introduction.

1. **Autoboxing:**
Autoboxing is the automatic conversion of a primitive type into its corresponding wrapper class. When you assign a primitive value to a wrapper class, autoboxing automatically converts the primitive value to an object of the wrapper class.

Example:
```java
// Before autoboxing
Integer i = new Integer(42); // Wrapping
int j = i.intValue(); // Unwrapping

// With autoboxing
Integer num = 42; // Autoboxing (int to Integer)
```

2. **Unboxing:**
Unboxing is the automatic conversion of a wrapper class object into its corresponding primitive type. When you retrieve a value from a wrapper class, unboxing automatically converts the object back to a primitive value.

Example:
```java
// Before unboxing
Integer num = new Integer(42); // Wrapping
int value = num.intValue(); // Unwrapping

// With unboxing
Integer wrappedValue = 17;
int unwrappedValue = wrappedValue; // Unboxing (Integer to int)
```

Before the introduction of autoboxing and unboxing, developers had to manually perform conversions between primitive types and wrapper classes using methods provided by the wrapper classes. This was more verbose and error-prone.

Before autoboxing and unboxing:
```java
Integer num = new Integer(42); // Wrapping
int value = num.intValue(); // Unwrapping

// Adding an int to a List<Integer> required explicit wrapping
List<Integer> numbers = new ArrayList<>();
numbers.add(new Integer(5));

// Extracting an int from a List<Integer> required explicit unwrapping
int extractedValue = numbers.get(0).intValue();
```

The introduction of autoboxing and unboxing made code cleaner and more intuitive:

With autoboxing and unboxing:
```java
Integer num = 42; // Autoboxing
int value = num; // Unboxing

List<Integer> numbers = new ArrayList<>();
numbers.add(5); // Autoboxing automatically

int extractedValue = numbers.get(0); // Unboxing automatically
```

Overall, autoboxing and unboxing improve code readability and reduce the likelihood of errors related to manual conversions. However, it's important to be aware of potential performance implications when using autoboxing excessively in performance-critical sections of code, as it can lead to unnecessary object creation and memory overhead.

## Application 
Wrapper classes in Java have various applications that revolve around converting primitive data types into objects (instances of these wrapper classes). These applications are particularly useful in scenarios where you need to work with collections, generic types, and APIs that expect objects instead of primitive types. Here are some common applications of wrapper classes:

1. **Collections and Generics:**
   Wrapper classes are often used in collections like ArrayList, LinkedList, HashSet, etc., which can only store objects, not primitive types. When you need to store primitive values in these collections, you use wrapper classes to wrap the primitives into objects.

   ```java
   ArrayList<Integer> numbers = new ArrayList<>();
   numbers.add(42); // Autoboxing - int to Integer
   ```

2. **Method Overloading:**
   In situations where you have overloaded methods with different parameter types, using wrapper classes can help in eliminating ambiguity and making the code more readable.

   ```java
   void processValue(int value) {
       // ...
   }
   
   void processValue(Integer value) {
       // ...
   }
   ```

3. **APIs and Libraries:**
   Many libraries and APIs in Java expect objects rather than primitive types. Wrapper classes allow you to seamlessly use primitive values with these APIs.

4. **Nullable Values:**
   Wrapper classes can represent nullable values since they can hold null references. This is particularly useful when you need to differentiate between an actual value and the absence of a value.

   ```java
   Integer nullableValue = null;
   ```

5. **Parsing and Conversion:**
   Wrapper classes provide methods for parsing and converting string representations of data into their corresponding primitive types and vice versa.

   ```java
   int intValue = Integer.parseInt("123"); // Parsing string to int
   String stringValue = Integer.toString(456); // Converting int to string
   ```

6. **Passing by Reference:**
   While Java is a "pass-by-value" language, when you pass a wrapper class object, you are effectively passing a reference to the object. This can be useful in certain scenarios where you want to modify the value within a method and have the change reflected outside the method.

   ```java
   void modifyValue(Integer value) {
       value++; // The change will be reflected outside the method
   }
   ```

7. **Working with Libraries:**
   Many external libraries and APIs that Java interfaces with might use objects and expect specific types. Using wrapper classes allows smooth integration with such libraries.

Overall, wrapper classes provide a bridge between primitive data types and object-oriented programming, making it possible to work with primitives in contexts where objects are required. They enhance the flexibility and functionality of Java code by enabling interoperability between different data types and programming paradigms.