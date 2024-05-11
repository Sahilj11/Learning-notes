# Basic of DS
Algo :- A well-defined list of steps for solving a particular problem.
## Data Structure
Data may be organized in many different ways; the logical or mathematical model of a particular organization of data is called "data structures"
### Primitive 
These are the structures which are supported at the machine level, they can be used to make non-primitive data structures. These are integral and are pure in form. They have predefined behaviour and specifications. Examples: Integer, float, character, pointers
### Non Primitive
The non-primitive data structures cannot be performed without the primitive data structures. Although, they too are provided by the system itself yet they are derived data structures and cannot be formed without using the primitive data structures

These are further divided into:
#### Array
Arrays are a homogeneous and contiguous collection of same data types. They have a static memory allocation technique, which means, if memory space is allocated for once, it cannot be changed during runtime.
####  Files
A file is a collection of records. The file data structure is primarily used for managing large amounts of data which is not in the primary storage of the system

#### Linear Lists
- Stack 
- Queue
#### Non Linear 
- Graph 
- Tree
## DS operation
- Traversing
- Searching 
- Inserting 
- Deleting

## Abstract Data Type
A tool that permits a designer to consider a component at an abstract level, without worrying about the details of its implementation is called Abstraction. Treating the data as objects with some predefined operations that can be performed on those objects is called Data Abstraction.
Data Abstraction when supported as a data type in a language is called Abstract Data Type (ADT).

## Static and Dynamic Memory Allocation
In static memory allocation memory is allocated at compile time.
allocating memory at run time (instead of compile time), this is called Dynamic Memory Allocation. It is done by using standard library functions malloc () and calloc ().

## Static and Dynamic Variable
Static variables are declared and named while writing the program. (Space for them exists as long as the program, in which they are declared, is running.) Static variables cannot be created or destroyed during execution of the program in which
they are declared.

Dynamic variables are created (and may be destroyed) during program execution since dynamic variables do not exist while the program is compiled, but only when it is run, they cannot be assigned names while it is being written. The only way to
access dynamic variables is by using pointers

## Data Representation of String 
### Sequential Fixed Length Structure
In this representation successive characters of a string will be placed in consecutive character positions
![](../../statics/Pasted%20image%2020240311071632.png)
### Linked List Fixed Size Node
The available memory is divided into nodes of fixed size. Each node has two fields: Data and Link. The size of a node is the number of characters that can be stored in the DATA fields.

# Array and Matrices
## Linear DS
A "data structure" which displays the relationship of adjacency between elements is said to be "linear"
## Arrays
The simplest data structure that makes use of computed addresses to locate its elements is the one-dimensional array. Normally a number of (contiguous) memory locations are sequentially allocated to the array.
**Category**
- 1D
- 2D
- 3D
- Multi D
### 1D
A one-dimensional array is a list of finite number n of homogeneous data elements (i.e. data elements of the same type) such that:
1. The elements of the array are referenced respectively by an index set consisting of n consecutive numbers.
2. The elements of the array are stored respectively in successive memory locations
Find Length
Length = UB-LB+1
Memory Space Request (UB-LB+1)\*s . here s is size of data type
If the address of A\[LB\] is a then the address of ith element of array will be given
by: Address of A\[i\] = a+(i-LB)\*s

### 2D
A two-dimensional 'mxn' Array A is a collection of m.n data elements such that each element is specified by a pair of integers (such as J, K), called subscripts, 
In Row Major Order elements of 1st row is stored first in linear order and then come elements of the next row and so on.
In Column Major Order elements of 1st column is stored first linearly and then come elements of the next column.

### Sparse Matrice
A sparse matrix is **a special case of a matrix in which the number of zero elements is much higher than the number of non-zero elements**. As a rule of thumb, if 2/3 of the total elements in a matrix are zeros, it can be called a sparse matrix.
# Linked List
### Structure of node
```c
struct node { 
	int data; 
	struct node* link; 
}
```
link is a pointer of struct node type i.e. it can hold the address of variable of struct node type.
### Operations
#### Insertion at beginning
**ALGO**
- addBeg(list,item)
- Create a new node
- assign the item to new node
- Set link of new node to node where head is pointing
- update head to new node
```c
addbeg() { 
	int x; 
	temp = malloc(sizeof(struct node)); 
	scanf("%d", &x); 
	temp->data = x; 
	temp->link = list; 
	list = temp; 
}
```
![](../../statics/Pasted%20image%2020240509101356.png)
#### Insertion of node at end
**ALGO**
- addLast(list,item)
- Create new node
- assign item to new node
- create ptr node and set it to head
- while ptr->next != null
- ptr = ptr->next
- set ptr-next = new node
![](../../statics/Pasted%20image%2020240509101640.png)

#### Insertion of node after specified node
**ALGO**
- addItem(list,item,location)
- create newnode and set link to NULL 
- assign item to newnode
- create ptr node and set it to head
- while ptr->data != location OR ptr->next != NULL
- ptr = ptr->next
- if(ptr->next = NULL AND ptr->data != location)
- then return location not exist
- assign newnode->next = ptr->next
- assign ptr->next = newnode
![](../../statics/Pasted%20image%2020240509102235.png)
#### Deletion of particular node from list
**ALGO**
- deleteItem(list,item)
- if head = NULL return
- if head->data = item then free(head) return
- create ptr node and set ptr->next = HEAD
- create nextptr node and set its next = HEAD->next
- while nextptr != NULL
	- if nextptr->data = item
		- then ptr->next = nextptr->next
		- free(nextptr) return
	- ptr = nextptr
	- nextptr = nextptr->next
- return item not exist
![](../../statics/Pasted%20image%2020240509103034.png)

## Concatenation of linked list
![](../../statics/Pasted%20image%2020240509103124.png)
- connect last node to head node of second list
## Merging Sorted linked list
**ALGO**
1. If one of the lists is empty return the other.
2. Initialize a node **output = NULL** , which will the head of the merged list. Compare the first element of both list and create a dummy node **temp** which stores the smaller value and make **output** referencing to it.
	- If **A.val < B.val** , create a dummy node **temp** and set output = temp and A = A.next.
	- Else, create a dummy node **temp** and set output = temp and B= B.next.
3. Initialize a pointer **curr** = **output** and Iterate till any of the lists reaches its end. Compare the current node’s value of both the list
	- If **A.val < B.val** , create a dummy node **temp** and set curr.next = temp and B= B.next.
	- Else, create a dummy node **temp** and set curr.next = temp and A= A.next
	- Move the **curr** pointer, **curr = curr.next** .
4. If list A reaches its end in the above loop then append the remaining node of B into the output list (or vice versa).
5. Return **output** .

## Reversing linked list
**ALGO**
- Initialize three pointers **prev** as NULL, **curr** as **head**, and **next** as NULL.
- Iterate through the linked list. In a loop, do the following:
    - Before changing the **next** of **curr**, store the **next** node 
        - next = curr -> next
    - Now update the **next** pointer of **curr** to the **prev** 
        - curr -> next = prev 
    - Update **prev** as **curr** and **curr** as **next**
        - prev = curr 
        - curr = next
## Application of Linked List
Linked lists have numerous applications in computer science and software engineering due to their flexibility and efficiency in dynamic memory allocation. Some common applications of linked lists include:

1. **File Systems**: In operating systems, linked lists are used to maintain the list of files in a directory. Each file is represented as a node in the linked list, containing information such as the filename, size, and pointers to the next and previous files.

2. **Memory Management**: In memory management systems, linked lists are used to maintain free memory blocks. Each block of free memory is represented as a node in the linked list, with pointers to the next and previous free blocks.

3. **Undo Functionality**: Linked lists are often used to implement undo functionality in text editors and other software applications. Each action performed by the user (e.g., typing, deleting) is stored as a node in a linked list, allowing users to undo their actions by traversing the list backward.

4. **Polynomial Manipulation**: Linked lists can be used to represent and manipulate polynomials in mathematical computations. Each term of the polynomial can be stored as a node in the linked list, with coefficients and exponents stored as data.

5. **Sparse Matrices**: Linked lists are used to represent sparse matrices, where most of the elements are zero. Each non-zero element is stored as a node in the linked list, containing its row, column, and value.
## Doubly and Circular
![](../../statics/Pasted%20image%2020240509100408.png)
![](../../statics/Pasted%20image%2020240509100451.png)
# Stack and Queue
## Queue
Queue is a linear list which has two ends, one for insertion of elements and other for deletion of elements. The first end is called 'Rear' and the latter is called 'Front'. Elements are inserted from rear end and deleted from front end. Queues are called First In First Out (FIFO)
Below is the implementation of a queue data structure in C using an array along with its operations: enqueue, dequeue, and display.

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100 // Maximum size of the queue

// Define the structure of a queue
struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Function to create an empty queue
struct Queue* createQueue() {
    struct Queue* queue = (struct Queue*)malloc(sizeof(struct Queue));
    queue->front = -1; // Initialize front and rear pointers
    queue->rear = -1;
    return queue;
}

// Function to check if the queue is full
int isFull(struct Queue* queue) {
    return (queue->rear == MAX_SIZE - 1);
}

// Function to check if the queue is empty
int isEmpty(struct Queue* queue) {
    return (queue->front == -1 && queue->rear == -1);
}

// Function to add an element to the queue (enqueue)
void enqueue(struct Queue* queue, int data) {
    if (isFull(queue)) {
        printf("Queue is full\n");
        return;
    }
    if (isEmpty(queue)) {
        queue->front = 0; // Initialize front pointer
    }
    queue->rear++;
    queue->items[queue->rear] = data;
}

// Function to remove an element from the queue (dequeue)
int dequeue(struct Queue* queue) {
    int data;
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
        return -1;
    }
    data = queue->items[queue->front];
    if (queue->front >= queue->rear) {
        queue->front = -1;
        queue->rear = -1;
    } else {
        queue->front++;
    }
    return data;
}

// Function to display the elements of the queue
void display(struct Queue* queue) {
    int i;
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
    } else {
        printf("Queue: ");
        for (i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->items[i]);
        }
        printf("\n");
    }
}

// Main function to test the queue operations
int main() {
    struct Queue* queue = createQueue();

    // Enqueue some elements
    enqueue(queue, 1);
    enqueue(queue, 2);
    enqueue(queue, 3);

    // Display the queue
    display(queue);

    // Dequeue an element
    int dequeuedElement = dequeue(queue);
    printf("Dequeued element: %d\n", dequeuedElement);

    // Display the queue after dequeue operation
    display(queue);

    return 0;
}
```

This code implements a queue data structure using an array. It includes functions to create a queue, check if it is full or empty, enqueue elements, dequeue elements, and display the elements of the queue. You can test the queue operations by compiling and running the code.

### Circular Queue
Below is the implementation of a circular queue data structure in C along with its operations: enqueue, dequeue, and display.

```c
insert_CQ(int x)
{
   if ((REAR+1)%MAX == FRONT)
    {
		printf("Q_FULL");
		return;
	}
	(REAR++)%MAX;
	CQUEUE[REAR]=x; // CQueue[ ] is an Array Represents
}
```
```c
int delete_cq()
{
	int x;
	if (REAR == FRONT)
	{
		printf("Q_Empty");
		return;
	}
	x = cqueue[FRONT];
	FRONT = (FRONT+1)%MAX;
	return (x);
}
```

### Deque
A deque "Double Ended Queue" is a linear list in which elements can be added or removed at either end but not in the middle. There are two variations of a deque namely:
1. An Input Restricted deque
2. An Output Restricted deque
Specifically, an Input-Restricted deque is a deque which allows insertions at only one end of the list but allows deletions at both ends of the list; and an OutputRestricted deque is a deque which allows deletions at only one end of the list but allows insertions at both ends of the list
![](../../statics/Pasted%20image%2020240311092943.png)

### Priority Queue 
A priority queue is a collection of elements such that each element has been assigned a priority and the order in which elements are deleted and processed comes from the following rules
-  An element of higher priority is processed before any element of lower priority.
- Two elements with the same priority are processed according to the order in which they were added to the queue

A prototype of priority is processed first, and programs with the same priority form a standard queue. There can be two types of implementations of priority queue:
1. Ascending Priority Queue
2. Descending Priority Queue

A collection of items into which items can be inserted arbitrarily and from which only the smallest item can be removed is called Ascending Priority Queue.

In Descending Priority Queue only, the largest item is deleted. The elements of priority queue need not be numbers or characters that can be composed directly.

## Stack
Stack is an ordered list in which there is only one end, for both insertions and deletions. Elements are inserted and deleted from the same end called "TOP" of the stack. Stack is called Last In First Out (LIFO) list

Using Array
Certainly! Below is a simple implementation of a stack using an array in C:

```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// Structure to represent a stack
typedef struct {
    int items[MAX_SIZE];
    int top;
} Stack;

// Function to initialize the stack
void initializeStack(Stack *stack) {
    stack->top = -1;
}

// Function to check if the stack is empty
int isEmpty(Stack *stack) {
    return (stack->top == -1);
}

// Function to check if the stack is full
int isFull(Stack *stack) {
    return (stack->top == MAX_SIZE - 1);
}

// Function to push an element onto the stack
void push(Stack *stack, int value) {
    if (isFull(stack)) {
        printf("Stack Overflow\n");
        return;
    }
    stack->items[++stack->top] = value;
}

// Function to pop an element from the stack
int pop(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack Underflow\n");
        return -1;
    }
    return stack->items[stack->top--];
}

// Function to peek at the top element of the stack
int peek(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack->items[stack->top];
}

int main() {
    Stack stack;
    initializeStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);

    printf("Top element is %d\n", peek(&stack));

    printf("Popped element : %d\n", pop(&stack));
    printf("Popped element : %d\n", pop(&stack));

    printf("Top element is %d\n", peek(&stack));

    push(&stack, 40);

    printf("Top element is %d\n", peek(&stack));

    return 0;
}
```

Using Linked List 
```c
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a node in the stack
typedef struct Node {
    int data;
    struct Node* next;
} Node;

// Function to create a new node
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        exit(1);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Structure to represent a stack
typedef struct {
    Node* top;
} Stack;

// Function to initialize the stack
void initializeStack(Stack *stack) {
    stack->top = NULL;
}

// Function to check if the stack is empty
int isEmpty(Stack *stack) {
    return (stack->top == NULL);
}

// Function to push an element onto the stack
void push(Stack *stack, int value) {
    Node* newNode = createNode(value);
    newNode->next = stack->top;
    stack->top = newNode;
}

// Function to pop an element from the stack
int pop(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack Underflow\n");
        return -1; // return a sentinel value or handle error appropriately
    }
    Node* temp = stack->top;
    int poppedValue = temp->data;
    stack->top = temp->next;
    free(temp);
    return poppedValue;
}

// Function to peek at the top element of the stack
int peek(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1; // return a sentinel value or handle error appropriately
    }
    return stack->top->data;
}

int main() {
    Stack stack;
    initializeStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);

    printf("Top element is %d\n", peek(&stack));

    printf("Popped element : %d\n", pop(&stack));
    printf("Popped element : %d\n", pop(&stack));

    printf("Top element is %d\n", peek(&stack));

    push(&stack, 40);

    printf("Top element is %d\n", peek(&stack));

    return 0;
}
```

## Tree
- A tree data structure is a hierarchical data structure that consists of nodes connected by edges. It is called a "tree" because it resembles a tree in nature, with a single root node representing the trunk and additional nodes branching off from it like branches. it is non cyclic 

# UNIT 3 
## Heapsort (Referred Mam ppt)

## Graphs 
![](../../statics/Pasted%20image%2020240502175847.png)
### Representation of Graph
- Sequential : - Adjacent matrix , incidence matrix
- Linear : Using list
![](../../statics/Pasted%20image%2020240502180017.png)
![](../../statics/Pasted%20image%2020240502180139.png)
![](../../statics/Pasted%20image%2020240502180236.png)
![](../../statics/Pasted%20image%2020240502180415.png)
- issues :- use large memory space , disadvantages of arrays also added
![](../../statics/Pasted%20image%2020240502180607.png)
**Attempting way**
![](../../statics/Pasted%20image%2020240502181156.png)
### DFS
![](../../statics/Pasted%20image%2020240502181425.png)
![](../../statics/Pasted%20image%2020240502181436.png)

![](../../statics/Pasted%20image%2020240502181528.png)![](../../statics/Pasted%20image%2020240502182211.png)
### BFS
![](../../statics/Pasted%20image%2020240502182500.png)
![](../../statics/Pasted%20image%2020240502182711.png)
![](../../statics/Pasted%20image%2020240502182816.png)

### Operations in Graph
- Insertion :- Just add new node in Linear representation or in case of Sequential representation add row and column 
- Deletion :- Do the opposite
![](../../statics/Pasted%20image%2020240502183739.png)

### Red black tree
![](../../statics/Pasted%20image%2020240511085418.png)
- It is a self balancing BST
- Every node is either red or black , root is always black
- Every leaf node which is nil is always black , if node is red then its children are black
- Every path from a node to any of its descendent NIL node has same number of black nodes
![](../../statics/Pasted%20image%2020240511084754.png)
### Splay trees
A splay tree is a self-adjusting binary search tree (BST) where recently accessed elements are quickly accessed again. When an element is accessed, it is moved to the root of the tree by a series of rotations called splaying. Here are some key features of splay trees:

1. **Self-Adjusting**: Splay trees adapt their structure based on the access pattern of elements. Frequently accessed elements move closer to the root, improving the average access time.

2. **Splaying Operation**: The splaying operation brings the accessed node to the root by performing a series of rotations (zig-zag and zig-zig rotations) and tree restructuring. This operation helps maintain balance and ensures that frequently accessed nodes are located closer to the root, improving future access times.

3. **No Balancing Factor**: Unlike AVL trees or red-black trees, splay trees do not maintain a balancing factor at each node. Instead, they rely on the splaying operation to maintain balance based on the access pattern.

4. **Amortized Analysis**: The time complexity of splay tree operations (such as insertion, deletion, and search) is analyzed in an amortized sense. Although individual operations might have a higher time complexity, the overall performance is efficient over a sequence of operations.

5. **No Strict Guarantees**: Splay trees do not provide strict worst-case performance guarantees like AVL trees or red-black trees. However, they perform well in practice for many applications, especially when there is temporal locality in theaccess pattern.
### Shortest Path

#### Dijkstra (Single source shortest path)
#### Floyd Warshall (Multisource shortest path)

# UNIT 4
## Binary search
### Pseudocode
1. Begin with an array sorted in ascending order.
2. Define two pointers, namely start and finish.
3. Assign the start pointer with 0, and the finish pointer with the last index of the array.
4. Define a variable mid, which refers to the middle of the array. It is calculated as (low+high)/2.
5. If the element at the mid index equals the searched element, return the mid index.
6. If the searched element is smaller than the mid index element, move the finish to mid-1, effectively discarding the right half of the array.
7. If the searched element is larger than the mid index element, move the start to mid+1, effectively discarding the left half of the array.
![](../../statics/Pasted%20image%2020240509083508.png)
## Sorting algorithms
### Selection sort
#### Pseudo 
1. Find the largest item x, in the range of \[0…n−1\] 
2. Swap x with the (n−1)th item 
3. Reduce n by 1 and go to Step 1
Time complexity : O(n<sup>2</sup>)
### Bubble Sort
1. Compare pair of adjacent items 
2. Swap if the items are out of order
3. Repeat until the end of array 
		The largest item will be at the last position 
4. Reduce n by 1 and go to Step 1

Time complexity : O(n<sup>2</sup>)

![](../../statics/Pasted%20image%2020240509084339.png)

### Insertion sort
#### Pseudo code
- We have to start with second element of the array as first element in the array is assumed to be sorted.
- Compare second element with the first element and check if the second element is smaller then swap them.
- Move to the third element and compare it with the second element, then the first element and swap as necessary to put it in the correct position among the first three elements.
- Continue this process, comparing each element with the ones before it and swapping as needed to place it in the correct position among the sorted elements.
- Repeat until the entire array is sorted.
![](../../statics/Pasted%20image%2020240509085107.png)

### Merge sort 
#### Pseudo code
- **Left** will be equal to **0** and the value of **right** will be equal to **size-1**, where size is the length of the given unsorted array.
- Find the middle point of this array by applying **mid = (left + right) / 2**.
- Call the function **mergeSort** by passing the arguments as **(left, mid)** and **(mid + 1, rear)**.
- The above steps will repeat till **left < right**.
- Then we will call the **merge** function on two sub-arrays.
#### Divide and conquer model
- Merge Sort is a divide-and-conquer sorting algorithm 
- Divide step 
	- Divide the array into two (equal) halves 
	- Recursively sort the two halves 
- Conquer step 
	- Merge the two halves to form a sorted array

time-complexity: O(nLogn)
![](../../statics/Pasted%20image%2020240509085924.png)
![](../../statics/Pasted%20image%2020240509090000.png)
### Quick sort
#### pseudo code
![](../../statics/Pasted%20image%2020240509090151.png)
![](../../statics/Pasted%20image%2020240509090231.png)
Time-complexity : O(nlogn)

Worst case in quicksort
![](../../statics/Pasted%20image%2020240509095056.png)
![](../../statics/Pasted%20image%2020240509095149.png)
The worst-case time complexity of the Quicksort algorithm occurs when the chosen pivot divides the array into two subarrays of unequal sizes, particularly when it consistently picks the smallest or largest element. This scenario leads to unbalanced partitions, where one partition has significantly more elements than the other. As a result, the recursive calls do not divide the problem into subproblems of nearly equal sizes, leading to poor performance.

In the worst-case scenario, Quicksort's time complexity approaches \(O(n^2)\), where \(n\) is the number of elements in the array. This occurs when the input array is already sorted (either in ascending or descending order) or contains many duplicate elements, and the pivot selection strategy consistently selects the minimum or maximum element.

However, it's important to note that the worst-case scenario is relatively rare in practice, especially with randomized pivot selection strategies or careful pivot selection methods like median-of-three. With these strategies, Quicksort typically exhibits an average-case time complexity of \(O(n \log n)\) and is highly efficient in practice for most inputs.
### Summary
![](../../statics/Pasted%20image%2020240509090352.png)
## Internal and external , stable sorting

### Stable sorting
  
Stability in sorting algorithms refers to the property where elements with equal keys maintain their relative order after sorting.

For example, suppose you have a list of objects sorted primarily by one attribute, such as their age, and then sorted secondarily by another attribute, such as their name. If you use a stable sorting algorithm, like stable merge sort or stable insertion sort, objects with equal ages will retain their relative order based on their names after sorting.

In scenarios where maintaining the original order of elements with equal keys is important, stable sorting algorithms are preferred. They ensure that the original order is preserved even after sorting, which can be crucial in various applications and algorithms

### Internal and External
If the data sorting process takes place **entirely within the Random-Access Memory (RAM) of a computer,** it’s called internal sorting. This is possible whenever the size of the dataset to be sorted is small enough to be held in RAM.

For sorting larger datasets, it may be necessary to hold only a smaller chunk of data in memory at a time, since it won’t all fit in the RAM. The rest of the data is normally held on some larger, but slower medium, like a hard disk. **The sorting of these large datasets will require different sets of algorithms which are called external sorting.**

- Internal sort:- Bubble sort,insertion sort,Quicksort
- External sort:-Merge sort
## Hash Tables
### Intro
In tree tables, the search for an identifier key is carried out via a sequence of comparisons. Hash differs from this, in that the address or location of an identifier, X, is obtained by computing some arithmetic function f, of X. f (X) gives the address of X in the table. This address will be referred to as the hash or home address of X.
The memory available to maintain the symbol table is assumed to be sequential. This memory is referred to as the hash table, HT.
Hash table is divided into b buckets , and each bucket is capable of holding records(meaning a single bucket can hold multiple records)
A hashing function, f (x) is used to perform an identifier transformation on X. f(x) maps the set of possible identifiers onto the integers 0 through b-1. We use the term bucket to denote a unit of storage that can store one or more records. A bucket is typically a disk but could be chosen to be smaller or larger than a disk block

### Hash function
A hashing function f, transforms an identifier X into a bucket address in the hash table. The desired properties of such a function are that it should be easily computable and that it should minimize the number of collisions.

An ideal hash function distributes the stored keys uniformly across all the buckets so that every bucket has the same number of records. 

Features of good hash function
- The distribution is uniform, that is, each bucket is assigned the same number of search key values from the set of all possible search key values.
- The distribution is random, that is, in the average case, each bucket will have nearly the same number of values assigned to it, regardless of the actual distribution of search key values.
#### Some hashing techniques
Sure, let's delve into each of these hash functions:

1. **Division Hash Function**:
   - The division hash function works by taking the remainder of dividing the key by a prime number, typically the size of the hash table.
   - The formula for the division hash function is: \( h(k) = k \mod m \), where \( k \) is the key and \( m \) is the size of the hash table.
   - It's a simple and commonly used hash function because it's easy to implement and works well in many situations.
   - However, it might suffer from clustering if the keys are not uniformly distributed.
   - Suppose we have a hash table of size 10.
   - Let's say we want to hash the key 27.
   - Using the division hash function \( h(k) = k \mod m \), where \( k \) is the key and \( m \) is the size of the hash table:
     - \( h(27) = 27 \mod 10 = 7 \).
   - So, the key 27 maps to index 7 in the hash table.


2. **Mid-Square Hash Function**:
   - The mid-square hash function involves squaring the key, taking a portion of the middle bits, and using that as the hash value.
   - The formula for the mid-square hash function is: \( h(k) = \text{{middle bits}}(k^2) \).
   - For example, if the key is 123 and its square is 15129, we can use the middle two digits (51) as the hash value.
   - This hash function is less commonly used due to potential issues with certain key distributions and difficulty in choosing an appropriate portion of the bits.

3. **Folding Hash Function**:
   - The folding hash function involves dividing the key into fixed-size parts, summing or concatenating these parts, and then applying the division hash function to the result.
   - It's particularly useful when dealing with keys of variable length, such as strings.
   - The formula for the folding hash function can vary depending on the method of folding used, but a common approach is to divide the key into equal-sized chunks, sum them up, and then apply the division hash function to the result.
   - For example, if the key is 123456789 and we divide it into two parts (12, 34, 56, 78, 9), summing them results in 189, which can then be hashed using the division hash function.
   - Folding hash functions can provide good distribution if properly implemented and can handle keys of variable length efficiently.
4. Digit analysis:- Digit analysis is a technique used in hashing to distribute keys evenly across hash table slots based on certain characteristics of the keys, such as their numerical values.In digit analysis, the keys are typically numeric values, and the hashing function operates on individual digits or groups of digits within the keys to determine the hash value. The idea is to partition the keys into different groups based on their digit patterns and distribute them across the hash table slots.
Here's a simplified example of digit analysis in hashing:
1. **Partitioning Keys**: Divide the keys into groups based on their digit patterns. For example, you might consider the first few digits or the last few digits of each key.
2. **Hashing Function**: Design a hashing function that operates on these digit groups to compute the hash value. This function should aim to distribute keys evenly across the hash table slots to minimize collisions.    
3. **Mapping Keys to Slots**: Apply the hashing function to each key to determine its corresponding hash value, and then map the key to the appropriate slot in the hash table based on this hash value.
4. **Collision Handling**: Handle collisions that may occur when multiple keys map to the same hash value. This can be done using various collision resolution techniques, such as chaining (for open hashing) or probing (for closed hashing). 
### Some Hash terms 
#### Identity factor
The ratio n/T is called the identifier density, where n = number of identifiers T = total number of possible identifiers. The number of identifiers, n, in use is usually several orders of magnitude less than the total number of possible identifiers, T. The number of buckets b, in the hash table are also much less than T.

#### Loading factor 
The loading factor a is equal to n/sb, where s = number of slots in a bucket b = total number of buckets The number of buckets b is also very less than the total number of possible identifiers, T.

#### Synonyms
The hash function f almost always maps several different identifiers into the same bucket. Two identifiers I1, I2 are said to be synonyms with respect to f if f(I1) = f (I2). Distinct synonyms are entered into the same bucket so long as all the s slots in that bucket have not been used.

#### Collision
A collision is said to occur, when two non-identical identifiers are hashed into the same bucket. When the bucket size is 1, collision and overflow occurs simultaneously 

### Bucket overflows
when a record is inserted, the bucket to which it is mapped has space to store the record, if the bucket does not have enough space, a bucket overflow is said to have occurred.

#### Handling this
- Overflow chaining:- If a record has be inserted into a bucket b, and b is alre ady full, an overflow bucket is provided for b, and the record is inserted into the overflow bucket. If the overflow bucket is also full, another overflow bucket is provi ded and so on. All the overflow buckets of a given bucket are chained together in a linked list. Overflow handling using such a linked list is called Overflow Chaining.
- ![](../../statics/Pasted%20image%2020240509094436.png)
- Deletion
- Open hashing

#### Open vs close hashing(Open addressing)
Open hashing and closed hashing (also known as open addressing) are two different approaches for resolving collisions in hash tables:
1. **Open Hashing**:
   - Open hashing, also known as separate chaining, involves storing all colliding keys in the same slot of the hash table.
   - Each slot of the hash table maintains a linked list, array, or other data structure to store multiple items that hash to the same index.
   - When a collision occurs, the new item is simply added to the existing data structure associated with the slot.
   - Searching for an item involves hashing the key to find its slot and then traversing the associated data structure to find the desired item.
   - Open hashing tends to be more memory-efficient compared to closed hashing because it doesn't require additional storage for overflow items.

2. **Closed Hashing (Open Addressing)**:
   - Closed hashing, or open addressing, involves storing all items directly within the hash table itself, even if collisions occur.
   - When a collision occurs, the algorithm probes for an alternative location (usually through a sequence of positions determined by a probing function) until an empty slot is found.
   - The probing function defines the sequence of slots to be examined in case of collisions. Common probing techniques include linear probing, quadratic probing, and double hashing.
   - Closed hashing typically requires less memory overhead compared to open hashing because it doesn't need additional data structures to handle collisions.
   - However, closed hashing can suffer from clustering, where consecutive items are placed in nearby slots, potentially leading to longer search times.