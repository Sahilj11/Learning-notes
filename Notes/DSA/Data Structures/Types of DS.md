### Linear DS 
- elements are arranged in linear (sequential )order
- or if each element have one predecessor and one successor 
![[Pasted image 20230720122635.png]]

### Non-Linear DS
- when all elements are not arranged in a linear order
![[Pasted image 20230720122741.png]]
### Static Data structures
- memory is allocated at compile time . therefore max size is fixed 
- like Array
- +ve :-  FAST ACCESS
- -ve:- slow insertion and deletion

### Dynamic Data structure
- memory is allocated at run time , therefore maximum size is flexible
- ![[Pasted image 20230720122922.png]]
## Queues
A queue is a fundamental data structure that follows the First-In-First-Out (FIFO) principle, which means that the first element added to the queue will be the first one to be removed. Think of a queue as a line of people waiting at a ticket counter or a queue of tasks waiting to be processed.

In a queue, elements are inserted at the rear (also known as the "enqueue" operation) and removed from the front (also known as the "dequeue" operation). The rear represents the end of the queue where new elements are added, and the front represents the beginning of the queue where elements are removed.

Basic Operations of a Queue:
1. **Enqueue**: Adding an element to the rear of the queue.
2. **Dequeue**: Removing the element from the front of the queue.
3. **Front**: Retrieving the element at the front of the queue without removing it.
4. **Rear**: Retrieving the element at the rear of the queue without removing it.
5. **IsEmpty**: Checking if the queue is empty.
6. **Size**: Getting the number of elements currently in the queue.

Illustration of a Queue:
Let's imagine a queue represented by a list of integers: [5, 9, 3, 7]

Initially, the front is at index 0 (5), and the rear is at index 3 (7).

- Enqueue(2): [5, 9, 3, 7, 2]  (2 is added to the rear)
- Enqueue(8): [5, 9, 3, 7, 2, 8]  (8 is added to the rear)

Now the front is still at index 0 (5), and the rear is at index 5 (8).

- Dequeue(): [9, 3, 7, 2, 8]  (5 is removed from the front)

Now the front is at index 1 (9), and the rear is at index 5 (8).

Key Points:
- Queues maintain the order in which elements are added, making them suitable for scenarios where the order of processing matters.
- The most recent element added is called the "rear," and the oldest element (first to be removed) is called the "front."
- Queues can be implemented using arrays or linked lists. Linked lists are more efficient for large queues since they allow constant time complexity for both enqueue and dequeue operations.
- Queues are commonly used in various algorithms, such as breadth-first search (BFS) and managing task scheduling in operating systems.

Example Use Cases:
1. Print queue: Printing tasks are added to the queue and processed in the order they are received.
2. CPU task scheduling: Processes in the ready state are placed in a queue and executed in the order they arrive.
3. Breadth-First Search: In graph traversal, a queue is used to visit nodes level by level.

Keep in mind that the efficiency of queue operations depends on the underlying implementation. For performance-critical applications, choosing an appropriate data structure and implementation is essential.

## Stack
A stack is a fundamental data structure that follows the Last-In-First-Out (LIFO) principle, which means that the last element added to the stack will be the first one to be removed. Think of a stack as a stack of plates in a cafeteria, where you can only add or remove plates from the top.

In a stack, elements are inserted and removed from the same end, often referred to as the "top" of the stack. The top represents the location where new elements are added or the location from which elements are removed.

Basic Operations of a Stack:
1. **Push**: Adding an element to the top of the stack.
2. **Pop**: Removing the element from the top of the stack.
3. **Top/Peek**: Retrieving the element at the top of the stack without removing it.
4. **IsEmpty**: Checking if the stack is empty.
5. **Size**: Getting the number of elements currently in the stack.

Illustration of a Stack:
Let's imagine a stack represented by a list of integers: [3, 7, 1]

Initially, the top is at index 2 (1).

- Push(5): [3, 7, 1, 5] (5 is added to the top)
- Push(9): [3, 7, 1, 5, 9] (9 is added to the top)

Now the top is at index 4 (9).

- Pop(): [3, 7, 1, 5] (9 is removed from the top)

Now the top is at index 3 (5).

Key Points:
- Stacks maintain the order in which elements are added, making them suitable for scenarios where the order of processing matters, but in reverse compared to a queue.
- The most recently added element is called the "top," and the oldest element (first to be removed) is at the bottom of the stack.
- Stacks can be implemented using arrays or linked lists. Linked lists are more efficient for large stacks since they allow constant time complexity for both push and pop operations.
- Stacks are commonly used in various algorithms and programming scenarios, such as function calls (using the call stack) and expression evaluation.

Example Use Cases:
1. Function Calls: When a function is called, its context (local variables and return address) is pushed onto the call stack. When the function returns, its context is popped from the stack.
2. Expression Evaluation: Stacks can be used to evaluate mathematical expressions, such as converting infix expressions to postfix notation and then evaluating them.
3. Undo/Redo functionality in text editors or software applications: Stacks can be used to store the history of operations, allowing users to undo or redo actions.

Keep in mind that the efficiency of stack operations depends on the underlying implementation. For performance-critical applications, choosing an appropriate data structure and implementation is essential.

## Linked List
A linked list is a data structure used to organize and store a collection of elements called nodes. Each node contains two main parts: the data it holds and a reference (or pointer) to the next node in the sequence. The organization of nodes through these references creates a linear data structure.

The most basic form of a linked list is a singly linked list, where each node points only to the next node in the list. However, there are variations like doubly linked lists (nodes pointing to both the next and previous nodes) and circular linked lists (the last node points back to the first node).

Here's a detailed explanation of a singly linked list:

1. Node:
   - A node is the fundamental building block of a linked list.
   - It contains two parts:
     - Data: This is the value or payload that the node holds. It can be any data type, such as integers, characters, objects, etc.
     - Next pointer: This is a reference to the next node in the linked list. In other words, it holds the memory address of the next node.
   - The last node of the list typically has its "Next" pointer set to NULL (or None in some programming languages) to indicate the end of the list.

2. Head:
   - The head is a special pointer that points to the first node in the linked list.
   - It allows us to access the list's elements and traverse the list.

3. Operations on Linked List:
   - Insertion: Adding a new node to the linked list.
   - Deletion: Removing a node from the linked list.
   - Searching: Finding a specific node in the linked list.
   - Traversing: Iterating through the linked list to access all nodes.

4. Advantages of Linked Lists:
   - Dynamic size: Linked lists can grow or shrink in size during program execution, unlike arrays with fixed sizes.
   - Efficient insertion and deletion: Insertion and deletion of nodes can be more efficient in linked lists compared to arrays.
   - Memory allocation: Linked lists can utilize memory more efficiently, as they can occupy non-contiguous memory locations.

5. Disadvantages of Linked Lists:
   - Sequential access: Random access is not as efficient as in arrays because to access an element, you need to traverse the list from the head.
   - Extra memory: Each node in the linked list requires additional memory to store the reference to the next node.

Example of a singly linked list:
Let's say we have a linked list to store integers: 7 -> 14 -> 21 -> 28 -> NULL

- Each node has an integer value (7, 14, 21, 28) and a reference to the next node.
- The head points to the first node (7).
- The last node (28) points to NULL, indicating the end of the list.

Linked lists are fundamental data structures used in various applications, including implementing stacks, queues, hash tables, and dynamic memory allocation in programming languages. Understanding linked lists is crucial for every computer scientist or software developer.

## Trees
Trees are a hierarchical data structure that consists of nodes connected by edges, forming a branching structure. Each tree has a root node, which is the topmost node in the hierarchy, and each node can have zero or more child nodes. Nodes with no children are called leaf nodes. Trees are widely used in computer science and other fields for organizing and representing data efficiently.

Here are some key terms related to trees:

1. Node: A basic unit of a tree that holds data and points to its child nodes (if any). It may also have a reference to its parent node (except for the root node).

2. Root: The topmost node in the tree, serving as the starting point for traversal.

3. Child: A node directly connected to another node, moving away from the root.

4. Parent: The node directly connected to a child node.

5. Sibling: Nodes that share the same parent.

6. Leaf: A node that has no children.

7. Depth: The number of edges from the root to a particular node.

8. Height: The maximum depth of any node in the tree (distance from the root to the deepest leaf).

Let's look at an example to illustrate a tree data structure:

```
        A
      /   \
     B     C
    / \   / \
   D   E F   G
            / \
           H   I
```

In this example, 'A' is the root node. It has two child nodes, 'B' and 'C'. Node 'B' has two children, 'D' and 'E', and node 'C' has two children, 'F' and 'G'. Node 'G' has two children, 'H' and 'I', making them leaf nodes as they have no children.

Now, let's see how a tree can be implemented in code using a common representation:

```python
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.children = []  # List to store child nodes

# Creating the tree from the example
root_node = TreeNode('A')

# Creating child nodes for 'A'
node_b = TreeNode('B')
node_c = TreeNode('C')
root_node.children = [node_b, node_c]

# Creating child nodes for 'B'
node_d = TreeNode('D')
node_e = TreeNode('E')
node_b.children = [node_d, node_e]

# Creating child nodes for 'C'
node_f = TreeNode('F')
node_g = TreeNode('G')
node_c.children = [node_f, node_g]

# Creating child nodes for 'G'
node_h = TreeNode('H')
node_i = TreeNode('I')
node_g.children = [node_h, node_i]
```

With this implementation, you can traverse the tree using various algorithms like depth-first traversal (pre-order, in-order, post-order) or breadth-first traversal. These algorithms allow you to visit and process nodes in different orders depending on your requirements.

Trees are used in various applications, such as file systems, hierarchical data representations, network routing algorithms, decision trees in machine learning, and much more. Their efficient hierarchical structure makes them a fundamental data structure in computer science.

## Hashing and Hash Table
#### Hash table
A hash table is a data structure that stores key-value pairs and provides efficient insertion, deletion, and retrieval operations. It is also known as a hash map or associative array in some programming languages. The primary idea behind a hash table is to use a hash function to convert a given key into an index or a "hash code," which is used to quickly locate the corresponding value in the underlying data structure.

The key components of a hash table are as follows:

1. Hash Function: A hash function takes a key as input and produces a hash code (or hash value) as output. The purpose of the hash function is to map keys to specific indices within the hash table. A good hash function should uniformly distribute the keys across the available indices to minimize collisions and maximize efficiency.

2. Array or Buckets: The hash table typically uses an array or a collection of "buckets" to store the key-value pairs. Each bucket is associated with an index and can hold one or more key-value pairs.

3. Collision Handling: Since multiple keys may hash to the same index (hash collision), collision handling mechanisms are employed to resolve this issue. Common collision resolution techniques include using linked lists, open addressing, or other data structures to store multiple key-value pairs that map to the same index.

The key operations supported by a hash table are:

- Insertion: To add a key-value pair to the hash table, the hash function is used to calculate the index for the key, and the key-value pair is then placed in the corresponding bucket.

- Retrieval: To retrieve a value associated with a given key, the hash function is applied to the key to find its index, and the value is then retrieved from the appropriate bucket.

- Deletion: To remove a key-value pair from the hash table, the hash function is used to determine the index of the key, and then the pair is deleted from the corresponding bucket.

The key advantage of a hash table is its efficiency in providing constant-time (O(1)) average-case complexity for insertion, retrieval, and deletion operations when the hash function distributes keys evenly and collisions are minimized. However, in the worst case, when many collisions occur, the time complexity may degrade to O(n) (linear time). Therefore, choosing a good hash function and appropriate collision resolution strategy is critical to maintaining the hash table's performance.

#### Hashing 
Hashing is a technique used to map data to a fixed-size array (or table) called a hash table. The main purpose of hashing is to quickly retrieve data from a large collection based on a unique identifier, known as a key. It is widely used in computer science for implementing data structures like hash tables, hash sets, and hash maps, as well as for security purposes, such as in cryptographic algorithms.

Hashing involves using a hash function that takes an input (often the key) and generates a fixed-size output, known as the hash value or hash code. This hash value is used as an index to store and retrieve the associated data in the hash table. The hash function should be efficient and produce a nearly uniform distribution of hash codes to minimize collisions (different keys generating the same hash code).

The hash table is a data structure that consists of an array of fixed size, along with a set of operations to store, retrieve, and remove data efficiently. Each element in the array, also known as a bucket, can hold one or more key-value pairs. When you want to store data with a specific key in the hash table, you pass the key through the hash function to get its hash code. Then, the data is stored in the corresponding bucket, based on the hash code.

To retrieve data from the hash table, you use the same key, pass it through the hash function to get the hash code, and then access the appropriate bucket to find the data associated with that key.

Collisions can occur in hash tables when two different keys produce the same hash code. There are different strategies to handle collisions, like:

1. Separate Chaining: Each bucket in the hash table contains a linked list or other data structure to store multiple key-value pairs with the same hash code.

2. Open Addressing: When a collision occurs, the algorithm searches for the next available bucket in a specific sequence until it finds an empty one to store the data.

3. Robin Hood Hashing: An open-addressing technique that tries to minimize the variance in the number of probes for each key.

Now let's summarize the main differences between hashing and a hash table:

Hashing:
- Hashing is a technique used to map data to a fixed-size hash code.
- It involves using a hash function that converts input data into a unique hash code.
- The primary purpose is to produce a fixed-size representation of the data (hash code) for efficient data retrieval and comparison.
- Hashing is a general concept and is not limited to any specific data structure.

Hash Table:
- A hash table is a data structure that uses hashing to store and retrieve data efficiently.
- It consists of an array (or buckets) and a set of operations to store, retrieve, and remove data using keys.
- The array size is determined during the hash table's creation and remains fixed unless the table is resized.
- It deals with collisions (two different keys producing the same hash code) by using techniques like separate chaining or open addressing.

In summary, hashing is the process of generating a fixed-size representation (hash code) of data, while a hash table is a specific data structure that uses hashing to efficiently store and retrieve data based on unique keys.

#### Chaining and open addressing 
Chaining in a hash table is a collision resolution technique used to handle situations where two different keys produce the same hash code (hash collision). When a collision occurs, instead of overwriting the existing value in the bucket, chaining allows multiple key-value pairs to be stored in the same bucket. Each bucket in the hash table contains a linked list or another data structure (e.g., a dynamic array) that can hold multiple key-value pairs.

Here's how chaining works in a hash table:

1. Hash Function: The input key is passed through a hash function to generate a hash code. This hash code is used to determine the bucket where the key-value pair will be stored.

2. Collision Handling: If two different keys produce the same hash code and need to be stored in the same bucket, the new key-value pair is simply added to the linked list or data structure associated with that bucket. This way, multiple key-value pairs can coexist in the same bucket.

3. Retrieval: When you want to retrieve data associated with a particular key, the hash function is applied to the key to find the appropriate bucket. Then, the linked list or data structure in that bucket is traversed to find the key-value pair with the matching key.

Chaining is a form of open hashing, where the data that collides with the same hash code is stored separately, outside the main array structure. Therefore, it is not the same as "closed addressing," which is a synonym for open addressing.

Open addressing, on the other hand, is another collision resolution technique used in hash tables. In open addressing, when a collision occurs (two different keys produce the same hash code), the algorithm searches for the next available (unoccupied) bucket in a specific sequence, called the probing sequence. The data is then stored in the first available empty bucket along this sequence.

There are different variations of open addressing:

1. Linear Probing: In linear probing, the algorithm checks the next consecutive bucket if the current one is already occupied. The probing sequence is simply +1 from the current bucket's index.

2. Quadratic Probing: Quadratic probing uses a quadratic function to calculate the next bucket to check. The probing sequence is +1, +4, +9, +16, and so on.

3. Double Hashing: Double hashing uses a secondary hash function to calculate the step size for probing. The probing sequence is determined by both the initial hash code and the secondary hash code.

Unlike chaining, open addressing stores all the key-value pairs directly in the main array structure. When a collision occurs, the algorithm searches for alternative positions within this array to store the data.

Both chaining and open addressing are techniques used to handle collisions in hash tables. The choice between them depends on the specific use case, the expected number of collisions, and the desired performance characteristics. Chaining is more memory-efficient as it doesn't require extra space for storing secondary structures, but it may result in slower lookups due to traversing linked lists. Open addressing can have better cache performance and reduced memory overhead, but it may suffer from clustering issues and decreased performance under heavy loads.

#### Open vs Close addressing 
The main difference between closed addressing and open addressing lies in how they handle collisions in a hash table.

1. Closed Addressing (Chaining):

- Also known as "separate chaining."
- In closed addressing, when a collision occurs (two different keys produce the same hash code), the new key-value pair is simply added to a linked list or another data structure associated with the corresponding bucket.
- Each bucket in the hash table contains a linked list or a dynamic array that can hold multiple key-value pairs with the same hash code.
- The data that collides with the same hash code is stored separately, outside the main array structure.
- Retrieval involves using the hash function to find the appropriate bucket and then traversing the linked list or data structure in that bucket to find the key-value pair with the matching key.
- Closed addressing is more memory-efficient because it does not require additional space for storing secondary structures.
- However, it may result in slower lookups due to traversing linked lists or data structures when multiple key-value pairs share the same bucket.

2. Open Addressing:

- In open addressing, when a collision occurs (two different keys produce the same hash code), the algorithm searches for the next available (unoccupied) bucket in a specific sequence, called the probing sequence.
- All the key-value pairs are stored directly in the main array structure itself.
- The probing sequence is determined based on the initial hash code and can involve linear probing, quadratic probing, double hashing, etc.
- The goal of open addressing is to find an alternative position within the main array to store the data when a collision occurs.
- Retrieval involves using the hash function to find the initial bucket and then applying the probing sequence to locate the key-value pair with the matching key.
- Open addressing can have better cache performance and reduced memory overhead compared to closed addressing because it stores all data in the main array.
- However, open addressing may suffer from clustering issues, where consecutive buckets get filled with data, leading to decreased performance under heavy loads.

In summary, the primary distinction between closed addressing (chaining) and open addressing is in how they handle hash collisions. Closed addressing stores colliding data separately in secondary structures (linked lists or arrays), while open addressing finds alternative positions within the main array to store the data when a collision occurs. Each approach has its advantages and disadvantages, and the choice between them depends on the specific use case and performance requirements.

##### Open addressing collison resolution 
Linear Probing, Quadratic Probing, and Double Hashing are all collision resolution techniques used in hash tables to handle situations when two or more keys map to the same hash index (hash collision). These techniques determine alternative positions for inserting or searching elements when a collision occurs.

1. Linear Probing:
Linear probing is a simple collision resolution technique where, when a collision occurs, the algorithm looks for the next available (unoccupied) slot in the hash table by linearly probing through the slots one by one until an empty slot is found. The probing sequence is usually in a linear fashion, hence the name.

For example, if the initial hash index for a key collides with another key's index, the algorithm will try the next index, and if that is also occupied, it will move to the subsequent index, and so on, until an empty slot is found.

Linear probing has the advantage of simplicity, but it can lead to clustering, where consecutive elements end up clustered together, increasing the likelihood of further collisions and reducing the hash table's efficiency. It can also cause performance degradation when the table becomes densely filled.

2. Quadratic Probing:
Quadratic probing is another collision resolution technique that aims to reduce clustering by using a quadratic function to determine the next probing position when a collision occurs. Instead of linearly searching for the next available slot, quadratic probing uses a quadratic function to calculate a new offset from the original hash index.

The probing sequence is given by:

HashIndex = (InitialHashIndex + c1 * i + c2 * i^2) % TableSize

where "InitialHashIndex" is the initial hash index for the key, "i" is the iteration number (0, 1, 2, ...), and "c1" and "c2" are constants that help generate a different sequence of positions.

Quadratic probing spreads out the search across the hash table more effectively than linear probing, but it still suffers from clustering, albeit to a lesser extent.

3. Double Hashing:
Double hashing is a more advanced collision resolution technique that uses a second hash function to calculate an offset when a collision occurs. The secondary hash function calculates a new probe offset, and the algorithm then searches for an available slot at the next position given by the sum of the original hash index and the offset.

The probing sequence is given by:

HashIndex = (InitialHashIndex + i * SecondaryHash(Key)) % TableSize

The idea behind double hashing is that it produces a more random and evenly distributed sequence of probing positions, reducing clustering and improving the overall performance of the hash table.

Each of these collision resolution techniques has its advantages and trade-offs, and the choice between them depends on the specific requirements of the application and the characteristics of the keys being hashed.

"Plus 3 rehash" is a specific variation of the linear probing collision resolution technique used in hash tables. It is also known as "open addressing with a fixed increment" or "linear probing with constant increment."

In regular linear probing, when a collision occurs, the algorithm increments the hash index by a fixed value (usually 1) to find the next available slot. In the case of "plus 3 rehash," instead of incrementing by 1, the algorithm increments the hash index by 3. This means that if a collision occurs at index H, the next probing index will be H + 3.

The probing sequence is given by:

HashIndex = (InitialHashIndex + 3 * i) % TableSize

where "InitialHashIndex" is the initial hash index for the key, "i" is the iteration number (0, 1, 2, ...), and "3" is the fixed increment used for rehashing.

The advantage of "plus 3 rehash" is that it can help to reduce clustering in the hash table compared to regular linear probing with an increment of 1. By using a larger increment, the algorithm can quickly explore alternative positions further apart, which may lead to better spreading of elements across the hash table.

However, "plus 3 rehash" is not without its drawbacks. If the increment value (in this case, 3) is not carefully chosen or does not work well with the specific hash function and data distribution, it may still result in clustering or other inefficiencies.

Different open addressing techniques, including linear probing with various increments like "plus 3 rehash," quadratic probing, and double hashing, have been studied and employed to balance collision resolution and overall hash table performance. The choice of the best technique depends on the characteristics of the data and the desired trade-offs between memory usage and lookup efficiency. Experimentation and analysis are necessary to determine the most suitable collision resolution method for a particular use case.
## Load factor 
In computer science, the load factor is a metric used to measure the fullness or occupancy of a data structure, particularly in the context of hash tables. A hash table is a data structure that stores key-value pairs and allows for efficient insertion, deletion, and lookup operations.

The load factor of a hash table is defined as the ratio of the number of elements (key-value pairs) stored in the hash table to the total number of slots (buckets) in the hash table. It is calculated using the following formula:

Load Factor = Number of elements / Total number of slots

Typically, the load factor is denoted by the symbol "λ" (lambda). It is a value between 0 and 1, representing the fraction of the hash table that is occupied. A load factor of 0 means the hash table is empty, while a load factor of 1 means the hash table is completely full.

A higher load factor indicates that the hash table is more densely filled with elements. While a lower load factor indicates that there are fewer elements relative to the total capacity of the hash table.

It's essential to maintain an appropriate load factor to ensure the hash table's efficiency. A common approach is to resize the hash table when the load factor exceeds a certain threshold (often referred to as the "load factor threshold"). When the load factor surpasses this threshold, the hash table is resized to increase the number of slots, which reduces the likelihood of collisions and maintains the average number of elements per slot at an acceptable level.

The appropriate load factor threshold may vary based on the application and the desired trade-off between memory usage and lookup/insertion efficiency. A common choice is to resize the hash table when the load factor reaches 0.7 or 0.8, but this can differ depending on specific implementation requirements.

#### Traversing list 
In the context of a hash table, "traversing the list" typically refers to the process of iterating through all the key-value pairs stored in the hash table. This is necessary when you want to access or process all the elements in the hash table, and it involves visiting each entry in the hash table one by one.

In a hash table, the elements (key-value pairs) are distributed across different buckets or slots based on the hash values of the keys. When you want to traverse the entire hash table, you need to visit each bucket and access the elements stored within them.

The steps to traverse a hash table are as follows:

1. Iterate through each bucket in the hash table.
2. For each bucket, check if it contains any elements (key-value pairs).
3. If the bucket is not empty, traverse the linked list (or any other data structure) within that bucket to access the key-value pairs.

It's essential to handle collisions properly during traversal because multiple key-value pairs can be stored in the same bucket due to hash collisions. A common approach is to use a linked list, an array of key-value pairs, or another collision resolution technique to handle multiple elements within the same bucket.

The time complexity of traversing a hash table depends on the number of elements in the table and the load factor. In the average case, the time complexity is typically O(n), where n is the number of elements in the hash table. However, it is essential to consider the hash function's quality and collision resolution strategy to ensure efficient traversal and access of elements in the hash table.