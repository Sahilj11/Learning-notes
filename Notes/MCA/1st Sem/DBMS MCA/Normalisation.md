## What is it

- Simple definition:- when you normalise a database table , you structure it in such a way that it cant express redundant information. For eg . in normalised table you wont be able to give 2 DOB to a customer with id 1001.
  - very broadly table can express one version of truth
  - these tables are protect from contradictory data
  - easier to understand
  - satisfy certain referential integrity constraints (ie particular row in one table can be related to at most one row in a related table)
  - easier to enhance and extend
  - protected from
    - insertion anomalies
    - update anomalies
    - deletion anomalies

## Identifying Primary key using functional dependencies

- Steps
  - Identify all candidate key by looking at determinants
  - Determine which candidate key is not functionally dependent on any other candidate key
  - ![](../../../statics/Pasted%20image%2020231013124935.png)

## Types of anomalies

In a relational database management system (DBMS), anomalies are inconsistencies or problems that can occur when the data is not organized or structured correctly. The three main types of anomalies that can occur in a relational database are insertion anomalies, update anomalies, and deletion anomalies. Here are examples of each type:

1. **Insertion Anomalies:**
   Insertion anomalies occur when you experience issues while adding new data to the database. These issues can result in incomplete or incorrect data entries.

   - **Example:** Suppose you have a table to store information about employees and their projects. The table has columns for Employee ID, Employee Name, and Project Name. An insertion anomaly can occur if you try to add a new employee who is not currently assigned to any project. In this case, the entry for the new employee would be incomplete because there's no project associated with them. This is an insertion anomaly because it's difficult to add an employee without a project.

2. **Update Anomalies:**
   Update anomalies happen when you modify data in a way that results in inconsistencies or unexpected changes in the database.
   - **Example:** Let's continue with the employee and project database. Suppose an employee changes their project assignment. If you update only the employee's project in one place but forget to update it in another, the database will contain inconsistent information. For example, if you change Employee A's project from "Project X" to "Project Y" in one record but forget to update the other record, it can lead to a mismatch between the employee's project assignment. This is an update anomaly because the data is no longer consistent.
3. **Deletion Anomalies:**
   Deletion anomalies occur when removing data leads to unintended or incomplete data loss.
   - **Example:** In the same employee and project database, suppose an employee leaves the company. If you delete the record of the employee entirely, you'll lose information about the projects they were involved in. This is a deletion anomaly because removing data about the employee causes unintended data loss, especially if you still need to track the projects.

Normalization, specifically the higher normal forms like Second Normal Form (2NF) and Third Normal Form (3NF), aims to address these anomalies by organizing the data in a way that minimizes redundancy and ensures data integrity. In the above example, you could achieve 2NF or 3NF by splitting the data into separate tables, one for employees and another for projects, with appropriate relationships to avoid anomalies.

## Dependencies types

### Join dependencies

In the context of a relational database management system (DBMS), join dependencies refer to constraints or relationships between tables that involve performing a join operation to retrieve meaningful data from multiple tables. These join dependencies are used to define how data is related or connected across different tables in a database. Join dependencies are a fundamental concept in the field of database design and normalization. There are two primary types of join dependencies:

1. Inclusion Dependencies: An inclusion dependency specifies that the values in one table must be a subset of the values in another table. In other words, it enforces that the data in one table is "included" in another. Inclusion dependencies are often used to represent one-to-one and one-to-many relationships between tables. For example, consider a database where you have a Customers table and an Orders table. An inclusion dependency would specify that the set of customer IDs in the Orders table must be a subset of the customer IDs in the Customers table.

2. Equijoin Dependencies: An equijoin dependency specifies that two or more tables should be joined using an equijoin condition (equality condition) on one or more attributes to retrieve meaningful data. Equijoin dependencies are used to represent relationships that require a join operation based on equality conditions. For example, in a university database, you might have a Students table and a Courses table, and an equijoin dependency would specify that you can join these tables using the student ID to find the courses a particular student is enrolled in.

Join dependencies play a critical role in database normalization and schema design, as they help define the relationships between tables. Ensuring that the join dependencies are correctly represented in the database schema is important for maintaining data integrity and optimizing query performance. In practice, these dependencies are often used to guide the design of foreign keys, indexes, and queries to efficiently retrieve and manipulate data from the database.

### Functional dependencies

a functional dependency is a fundamental concept that helps define the relationships between attributes (columns) in database tables. It describes how the values of one attribute (or a set of attributes) determine or are determined by the values of another attribute within the same table. Functional dependency is critical for designing and understanding the structure of a relational database.

Functional dependency is typically denoted as X -> Y, where X represents a set of attributes and Y represents a single attribute. This notation indicates that the values of attributes in set X uniquely determine the value of attribute Y.

_condition need to be satisfied if determinant value is same to see if it is functional dependecy_
x(determinant) -> y(dependent) if t<sub>1</sub>.x = t<sub>2</sub>.x then t<sub>1</sub>.y = t<sub>2</sub>.y

#### Full vs partial functional dependencies

- Full : - determinants have minimal number of attributes (ie primary key attributes) to maintain the functional dependency with all non-key attributes (ie B is functionally dependent on A but not on a subset of A)
  - order_id , product_id --> quantity
  - here only product_id or only order_id cannot be used to determine quantity but we need both the determinants
- Partial:- Non-key attributes are functionally dependent on a subset of primary key
  - order_id --> order_date,custome_id,name,address
  - product_id --> description , finish , price

#### Trivial functional dependencies

##### Augmented functional dependency

- Non key attributes are functionally dependent on a subset of its determinant
- meaning that there could be multiple attribute on the left but only one of those is necessary to find the value of non key attribute
- for example
  - order_id,order_date --> customer_id
  - order_id --> customer_id
  - here we can get value of customer id from order id alone

##### Equivalent functional dependency

- In this determinants (on the left) and non-key attributes are interchangeable
  - product_id --> description
  - description --> product_id

### Multi-valued functional dependencies

Multi-valued functional dependencies are a concept in database theory that extends the idea of functional dependencies. Functional dependencies describe a relationship between attributes in a relation, where one attribute's value uniquely determines another attribute's value. Multi-valued functional dependencies, on the other hand, describe situations where one attribute's value can determine a set of values for another attribute.

Let's explain multi-valued functional dependencies with an example:

Suppose you have a relation called "EmployeeSkills," which contains information about employees and their skills. This relation has the following attributes:

- EmployeeID (unique identifier for each employee)
- EmployeeName
- EmployeeSkills (a multi-valued attribute that lists the skills an employee possesses)

Now, let's consider some data in this relation:

| EmployeeID | EmployeeName | EmployeeSkills      |
| ---------- | ------------ | ------------------- |
| 1          | Alice        | {Java, Python}      |
| 2          | Bob          | {C++, SQL}          |
| 3          | Carol        | {Java, Python, SQL} |
| 4          | David        | {C++, Java}         |

In this example, the EmployeeSkills attribute is a multi-valued attribute because it can contain a set of values (skills) for each employee.

Now, let's define a multi-valued functional dependency. We say that EmployeeID determines EmployeeSkills (denoted as EmployeeID ->> EmployeeSkills) if, for each employee, their EmployeeSkills are determined by their EmployeeID. This means that for each employee, their set of skills is independent of other employees' skills.

In our example, we can observe the following multi-valued functional dependencies:

1. EmployeeID ->> EmployeeSkills
   - For each employee, their skills are determined by their unique EmployeeID. For example, EmployeeID 1 (Alice) has the skills {Java, Python}, and this set of skills is determined by her EmployeeID.

However, multi-valued functional dependencies also have certain implications:

1. If A ->> B and B ->> C, then A ->> C. This is known as the transitive rule. In the context of our example, if EmployeeID determines EmployeeSkills and EmployeeSkills determine specific skills, then EmployeeID determines specific skills.

2. If A ->> B and B ->> A, then A and B are said to have a mutual multi-valued dependency. In our example, if EmployeeID determines EmployeeSkills and EmployeeSkills determine EmployeeID, we have a mutual multi-valued dependency.

Understanding multi-valued functional dependencies is important for database design and normalization to avoid redundancy and data anomalies when dealing with complex data structures like the one in our example.

### Transitive functional dependencies

- the primary key is determinant for another attribute which is a determinat for a third attribute
  - A --> B --> C
  - B is functionally dependent on A
  - C is functionally dependent on B
  - C is transitively dependent on A through B
  - A is not functionally dependent on B or C
- ![](../../../statics/Pasted%20image%2020231013130001.png)
-

## How to determine whether a table is normalised or not

- there are certain set of criteria which can be used to assess the danger which a non-normalised data can create
- normal forms:- these are like safety assessment and each level representing certain level of safety from redundant date. types are 1NF , 2NF , to 5NF
- Formal definition of normal form
  - In database management systems (DBMS), normal forms are a set of guidelines for organizing the data in relational databases to minimize redundancy and improve data integrity. The normalization process involves decomposing tables into smaller, related tables to eliminate data anomalies, such as update anomalies, insertion anomalies, and deletion anomalies.

### Types of NF

#### First normal forms

- guideline to achieve 1NF
  Certainly, I'll explain each of the guidelines for achieving First Normal Form (1NF) with examples:

Certainly, let's provide examples of normalized tables for each of the guidelines in the context of First Normal Form (1NF):

1. **Using Row Order to Convey Information is Not Permitted:**

   - This guideline means that the order in which rows appear in a table should not carry any meaningful information. Data in a relational database should be unordered, and the order of rows should not be relied upon for interpreting the data
   - in below table at first row order was used to project height ranking , in normalised table separate attribute is there
   - Original Table (Violating 1NF):

   | Student name |
   | ------------ |
   | Ram          |
   | shyam        |
   | rahul        |
   | ankit        |

   - Normalized Table (1NF Compliant):

   **Tasks:**

   | Height ranking | Student name |
   | -------------- | ------------ |
   | 3              | shyam        |
   | 1              | ram          |
   | 4              | rahul        |
   | 2              | ankit        |

   In the normalized table, the order of the tasks no longer conveys information as it did in the original table.

2. **Mixing Data Types within the Same Column is Not Permitted:**

   - Each column in a table should contain data of the same data type. Mixing different data types within a single column can lead to data integrity issues.
   - Original Table (Violating 1NF):

   | Contact          |
   | ---------------- |
   | (123) 456-7890   |
   | john@example.com |
   | (987) 654-3210   |

   - Normalized Table (1NF Compliant):

   **Contacts:**

   | Phone          | Email            |
   | -------------- | ---------------- |
   | (123) 456-7890 |                  |
   | (235) 234-3421 | john@example.com |
   | (987) 654-3210 |                  |

   In the normalized table, phone numbers and email addresses are stored in separate columns with a consistent data type.

3. **Having a Table Without a Primary Key is Not Permitted:**

   - Every table in a relational database must have a primary key, which uniquely identifies each row. A primary key is crucial for data integrity and to avoid duplicate rows.
   - Original Table (Violating 1NF):

   | Order Number | Product  | Quantity |
   | ------------ | -------- | -------- |
   | 1001         | Widget A | 5        |
   | 1002         | Widget B | 3        |
   | 1001         | Widget A | 2        |

   - Normalized Table (1NF Compliant):

   **Orders:**

   | Order ID | Order Number | Product  | Quantity |
   | -------- | ------------ | -------- | -------- |
   | 1        | 1001         | Widget A | 5        |
   | 2        | 1002         | Widget B | 3        |
   | 3        | 1001         | Widget A | 2        |

   In the normalized table, an "Order ID" serves as the primary key, ensuring each row is uniquely identified.

4. **Repeating Groups are Not Permitted:**

   - Repeating groups refer to storing multiple values for the same attribute in a single column. Each column should contain only atomic (indivisible) values
   - Original Table (Violating 1NF):

   | Person | Hobbies                    |
   | ------ | -------------------------- |
   | Alice  | Reading, Painting, Cooking |
   | Bob    | Hiking, Photography        |

   - Normalized Table (1NF Compliant):

   **People:**

   | Person | Hobby       |
   | ------ | ----------- |
   | Alice  | Reading     |
   | Alice  | Painting    |
   | Alice  | Cooking     |
   | Bob    | Hiking      |
   | Bob    | Photography |

   In the normalized table, each hobby is stored in a separate row with a reference to the respective person.

These normalized tables adhere to the guidelines of 1NF by eliminating redundancy and ensuring that data is stored in a structured, atomic form.

#### Second Normal form

- Informal definition:- each non-key attribute must depend on entire primary key
- ![](../../../statics/Pasted%20image%2020231013114901.png)
- here in this example
  - item quantity is depended on both player id and item type
    - {player_id , Item_type} --> {item_Quantity}
  - But player rating is not depended on entire primary key , because it is the property of player only
    - {Player_ID} --> {Player_rating}
- Normalised tables , by creating a separate table for players
- ![](../../../statics/Pasted%20image%2020231013115425.png)

##### Formal explanation

Second Normal Form (2NF) is a level of database normalization that builds upon the concepts of First Normal Form (1NF) to further organize and structure data in a relational database. The primary goal of 2NF is to eliminate partial dependencies by ensuring that non-key attributes are fully functionally dependent on the entire primary key.

To achieve 2NF, a table must meet the following requirements:

1. It must already be in First Normal Form (1NF), which means that each column contains atomic values, and there are no repeating groups or lists within the table.

2. It must have a composite primary key, which consists of two or more attributes (columns). One or more of these attributes may be a foreign key that references another table's primary key.

3. All non-key attributes (attributes that are not part of the primary key) must be fully functionally dependent on the entire composite primary key. This means that the values of non-key attributes should be determined by the combination of all the attributes in the primary key, not just part of it.

To illustrate 2NF, consider an example of a table that stores information about books borrowed from a library:

**LibraryTransactions:**

| TransactionID | BookID | BorrowerName | BookTitle | Author  |
| ------------- | ------ | ------------ | --------- | ------- |
| 1             | 101    | Alice        | "Book1"   | Author1 |
| 2             | 102    | Bob          | "Book2"   | Author2 |
| 3             | 101    | Carol        | "Book1"   | Author1 |

In this table, "TransactionID" is the primary key, but it's not enough to ensure 2NF because we have a partial dependency. The "BookTitle" and "Author" attributes depend on the "BookID," not the entire primary key. We have multiple rows for the same book, and the book's details are repeated, which can lead to data redundancy and inconsistency.

To achieve 2NF, we should create separate tables for books and transactions, where "BookID" becomes the primary key for the "Books" table, and the "TransactionID" remains the primary key for the "Transactions" table. This eliminates partial dependencies and ensures that the book details are fully functionally dependent on the "BookID."

In summary, Second Normal Form (2NF) helps eliminate partial dependencies and reduces data redundancy by ensuring that non-key attributes are fully dependent on the entire composite primary key. This level of normalization is essential for maintaining data integrity and consistency in a relational database.

##### Can non composite primary key table come under 2NF

A table with a non-composite (single-attribute) primary key can still be in Second Normal Form (2NF), but the concept of 2NF becomes particularly relevant when you have a composite (multi-attribute) primary key.

In 2NF, the key requirement is that non-key attributes (attributes that are not part of the primary key) must be fully functionally dependent on the entire primary key, whether the primary key is composed of a single attribute or multiple attributes. Here's a breakdown:

1. **Single-Attribute Primary Key (Non-Composite):** If a table has a primary key consisting of a single attribute, all non-key attributes must be fully functionally dependent on that single attribute. In this case, the concept of partial dependencies doesn't apply because there's only one attribute in the primary key. The table can still be in 2NF as long as non-key attributes depend on the entire primary key.

2. **Composite Primary Key (Multiple Attributes):** When the primary key is composed of multiple attributes (a composite key), it's crucial to ensure that non-key attributes are fully functionally dependent on the entire combination of attributes in the composite key. The 2NF requirement here is primarily aimed at eliminating partial dependencies, where non-key attributes depend on only part of the composite key.

In summary, 2NF is relevant for tables with both single-attribute and composite primary keys. In the case of a single-attribute primary key, all non-key attributes must depend on that attribute entirely. In the case of a composite primary key, non-key attributes must be fully dependent on the entire set of attributes that make up the primary key. The key idea is to eliminate partial dependencies and maintain data integrity.

#### Third normal form

- Every non-key attribute in a table should depend on the key , the whole key , and nothing but key. - if from above definition we remove "non-key" then we get a more strong version of 3rd normal form called Boyce-codd Normal form
  The Third Normal Form (3NF) is a level of normalization in relational database design that helps eliminate data redundancy and improve data integrity by organizing data into separate, related tables. It builds upon the concepts of the First Normal Form (1NF) and Second Normal Form (2NF). To achieve 3NF, a table must meet the following two criteria:

1. It must be in 2NF: This means that the table should first satisfy the requirements of the Second Normal Form, which include having a composite primary key (a primary key composed of more than one attribute) and ensuring that all non-key attributes are functionally dependent on the entire primary key.

2. It must not have transitive dependencies: A transitive dependency occurs when an attribute depends on another attribute, which in turn depends on the primary key. In a 3NF table, all non-key attributes should be directly dependent on the primary key and should not have indirect dependencies through other non-key attributes.
   ![](../../../statics/Pasted%20image%2020231013120948.png)
   3NF formids this type of dependencies
   Normalised table
   ![](../../../statics/Pasted%20image%2020231013121046.png)

To illustrate 3NF with an example, let's consider a simplified database for a library:

**Table: Books**

- ISBN (Primary Key)
- Title
- Author
- Author Birthdate
- Author Nationality

In this case, we have a transitive dependency because the attributes "Author Birthdate" and "Author Nationality" depend on the non-key attribute "Author," which itself depends on the primary key "ISBN." To bring this table into 3NF, we can create two separate tables:

**Table: Books**

- ISBN (Primary Key)
- Title
- Author (Foreign Key)

**Table: Authors**

- Author (Primary Key)
- Author Birthdate
- Author Nationality

Now, the Authors table has a primary key of "Author," and the Books table has a foreign key relationship with the Authors table. This structure satisfies 3NF because it eliminates the transitive dependency by creating a separate table for author-related information.

In summary, the Third Normal Form (3NF) is a critical step in database normalization, ensuring that data is efficiently organized and minimizing data redundancy while preserving data integrity by removing transitive dependencies. This normalization process helps maintain data consistency and simplifies data retrieval and manipulation in relational databases.

#### Fourth normal form

Fourth Normal Form (4NF) is a level of database normalization that deals with multi-valued dependencies in a relational database. It extends the concepts of the previous normalization forms (1NF, 2NF, and 3NF) by addressing situations where a single row in a table can be associated with multiple, independent values for certain attributes. 4NF aims to eliminate redundancy and maintain data integrity in such cases.

Multivalued dependencies in a table must be multivalued dependencies on the key

To understand 4NF, let's use an example:

Suppose you have a relation named "BookAuthors," which tracks information about books and their authors. This relation has the following attributes:

- ISBN (unique identifier for books)
- Title (title of the book)
- Author (name of the author)

Now, let's consider some data in this relation:

| ISBN      | Title   | Author    |
| --------- | ------- | --------- |
| 978-12345 | "Book1" | "Author1" |
| 978-12345 | "Book1" | "Author2" |
| 978-67890 | "Book2" | "Author2" |
| 978-67890 | "Book2" | "Author3" |

In this example, the ISBN attribute uniquely identifies each book, but you can see that for some books, there are multiple authors associated with the same ISBN. This creates a multi-valued dependency because the ISBN determines a set of authors, and multiple authors can be associated with a single book.

To bring this relation into 4NF, we need to split it into two relations:

1. The "Books" relation:

   - ISBN (unique identifier for books)
   - Title (title of the book)

2. The "Authors" relation:
   - ISBN (foreign key referencing the Books relation)
   - Author (name of the author)

After splitting the relation, you achieve 4NF because there are no multi-valued dependencies anymore. The Books relation contains unique ISBNs and their corresponding titles, while the Authors relation links ISBNs to individual authors.

Here's how the data would look in the normalized form:

**Books Relation:**

| ISBN      | Title   |
| --------- | ------- |
| 978-12345 | "Book1" |
| 978-67890 | "Book2" |

**Authors Relation:**

| ISBN      | Author    |
| --------- | --------- |
| 978-12345 | "Author1" |
| 978-12345 | "Author2" |
| 978-67890 | "Author2" |
| 978-67890 | "Author3" |

This 4NF decomposition reduces redundancy, as book information is stored only once in the "Books" relation, and the "Authors" relation maintains the relationships between ISBNs and authors. It ensures that the data is more organized and prevents anomalies that can occur in the presence of multi-valued dependencies.

#### Fifth normal form

Fifth Normal Form (5NF), also known as Project-Join Normal Form (PJ/NF), is a level of database normalization that focuses on eliminating redundancy and addressing issues related to the projection and joining of relations. It is a highly specialized form of normalization typically used in data warehousing and complex database systems. To illustrate 5NF, let's consider a simple example:

Suppose we have a database for tracking product sales in a retail store. We have three relations: Products, Customers, and Sales.

1. **Products (ProductID, ProductName, Manufacturer)**

   - ProductID (Primary Key)
   - ProductName
   - Manufacturer

2. **Customers (CustomerID, CustomerName)**

   - CustomerID (Primary Key)
   - CustomerName

3. **Sales (SaleID, CustomerID, ProductID, Date, Quantity)**
   - SaleID (Primary Key)
   - CustomerID (Foreign Key referencing Customers)
   - ProductID (Foreign Key referencing Products)
   - Date
   - Quantity

In the Sales relation, we store information about each sale, including the customer, product, date, and quantity.

Now, let's say we want to achieve 5NF by removing redundancy and ensuring that there are no non-trivial join dependencies. In this example, there is a non-trivial join dependency between Products, Customers, and Sales because, to obtain the names of the customers and products associated with each sale, we need to join these three relations.

To bring this database into 5NF, we can create the following relations:

1. **Products (ProductID, ProductName, Manufacturer)**

2. **Customers (CustomerID, CustomerName)**

3. **Sales (SaleID, CustomerID, ProductID, Date, Quantity)**

4. **SalesProducts (SaleID, ProductID)**

   - SaleID (Foreign Key referencing Sales)
   - ProductID (Foreign Key referencing Products)

5. **SalesCustomers (SaleID, CustomerID)**
   - SaleID (Foreign Key referencing Sales)
   - CustomerID (Foreign Key referencing Customers)

By introducing the **SalesProducts** and **SalesCustomers** relations, we have removed the non-trivial join dependency between Products, Customers, and Sales. Each sale is now represented by its own unique SaleID, and we can efficiently retrieve product and customer information by joining the appropriate relations. This decomposition eliminates redundancy and allows for more efficient queries while maintaining data integrity.

In 5NF, the goal is to ensure that you can derive all information without any non-trivial join dependencies, making it useful for complex data warehousing scenarios where large volumes of data need to be stored and efficiently retrieved.

## Denormalisation

Denormalization is a database design technique that involves intentionally introducing redundancy into a relational database. This goes against the principles of normalization, which aims to reduce redundancy and improve data integrity. Denormalization is used when there is a specific need to optimize database performance for read-heavy operations, often at the cost of increased storage space and potential data update complexities.

Here are some scenarios in which denormalization is needed and when normalization might not be required:

1. Performance Optimization: Denormalization is primarily used to improve query performance. When a database is normalized to the extreme, it can lead to complex joins and slower query execution times, especially for read-heavy workloads. Denormalizing the data can reduce the number of joins, resulting in faster query performance.

2. Reporting and Analytics: In data warehousing and reporting systems, where complex queries and aggregations are common, denormalization is often employed to simplify and speed up these operations.

3. Frequently Accessed Data: When certain pieces of data are frequently accessed together, denormalization can be used to store them together in a single table or document. This reduces the need for joining multiple tables and improves query performance.

4. Reduced Complexity: In some cases, normalization can lead to an overly complex schema that is difficult to work with. Denormalizing the data can simplify the schema and make it more intuitive for developers.

Benefits of Denormalization:

1. Improved Query Performance: Denormalization can significantly improve the speed of read operations, as it reduces the need for complex joins and related overhead.

2. Reduced Join Complexity: Fewer joins mean simpler SQL queries, which are easier to write and maintain.

3. Enhanced Data Retrieval: Denormalization is particularly useful for data retrieval-heavy applications, such as reporting and analytics, where quick access to aggregated or summarized data is crucial.

4. Minimized Locking and Concurrency Issues: In some cases, denormalization can reduce contention for locks during database updates, as it may involve fewer tables that need to be modified.
   -ves
   Certainly, here are the top 5 disadvantages of denormalization:

5. **Data Redundancy:** Denormalization introduces redundancy into the database, leading to increased storage requirements and the potential for data inconsistencies.

6. **Update Anomalies:** Redundant data can result in update anomalies, making it challenging to maintain data consistency and integrity.

7. **Increased Complexity:** Denormalized databases are more complex to manage and maintain, both in terms of schema design and data updates.

8. **Query Performance Trade-offs:** While read query performance may improve, write query performance can suffer due to the need to update multiple tables.

9. **Constraints and Validation:** Enforcing data constraints and validation can be more challenging in denormalized databases, increasing the risk of data errors.
   However, denormalization comes with trade-offs, including increased storage requirements, data update anomalies, and the need for careful management to ensure data consistency. It is not suitable for all database systems and should be used judiciously, with a clear understanding of the specific use cases where it offers benefits. Normalization, on the other hand, is essential for maintaining data integrity, reducing redundancy, and ensuring consistency, especially in transactional databases. The decision to denormalize should be made with a thorough understanding of the application's requirements and performance considerations.

## Decomposition

Decomposition in database management systems (DBMS) is a process of breaking down a single relation (table) into multiple smaller relations, often referred to as "child" relations. This process is a key step in the normalization of a database schema. Decomposition is primarily aimed at improving data integrity, reducing data redundancy, and simplifying database maintenance.

Here are detailed notes on decomposition in DBMS:

**1. Purpose of Decomposition:**

- Decomposition is used to achieve a higher level of normalization in a relational database schema.
- It helps in organizing data in a way that minimizes data redundancy and ensures data consistency.

**2. Normalization:**

- Decomposition is closely related to the concept of normalization. Normalization is a series of rules and guidelines used to organize data in a relational database to reduce data redundancy and ensure data integrity.
- There are several normal forms (e.g., 1NF, 2NF, 3NF, BCNF, 4NF, 5NF) that indicate the level of normalization, and decomposition is the process of achieving these normal forms.

**3. Functional Dependencies:**

- Decomposition is guided by the functional dependencies that exist in the data. Functional dependencies describe the relationships between attributes in a relation.
- For example, if you have a relation R with attributes A, B, and C, a functional dependency A -> B indicates that for each unique value of A, there is a unique value of B.

**4. Types of Decomposition:**

- Lossless Decomposition: A decomposition is considered lossless if it preserves all the information from the original relation without losing any data. This means that you can reconstruct the original relation from its decomposed parts.
- Dependency-Preserving Decomposition: In a dependency-preserving decomposition, all functional dependencies in the original relation should be preserved in the decomposed relations.

**5. Decomposition Steps:**

- Identify the functional dependencies in the original relation.
- Determine the normal form you want to achieve (e.g., 3NF or BCNF).
- Break down the original relation into smaller relations such that the functional dependencies are preserved.
- Check if the decomposition is lossless and dependency-preserving. Adjust the decomposition as needed to meet these criteria.

**6. Advantages of Decomposition:**

- Reduced data redundancy: Decomposition ensures that data is stored efficiently without unnecessary duplication.
- Improved data integrity: By reducing redundancy and adhering to normalization rules, data consistency and accuracy are improved.
- Easier maintenance: Smaller, well-structured relations are easier to manage and maintain.

**7. Considerations:**

- Decomposition is not always suitable for every database. In some cases, a certain level of denormalization may be needed to optimize query performance, although this comes with its own trade-offs.
- The decomposition process can lead to a larger number of tables in the database, which may increase the complexity of queries that require joining multiple tables.

**8. Examples:**

- Consider an employee database with a single "Employee" table. This table can be decomposed into "EmployeeInfo" and "EmployeeSalary" tables to reduce data redundancy and maintain data integrity.

In summary, decomposition in DBMS is a crucial process in achieving higher levels of normalization, reducing data redundancy, and maintaining data integrity in a relational database. It is guided by functional dependencies and can result in a more organized and efficient database schema.
