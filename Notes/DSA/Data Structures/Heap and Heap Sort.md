
### Priority Queue 
- A **priority queue** is a type of queue that arranges elements based on their priority values. Elements with higher priority values are typically retrieved before elements with lower priority values
- dequeue the highest priority and enqueue based on the priority of the value (instead of adding it to last)
- as you can doing this can be very computationally heavy so to solve this issue , heap data structure is used.
### Complete binary tree
- Complete binary tree
	- **a special type of binary tree where all the levels of the tree are filled completely except the lowest level nodes which are filled from as left as possible**
	- nodes added from the left first
	- ![[Pasted image 20230906130913.png]]
### What is Heap
- it is a complete binary tree that comes with a heap order property(Max heap and min heap). allow us to implement priority queue 
- Max heap : - key of node is >= than the keys of its children
- 
- insertion:-
	- node:- i
	- left child: 2`*`i
	- right child : - 2 `*`i +1
	- parent of the these child can be retreived from :- i/2
- operation on heap
	- insert element x into set S 
	- return element of S with largest key
	- extract_max:- 