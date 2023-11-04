## SQL Basics 
Sure, here's a basic note on SQL (Structured Query Language):

**What is SQL?**
SQL (Structured Query Language) is a Database language used for manipulating and managing data stored in relational databases. 

**Basic Operations**
1. **Create:** it refers to the action of adding new data to a database. 
2. **Read:** it involves retrieving or accessing data from the database. 
3. **Update:** it is used to modify or edit existing data in the database. 
4. **Delete:** it is used to remove or delete data from the database. 

**Key Concepts in SQL:**
1. **Data Manipulation Language (DML):**
   - **SELECT:** Used to retrieve data from a database.
   - **INSERT:** Adds new records into a database table.
   - **UPDATE:** Modifies existing records in a database table.
   - **DELETE:** Removes records from a database table.
2. **Data Definition Language (DDL):**
   - **CREATE:** Constructs new databases, tables, or other objects.
   - **ALTER:** Modifies existing database objects.
   - **DROP:** Deletes databases, tables, or other objects.
   - **TRUNCATE:** Removes all records from a table without logging individual row deletions.
3. **Database Queries:**
  - **SELECT:** Used to fetch data from one or more tables based on specified criteria.
  - **WHERE:** Filters data based on given conditions.
  - **GROUP BY:** Groups rows that have the same values into summary rows.
  - **ORDER BY:** Sorts the result set in ascending or descending order.
4. **Database Joins:**
  - **INNER JOIN:** Retrieves records that have matching values in both tables.
  - **LEFT (OUTER) JOIN:** Retrieves all records from the left table and matched records from the right table.
  - **RIGHT (OUTER) JOIN:** Retrieves all records from the right table and matched records from the left table.
  - **FULL (OUTER) JOIN:** Retrieves all records when there is a match in either the left or right table.
5. **Constraints:**
  - **PRIMARY KEY:** Uniquely identifies each record in a table.
  - **FOREIGN KEY:** Ensures referential integrity between two related tables.
  - **UNIQUE:** Ensures that all values in a column are different.
  - **NOT NULL:** Ensures that a column cannot have a NULL value.
6. **Normalization:**
  - The process of organizing data in a database to minimize redundancy and dependency.
7. **Transactions:**
  - A collection of SQL statements executed as a single unit of work.
