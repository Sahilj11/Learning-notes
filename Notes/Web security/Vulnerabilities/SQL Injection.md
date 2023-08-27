### Retrieving hidden data
- modify a SQL query to return additional results.
- `https://insecure-website.com/products?category=Gifts'+OR+1=1--` here the 1=1 represent true , 
- Take care when injecting the condition `OR 1=1` into a SQL query. Although this may be harmless in the initial context you're injecting into, it's common for applications to use data from a single request in multiple different queries. If your condition reaches an `UPDATE` or `DELETE` statement, for example, this can result in an accidental loss of data.


### Subverting application logic
- administrator'--' AND password = ''

### Retrieving data from other database tables
- attacker can leverage a SQL injection vulnerability to retrieve data from other tables within the database. This is done using the `UNION` keyword, which lets you execute an additional `SELECT` query and append the results to the original query.
- 2 requirement for this to work
	- 1. he individual queries must return the same number of columns: Each query within the UNION must have the same number of columns in its result set. For example, if the first query returns three columns (e.g., Name, Age, and City), the subsequent queries must also return three columns with the same or compatible data types. This requirement ensures that the columns from different queries can be matched and merged accurately.
	2. The data types in each column must be compatible between the individual queries: The data types of corresponding columns in the individual queries must be compatible or convertible to a common data type. For example, if the first query returns the Name column as a VARCHAR data type, the subsequent queries should also have the Name column with a compatible data type, such as VARCHAR or CHAR. If the data types are not compatible, the UNION operation may produce an error or unexpected results.
- Determining the number of columns required in a SQL injection UNION attack
	- first method involves injecting a series of `ORDER BY` ' ORDER BY 1--
		- This series of payloads modifies the original query to order the results by different columns in the result set. The column in an `ORDER BY` clause can be specified by its index, so you don't need to know the names of any columns. When the specified column index exceeds the number of actual columns in the result set, the database returns an error,
	- The second method involves submitting a series of `UNION SELECT` payloads specifying a different number of null values:
	- `' UNION SELECT NULL-- ' UNION SELECT NULL,NULL-- ' UNION SELECT NULL,NULL,NULL-- etc.`If the number of nulls does not match the number of columns, the database returns an error
- The reason for using `NULL` as the values returned from the injected `SELECT` query is that the data types in each column must be compatible between the original and the injected queries. Since `NULL` is convertible to every commonly used data type, using `NULL` maximizes the chance that the payload will succeed when the column count is correct.
- On Oracle, every `SELECT` query must use the `FROM` keyword and specify a valid table. There is a built-in table on Oracle called `dual` which can be used for this purpose. So the injected queries on Oracle would need to look like:
    `' UNION SELECT NULL FROM DUAL--`
- The payloads described use the double-dash comment sequence `--` to comment out the remainder of the original query following the injection point. On MySQL, the double-dash sequence must be followed by a space. Alternatively, the hash character `#` can be used to identify a comment
#### Using NULL
In the context of a UNION query, the use of NULL values in the SELECT statement can serve a specific purpose. 

When you see a UNION query with the syntax "SELECT NULL, NULL, NULL", it typically means that you want to include additional rows in the result set, but you don't have any specific values to populate in those columns. 

For example, let's say you have two tables, TableA and TableB, with the same number of columns but different data. If you want to combine the results of querying both tables, but one of the tables has fewer rows or doesn't have data for certain columns, you can use NULL to fill in the missing values.

Consider the following example:

TableA:
| Column1 | Column2 | Column3 |
|---------|---------|---------|
|   A1    |   A2    |   A3    |
|   B1    |   B2    |   B3    |

TableB:
| Column1 | Column2 | Column3 |
|---------|---------|---------|
|   C1    |   C2    |   C3    |

If you perform the following UNION query:

SELECT Column1, Column2, Column3
FROM TableA
UNION
SELECT Column1, Column2, Column3
FROM TableB;

The result would be:

| Column1 | Column2 | Column3 |
|---------|---------|---------|
|   A1    |   A2    |   A3    |
|   B1    |   B2    |   B3    |
|   C1    |   C2    |   C3    |

However, if TableB has fewer rows or doesn't have data for certain columns, you can use NULL values to fill in the gaps. For example:

SELECT Column1, Column2, Column3
FROM TableA
UNION
SELECT NULL, NULL, NULL
FROM TableB;

The result would be:

| Column1 | Column2 | Column3 |
|---------|---------|---------|
|   A1    |   A2    |   A3    |
|   B1    |   B2    |   B3    |
|  NULL   |  NULL   |  NULL   |

In this case, the NULL values represent the missing data from TableB, allowing you to align the columns and combine the results seamlessly in the UNION query.

## Cheatsheet 
- https://portswigger.net/web-security/sql-injection/cheat-sheet

### Finding columns with a useful data type in a SQL injection UNION attack
Having already determined the number of required columns, you can probe each column to test whether it can hold string data by submitting a series of `UNION SELECT` payloads that place a string value into each column in turn. For example, if the query returns four columns, you would submit:
`' UNION SELECT 'a',NULL,NULL,NULL-- ' UNION SELECT NULL,'a',NULL,NULL-- ' UNION SELECT NULL,NULL,'a',NULL-- ' UNION SELECT NULL,NULL,NULL,'a'--`

If the data type of a column is not compatible with string data, the injected query will cause a database error,

### Why null is been used
- The reason for using `NULL` as the values returned from the injected `SELECT` query is that the data types in each column must be compatible between the original and the injected queries. Since `NULL` is convertible to every commonly used data type, using `NULL` maximizes the chance that the payload will succeed when the column count is correct.
- On Oracle, every `SELECT` query must use the `FROM` keyword and specify a valid table. There is a built-in table on Oracle called `dual` which can be used for this purpose. So the injected queries on Oracle would need to look like:
    `' UNION SELECT NULL FROM DUAL--`
- The payloads described use the double-dash comment sequence `--` to comment out the remainder of the original query following the injection point. On MySQL, the double-dash sequence must be followed by a space. Alternatively, the hash character `#` can be used to identify a comment

### Retrieving multiple values within a single column
- In the preceding example, suppose instead that the query only returns a single column.
You can easily retrieve multiple values together within this single column by concatenating the values together, ideally including a suitable separator to let you distinguish the combined values. For example, on Oracle you could submit the input:
`' UNION SELECT username || '~' || password FROM users--`
This uses the double-pipe sequence `||` which is a string concatenation operator on Oracle. The injected query concatenates together the values of the `username` and `password` fields, separated by the `~` character.
The results from the query will let you read all of the usernames and passwords,