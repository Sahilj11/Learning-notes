## What is collection 
Collection contains the core functionality required of any collection other than a
map. It has no direct concrete implementations; the concrete collection classes all
implement one of its subinterfaces as well.
## Iterable 
defines the contract that a class has to fulfill for its instances to be usable
with the foreach statement.

## Main types of collection 
- Set :- Set is a collection, without duplicates, in which order is not significant. Sorted
	Set automatically sorts its elements and returns them in order. NavigableSet ex-
	tends this, adding methods to find the closest matches to a target element.
- Queue:- Queue is a collection designed to accept elements at its tail for processing, yielding them up at its head in the order in which they are to be processed. Its subinterface. Deque extends this by allowing elements to be added or removed at both head and tail. Queue and Deque have subinterfaces, BlockingQueue and BlockingDeque respec-tively, that support concurrent access and allow threads to be blocked, indefinitely
	or for a maximum time, until the requested operation can be carried out
- List is a collection in which order is significant, accommodating duplicate elements.
- Map is a collection which uses key-value associations to store and retrieve elements.
It is extended by ConcurrentMap, which provides support for concurrent access, by
SortedMap, which guarantees to return its values in ascending key order, by Navi
gable-Map which extends SortedMap to find the closest matches to a target element,
and by ConcurrentNavigableMap which extends ConcurrentMap and NavigableMap.

# Four main structure
## Array 
Arrays are used in the Collections Frame-
work as the backing structure for ArrayList, CopyOnWriteArrayList, EnumSet and
EnumMap, and for many of the Queue and Deque implementations. They also form an
important part of the mechanism for implementing hash tables (discussed shortly)

## Linked list 
primary backing structure used for the classes ConcurrentLinkedQueue, LinkedBlock
ingQueue, and LinkedList, and the new skip list collections ConcurrentSkipList
Set and ConcurrentSkipListMap. They are also used in implementing HashSet and
LinkedHashSet.

## Hash table 
These provide a way of **storing elements indexed on their content rather than on
an integer-valued index**, as with lists. In contrast to arrays and linked lists, hash
tables provide no support for accessing elements by position, but access by content
is usally very fast, as are insertion and removal. Hash tables are the backing struc-
ture for many Set and Map implementations, including HashSet and LinkedHash
Set together with the corresponding maps HashMap and LinkedHashMap, as well as
WeakHashMap, IdentityHashMap and ConcurrentHashMap

## Tree 
These also organize their elements by content, but with the important difference
that they can store and retrieve them in sorted order. They are relatively fast for
the operations of inserting and removing elements, accessing them by content and
iterating over them. Trees are the backing structures for TreeSet and TreeMap. Pri-
ority heaps, used in the implementation of PriorityQueue and PriorityBlocking
Queue, are treerelated structures.

# Bookmark 171 page (collection and thread safety)
## Collection and thread safety

### Intro to thread 
When a Java program is running, it is executing one or more execution streams, or
threads. A thread is like a lightweight process, so a program simultaneously executing
several threads can be thought of as a computer running several programs simultane-
ously, but with one important difference: different threads can simultaneously access
the same memory locations and other system resources.

If, however, there are more threads than processors—the usual case—
multithreading is implemented by time slicing, in which a processor executes some
instructions from each thread in turn before switching to the next one.

### reason of multithreading 
There are two good reasons for using multithread programming. An obvious one, in
the case of multicore and multiprocessor machines, is to share the work and get it done
quicker. (This reason is becoming ever more compelling as hardware designers turn
increasingly to parallelism as the way of improving overall performance.) A second one
is that two operations may take varying, perhaps unknown, amounts of time, and you
do not want the response to one operation to await the completion of the other. This
is particularly true for a graphical user interface (GUI), where the response to the user
clicking a button should be immediate, and should not be delayed if, say, the program
happens to be running compute-intensive part of the application at the time.

### Issue 
- concurrency 
- Race condition
### Using sychronised keyword 
