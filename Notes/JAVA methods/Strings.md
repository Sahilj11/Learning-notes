Certainly! Here are 20 important methods for working with strings in Java, along with code examples:

1. **Creating a String**:

   ```java
   String str = "Hello, World!";
   ```

2. **Getting the Length**:

   ```java
   int length = str.length();
   ```

3. **Concatenation**:

   ```java
   String concatStr = str.concat(" Welcome");
   ```

4. **Substring**:

   ```java
   String subStr = str.substring(7); // "World!"
   String subStr2 = str.substring(0, 5); // "Hello"
   ```

5. **Trimming**:

   ```java
   String trimmedStr = "   Trim Me   ".trim(); // "Trim Me"
   ```

6. **String Comparison**:

   ```java
   boolean isEqual = str.equals("Hello, World!");
   boolean isIgnoreCaseEqual = str.equalsIgnoreCase("hello, world!");
   ```

7. **String Searching**:

   ```java
   boolean contains = str.contains("World"); // true
   int indexOf = str.indexOf("World"); // 7
   int lastIndexOf = str.lastIndexOf("o"); // 8
   ```

8. **Replacing**:

   ```java
   String replacedStr = str.replace("World", "Universe");
   ```

9. **Converting to Uppercase/Lowercase**:

   ```java
   String upperCaseStr = str.toUpperCase();
   String lowerCaseStr = str.toLowerCase();
   ```

10. **Checking for Empty or Null**:

    ```java
    boolean isEmpty = str.isEmpty(); // false
    boolean isNull = str == null;
    ```

11. **Checking Prefix and Suffix**:

    ```java
    boolean startsWith = str.startsWith("Hello"); // true
    boolean endsWith = str.endsWith("!"); // true
    ```

12. **Splitting**:

    ```java
    String[] parts = str.split(", "); // ["Hello", "World!"]
    ```

13. **Joining Strings**:

    ```java
    String[] words = {"Hello", "World!"};
    String joinedStr = String.join(", ", words); // "Hello, World!"
    ```

14. **Converting to Character Array**:

    ```java
    char[] charArray = str.toCharArray();
    ```

15. **Formatting with `String.format`**:

    ```java
    int age = 30;
    String formattedStr = String.format("I am %d years old.", age);
    ```

16. **Checking for Prefix/Suffix with `startsWith` and `endsWith`**:

    ```java
    boolean startsWith = str.startsWith("Hello"); // true
    boolean endsWith = str.endsWith("!"); // true
    ```

17. **Comparing Strings Lexicographically**:

    ```java
    int compareTo = str.compareTo("Hello, Java!"); // Negative value means less, 0 means equal, positive means greater
    ```

18. **Converting to a Character at a Specific Index**:

    ```java
    char charAtIndex = str.charAt(7); // 'W'
    ```

19. **Checking for Substring Existence**:

    ```java
    boolean containsSubstr = str.contains("World"); // true
    ```

20. **Converting to a String from Other Types**:

    ```java
    int number = 42;
    String strFromInt = Integer.toString(number);
    double pi = 3.14159265359;
    String strFromDouble = Double.toString(pi);
    ```

These are some of the commonly used methods for working with strings in Java. Remember that strings in Java are immutable, so methods like `concat`, `replace`, and `toUpperCase` return new string instances rather than modifying the original string.