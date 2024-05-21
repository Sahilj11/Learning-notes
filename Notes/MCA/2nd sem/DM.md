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
![](../../statics/Pasted%20image%2020240521081059.png)
![](../../statics/Pasted%20image%2020240521081115.png)
![](../../statics/Pasted%20image%2020240521081246.png)
![](../../statics/Pasted%20image%2020240521081347.png)

### Powerset
The set consisting of all the subsets of a given set A as its elements, is called the power set
of A and is denoted by P(A) or 2<sup>A</sup>. Thus, P(A) or 2<sup>A</sup> = {X: X ⊆ A}
if A = {1, 2}, then PA= {$, {1}, {2}, A}
From these examples we can conclude that if a set A has n elements,then P(A) has 2<sup>n</sup>elements
![](../../statics/Pasted%20image%2020240521081435.png)

### Universal set
A set is called a Universal Set or the Universal discourse if it contains all the sets under consideration in a particular discussion. A universal set is denoted by U.

In connection with the sets N, Z, Q we can take R as the universal set

### Disjoint set
![](../../statics/Pasted%20image%2020240521082029.png)

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
![](../../statics/Pasted%20image%2020240521081702.png)

### Symmetric 
![](../../statics/Pasted%20image%2020240521082549.png)
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
The counting principle, also known as the rule of product, is a fundamental concept in combinatorics that helps determine the number of possible outcomes in various situations. When applied to sets, it allows us to count the number of ways to combine elements from different sets under certain conditions.

### Basic Counting Principle (Rule of Product)
The basic counting principle states that if you have a sequence of events where each event can occur in a certain number of ways, the total number of possible outcomes for the sequence is the product of the number of ways each event can occur.

#### Example:
If you have two sets:
- Set \( A \) with \( |A| = 3 \) elements: \( A = \{a_1, a_2, a_3\} \)
- Set \( B \) with \( |B| = 2 \) elements: \( B = \{b_1, b_2\} \)

The number of ways to choose one element from \( A \) and one element from \( B \) is:
\[ |A| \times |B| = 3 \times 2 = 6 \]

So, the possible pairs are: \( (a_1, b_1), (a_1, b_2), (a_2, b_1), (a_2, b_2), (a_3, b_1), (a_3, b_2) \).

### Extended Counting Principle

The counting principle can be extended to more than two sets. If you have \( n \) sets, the total number of ways to choose one element from each set is the product of the number of elements in each set.

#### Example:
If you have three sets:
- Set \( A \) with \( |A| = 3 \) elements: \( A = \{a_1, a_2, a_3\} \)
- Set \( B \) with \( |B| = 2 \) elements: \( B = \{b_1, b_2\} \)
- Set \( C \) with \( |C| = 4 \) elements: \( C = \{c_1, c_2, c_3, c_4\} \)

The number of ways to choose one element from each set is:
\[ |A| \times |B| \times |C| = 3 \times 2 \times 4 = 24 \]

### Applications of the Counting Principle

1. **Permutations and Combinations:**
   - **Permutations:** The counting principle helps calculate permutations where the order matters. For example, the number of ways to arrange \( n \) distinct items is \( n! \) (n factorial).
   - **Combinations:** The counting principle is also the basis for combinations where the order does not matter. The number of ways to choose \( k \) items from \( n \) items is given by \( \binom{n}{k} \).

2. **Probability:**
   - In probability, the counting principle helps calculate the total number of possible outcomes, which is essential for determining probabilities of specific events.

3. **Cartesian Products:**
   - The principle is directly applied in finding the size of Cartesian products of sets. If \( A \) and \( B \) are sets, then \( |A \times B| = |A| \times |B| \).
## Classes of Set(Write types of sets)
- Singleton : - only one element
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

## Duality 
![](../../statics/Pasted%20image%2020240521083352.png)
![](../../statics/Pasted%20image%2020240521083612.png)

# Relation and Function

## Intro
Cartesian product 
The Cartesian product of A and B is denoted by A×B and is defined by AXB = {(a,b):a∈A, b∈B}
(a, b) is called an ordered pair. Let a∈A, c∈A; b∈B, d∈B.

## Concept of relation
![](../../statics/Pasted%20image%2020240521084319.png)
total possible relation is 2<sup>mXn</sup>
![](../../statics/Pasted%20image%2020240521084615.png)
![](../../statics/Pasted%20image%2020240521084800.png)

Let A and B be two non-empty sets. A subset R of AXB is said to be a relation from A to B.If A=B, then any subset of A X A is said to be a relation on A. If R ⊆ A X B, and (a,b)∈R;a∈A,b∈B,it is also written as *aRb* and is read as ‘a is R related to b’.

The set of the first components of the ordered pairs of R is called the domain and the set of the second components of the ordered pairs of R is called the range of R. If A,B are finite sets and n(A)=x,n(B)=y; then n(AXB)=xy.So,the number of subsets of AXB is2<sup>xy</sup>.Therefore, the number of relations from A to B is 2<sup>x</sup>

## Identity relation
A relation on set is said to be identity relation if each element of ordered pair is related to itself only in the given relation Let A be a non-empty set. I = {(a, a): a∈A} ⊆A xA I<sub>A</sub> is called the identity relation on A.

Let A = {1, 2, 3, 4} Then I = {(1, 1), (2, 2), (3, 3), (4, 4)} ⊆A x A

## Inverse relation
Let A,B be two non-empty sets.Let R be a relation from A to B,i.e. R⊆AxB. The inverse relation of R is denoted by R<sup>-1</sup>,and is defined by R<sup>-1</sup>= {(b, a): (a, b)∈R} ⊆B xA. Clearly, domain of R<sup>-1</sup>= range of R range of R<sup>-1</sup>= domain of R

## Type of relation
![](../../statics/Pasted%20image%2020240308150714.png)
![](../../statics/Pasted%20image%2020240308150207.png)
![](../../statics/Pasted%20image%2020240308150306.png)
![](../../statics/Pasted%20image%2020240308150433.png)
![](../../statics/Pasted%20image%2020240308150639.png)

## Equivalence relation
Let A be a non-empty set. A relation R on A is called an equivalence relation if it is reflexive, symmetric and transitive

## Equivalence Class
![](../../statics/Pasted%20image%2020240308180312.png)
## POSET (Partial ordering relation)
- if R is reflexive , antisymettric and transitive it is partial order relation . And A set 'A' is POSET if it has partial order relation
![](../../statics/Pasted%20image%2020240308193919.png)
## Function
![](../../statics/Pasted%20image%2020240308191103.png)
X is domain , Y is co-domain  and to where we go is range
![](../../statics/Pasted%20image%2020240308191210.png)
### Function Composition

![](../../statics/Pasted%20image%2020240308191701.png)
![](../../statics/Pasted%20image%2020240308191943.png)

### Types of function

#### Injective
![](../../statics/Pasted%20image%2020240308192322.png)
![](../../statics/Pasted%20image%2020240308192412.png)

#### Onto 
![](../../statics/Pasted%20image%2020240308192655.png)

#### Bijective function
![](../../statics/Pasted%20image%2020240308193017.png)

#### Inverse function
![](../../statics/Pasted%20image%2020240308193424.png)

# Logic and Propositional Calculus
## Proposition and its Compound Statement
A proposition (or statement) is a declarative statement which is true or false, but not both.

In everyday life we often combine propositions to form more complex propositions or we can say compound proposition. For 
example combining "Grass is green", and "The sun is red" we say something like "Grass is green and the sun is red"

The fundamental property of a compound proposition is that its truth value is completely determined by the truth values of its sub propositions together with the way in which they are connected to form the compound propositions

## Basic Logic Operation
### Conjunction (∧)
Conjunction, p ∧ q Any two propositions can be combined by the word “and” to form a compound
proposition called the conjunction of the original propositions
![](../../statics/Pasted%20image%2020240310143856.png)

### Disjunction (∨)
Any two propositions can be combined by the word “or” to form a compound proposition called the
disjunction of the original propositions. Symbolically, p ∨ q read “p or q,” denotes the disjunction of p
and q
If p and q are false, then p ∨ q is false; otherwise p ∨ q is true. 

### Negation (¬)
Given any proposition p, another proposition, called the negation of p, can be formed by writing “It is not true that ...” or “It is false that ...” before p or, if possible, by inserting in p the word “not.” Symbolically, the negation of p, read “not p,” is denoted by ¬p

## Tautologies and Contradiction

![](../../statics/Pasted%20image%2020240310144710.png)
A TAUTOLOGY is a formula which is "always true" --- that is, it is true for every assignment of truth
values to its simple components.

The opposite of a tautology is a CONTRADICTION, a formula which is "always false". In other words,
a contradiction is false for every assignment of truth values to its simple components.

Contingency

## Logical Equivalence 
Two propositions P (p, q, . . .) and Q(p, q, . . .) are said to be logically equivalent, or simply equivalent
or equal, denoted by P (p, q, . . .) ≡ Q(p, q, . . .) If they have identical truth tables.

## Conditional and Biconditional
**Conditional**
Let p and q are two statements and these two statements are of the form “If p then q.” Then Such
statements are called conditional statements and are denoted by p → q
![](../../statics/Pasted%20image%2020240310145201.png)
the conditional p → q is frequently read “p implies q” or “p only if q.” The implication p→ q is false only when p is true, and q is false; otherwise, it is always true. In this implication, p is called the hypothesis (or antecedent) and q is called the conclusion (or consequent)

**Biconditional**
If p and q are two statements then "p if and only if q" is a compound statement, denoted as p ↔ q and
referred as a biconditional statement or an equivalence. The equivalence p ↔ q is true only when both p
and q are true or when both p and q are false.

![](../../statics/Pasted%20image%2020240310145238.png)