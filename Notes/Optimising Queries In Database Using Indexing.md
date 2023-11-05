## What is indexing 
- Indexing is technique through which speed of retierval of data from database can be increased.
- It apply a data structure under the hood to store information about the database in a more efficient manner , so that techniques like binary search can be performed, which is possible only on a sorted data.
- To understand it with the help of an example thing about searching a topic in your DBMS book , if you do not have access to the index than it can be very tiring to find the desired topic , but if an index is maintained inside the book than we can directly go to that chapter which contains the required topic.
- Same thing is done by a DBMS when we instruct it to create index for a relation or attribute , it store broad info about the database in similar fashion of how in book pages are classified based on chapters.
### What is happening under the hood?
- Before going into working of index , we need to understand how a system store information inside disk . In general in HDD information are stored in blocks. 
- Meaning that if we create a relation with 10,000 tuples then in HDD all that information may be stored in 1000 different blocks where each block contains 100 records each.
| EmployeeID | Name         | Department | Salary | Block Number |
|------------|--------------|------------|--------|--------------|
| 1          | John Doe     | IT         | 60000  | 1            |
| 2          | Jane Smith   | HR         | 55000  | 1            |
| ---      | ---          | ...        | ...    | ...          |
| 100        | Bob Johnson  | Sales      | 62000  | 1            |
| 101        | Emily Davis  | IT         | 58000  | 2            |
| ...        | ...          | ...        | ...    | ...          |
| 200        | ...          | ...        | ...    | 2            |
| ...        | ...          | ...        | ...    | ...          |
| 1000       | ...          | ...        | ...    | 10           |

## Why is it needed?
## SQL Query to implement indexing on a relation or attribute
## What are tradeoff?