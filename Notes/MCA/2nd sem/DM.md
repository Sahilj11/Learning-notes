# Set
## Set and their representation
A set is a collection of well-defined objects. By well-defined, it is meant that given a particular collection of objects as a set and a particular object, it must be possible to determine whether that particular object is a member of the set or not

Representation of Sets: Sets are represented in the following two methods:
1. Roster or tabular method
2. Set-builder or Rule method
In the Roster method, the elements of a set are listed in any order, separated by commas and are
enclosed within braces, For example, A = {2, 3, 5, 7, 11, 13}

In the Rule method,a variable x is used to represent the elements of a set, where the elements satisfy a
definite property, say P(x). Symbolically, the set is denoted by {x:P(x)} or {x|p(x)}.For example,
A = {x: x is an odd natural number} B = {x: x<sup>2</sup>–3x+2 = 0}, etc.

Some standard symbol for set and number
N for natural number , Z for integer , Q for rational number , R for real number , Z<sup>+</sup> for positive int , Z<sup>0</sup> for non zero int

### Empty set
A set which does not contain any element is called an empty set or a null set or a void
set. It is denoted by Ø
Example:
- the set of people in Assam who are older than 500 years
- the set of real roots of the equation x<sup>2</sup>+ 4 =0

### Finite and infinite set
A set containing finite number of distinct elements so that the process of counting the
elements comes to an end after a definite stage is called a finite set; otherwise, a set is called an infinite
set.
 A = {1, 2, 3, 4, 5}and B = {1, 4, 7, 10, 13, ...}

### Equal Set 
Two sets A and B are said to be equal sets if every element of A is an element of B and every element of B is also an element of A.
denoted by A = B 
Example :- 
A = {1, 4,9}
B = {12, 22, 33}

### Subset , superset and propersubset
A = {1, 2, 3}, B = {1, 2, 3, 4} and C = {3, 2, 1}. 

If every element of a set A is also an element of another set B, then A is called a subset of
B, or A is said to be contained in B, and is denoted by A ⊆ B. Equivalently, we say that B contains A or
B is a super set of A and is denoted by B ⊇ A.

If A is a subset of B, but the re exists at least one element in B which is not in A, then A is called a
proper subset of B, denoted by A⊂B.In other words, A⊂B <-> (A ⊆ B and A≠B)
Example of propersubset is N ⊂ Z where N is set of natural number and Z is set of integer
A is also subset of itself

### Powerset
The set consisting of all the subsets of a given set A as its elements, is called the power set
of A and is denoted by P(A) or 2<sup>A</sup>. Thus, P(A) or 2<sup>A</sup> = {X: X ⊆ A}
if A = {1, 2}, then PA= {$, {1}, {2}, A}
From these examples we can conclude that if a set A has n elements,then P(A) has 2<sup>n</sup>elements

### Universal set
A set is called a Universal Set or the Universal discourse if it contains all the sets under consideration in a particular discussion. A universal set is denoted by U.

In connection with the sets N, Z, Q we can take R as the universal set

## SET OPERATIONS
### UNION OF SET
The union of two sets A and B is the set of all elements which are members of set A or set B
or both. It is denoted by A U B
![](../../statics/Pasted%20image%2020240308103018.png)
 Let A = {1, 2, 3, 4}, B = {2, 4, 5, 6}
Then A U B = {1, 2, 3, 4, 5, 6}

Identities

![](../../statics/Pasted%20image%2020240308104447.png)
### INTERSECTION OF SET
The intersection of two sets A and B is the set of all elements which are members of both A
and B. It is denoted by A ∩ B
A ∩ B = {x: x ∈A and x ∈ B}

From definition it is clear that if A and B have no common element, then A ∩ B = ∅. In this case, the two
sets A and B are called disjoint sets
![](../../statics/Pasted%20image%2020240308104527.png)
### DIFFERENCE OF SET
The difference of two sets A and B is the set of all elements which are members of A, but not of B. It is denoted by A–B.
![](../../statics/Pasted%20image%2020240308104249.png)
![](../../statics/Pasted%20image%2020240308104542.png)

### COMPLEMENT OF SET

If U be the universal set of a set A, then the set of all those elements in U which are not
members of A is called the Compliment of A, denoted by A<sup>c</sup> or A<sup>'</sup>.
![](../../statics/Pasted%20image%2020240308104704.png)
identities
![](../../statics/Pasted%20image%2020240308104929.png)
![](../../statics/Pasted%20image%2020240308104939.png)
## Law of algebra of sets
Sure, let's integrate proofs for some of the laws of algebra of sets with the above responses:

1. **Commutative Laws**:
    - **Union (A ∪ B = B ∪ A)**:
      To prove this, we show that for any element x, x ∈ A ∪ B if and only if x ∈ B ∪ A.
      Suppose x ∈ A ∪ B. This means that x is in at least one of A or B, so x ∈ A or x ∈ B. Hence, x ∈ B ∪ A.
      Similarly, if x ∈ B ∪ A, then x is in at least one of B or A, so x ∈ B or x ∈ A. Hence, x ∈ A ∪ B.
      Therefore, A ∪ B = B ∪ A.
    
    - **Intersection (A ∩ B = B ∩ A)**:
      Similar to the above, we can prove this by showing that for any element x, x ∈ A ∩ B if and only if x ∈ B ∩ A.

2. **Associative Laws**:

    - **Union ((A ∪ B) ∪ C = A ∪ (B ∪ C))**:
      To prove this, we need to show that for any element x, x ∈ (A ∪ B) ∪ C if and only if x ∈ A ∪ (B ∪ C).
      
      This can be proved by considering the properties of unions and the definition of sets.

    - **Intersection ((A ∩ B) ∩ C = A ∩ (B ∩ C))**:
      Similar to the union property, we can prove this by considering the properties of intersections and the definition of sets.

3. **Distributive Laws**:

    - **Union over Intersection (A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C))**:
      To prove this, we need to show that for any element x, x ∈ A ∪ (B ∩ C) if and only if x ∈ (A ∪ B) ∩ (A ∪ C).
      
      This can be proved by considering the properties of unions, intersections, and the definition of sets.

    - **Intersection over Union (A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C))**:
      Similar to the previous property, we can prove this by considering the properties of unions, intersections, and the definition of sets.

4. **Identity Laws**:

    - **Union (A ∪ ∅ = A)**:
      This is straightforward because the union of any set with the empty set is the set itself.

    - **Intersection (A ∩ U = A)**:
      Similarly, the intersection of any set with the universal set is the set itself.

5. **Complement Laws**:

    - **Union with Complement (A ∪ A' = U)**:
      This can be proved by considering the properties of unions and complements. If an element is not in A, then it must be in the complement of A.

    - **Intersection with Complement (A ∩ A' = ∅)**:
      Similar to the previous property, we can prove this by considering the properties of intersections and complements.

6. **Idempotent Laws**:

    - **Union (A ∪ A = A)**:
      This is straightforward because if an element is in A, it's still in A when you union A with itself.

    - **Intersection (A ∩ A = A)**:
      Similarly, if an element is in A, it's still in A when you intersect A with itself.

7. **De Morgan's Laws**:

    - **Union ((A ∪ B)') = A' ∩ B'**:
      To prove this, we need to show that for any element x, x ∈ (A ∪ B)' if and only if x ∈ A' ∩ B'.
      
      This can be proved by considering the properties of unions, intersections, complements, and the definition of sets.

    - **Intersection ((A ∩ B)') = A' ∪ B'**:
      Similar to the previous property, we can prove this by considering the properties of unions, intersections, complements, and the definition of sets.

## Counting principles
## Classes of Set
## Partition of set
Let S be a nonempty set. A partition of S is a subdivision of S into non overlapping, nonempty subsets.
Precisely, a partition of S is a collection {Ai } of nonempty subsets of S such that:
(i) Each a in S belongs to one of the Ai .
(ii) The sets of {Ai } are mutually disjoint; that is, if
Aj ≠ Ak then Aj ∩ Ak = Φ
The subsets in a partition are called cells. Figure given below is a Venn diagram of a partition of the
rectangular set
S of points into five cells, A1, A2,A3,A4,A5.
![](../../statics/Pasted%20image%2020240308110430.png)
## Multiset 
A multiset in mathematics is a generalization of the concept of a set. It’s a collection of unordered numbers (or other elements), where every element X occurs a finite number of times.

The difference between sets and multisets is in how they address multiples: a set includes any number at most once, while a multiset allows for multiple instances of the same number. There is just one set with elements a and b, the set {a,b}, but there are many multisets: {a, b, b}, {a, a, b}, and {a, a, a, a, b, b} are just a few.

**Multiplicity**
The multiplicity of an element x in a multiset is just the number of times that element appears in the set. For instance, in the multiset {3, 3, 4, 5, 6} the element 3 has multiplicity 2. The elements 4, 5, and 6 all have multiplicity 1.

To distinguish between sets and multisets, a notation that incorporates square brackets is sometimes
used: the multiset {a, a, b} can be denoted as \[a, a, b \].
The cardinality of a multiset is constructed by summing up the multiplicities of all its elements

# Relation and Function
