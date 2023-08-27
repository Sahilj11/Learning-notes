## Relational Database
- going to store data in rows and columns , in table
- Sql does only 4 things , CRUD
- C :- CREATE, INSERT
- R:- SELECT
- U:- UPDATE
- D:- DELETE, DROP
## Change CSV to SQL
- ![[Pasted image 20230612160134.png]]
- here the table named favorites was created

## Keys
- PRIMARY KEY :- database will use the column as a unique identifier. The _PRIMARY KEY constraint uniquely identifies each record in a table_. Primary keys must contain UNIQUE values, and cannot contain NULL values
- FOREIGN KEY :- In SQL, a foreign key is a column or a set of columns in a table that refers to the primary key or a unique key of another table. It establishes a relationship between two tables by enforcing referential integrity. The foreign key constraint ensures that the values in the foreign key column(s) of a table correspond to the values in the referenced primary key or unique key column(s) of another table.The table containing the foreign key is called the referencing table or child table, while the table being referred to is called the referenced table or parent table.
	- here the id of table you want to reference
	- FOREIGN KEY (show_id). here the show_id is the primary key of shows table but using FOREIGN KEY constraint it is been used in stars table.
	- remember to create separate column to store there foreign key , like show_id INTEGER NOT NULL , in stars table
- REFERENCE KEY:-A reference key, on the other hand, is not a commonly used term in SQL. It may refer to the primary key or unique key column(s) in a table that is being referenced by a foreign key in another table. Essentially, the reference key would be the primary key or unique key column(s) of the referenced table that are used as the target for the foreign key relationship.
- ![[Pasted image 20230612160531.png]]

## Indexes
- if you are searching a column frequently you can tell to build an index , making the searching more faster
- `CREATE INDEX name ON table(column,...);` here the name can be given anything so that you can reference later if you want 
- It is going to create B-trees

## Race condition
- In database management, a race condition refers to a situation where the outcome of a database operation depends on the sequence or timing of concurrent or parallel transactions. It occurs when multiple transactions or processes attempt to access or modify shared data simultaneously, and the final result depends on the order in which these operations are executed.Race conditions can lead to unexpected and incorrect results in a database system
- use additional condition 
- Begin transaction 
- Commit 
- Rollback
## Cursors
- In SQL, a cursor is a database object that allows you to retrieve and manipulate data row by row. It's like a pointer or marker that helps you navigate through the result set of a query.
- When you execute a query, it may return a set of rows from a table or tables. A cursor enables you to process these rows one at a time instead of dealing with the entire result set all at once.
- Here's a step-by-step explanation of how a cursor works:
	1. Declare and initialize the cursor: You start by declaring a cursor variable and associating it with a specific query. This query defines the result set that the cursor will work with. You can also specify any necessary parameters or conditions.
	2. Open the cursor: Once the cursor is declared, you open it to make it active. This allows you to start fetching rows from the result set.
	3. Fetch rows: With the cursor open, you can fetch one row at a time from the result set. You can use a FETCH statement to retrieve the current row and move the cursor to the next row.
	4. Process the fetched row: After fetching a row, you can perform operations on the data within that row. You can read the values, update them, delete the row, or perform any necessary calculations or actions.
	5. Repeat fetching: You continue fetching rows from the result set until there are no more rows left or until you explicitly close the cursor.
	6. Close the cursor: When you're done working with the cursor and no longer need to fetch any more rows, you close the cursor. This releases any resources associated with the cursor.
- Cursors are particularly useful when you need to perform row-by-row processing, such as applying complex calculations or performing updates based on specific conditions. However, it's important to note that cursors can sometimes be less efficient than set-based operations, so they should be used judiciously when necessary.

## Triggers
- Triggers in SQL are special database objects that are designed to automatically respond to specific events or actions that occur within a database. They are like "triggers" that are activated when certain conditions are met.
- When a specified event or action occurs, such as inserting, updating, or deleting data in a table, a trigger can be set up to execute a predefined set of instructions or actions. These actions can include modifying data, validating data, logging information, or even performing calculations.
- Triggers consist of three main components:
	1. Event: This is the specific action or event that triggers the execution of the trigger, such as an INSERT, UPDATE, or DELETE operation on a table.
	2. Condition: The trigger can have conditions that determine whether it should be executed or not. For example, a trigger may only be activated if a specific value is being inserted or if certain criteria are met.
	3. Action: The action is the set of SQL statements or procedures that are executed when the trigger is activated. These statements can include modifying data, interacting with other database objects, or performing any other necessary tasks.
- Triggers are useful for enforcing business rules, maintaining data integrity, auditing changes, or implementing complex logic that needs to be executed automatically when certain events occur in the database. They provide a way to automate tasks and ensure consistency and accuracy in database operations.
## transaction
- Sure! Imagine you have a favorite video game where you can buy and sell items. Let's say you want to buy a sword for 10 coins and sell a potion for 5 coins. Now, imagine you have only 10 coins in your pocket.
- To make sure everything goes smoothly, you decide to use a transaction. A transaction is like a special box that keeps track of your actions. It ensures that either all your actions are completed successfully, or if something goes wrong, it cancels everything and brings you back to where you started.
- In this case, the transaction ensures that you can only buy the sword and sell the potion if you have enough coins (10 for the sword and 5 for the potion). If you don't have enough coins, the transaction won't let you buy or sell anything.
- Let's say you have 10 coins, so the transaction allows you to buy the sword for 10 coins. Now, you have 0 coins left. Next, you try to sell the potion for 5 coins. The transaction checks if you have the potion and allows you to sell it. After selling the potion, you have 5 coins.
- The great thing about transactions is that if something unexpected happens during the process, like if the game crashes or you lose internet connection, the transaction will cancel everything and bring you back to the point before you bought the sword or sold the potion. So, you won't lose any coins or items.
- Transactions make sure that your actions happen all together or none at all. They keep things fair and prevent any problems from ruining your game.
- like in sqlite3 `.commit()` method is used

## UNIQUE
- If we use a UNIQUE constraint in the table, MySQL automatically creates a UNIQUE index behind the scenes. The following statement explains how to create a unique constraint when we create a table.
- ``` CREATE UNIQUE INDEX index_name  ON table_name (index_column1, index_column2,...);```
- 