## What is indexing 

- Indexing is technique through which speed of retrieval of data from database can be increased.
- It apply a data structure under the hood to store information about the database in a more efficient manner , so that techniques like binary search can be performed, which is possible only on a sorted data.
- To understand it with the help of an example thing about searching a topic in your DBMS book , if you do not have access to the index than it can be very tiring to find the desired topic , but if an index is maintained inside the book than we can directly go to that chapter which contains the required topic.
- Same thing is done by a DBMS when we instruct it to create index for a attribute , it store broad info about the database in similar fashion of how in book pages are classified based on chapters.
### What is happening under the hood?

- Before going into working of index , we need to understand how a system store information inside disk . In general in HDD information are stored in blocks. 
- Meaning that if we create a relation with 10,000 tuples then in HDD all that information may be stored in 1000 different blocks where each block contains 100 records each.
- If without indexing user query something like `SELECT "roll" FROM "student" WHERE "name" = 'ram';` DBMS will search all 10,000 tuples to get result 
- but with indexing a separate index file will get created which will have first/last value of each block in sorted order (on which indexing is performed ) and a pointer to the block where that attribute value exist.
- So now if user do the same command , DBMS will perform a binary search on that index file and find the block pointer , from thereon search will be performed only on that block to get the answer.
- Here important thing to note that most DBMS's automatically apply index on Primary key

### Advantages of using indexing

1. **Improved Query Performance:** Indexes speed up data retrieval, speeding up query execution by providing a quicker path to specific rows or ranges of rows.
2. **Faster Data Retrieval:** Indexes reduce the time required to retrieve data, particularly for columns on which indexes are created, resulting in faster response times.
3. **Efficient Disk I/O :** Indexes minimize disk I/O by reducing the need for full-table scans
## Types of Index

### Primary Index

- If the data file containing the records is sequentially ordered , a primary index is an index whose search key also defines the sequential order of file
- All files are ordered sequentially on some search key. it could be primary key or non-primary key
- Indexing will be called clustering indexing if it is done on non-key attribute (some consider clustering index as a different category ) 
- Dense and sparse Indices 
	- Dense Index:- it contains an index for every search key value in data file
	- Sparse Index:- An index record appears for only some of the search-key values.
### Secondary Index

- Datafile is unsorted in this case , hence primary indexing is not possible
- So secondary indexing is performed on this type of datafile.
- It can be done on key or non-key attribute 
- Here number of entries in index file = number of records in data file.
- Because index file is sorted so binary search can be applied on it.
## SQL Query to implement indexing on a attribute

- So now that we have learned about indexing and how it works , here are some sql command which you can use to create index
```SQL
CREATE INDEX name
ON table (column0,...);
```

## What are tradeoff?

So we have talked about how indexing can benefit us in retrieving the data , but there are some tradeoff involved before you start start indexing all your attributes
1. **Increased Storage Space:** Indexes consume additional storage space in the database. They require storage for the index data structure itself, which can significantly increase the overall size of the database. This additional storage overhead can be considerable, especially in scenarios where multiple indexes are created on a table.
2. **Slower Write Operations:** When data is modified (inserted, updated, or deleted), indexes need to be updated accordingly. This means that every write operation that affects indexed columns necessitates updates to the indexes, which can slow down write performance. Maintaining indexes during data modifications introduces overhead and can impact the overall speed of write operations.

Understanding these trade-offs is crucial when deciding to use indexes in a database. It's essential to carefully analyze the specific requirements, access patterns, and performance needs of the system before creating indexes to ensure that the benefits outweigh the associated costs.

## Some strategies to adopt while indexing
- **Use narrow index keys whenever possible** – Keep indexes narrow, that is, with as few columns as possible. Exact numeric keys are the most efficient SQL index keys (e.g. integers). These keys require less disk space and maintenance overhead
- **Use clustered indexes on unique columns** – Consider columns that are unique or contain many distinct values and avoid them for columns that undergo frequent changes