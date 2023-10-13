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
   |                 | john@example.com   |
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
