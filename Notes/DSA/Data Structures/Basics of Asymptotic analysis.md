## Brief intro
Asymptotic analysis is a technique used in computer science and mathematics to analyze the efficiency of algorithms and the performance of programs. It focuses on understanding how the time and space requirements of an algorithm or program grow as the size of the input data increases towards infinity. The primary goal of asymptotic analysis is to gain insights into the scalability of algorithms and to compare different algorithms to determine which one performs better for large inputs.

In asymptotic analysis, we typically express the performance characteristics of an algorithm using big O, big Omega, and big Theta notations. These notations provide a way to describe the upper bound, lower bound, and tight bound, respectively, on the growth rate of an algorithm's time complexity or space complexity as the input size increases.

The three main notations used in asymptotic analysis are as follows:

1. Big O notation (O): It represents the upper bound of an algorithm's growth rate. If an algorithm has a time complexity of O(f(n)), it means that the algorithm's running time will not exceed the value of f(n) for sufficiently large input n.

2. Big Omega notation (Ω): It represents the lower bound of an algorithm's growth rate. If an algorithm has a time complexity of Ω(g(n)), it means that the algorithm's running time will not be faster than the value of g(n) for sufficiently large input n.

3. Big Theta notation (Θ): It represents the tight bound of an algorithm's growth rate. If an algorithm has a time complexity of Θ(h(n)), it means that the algorithm's running time will be bounded both from above and below by the value of h(n) for sufficiently large input n.

Asymptotic analysis allows us to reason about the efficiency of algorithms without getting into the specifics of hardware or constant factors. It provides a high-level understanding of how the algorithms behave for large inputs and helps in making informed decisions when choosing the best algorithm for a particular problem.

## Efficiency 
- ![[Pasted image 20230720123057.png]]
- ![[Pasted image 20230720123141.png]]
When comparing the time complexity of different data structures, we typically consider the time required to perform common operations on those data structures. These operations can include insertion, deletion, searching, access, and traversal. By analyzing the time complexity of these operations, we can understand how the data structure performs in terms of efficiency for various tasks.

Here's an explanation of how time complexity comparisons are made based on common operations for different data structures:

1. Arrays:
   - Access (read/write by index): O(1) - Arrays have constant-time access since elements are stored in contiguous memory locations, and accessing an element by its index can be done directly.
   - Insertion/Deletion (at the beginning or middle): O(n) - Insertion or deletion at arbitrary positions requires shifting elements, resulting in a linear time complexity.
   - Insertion/Deletion (at the end if not dynamically resized): O(1) - Appending elements to the end of the array is constant time if there is enough space. However, if the array needs to be dynamically resized, it can take O(n) time occasionally.

2. Linked Lists:
   - Access (by index): O(n) - Linked lists do not support direct index-based access, so finding an element by index requires traversing from the head (or tail) node, which takes linear time.
   - Insertion/Deletion (at the beginning): O(1) - Insertion and deletion at the head of a linked list are constant time since it only involves adjusting a few pointers.
   - Insertion/Deletion (at the end if singly linked): O(n) - For singly linked lists, adding or removing elements at the tail requires traversing the entire list, resulting in linear time complexity.
   - Insertion/Deletion (at the end if doubly linked): O(1) - For doubly linked lists, adding or removing elements at the tail can be done in constant time with proper pointers adjustment.

3. Binary Search Trees (BSTs):
   - Search/Insertion/Deletion (on average for balanced BSTs): O(log n) - In balanced BSTs, search, insertion, and deletion operations have logarithmic time complexity as the tree height remains balanced.
   - Search/Insertion/Deletion (in worst-case for unbalanced BSTs): O(n) - If the BST becomes skewed, it can behave like a linked list, resulting in linear time complexity for search, insertion, and deletion.

4. Hash Tables:
   - Search/Insertion/Deletion (average case, with good hash function): O(1) - Hash tables offer constant time complexity for these operations on average when the hash function distributes keys uniformly.
   - Search/Insertion/Deletion (worst-case, with collisions): O(n) - In the worst case, multiple keys can collide, leading to linear time complexity.

5. Heaps:
   - Insertion/Deletion (insert and remove minimum/maximum): O(log n) - Heaps, like binary heaps or Fibonacci heaps, provide logarithmic time complexity for these operations.

These are just some examples, and the time complexity may vary based on specific implementations and scenarios. When comparing data structures, it's essential to consider the specific use case and the type of operations required to choose the most appropriate one for the given problem.

### How to find time complexity 
- input always greater or equal to 0
- here n is number of input
- ignore lower order terms
	- ![[Pasted image 20230720130443.png]]
	- take only n3 
- ignore the base of logs 
- 2n = O(n) , this means 2n is member of O(n) 
- function do more work for move input 
- drop all constants 
	- ![[Pasted image 20230720130238.png]]
- ![[Pasted image 20230720130337.png]]
- 1 , c  = constant time 
- logn - generally when we divide things in half or multiply by 2 (or any other number). like trees
- n - once per item
- n2  - compare all v all
- n! - traveling sales
### Why calculating time complexity in absolute terms is difficult 
Calculating the exact time complexity of an algorithm for all possible inputs is often not practical due to the following reasons:

1. Algorithm complexity depends on the input: The time complexity of an algorithm can vary based on the size and nature of the input data. Calculating the exact time complexity for all possible input cases can be extremely time-consuming or even impossible for algorithms with a large number of possible inputs.

2. Input size can be large: Some algorithms, especially those used for complex computational problems, may have input sizes that are too large to analyze exhaustively. For example, analyzing the time complexity of an algorithm with an input size of one billion elements would be impractical.

3. Complexity can be affected by external factors: The exact time complexity of an algorithm can be influenced by various external factors, such as hardware architecture, compiler optimizations, and memory hierarchy. Taking all these factors into account for an exact analysis becomes cumbersome.

4. Overhead from low-level operations: Many algorithms involve low-level operations that may not have constant time complexity. Considering these low-level operations in the analysis can make the exact time complexity calculations very intricate.

5. Focus on growth rate: Asymptotic analysis, which focuses on the growth rate of algorithms as the input size increases, provides a high-level understanding of performance without being overly concerned with the precise constants or lower-order terms in the time complexity equation. Asymptotic analysis allows us to compare algorithms more easily and make decisions based on their scalability.

Instead of calculating the exact time complexity, computer scientists often use asymptotic analysis with big O, big Omega, and big Theta notations to represent the upper bound, lower bound, and tight bound of an algorithm's time complexity, respectively. This provides a simplified way to compare algorithms' efficiency and allows them to make informed decisions without the need for precise measurements for all possible inputs. Asymptotic analysis is a powerful tool to reason about algorithm efficiency and is widely used in practice to evaluate and compare different algorithms.

### Running time and size of input
![[Pasted image 20230720124504.png]]
- therefore if the size of input is n, then f(n) is a function of n denotes the time complexity
- in other words , f(n) represent the number of instructions executed for input value n.
- ![[Pasted image 20230720124718.png]]
- ![[Pasted image 20230720125011.png]]

### Big O notation
![[Pasted image 20230720125254.png]]
