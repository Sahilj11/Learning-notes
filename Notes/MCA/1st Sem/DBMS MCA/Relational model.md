## Query Language
![[Pasted image 20230914120733.png]]

## relational algebra
- procedural query language which takes relation as an input and genrates a relation as an output
- it is a language for expressing relational database queries
- uses operators to perform queries . an operator can be either unary or binary 
- Types of operators 
	- Basic / fundamental operators
	- Addititonal / Derived operators
- Operations work on one or more relations to define another relation without changing the original relation
- Operations are performed recursively on a relation
- ![[Pasted image 20230914121544.png]]

### Relational algebra operations 
![[Pasted image 20230914121752.png]]

#### Selection operator 
- unary operator that performs a selection operation
- selects tuples that satisfy give condition(or predicate) from a relation
- denoted by sigma
- ![[Pasted image 20230914122034.png]]
- WHERE clause of sql command corresponds to relational select 
- ![[Pasted image 20230914122153.png]]
- ![[Pasted image 20230914122231.png]]
- ![[Pasted image 20230914122323.png]]
- ![[Pasted image 20230914122402.png]]
#### Projection operator 
- unary operator 
- projects the particular columns (or attributes ) from a relation and it delete column that are not in the projection list
- ![[Pasted image 20230914122549.png]]
- ![[Pasted image 20230914122647.png]]
- ![[Pasted image 20230914122754.png]]
- ![[Pasted image 20230914122842.png]]
- ![[Pasted image 20230914122911.png]]

### Set operators : Union , Set Intersection , Set difference 
- ![[Pasted image 20230914123121.png]]
- set operators are binary operators as they take two input relations 
- to use set operators on two relation . two relation must be compatible 
- two relation are compatible if 
	- both relation must have same number of attributes 
	- Corresponding attributes have same domain 
- Duplicate tuples are automatically eliminated
##### Union operator 
- ![[Pasted image 20230914123518.png]]
- ![[Pasted image 20230914123725.png]]
- even though name of attributes are different , we chosed roll_no as attri name in union table as it is convention to choose name of first table . 
##### Set intersection operator 
![[Pasted image 20230914124148.png]]

![[Pasted image 20230914124316.png]]
because here common tuple is 2-B

##### Set difference 
![[Pasted image 20230914124446.png]]
![[Pasted image 20230914124612.png]]

#### Cartesian product 
![[Pasted image 20230914124910.png]]
SQL : SELECT * from R1,R2
![[Pasted image 20230914125035.png]]
![[Pasted image 20230914125124.png]]
![[Pasted image 20230914125257.png]]
![[Pasted image 20230914125521.png]]

### Rename operator 
![[Pasted image 20230914144121.png]]

### Example
![[Pasted image 20230914144530.png]]

### join operator
![[Pasted image 20230914145825.png]]
- both relation must have some attribute in common
![[Pasted image 20230914151600.png]]
#### Type of join
![[Pasted image 20230914152140.png]]

## Inner join
- Includes only those tuples that satisfy the matching criteria , while the rest of tuples are excluded
##### Theta / conditional join
![[Pasted image 20230914152512.png]]
![[Pasted image 20230914152653.png]]
#####  equi join
![[Pasted image 20230914152808.png]]

#### Natural join
![[Pasted image 20230914153111.png]]
![[Pasted image 20230914153259.png]]
![[Pasted image 20230914153611.png]]
### Outer join
![[Pasted image 20230914153825.png]]
![[Pasted image 20230914154250.png]]
![[Pasted image 20230914154402.png]]
![[Pasted image 20230914154440.png]]
![[Pasted image 20230914154522.png]]
![[Pasted image 20230914154552.png]]
### Division operator 
![[Pasted image 20230914154843.png]]
![[Pasted image 20230914155715.png]]

## Relational calculus 
![[Pasted image 20230914160010.png]]
TRC example :- sql

![[Pasted image 20230914160120.png]]
![[Pasted image 20230914160323.png]]
![[Pasted image 20230914160629.png]]
In the context of relational calculus, which is a formal and theoretical framework for querying relational databases, the existential (∃) and universal (∀) quantifiers are used to express conditions and constraints on the tuples (rows) in a relation (table). Relational calculus is divided into two sub-languages: Tuple Relational Calculus (TRC) and Domain Relational Calculus (DRC). I'll explain the use of these quantifiers in the context of both sub-languages:

1. **Tuple Relational Calculus (TRC)**:

   In TRC, you formulate queries by specifying what you want to retrieve from a relation without specifying how to retrieve it. The quantifiers are used to define conditions on tuples.

   - **Existential Quantifier (∃)** in TRC: In TRC, ∃ is used to express the existence of tuples that satisfy a certain condition. For example, if you have a relation "Employees," you could write a TRC query like this:
   
     `{t | ∃t (Employees(t) ∧ t.Salary > 50000)}`

     This query retrieves all tuples `t` from the "Employees" relation for which there exists a tuple `t` in "Employees" with a salary greater than 50000.

   - **Universal Quantifier (∀)** in TRC: In TRC, ∀ is used to express a condition that must hold true for all tuples in a relation. For example:

     `{t | ∀t (Employees(t) → t.Salary > 40000)}`

     This query retrieves all tuples `t` from the "Employees" relation for which the condition "t.Salary > 40000" holds true for all tuples `t` in "Employees."

2. **Domain Relational Calculus (DRC)**:

   In DRC, you formulate queries by specifying what you want to retrieve from a relation using variables that range over domain values. The quantifiers are used to define conditions on those variables.

   - **Existential Quantifier (∃)** in DRC: In DRC, ∃ is used to express the existence of domain values that satisfy a certain condition. For example:

     `{x | ∃x (Employees(x) ∧ x.Salary > 50000)}`

     This query retrieves all domain values `x` for which there exists a domain value `x` such that "Employees(x)" is true and "x.Salary > 50000" is true.

   - **Universal Quantifier (∀)** in DRC: In DRC, ∀ is used to express a condition that must hold true for all domain values. For example:

     `{x | ∀x (Employees(x) → x.Salary > 40000)}`

     This query retrieves all domain values `x` for which the condition "Employees(x) → x.Salary > 40000" holds true for all domain values `x`.

In both TRC and DRC, these quantifiers help you specify complex conditions and constraints for retrieving data from relations based on the existence or universality of certain criteria within those relations. They are powerful tools for expressing queries and constraints in a formal and precise manner.

![[Pasted image 20230914160800.png]]

### Difference b/w TRC and DRC
Tuple Relational Calculus (TRC) and Domain Relational Calculus (DRC) are two different flavors of relational calculus, which is a formal and theoretical framework for querying relational databases. While they both serve the purpose of expressing queries and constraints, they do so in slightly different ways. Here are the key differences between TRC and DRC:

1. **Form of Expression**:
   - **TRC (Tuple Relational Calculus)**: In TRC, you specify what you want to retrieve from a relation by defining a formula that describes the desired tuples. You use variables ranging over entire tuples (i.e., variables represent entire rows). Queries are expressed as sets of tuples that satisfy the specified conditions.
   - **DRC (Domain Relational Calculus)**: In DRC, you specify what you want to retrieve from a relation by defining a formula that describes the desired attributes or domain values. You use variables ranging over domain values (i.e., variables represent individual column values). Queries are expressed as sets of domain values that satisfy the specified conditions.

2. **Use of Quantifiers**:
   - **TRC (Tuple Relational Calculus)**: TRC uses quantifiers like ∃ (existential) and ∀ (universal) to define conditions on entire tuples. You use these quantifiers to express conditions about rows and the relationships between rows.
   - **DRC (Domain Relational Calculus)**: DRC also uses quantifiers like ∃ and ∀, but they are used to define conditions on individual domain values or attributes. You use these quantifiers to express conditions about column values.

3. **Clarity and Expressiveness**:
   - **TRC (Tuple Relational Calculus)**: TRC can be more intuitive for expressing complex queries that involve conditions on entire rows. It's often easier to understand when the query requires retrieval of specific rows or tuples based on relationships between them.
   - **DRC (Domain Relational Calculus)**: DRC can be more concise and suitable for queries that primarily involve conditions on individual attribute values. It's often used when you want to extract specific attributes or domain values from a relation.

4. **Usage**:
   - **TRC (Tuple Relational Calculus)**: TRC is less commonly used in practice compared to SQL (Structured Query Language) because it focuses on specifying what to retrieve without specifying how to retrieve it. SQL is more widely used for practical database querying.
   - **DRC (Domain Relational Calculus)**: DRC is even less commonly used in practice compared to TRC and SQL. It's primarily used in theoretical discussions and academic contexts to study the formal foundations of database querying.

In summary, TRC and DRC are two variants of relational calculus with distinct approaches to specifying queries. TRC deals with entire rows and can be more intuitive for expressing row-level conditions, while DRC deals with individual column values and is more concise for expressing attribute-level conditions. Both are theoretical frameworks and are not as commonly used in practical database querying as SQL.