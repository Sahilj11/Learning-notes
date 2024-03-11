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
# Searching 
Certainly! Let's start with brief notes on each sorting algorithm followed by code examples in C:

1. **Bubble Sort**:
   - Bubble sort repeatedly compares adjacent elements and swaps them if they are in the wrong order. This process is repeated until the entire array is sorted.
   - It has a time complexity of O(n^2) in the worst-case scenario.
   - Although simple, bubble sort is not efficient for large datasets.
   
   ```c
   // Bubble Sort implementation in C
   void bubbleSort(int arr[], int n) {
       for (int i = 0; i < n-1; i++) {
           for (int j = 0; j < n-i-1; j++) {
               if (arr[j] > arr[j+1]) {
                   // Swap arr[j] and arr[j+1]
                   int temp = arr[j];
                   arr[j] = arr[j+1];
                   arr[j+1] = temp;
               }
           }
       }
   }
   ```

2. **Selection Sort**:
   - Selection sort divides the array into two parts: sorted and unsorted. It repeatedly selects the minimum element from the unsorted part and moves it to the beginning of the sorted part.
   - It has a time complexity of O(n^2) in all cases.
   - Selection sort has fewer swaps compared to bubble sort.
   
   ```c
   // Selection Sort implementation in C
   void selectionSort(int arr[], int n) {
       for (int i = 0; i < n-1; i++) {
           int minIndex = i;
           for (int j = i+1; j < n; j++) {
               if (arr[j] < arr[minIndex]) {
                   minIndex = j;
               }
           }
           // Swap arr[i] and arr[minIndex]
           int temp = arr[i];
           arr[i] = arr[minIndex];
           arr[minIndex] = temp;
       }
   }
   ```

3. **Insertion Sort**:
   - Insertion sort builds the final sorted array one element at a time by iteratively inserting each element into its correct position.
   - It has a time complexity of O(n^2) in the worst-case scenario.
   - Insertion sort performs well for small datasets and nearly sorted arrays.
   
   ```c
   // Insertion Sort implementation in C
   void insertionSort(int arr[], int n) {
       for (int i = 1; i < n; i++) {
           int key = arr[i];
           int j = i - 1;
           while (j >= 0 && arr[j] > key) {
               arr[j + 1] = arr[j];
               j = j - 1;
           }
           arr[j + 1] = key;
       }
   }
   ```

4. **Merge Sort**:
   - Merge sort divides the array into smaller subarrays, sorts them recursively, and then merges the sorted subarrays to produce the final sorted array.
   - It has a time complexity of O(n log n) in all cases.
   - Merge sort is a stable sorting algorithm and is often used for large datasets.
   
   ```c
   // Merge Sort implementation in C
   void merge(int arr[], int l, int m, int r) {
       int i, j, k;
       int n1 = m - l + 1;
       int n2 = r - m;
       int L[n1], R[n2];
       for (i = 0; i < n1; i++)
           L[i] = arr[l + i];
       for (j = 0; j < n2; j++)
           R[j] = arr[m + 1 + j];
       i = 0;
       j = 0;
       k = l;
       while (i < n1 && j < n2) {
           if (L[i] <= R[j]) {
               arr[k] = L[i];
               i++;
           } else {
               arr[k] = R[j];
               j++;
           }
           k++;
       }
       while (i < n1) {
           arr[k] = L[i];
           i++;
           k++;
       }
       while (j < n2) {
           arr[k] = R[j];
           j++;
           k++;
       }
   }
   void mergeSort(int arr[], int l, int r) {
       if (l < r) {
           int m = l + (r - l) / 2;
           mergeSort(arr, l, m);
           mergeSort(arr, m + 1, r);
           merge(arr, l, m, r);
       }
   }
   ```

5. **Quick Sort**:
   - Quick sort selects a pivot element and partitions the array into two subarrays such that elements less than the pivot are on the left, and elements greater than the pivot are on the right. It then recursively sorts the subarrays.
   - It has an average-case time complexity of O(n log n) and a worst-case time complexity of O(n^2).
   - Quick sort is widely used due to its efficiency and low overhead.

```c
   // Quick Sort implementation in C
#include <stdio.h>
void quickSort(int arr[], int start, int end);
int partition(int arr[], int start, int end);
int main(int argc, char *argv[]) {
  int arr[] = {4, 3, 2, 1};
  int size = sizeof(arr) / sizeof(arr[0]);
  quickSort(arr, 0, size - 1);
  for (int i = 0; i < size; i++) {
    printf("%d", arr[i]);
  }
  return 0;
}

void quickSort(int arr[], int start, int end) {
  if (end <= start)
    return;
  int pivot = partition(arr, start, end);
  quickSort(arr, start, pivot - 1);
  quickSort(arr, pivot + 1, end);
}
int partition(int arr[], int start, int end) {
  int i = start - 1;
  int pivot = arr[end];
  for (int j = start; j <= end; j++) {
    if (arr[j] < pivot) {
      i++;
      int tmp = arr[j];
      arr[j] = arr[i];
      arr[i] = tmp;
    }
  }
  i++;
  int tmp = arr[end];
  arr[end] = arr[i];
  arr[i] = tmp;
  return i;
}
```

# Linked List
Below is the code for a basic singly linked list implementation in C, along with common operations like insertion, deletion, and traversal:

```c
#include <stdio.h>
#include <stdlib.h>

// Define the structure of a node
typedef struct Node {
    int data;
    struct Node* next;
};
Node
// Function to create a new node
struct Node* newNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new node at the beginning of the linked list
void insertAtBeginning(struct Node** headRef, int data) {
    struct Node* newNode = newNode(data);
    newNode->next = *headRef;
    *headRef = newNode;
}

// Function to insert a new node at the end of the linked list
void insertAtEnd(struct Node** headRef, int data) {
    struct Node* newNode = newNode(data);
    if (*headRef == NULL) {
        *headRef = newNode;
        return;
    }
    struct Node* temp = *headRef;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

// Function to delete a node with a given key
void deleteNode(struct Node** headRef, int key) {
    struct Node* temp = *headRef;
    struct Node* prev = NULL;
    if (temp != NULL && temp->data == key) {
        *headRef = temp->next;
        free(temp);
        return;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Key not found in the list\n");
        return;
    }
    prev->next = temp->next;
    free(temp);
}

// Function to print the linked list
void printList(struct Node* node) {
    while (node != NULL) {
        printf("%d ", node->data);
        node = node->next;
    }
    printf("\n");
}

// Main function to test the linked list operations
int main() {
    struct Node* head = NULL;

    // Insert some nodes
    insertAtEnd(&head, 1);
    insertAtEnd(&head, 2);
    insertAtEnd(&head, 3);

    // Print the initial list
    printf("Initial list: ");
    printList(head);

    // Insert a node at the beginning
    insertAtBeginning(&head, 0);
    printf("List after inserting 0 at the beginning: ");
    printList(head);

    // Delete a node with key 2
    deleteNode(&head, 2);
    printf("List after deleting node with key 2: ");
    printList(head);

    return 0;
}
```

This code defines a singly linked list with basic operations like insertion at the beginning and end, deletion of a node with a given key, and printing the list. You can test these operations by compiling and running the code.

## Application of Linked List
Linked lists have numerous applications in computer science and software engineering due to their flexibility and efficiency in dynamic memory allocation. Some common applications of linked lists include:

1. **File Systems**: In operating systems, linked lists are used to maintain the list of files in a directory. Each file is represented as a node in the linked list, containing information such as the filename, size, and pointers to the next and previous files.

2. **Memory Management**: In memory management systems, linked lists are used to maintain free memory blocks. Each block of free memory is represented as a node in the linked list, with pointers to the next and previous free blocks.

3. **Undo Functionality**: Linked lists are often used to implement undo functionality in text editors and other software applications. Each action performed by the user (e.g., typing, deleting) is stored as a node in a linked list, allowing users to undo their actions by traversing the list backward.

4. **Polynomial Manipulation**: Linked lists can be used to represent and manipulate polynomials in mathematical computations. Each term of the polynomial can be stored as a node in the linked list, with coefficients and exponents stored as data.

5. **Sparse Matrices**: Linked lists are used to represent sparse matrices, where most of the elements are zero. Each non-zero element is stored as a node in the linked list, containing its row, column, and value.
## Doubly and Circular 
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
