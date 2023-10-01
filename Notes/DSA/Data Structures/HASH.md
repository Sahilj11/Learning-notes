## What is set
a set is a well-defined collection of distinct objects, considered as an object in its own right.

## Difference b/w set and array
A set and an array are both data structures used in computer programming, but they have distinct characteristics and purposes. Here are the main differences between sets and arrays:

1. Data Type:
   - Array: An array is a collection of elements of the same data type that are stored in contiguous memory locations. Elements in an array are accessed using an index, which is typically an integer.
   - Set: A set is a collection of unique elements, and it does not allow duplicate values. Sets are typically used to store and manage distinct values, and they don't rely on indexes for element access.

2. Order:
   - Array: In most programming languages, arrays maintain the order of elements. You can access elements in an array by their index, and the order of elements is important.
   - Set: Sets do not guarantee any specific order of elements. Elements are stored in a way that allows for efficient membership checks and uniqueness, but you cannot rely on the order in which elements were added.

3. Duplicates:
   - Array: Arrays can contain duplicate values, meaning the same value can appear multiple times in an array.
   - Set: Sets are designed to store distinct values only. If you attempt to add a duplicate value to a set, it will not be added, as sets automatically eliminate duplicates.

4. Operations:
   - Array: Arrays support operations like adding elements, removing elements, and accessing elements by index. They are suitable for scenarios where the order of elements matters, and you need to work with duplicates.
   - Set: Sets are primarily used for operations related to checking membership (whether an element is present in the set), adding unique elements, and removing elements. Sets are efficient for ensuring uniqueness and testing for the presence of specific values.

5. Use Cases:
   - Array: Arrays are commonly used when you need to store a collection of elements with a specific order, and duplicates are allowed. They are suitable for scenarios where you need direct access to elements by index.
   - Set: Sets are used when you want to store a collection of unique elements, and the order of elements is not important. Sets are helpful in scenarios like checking for unique values, filtering out duplicates, and performing set operations (e.g., union, intersection, difference).

In summary, arrays are used for ordered collections of elements with possible duplicates, while sets are used for unordered collections of unique elements. The choice between them depends on your specific programming needs and the characteristics of the data you are working with.

## Hashset
- complexity:-
	- add, remove,contains - O(1)
	- 