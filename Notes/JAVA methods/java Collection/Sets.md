A set is a collection of items that cannot contain duplicates; adding an item if it is already
present in the set has no effect. The Set interface has the same methods as those of
Collection, but it is defined separately in order to allow the contract of add (and
addAll, which is defined in terms of add) to be changed in this way.

There are six concrete implementations of Set in the Collections Framework.
![[Pasted image 20230927095721.png]]

## Hash set 
This class is the most commonly used implementation of Set. As the name implies, it
is implemented by a hash table, an array in which elements are stored at a position
derived from their contents
![[Pasted image 20230927104745.png]]

An element’s position in a hash table is calculated by a hash function of its contents.
Hash functions are designed to give, as far as possible, an even spread of results (hash
codes) over the element values that might be stored.

when collision occur
We will look at linked lists in more detail as part of the implementations
of ConcurrentSkipListSet (see Section 13.2.3) but, for now, it’s enough to see that
elements stored at the same bucket can still be accessed, at the cost of following a chain
of cell references.

If a collision does take place, a linked list has to be created and subsequently
traversed, adding an extra cost to insertion proportional to the number of elements in
the list. If the size of the hash table is fixed, performance will worsen as more elements
are added and the load increases. To prevent this from happening, the table size is
increased by rehashing—copying to a new and larger table—when the load reaches a
specified threshold (its load factor).

The chief attraction of a hash table implementation for sets is the (ideally) constant-
time performance for the basic operations of add, remove, contains, and size.

but iteration is equal to O(n)
```java
Set<Character> s1 = new HashSet<Character>(8);
s1.add('a');
s1.add('b');
s1.add('j');
```

HashSet has the standard constructors that we introduced in Section 12.3, together with
two additional constructors:
```java
HashSet(int initialCapacity)
HashSet(int initialCapacity, float loadFactor)
```

HashSet is unsychronized and not thread-safe; its iterators are fail-fast.

### LinkedHashset

This class inherits from HashSet, still implementing Set and refining the contract of its
superclass in only one respect: it guarantees that its iterators will return their elements
in the order in which they were first added. It does this by maintaining a linked list of
the set elements, as shown by the curved arrows in Figure 13-3. The situation in the
figure would result from this code:

![[Pasted image 20230927104542.png]]
```java
Set<Character> s2 = new LinkedHashSet<Character>(8);
Collections.addAll(s2, 'a', 'b', 'j');
// iterators of a LinkedHashSet return their elements in proper order:
assert s2.toString().equals("[a, b, j]");
```
here you can see that arrows are allowing to keep track of order of insertion

The linked structure also has a useful consequence in terms of improved performance
for iteration: next performs in constant time, as the linked list can be used to visit each
element in turn. This is in contrast to HashSet, for which every bucket in the hash table
must be visited whether it is occupied or not, but the overhead involved in maintaining
the linked list means that you would choose LinkedHashSet in preference to HashSet
only if the orde or the efficiency of iteration were important for your application.

Like HashSet, it is unsychronized and not thread-
safe; its iterators are fail-fast.

### CopyOnWriteArraySet
This array is treated as immutable; a change
to the contents of the set results in an entirely new array being created. So add has
complexity O(n), as does contains, which has to be implemented by a linear search.
Clearly you wouldn’t use CopyOnWriteArraySet in a context where you were expecting
many searches or insertions. But the array implementation means that iteration costs
O(1) per element—faster than HashSet—and it has one advantage which is really com-
pelling in some applications:

### enumset 
This class exists to take advantage of the efficient implementations that are possible
when the number of possible elements is fixed and a unique index can be assigned to
each. These two conditions hold for a set of elements of the same Enum; the number of
keys is fixed by the constants of the enumerated type, and the ordinal method returns
values that are guaranteed to be unique to each constant.

