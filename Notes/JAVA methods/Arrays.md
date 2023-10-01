Certainly! Here are 20 important methods for working with arrays in Java, along with code examples:

1. **Declaration and Initialization**:

   ```java
   int[] numbers = {1, 2, 3, 4, 5};
   ```

2. **Accessing Elements**:

   ```java
   int firstElement = numbers[0];
   ```

3. **Length of Array**:

   ```java
   int length = numbers.length;
   ```

4. **Looping Through Array**:

   ```java
   for (int i = 0; i < numbers.length; i++) {
       System.out.print(numbers[i] + " ");
   }
   ```

5. **Enhanced For Loop** (for-each):

   ```java
   for (int num : numbers) {
       System.out.print(num + " ");
   }
   ```

6. **Sorting Array**:

   ```java
   Arrays.sort(numbers);
   ```

7. **Searching in Array**:

   ```java
   int index = Arrays.binarySearch(numbers, 3);
   ```

8. **Copying Arrays**:

   ```java
   int[] copy = Arrays.copyOf(numbers, numbers.length);
   ```

9. **Filling Array**:

   ```java
   Arrays.fill(numbers, 0); // Fills array with 0
   ```

10. **Comparing Arrays**:

    ```java
    boolean isEqual = Arrays.equals(numbers1, numbers2);
    ```

11. **Concatenating Arrays**:

    ```java
    int[] combined = Arrays.copyOf(numbers1, numbers1.length + numbers2.length);
    System.arraycopy(numbers2, 0, combined, numbers1.length, numbers2.length);
    ```

12. **Resizing an Array** (Note: Arrays are fixed size, so a new one must be created):

    ```java
    int[] resizedArray = Arrays.copyOf(numbers, newLength);
    ```

13. **Checking for Element Existence**:

    ```java
    boolean containsElement = Arrays.asList(numbers).contains(3);
    ```

14. **Finding Minimum and Maximum**:

    ```java
    int min = Arrays.stream(numbers).min().getAsInt();
    int max = Arrays.stream(numbers).max().getAsInt();
    ```

15. **Converting Array to String**:

    ```java
    String arrayAsString = Arrays.toString(numbers);
    ```

16. **Copying Range of Elements**:

    ```java
    int[] subArray = Arrays.copyOfRange(numbers, startIndex, endIndex);
    ```

17. **Removing an Element** (Arrays are fixed size, so a new one must be created):

    ```java
    int[] newArray = new int[numbers.length - 1];
    System.arraycopy(numbers, 0, newArray, 0, index);
    System.arraycopy(numbers, index + 1, newArray, index, numbers.length - index - 1);
    ```

18. **Checking for Empty Array**:

    ```java
    boolean isEmpty = numbers.length == 0;
    ```

19. **Finding Index of an Element**:

    ```java
    int index = Arrays.asList(numbers).indexOf(3);
    ```

20. **Summing Array Elements**:

    ```java
    int sum = Arrays.stream(numbers).sum();
    ```

Remember to import `java.util.Arrays` when using these methods. Arrays in Java are zero-indexed, so the first element is at index 0, the second at index 1, and so on.