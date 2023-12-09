## (Experiment 1) SQL Basics

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

## (Experiment 2) Creating a Database

![](../../../../statics/Pasted%20image%2020231109130034.png)

1. **Open the Command Line Interface (CLI)**

2. **Login to MySQL**

   ```
   mysql -u sahil -p
   ```

3. **Create a Database**: Once you're logged in, you can create a new database using the `CREATE DATABASE` command. For example, let's create a database named `my_database`:

   ```sql
   CREATE DATABASE dbms_pract_60;
   ```

4. **Verify the Creation**: You can verify if the database has been created successfully using the following command:

   ```sql
   SHOW DATABASES;
   ```

   This command will display a list of all the databases in your MySQL server.

5. **Using created database**:- After creating database now you have to use it to add data to it

```sql
USE dbms_pract_60;
```

## (Experiment 3) Create Table with Constraints

You can use the CREATE TABLE command with specified constraints to create a table in MySQL with constraints, such as primary keys, foreign keys, unique constraints, or non null constraints. Here's one instance:

![](../../../../statics/Pasted%20image%2020231117081843.png)

Here are the functions of this SQL script:

```sql
CREATE TABLE customers_60 (
    user_id INT AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(100) NOT NULL,
    PRIMARY KEY (user_id),
);
```

1. The primary key field, user_id, is an integer that automatically increases with each new record.
2. The string field username requires unique values.
3. The string field "email" is configured to be unique and non-nullable.
4. The string field password is configured to be non-nullable.

These fields are designated as main keys and unique keys, respectively, by the `main KEY` and `UNIQUE KEY` constraints.

Keep in mind that depending on the type of data you're working with, different data types and constraints may apply.
To create a table in MySQL with constraints, such as primary keys, foreign keys, unique constraints, or not null constraints, you can use the `CREATE TABLE` statement with specific constraints.

## (Experiment 4) Alter Table

The `ALTER TABLE` statement in MySQL is used to modify an existing table by adding, modifying, or dropping columns, constraints, or indexes. Here are some examples of how to use `ALTER TABLE` in MySQL:

### Add a new column to an existing table:

![](../../../../statics/Pasted%20image%2020231117082216.png)

```sql
ALTER TABLE your_table_name
ADD new_column_name data_type;
```

Example:

```sql
ALTER TABLE users
ADD age INT;
```

This command adds a new column named `age` of type `INT` to the existing `users` table.

### Drop a column from a table:

![](../../../../statics/Pasted%20image%2020231117082404.png)

```sql
ALTER TABLE your_table_name
DROP COLUMN column_name;
```

Example:

```sql
ALTER TABLE users
DROP COLUMN age;
```

This command removes the `age` column from the `users` table.

### Modify a column's data type:

![](../../../../statics/Pasted%20image%2020231117082315.png)

```sql
ALTER TABLE your_table_name
MODIFY column_name new_data_type;
```

Example:

```sql
ALTER TABLE users
MODIFY age VARCHAR(3);
```

This command changes the data type of the `age` column from `INT` to `VARCHAR(3)`.

### Add a primary key constraint:

```sql
ALTER TABLE your_table_name
ADD PRIMARY KEY (column_name);
```

Example:

```sql
ALTER TABLE users
ADD PRIMARY KEY (user_id);
```

This command sets the `user_id` column as the primary key in the `users` table.

### Add a foreign key constraint:

```sql
ALTER TABLE your_table_name
ADD CONSTRAINT fk_constraint_name
FOREIGN KEY (column_name)
REFERENCES related_table(related_column);
```

Example:

```sql
ALTER TABLE orders
ADD CONSTRAINT fk_user_id
FOREIGN KEY (user_id)
REFERENCES users(user_id);
```

This command adds a foreign key constraint `fk_user_id` on the `orders` table's `user_id` column, referencing the `user_id` column in the `customers_60s` table.

## (Experiment 5) Add a record to database

To add a record (also known as a row or entry) to a database table in MySQL, you can use the `INSERT INTO` statement. Here's an example of how to add a record to a table:

Let's say you have a table named `customers_60` with columns `user_id`, `username`, `email`, and `password`. To insert a new record into this table:

```sql
INSERT INTO customers_60 (user_id, username, email, password)
VALUES (1, 'Sahil', 'sahil123@gmail.com', 'securepassword');
```

![](../../../../statics/Pasted%20image%2020231117082755.png)

This SQL command inserts a new record into the `customers_60s` table. You specify the columns that will receive the values within parentheses after the table name in the `INSERT INTO` statement. Then, using the `VALUES` keyword, you provide the values for those columns in the same order.

The `VALUES` clause corresponds to the respective columns in the table. For instance, in the above example, the values `1`, `'Sahil'`, `'sahil123@gmail.com'`, and `'securepassword'` are inserted into the columns `user_id`, `username`, `email`, and `password`, respectively.

If the `user_id` column is set to auto-increment and you don't explicitly specify the value for it, the database will automatically assign the next incremental value.

Remember to ensure that the data types and constraints align with the table's schema to prevent errors while inserting records.

## (Experiment 6) Viewing the database

1. **Select the Database:**
   Choose the database you want to work with:

   ```sql
   USE your_database_name;
   ```

   Replace `your_database_name` with the actual name of your database.

2. **View Tables:**
   ![](../../../../statics/Pasted%20image%2020231117083207.png)
   To see the tables in the selected database, you can use the following query:

   ```sql
   SHOW TABLES;
   ```

3. **View Table Structure:**
   ![](../../../../statics/Pasted%20image%2020231117083238.png)
   If you want to see the structure (columns and their data types) of a specific table, you can use:

   ```sql
   DESCRIBE your_table_name;
   ```

   Replace `your_table_name` with the actual name of your table.

4. **View Table Data:**
   ![](../../../../statics/Pasted%20image%2020231117083309.png)
   To view the data in a table, you can use the `SELECT` statement:

   ```sql
   SELECT * FROM your_table_name;
   ```

   Replace `your_table_name` with the actual name of your table. This will retrieve all columns (`*`) for all rows in the specified table.

   If you only want specific columns, you can specify them in the query:
   ![](../../../../statics/Pasted%20image%2020231117083339.png)

   ```sql
   SELECT column1, column2 FROM your_table_name;
   ```

   Replace `column1` and `column2` with the actual column names.

## (Experiment 8) Modify record

To modify (update) records in MySQL, you can use the `UPDATE` statement. Here's a basic example:

```sql
UPDATE your_table_name
SET column1 = new_value1, column2 = new_value2
WHERE your_condition;
```

Replace the following placeholders:

- `your_table_name`: The name of your table.
- `column1`, `column2`: The names of the columns you want to update.
- `new_value1`, `new_value2`: The new values you want to set for the specified columns.
- `your_condition`: The condition that determines which records to update. If you omit the `WHERE` clause, all records in the table will be updated.

For example, let's say you have a table named `customers_60` and you want to update the salary of the employee with ID 1:
![](../../../../statics/Pasted%20image%2020231117083910.png)

```sql
UPDATE customers_60
SET username = 'John'
WHERE user_id = 1;
```

This query updates the `username` column for the employee with `user_id` equal to 1.

If you want to update multiple columns, you can include them in the `SET` clause:
![](../../../../statics/Pasted%20image%2020231117084027.png)

```sql
UPDATE customers_60
SET email = 'john@gmail.com', password = 'qwerty'
WHERE user_id = 1;
```

This query updates both the `email` and `password` columns for the employee with `user_id` equal to 1.

Always be cautious when using the `UPDATE` statement, especially without a `WHERE` clause, as it can update a large number of records. Make sure to use the `WHERE` clause to specify the condition for the records you want to update.

## (Experiment 9) Ordering record

To order records in MySQL, you can use the `ORDER BY` clause in your `SELECT` statement. The `ORDER BY` clause is used to sort the result set based on one or more columns. Here's the basic syntax:

```sql
SELECT column1, column2, ...
FROM your_table_name
ORDER BY column_to_sort [ASC | DESC], ...;
```

- `column1, column2, ...`: The columns you want to select in your result set.
- `your_table_name`: The name of your table.
- `column_to_sort`: The column by which you want to order the result set.
- `ASC` (Ascending) or `DESC` (Descending): The order in which you want to sort the result set. ASC is the default if not specified.

For example, if you have a table named `customers_60` and you want to retrieve the names in ascending order:

![](../../../../statics/Pasted%20image%2020231117084848.png)

```sql
SELECT *
FROM customers_60
ORDER BY username ASC;
```

## (Experiment 10) Grouping record

To group records in MySQL, you can use the `GROUP BY` clause along with aggregate functions like `COUNT`, `SUM`, `AVG`, etc. This allows you to group rows based on the values in one or more columns and perform calculations on each group. Here's a basic example using the `customers_60` table you provided:
![](../../../../statics/Pasted%20image%2020231117085217.png)

1. **Group by the `username` column and count the number of users with each username:**

![](../../../../statics/Pasted%20image%2020231117085423.png)

````sql
    SELECT username, COUNT(*) AS user_count
    FROM customers_60
    GROUP BY username
    ```

This query counts the number of occurrences of each unique `username` in the `customers_60` table.

2. **Group by the `username` column and calculate the average password length for each user:**

![](../../../../statics/Pasted%20image%2020231117085657.png)
```sql
    SELECT username, AVG(CHAR_LENGTH(password)) AS avg_password_length
    FROM customers_60
    GROUP BY username;
````

This query calculates the average password length for each unique `username` in the `customers_60` table.

## (Experiment 11) Using Aggregate functions

![](../../../../statics/Pasted%20image%2020231117090352.png)

1. **Count the total number of users:**
   ![](../../../../statics/Pasted%20image%2020231117090436.png)

````sql
    SELECT COUNT(*) AS total_users
    FROM customers_60;
    ```

 This query returns the total number of rows in the `customers_60` table.

2. **Find the average length of passwords:**
![](../../../../statics/Pasted%20image%2020231117090555.png)
 ```sql
    SELECT AVG(CHAR_LENGTH(password)) AS average_password_length
    FROM customers_60;
    ```

 This query calculates the average length of passwords in the `customers_60` table.

3. **Find the maximum and minimum age among the users:**
![](../../../../statics/Pasted%20image%2020231117090807.png)
```sql
    SELECT MAX(age) AS max_age, MIN(age) AS min_age
    FROM customers_60;
    ```

Assuming there is a `age` column in your table, this query finds the maximum and minimum age values.

## (Experiment 12) Queries using the Set operations
## (Experiment 13) Creating views
Views allow you to encapsulate complex queries and present the result as if it were a table. Here's how you can create a view:

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM your_table_name
WHERE your_condition;
````

Replace the following placeholders:

- `view_name`: The name you want to give to your view.
- `column1, column2, ...`: The columns you want to include in your view.
- `your_table_name`: The name of the table you are querying.
- `your_condition`: The condition to filter the records (optional).

For example, let's say you want to create a view that contains the usernames and email addresses of users from the `customers_60` table:
![](../../../../statics/Pasted%20image%2020231117140850.png)

```sql
CREATE VIEW user_info AS
SELECT username, email
FROM customers_60;
```

Now, you can query this view as if it were a table:

```sql
SELECT * FROM user_info;
```

This will retrieve the usernames and email addresses from the `user_info` view.

To drop (delete) a view, you can use the `DROP VIEW` statement:

```sql
DROP VIEW IF EXISTS view_name;
```

Replace `view_name` with the name of the view you want to drop. The `IF EXISTS` clause prevents an error if the view doesn't exist.

## (Experiment 14) Generating Sub-Queries

A subquery in MySQL is a query nested within another query. Subqueries, also known as nested queries or inner queries, are used to retrieve data that will be used in the main query as a condition to further restrict the data to be retrieved. Subqueries can be used in various parts of a SQL statement, such as the SELECT, FROM, WHERE, or HAVING clauses.

![](../../../../statics/Pasted%20image%2020231117144046.png)

## (Experiment 15) Join in SQL

In MySQL, the `JOIN` clause is used to combine rows from two or more tables based on a related column between them. There are different types of joins in MySQL, including INNER JOIN, LEFT JOIN (or LEFT OUTER JOIN), RIGHT JOIN (or RIGHT OUTER JOIN), and FULL JOIN (or FULL OUTER JOIN). Here's a brief overview of each:

1. **INNER JOIN:**

   - Returns only the rows where there is a match in both tables based on the specified condition.
   - ![](../../../../statics/Pasted%20image%2020231117145507.png)

   ```sql
   SELECT *
   FROM table1
   INNER JOIN table2 ON table1.column = table2.column;
   ```

2. **LEFT JOIN (or LEFT OUTER JOIN):**

   - Returns all rows from the left table and the matched rows from the right table. If there is no match, NULL values are returned for columns from the right table.

   ```sql
   SELECT *
   FROM table1
   LEFT JOIN table2 ON table1.column = table2.column;
   ```

3. **RIGHT JOIN (or RIGHT OUTER JOIN):**

   - Returns all rows from the right table and the matched rows from the left table. If there is no match, NULL values are returned for columns from the left table.

   ```sql
   SELECT *
   FROM table1
   RIGHT JOIN table2 ON table1.column = table2.column;
   ```

4. **FULL JOIN (or FULL OUTER JOIN):**

   - Returns all rows when there is a match in either the left or right table. If there is no match, NULL values are returned for columns from the table without a match.

   ```sql
   SELECT *
   FROM table1
   FULL JOIN table2 ON table1.column = table2.column;
   ```
