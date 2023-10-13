## What is it 
- Simple definition:- when you normalise a database table , you structure it in such a way that it cant express redundant information. For eg . in normalised table you wont be able to give 2 DOB to a customer with id 1001. 
	- very broadly table can express one version of truth
	- these tables are protect from contradictory data 
	- easier to understand
	- easier to enhance and extend
	- protected from 
		- insertion anomalies
		- update anomalies
		- deletion anomalies

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

   | Student name|
   | ------- |
   | Ram     | 
   | shyam      |
   | rahul       |
   | ankit    |

   - Normalized Table (1NF Compliant):

   **Tasks:**

   | Height ranking| Student name       |
   | ------- | ---------------------- |
   | 3      | shyam  |
   | 1       | ram                |
   | 4       | rahul           |
   | 2       | ankit               |

   In the normalized table, the order of the tasks no longer conveys information as it did in the original table.

2. **Mixing Data Types within the Same Column is Not Permitted:**
   - Each column in a table should contain data of the same data type. Mixing different data types within a single column can lead to data integrity issues.
   - Original Table (Violating 1NF):

   | Contact           |
   | ------------------ |
   | (123) 456-7890     |
   | john@example.com   |
   | (987) 654-3210     |

   - Normalized Table (1NF Compliant):

   **Contacts:**

   | Phone           | Email              |
   | --------------- | ------------------- |
   | (123) 456-7890   |                   |
   |   (235) 234-3421              | john@example.com   |
   | (987) 654-3210   |                   |

   In the normalized table, phone numbers and email addresses are stored in separate columns with a consistent data type.

3. **Having a Table Without a Primary Key is Not Permitted:**
   - Every table in a relational database must have a primary key, which uniquely identifies each row. A primary key is crucial for data integrity and to avoid duplicate rows.
   - Original Table (Violating 1NF):

   | Order Number | Product       | Quantity |
   | ------------ | ------------- | -------- |
   | 1001         | Widget A      | 5        |
   | 1002         | Widget B      | 3        |
   | 1001         | Widget A      | 2        |

   - Normalized Table (1NF Compliant):

   **Orders:**

   | Order ID | Order Number | Product       | Quantity |
   | -------- | ------------ | ------------- | -------- |
   | 1        | 1001         | Widget A      | 5        |
   | 2        | 1002         | Widget B      | 3        |
   | 3        | 1001         | Widget A      | 2        |

   In the normalized table, an "Order ID" serves as the primary key, ensuring each row is uniquely identified.

4. **Repeating Groups are Not Permitted:**
   - Repeating groups refer to storing multiple values for the same attribute in a single column. Each column should contain only atomic (indivisible) values
   - Original Table (Violating 1NF):

   | Person | Hobbies                |
   | ------ | ---------------------- |
   | Alice  | Reading, Painting, Cooking |
   | Bob    | Hiking, Photography     |

   - Normalized Table (1NF Compliant):

   **People:**

   | Person | Hobby               |
   | ------ | ------------------- |
   | Alice  | Reading             |
   | Alice  | Painting            |
   | Alice  | Cooking             |
   | Bob    | Hiking              |
   | Bob    | Photography         |

   In the normalized table, each hobby is stored in a separate row with a reference to the respective person.

These normalized tables adhere to the guidelines of 1NF by eliminating redundancy and ensuring that data is stored in a structured, atomic form.

#### Second Normal form
- Informal definition:- each non-key attribute must depend on entire primary key
- ![[Pasted image 20231013114901.png]]
- here in this example 
	- item quantity is depended on both player id and item type 
		-  {player_id , Item_type} --> {item_Quantity}
	- But player rating is not depended on entire primary key , because it is the property of player only
		- {Player_ID} --> {Player_rating} 
- Normalised tables , by creating a separate table for players
- ![[Pasted image 20231013115425.png]]

##### Formal explanation
Second Normal Form (2NF) is a level of database normalization that builds upon the concepts of First Normal Form (1NF) to further organize and structure data in a relational database. The primary goal of 2NF is to eliminate partial dependencies by ensuring that non-key attributes are fully functionally dependent on the entire primary key.

To achieve 2NF, a table must meet the following requirements:

1. It must already be in First Normal Form (1NF), which means that each column contains atomic values, and there are no repeating groups or lists within the table.

2. It must have a composite primary key, which consists of two or more attributes (columns). One or more of these attributes may be a foreign key that references another table's primary key.

3. All non-key attributes (attributes that are not part of the primary key) must be fully functionally dependent on the entire composite primary key. This means that the values of non-key attributes should be determined by the combination of all the attributes in the primary key, not just part of it.

To illustrate 2NF, consider an example of a table that stores information about books borrowed from a library:

**LibraryTransactions:**

| TransactionID | BookID | BorrowerName | BookTitle      | Author      |
| ------------- | ------ | ------------ | -------------- | ----------- |
| 1             | 101    | Alice        | "Book1"        | Author1     |
| 2             | 102    | Bob          | "Book2"        | Author2     |
| 3             | 101    | Carol        | "Book1"        | Author1     |

In this table, "TransactionID" is the primary key, but it's not enough to ensure 2NF because we have a partial dependency. The "BookTitle" and "Author" attributes depend on the "BookID," not the entire primary key. We have multiple rows for the same book, and the book's details are repeated, which can lead to data redundancy and inconsistency.

To achieve 2NF, we should create separate tables for books and transactions, where "BookID" becomes the primary key for the "Books" table, and the "TransactionID" remains the primary key for the "Transactions" table. This eliminates partial dependencies and ensures that the book details are fully functionally dependent on the "BookID."

In summary, Second Normal Form (2NF) helps eliminate partial dependencies and reduces data redundancy by ensuring that non-key attributes are fully dependent on the entire composite primary key. This level of normalization is essential for maintaining data integrity and consistency in a relational database.

##### Can non composite primary key table come under 2NF
A table with a non-composite (single-attribute) primary key can still be in Second Normal Form (2NF), but the concept of 2NF becomes particularly relevant when you have a composite (multi-attribute) primary key.

In 2NF, the key requirement is that non-key attributes (attributes that are not part of the primary key) must be fully functionally dependent on the entire primary key, whether the primary key is composed of a single attribute or multiple attributes. Here's a breakdown:

1. **Single-Attribute Primary Key (Non-Composite):** If a table has a primary key consisting of a single attribute, all non-key attributes must be fully functionally dependent on that single attribute. In this case, the concept of partial dependencies doesn't apply because there's only one attribute in the primary key. The table can still be in 2NF as long as non-key attributes depend on the entire primary key.

2. **Composite Primary Key (Multiple Attributes):** When the primary key is composed of multiple attributes (a composite key), it's crucial to ensure that non-key attributes are fully functionally dependent on the entire combination of attributes in the composite key. The 2NF requirement here is primarily aimed at eliminating partial dependencies, where non-key attributes depend on only part of the composite key.

In summary, 2NF is relevant for tables with both single-attribute and composite primary keys. In the case of a single-attribute primary key, all non-key attributes must depend on that attribute entirely. In the case of a composite primary key, non-key attributes must be fully dependent on the entire set of attributes that make up the primary key. The key idea is to eliminate partial dependencies and maintain data integrity.
