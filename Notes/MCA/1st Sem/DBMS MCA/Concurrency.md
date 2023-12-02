## Introduction of Transaction

A transaction is a logical unit of work of database processing that includes one or more database access operations.
Transaction that changes the contents of the database must alter the database from one consistent state to another

## ACID

### Atomicity

By this, we mean that either the entire transaction takes place at once or doesn’t happen at all. There is no midway i.e. transactions do not occur partially
Each transaction is considered as one unit and either runs to completion or is not executed at all. It involves the following two operations.

- Abort: If a transaction aborts, changes made to database are not visible.
- Commit: If a transaction commits, changes made are visible

### Consistency

This means that integrity constraints must be maintained so that the database is consistent before and after the transaction. It refers to the correctness of a database.
Referring to the example above, the total amount before and after the transaction must be maintained

### Isolation(Logical isolation not physical isolation)

This property ensures that multiple transactions can occur concurrently without leading to the inconsistency of database state. Transactions occur independently without interference. Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed.

### Durability

This property ensures that once the transaction has completed execution, the updates and modifications to the database are stored in and written to disk and they persist even if a system failure occurs. These updates now become permanent and are stored in non-volatile memory. The effects of the transaction, thus, are never lost.

### Example

Certainly! Let's use a simple table structure to illustrate the ACID properties in a banking scenario:

Consider two tables: `Accounts` and `Transactions`.

**1. Accounts Table:**

| AccountID | Customer   | Balance |
| --------- | ---------- | ------- |
| 1         | Customer A | $500    |
| 2         | Customer B | $800    |

**2. Transactions Table:**

| TransactionID | AccountID | TransactionType | Amount | Status     |
| ------------- | --------- | --------------- | ------ | ---------- |
| 101           | 1         | Withdrawal      | $200   | Completed  |
| 102           | 2         | Deposit         | $200   | Completed  |
| 103           | 1         | Transfer        | $100   | In Process |
| 104           | 2         | Transfer        | $100   | In Process |

Now, let's show how the ACID properties are reflected in these tables:

**Atomicity:**

- Transaction 103 and Transaction 104 together form a transfer from Account 1 to Account 2. If either of them fails, the entire transfer is rolled back to maintain atomicity.

**Consistency:**

- If Transaction 101 attempts to withdraw $300 from Account 1, it will fail to maintain consistency because the account balance is insufficient.

**Isolation:**

- While Transaction 103 is in process (not yet committed), other transactions can still proceed independently, such as Transaction 102 depositing money into Account 2.

**Durability:**

- Once Transaction 102 is completed, the deposit is permanent even if the system crashes afterward. The change to the database (increase in Account 2's balance) is durable.

These examples demonstrate how the ACID properties are applied in a database context, ensuring the reliability and integrity of transactions.

## States of Transaction

![](../../../statics/Pasted%20image%2020231126083122.png)

| State               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Active state        | A transaction goes into an active state immediately after it starts execution, where it can issue READ and WRITE operations. A transaction may be aborted when the transaction itself detects an error during execution that it cannot recover from, such as attempting to debit a loan amount from an employee's insufficient gross salary. A transaction may also be aborted before it has been committed due to system failure or other circumstances beyond its control. |
| Partially committed | When the transaction ends, it moves to the partially committed state. At this point, some recovery protocols need to ensure that a system failure will not result in an inability to record the changes of the transaction permanently. Once this check is successful, the transaction is said to have reached its commit point and enters the committed state.                                                                                                              |
| Aborted             | When the normal execution can no longer be performed. Failed or aborted transactions may be restarted later, either automatically or after being resubmitted by the user as new transactions.                                                                                                                                                                                                                                                                                |
| Committed           | After the successful completion of a transaction. A transaction is said to be in a committed state if it has partially committed, and it can be ensured that it will never be aborted.                                                                                                                                                                                                                                                                                       |

## Database Recovery

The techniques used to recover the lost data due to system crash, transaction errors, viruses, catastrophic failure, incorrect commands execution etc. are database recovery techniques

1. Transaction failure
2. System failure
3. Media failure (like disk faliure)
   Recovery techniques are heavily dependent upon the existence of a special file known as a system log. It contains information about the start and end of each transaction and any updates which occur in the transaction.

### Recovery Process

- Undoing – If a transaction crashes, then the recovery manager may undo transactions i.e. reverse the operations of a transaction. This involves examining a transaction for the log entry write_item(T, x, old_value, new_value) and setting the value of item x in the database to old-value.There are two major techniques for recovery from noncatastrophic transaction failures: deferred updates and immediate updates.
- Deferred update – This technique does not physically update the database on disk until a transaction has reached its commit point. Before reaching commit, all transaction updates are recorded in the local transaction workspace. If a transaction fails before reaching its commit point, it will not have changed the database in any way so UNDO is not needed
- Immediate update – In the immediate update, the database may be updated by some operations of a transaction before the transaction reaches its commit point. However these operations are recorded in a log on disk before they are applied to the database, making recovery still possible. If a transaction fails to reach its commit point, the effect of its operation must be undone
- Caching/Buffering – In this one or more disk pages that include data items to be updated are cached into main memory buffers and then updated in memory before being written back to disk. A collection of in-memory buffers called the DBMS cache is kept under control of DBMS for holding these buffers
- Shadow paging – It provides atomicity and durability. A directory with n entries is constructed, where the ith entry points to the ith database page on the link. When a transaction began executing the current directory is copied into a shadow directory. When a page is to be modified, a shadow page is allocated in which changes are made and when it is ready to become durable, all pages that refer to original are updated to refer new replacement page.

## Advantages of concurrency

1. **Reduced Waiting Time:**

   - **Explanation:** Concurrency allows multiple tasks or processes to run simultaneously. As a result, when one task is waiting for a particular resource or is blocked, other tasks can continue execution. This reduces the overall waiting time for processes, leading to improved system responsiveness.

2. **Improved Response Time:**

   - **Explanation:** Concurrency enables parallel execution of tasks, which can lead to faster response times. Multiple tasks can make progress concurrently, resulting in quicker completion of overall operations. This is especially beneficial in systems where responsiveness is crucial, such as interactive applications.

3. **Optimized Resource Utilization:**

   - **Explanation:** Concurrency allows for better utilization of system resources. While one part of the system is waiting or performing I/O operations, other parts can use the CPU or other resources. This leads to more efficient use of resources and a higher throughput for the system.

4. **Enhanced Efficiency:**
   - **Explanation:** Concurrency can improve the overall efficiency of a system by allowing it to handle multiple tasks simultaneously. Tasks can be executed in parallel, making the best use of available resources and reducing idle time. This is particularly important in systems with high workloads or those that require quick processing of multiple tasks.

## Concurrency control

### Intro

Concurrency Control in Database Management System is a procedure of managing simultaneous operations without conflicting with each other. It ensures that Database transactions are performed concurrently and accurately to produce correct results without violating data integrity of the respective Database

### Advantages

- To apply Isolation through mutual exclusion between conflicting transactions
- To resolve read-write and write-write conflict issues
- To preserve database consistency through constantly preserving execution obstructions
- The system needs to control the interaction among the concurrent transactions. This control is achieved using concurrent-control schemes.
- Concurrency control helps to ensure serializability

### Various Concurrency control techniques

1. Two-phase locking Protocol
2. Time stamp ordering Protocol
3. Multi version concurrency control
4. Validation concurrency control

### Multi version concurrency control

MVCC provides concurrent access to the database without locking the data. This feature improves the performance of database applications in a multiuser environment. Applications will no longer hang because a read cannot acquire a lock

MVCC provides each user connected to the database with a "snapshot" of the data to work with. The data is consistent with a point in time. Other users of the database see no changes until the transaction is committed. The snapshot can be taken at the start of a transaction, or at the start of each statement, as determined by the isolation level setting.

**Multiversion Concurrency Control (MVCC):**

**Definition:**
Multiversion Concurrency Control is a technique used in database management systems to allow multiple transactions to concurrently access and modify the same data without conflicts. It achieves this by maintaining multiple versions of a data item, each associated with a specific timestamp or transaction identifier.

**Key Concepts:**

1. **Versioning:**
   - MVCC creates and maintains multiple versions of a data item. Each version is associated with a specific timestamp or transaction identifier.
   - Versions are used to represent the state of the data at different points in time.
2. **Read Operations:**
   - When a transaction reads a data item, it sees a snapshot of the data based on its own timestamp. This ensures that a transaction sees a consistent view of the database, even if other transactions are modifying the data concurrently.
3. **Write Operations:**
   - When a transaction writes to a data item, it creates a new version of that item. The new version is associated with the timestamp of the modifying transaction.
   - Existing transactions continue to read the old version, while new transactions read the updated version.
4. **Concurrency Control:**
   - MVCC provides a mechanism for handling concurrent access to data without resorting to locks. Transactions can proceed concurrently as long as they do not conflict at the version level.
5. **Snapshot Isolation:**
   - MVCC enables a form of isolation known as "snapshot isolation." Each transaction sees a snapshot of the database as it existed at the start of the transaction. This prevents the unrepeatable read problem.
6. **Garbage Collection:**
   - To avoid an indefinite increase in the number of versions, MVCC systems often employ garbage collection mechanisms to remove outdated versions of data items that are no longer needed.

**Advantages:**

1. **Increased Concurrency:**
   - MVCC allows for high levels of concurrency as transactions can read and write data simultaneously without causing conflicts.
2. **Isolation and Consistency:**
   - Snapshot isolation provides a consistent view of the database for each transaction, enhancing isolation and maintaining data consistency.
3. **No Deadlocks:**
   - Since MVCC doesn't rely on locking mechanisms, the occurrence of deadlocks is reduced.

**Challenges:**

1. **Increased Storage Requirements:**
   - Maintaining multiple versions of data items can lead to increased storage requirements.
2. **Complexity of Implementation:**
   - Implementing and managing MVCC can be complex, requiring careful handling of versioning and timestamps.
3. **Potential for Phantom Reads:**
   - Although MVCC addresses the unrepeatable read problem, there is still a potential for phantom reads when dealing with insertions and deletions.

### Time Stamp Ordering Protocol

The main idea for this protocol is to order the transactions based on their Timestamps. A schedule in which the transactions participate is then serializable and the only equivalent serial schedule permitted has the transactions in the order of their Timestamp Values. Stating simply, the schedule is equivalent to the particular Serial Order corresponding to the order of the Transaction timestamps. Algorithm must ensure that, for each items accessed by Conflicting Operations in the schedule, the order in which the item is accessed does not violate the ordering. To ensure this, use two Timestamp Values relating to each database item X.

- W_TS(X) is the largest time stamp of any transaction that executed write(X) successfully
- R_TS(X) is the largest executed read(X) successfully
  Alright, let's simplify this:

```
Imagine you have a bunch of transactions happening in a database, and each transaction is given a timestamp based on when it started. Now, we want to make sure that when we look at all these transactions together, they act as if they happened one after the other in a certain order.

So, the plan is to order these transactions by their timestamps. If we arrange them this way, it means we can consider the whole set of transactions as if they were done one at a time, in the order of their timestamps.

Here's the catch: We need to be careful when transactions involve the same piece of data and conflict with each other (like one changing something while another is trying to read it). We want to make sure that the order in which they access this data follows the timestamp order.

To do this, for every piece of data (let's call it X) in the database, we attach two timestamp values to it. These timestamps help us keep track of when the data was last accessed and modified. By paying attention to these timestamps, we can make sure that conflicting operations on the same piece of data don't mess up the order we've established based on transaction timestamps.

In simpler terms, this protocol ensures that even though many things are happening in the database at the same time, we can pretend they're happening one after the other by looking at the timestamps. And by using these extra timestamps for each piece of data, we avoid conflicts that could mess up our nice, orderly sequence of transactions.
```

#### Basic TimeStamp Ordering

Every transaction is issued a timestamp based on when it enters the system. Suppose, if an old transaction Ti has timestamp TS(Ti), a new transaction Tj is assigned timestamp TS(Tj) such that TS(Ti) < TS(Tj).The protocol manages concurrent execution such that the timestamps determine the serializability order.

![](../../../statics/Pasted%20image%2020231126204729.png)

The timestamp ordering protocol ensures that any conflicting read and write operations are executed in timestamp order. Whenever some Transaction T tries to issue a R_item(X) or a W_item(X), the Basic TO algorithm compares the timestamp of T with R_TS(X) & W_TS(X) to ensure that the Timestamp order is not violated. This describe the Basic TO protocol in following two cases

1. Whenever a Transaction T issues a W_item(X) operation, check the following
   conditions:
   If R_TS(X) > TS(T) or if W_TS(X) > TS(T), then abort and rollback T and reject the operation. else,
   Execute W_item(X) operation of T and set W_TS(X) to TS(T).
2. Whenever a Transaction T issues a R_item(X) operation, check the following conditions:
   If W_TS(X) > TS(T), then abort and reject T and reject the operation, else
   If W_TS(X) <= TS(T), then execute the R_item(X) operation of T and set R_TS(X) to the larger of TS(T) and current R_TS(X).

#### +ve and -ve

**Advantages of Timestamp Ordering:**

1. **Concurrency Control:** Timestamp ordering is effective for managing concurrency in a database system. By using timestamps, it can allow multiple transactions to work simultaneously without causing conflicts, as long as they don't interfere with each other based on their timestamps.

2. **Serializability:** The protocol ensures that the schedule of transactions is serializable, meaning it behaves as if transactions were executed in some order. This helps maintain consistency and predictability in the database system.

3. **Optimistic Approach:** Timestamp ordering takes an optimistic approach to concurrency control. It assumes that conflicts will be rare, and transactions can proceed without interference unless a conflict is detected. This can lead to efficient execution when there are fewer conflicts.

**Disadvantages of Timestamp Ordering:**

1. **High Contention:** In scenarios with high contention for the same data items, conflicts can occur frequently, leading to a situation where transactions need to be rolled back and retried. This rollback and retry mechanism can increase the overhead and reduce system performance.

2. **Dependency on Timestamp Accuracy:** The effectiveness of timestamp ordering relies heavily on the accuracy of timestamps. If timestamps are not assigned or managed accurately, it can lead to incorrect scheduling, resulting in potential data inconsistencies and violations of serializability.

3. **Complexity of Implementation:** Implementing a timestamp ordering protocol can be complex. Managing timestamps for each transaction and each data item requires careful coordination. Additionally, resolving conflicts and ensuring correctness adds another layer of complexity to the system.

### LOCKING METHODS OF CONCURRENECY CONTROL

Two phase locking prevents deadlock from occurring in distributed systems by releasing all the resources it has acquired, if it is not possible to acquire all the resources required without waiting for another process to finish using a lock. This means that no process is ever in a state where it is holding some shared resources, and waiting for another process to release a shared resource which it requires. This means that deadlock cannot occur due
to resource contention.

The 3 activities taking place in the two phase update algorithm are:

1. Lock Acquisition
2. Modification of Data
3. Release Lock

#### A transaction in the Two Phase Locking Protocol can assume one of the 2 phases:

1. Growing Phase: In this phase a transaction can only acquire locks but cannot release any lock. The point when a transaction acquires all the locks it needs is called the Lock Point.
2. Shrinking Phase:In this phase a transaction can only release locks but cannot acquire any.

#### Locks are further divided into three fields:

##### Lock Granularity

A database is basically represented as a collection of named data items. The size of the data item chosen as the unit of protection by a concurrency control program is called GRANULARITY. Locking can take place at the following level:

- Database level.
- Table level.
- Page level.
- Row (Tuple) level.
- Attributes (fields) level.

##### Locks Types

The DBMS mainly uses following types of locking techniques.

1. Binary locks
2. Shared/Exclusive:-
   - Shared:These locks are reffered as read locks, and denoted by 'S'. If a transaction T has obtained Shared-lock on data item X, then T can read X, but cannot write X. Multiple Shared lock can be placed simultaneously on a data item.
   - Exclusive: These Locks are referred as Write locks, and denoted by 'X'. If a transaction T has obtained Exclusive lock on data item X, then T can be read as well as write X. Only one Exclusive lock can be placed on a data item at a time. This means multipls transactions does not modify the same data simultaneously
3. 2 Phase Locking

## LOCKING AND RECOVERY TECHNIQUES IN CENTRALIZED DBMS

### What is lock

A lock is a variable associated with a data item that describes the status of the item with respect to possible operations that can be applied to it

### Types of locks

#### Binary Lock

A binary lock can have two states or values: locked and unlocked. A distinct lock is associated with each database item A. If the value of the lock on A is 1, item A cannot be accessed by a database operation that requests the item. If the value of the lock on A is 0 then item can be accessed when requested.

##### Rules

1. A transaction must issue the operation lock_item (A) before any read_item (A) or write, item operations are performed in T.
2. A transaction T must issue the operation unlock_item (A) after all read_item (A) and write_item (A) operations are completed in T.
3. A transaction T will not issue a lock_item (A) operation if it already holds the lock on Item A.
4. A transaction T will not issue an unlock \_item (A) operation unless it already holds the lock on item A.

#### Share/Exclusive (for Read/Write) Lock

We should allow several transactions to access the same item A if they all access A’ for reading purposes only. However, if a transaction is to write an item A, it must have exclusive access to A. For this purpose, a different type of lock called a multiple-mode lock is used. In this scheme there are shared/exclusive or read/write locks are used.

#### Compatibility

Imagine you have two ways of locking things, called Mode A and Mode B. If one action (let's call it T1) wants to lock something (let's call it item Q) in Mode A, but another action (T2) already has it locked in Mode B, we need to know if Mode A and Mode B can peacefully coexist.

So, compatibility means whether Mode A and Mode B can work together. For example, if T1 just wants to read something and T2 also just wants to read it, no problem. But if T1 wants to write (change) something and T2 either wants to read or write it, that's a conflict.

To lock an item, an action can either do a shared lock (lock-S) or an exclusive lock (lock-X). To unlock, it uses the unlock instruction.

Now, if T1 wants to use an item but someone else has it locked in a way that doesn't allow T1's intended use (like T2 has an exclusive lock), T1 has to wait until T2 is done.

In simpler terms, it's like saying, "Can these two ways of locking things play nice together, or will they cause trouble when different actions want to use the same thing in different ways?" If there's a potential problem, one action has to wait until the other is done using it.

## Deadlock

In a database, a deadlock is an unwanted situation in which two or more transactions are waiting indefinitely for one another to give up locks. Deadlock is said to be one of the most feared complications in DBMS as it brings the whole system to a Halt.
![](../../../statics/Pasted%20image%2020231126210107.png)

## Some Problem

### Dirty Read Problem

A "dirty read" is a concept in database management systems (DBMS) that refers to a situation where one transaction reads data that has been modified by another transaction but has not yet been committed. In other words, a transaction reads data that is still in a "dirty" or intermediate state.

Let's break it down:

1. **Transaction 1 (T1) starts:** It reads a piece of data from the database.

2. **Transaction 2 (T2) modifies the same data:** However, T2 has not yet completed (committed) its changes to the database.

3. **Transaction 1 reads the same data again before T2 commits its changes:** Now, T1 reads the data again, but this time it's in an intermediate state because T2 hasn't finished its modifications.

This scenario poses a problem because T1 might base decisions on data that is not yet finalized. If T2 decides to rollback (undo) its changes, T1 would have based its actions on information that is no longer valid.

### Unrepeatable Read

The "unrepeatable read" problem is another concept in database management systems (DBMS), and it occurs when a transaction reads the same data multiple times within its scope, but the data changes between the reads due to the actions of another concurrent transaction.

Here's a breakdown:

1. **Transaction 1 (T1) starts:** It reads a piece of data from the database.

2. **Transaction 2 (T2) modifies the same data:** T2 changes the data that T1 read in the first step.

3. **Transaction 1 reads the same data again:** Now, T1 reads the same data for the second time, but this time, the data has been modified by T2.

This situation can be problematic because T1 might make decisions or calculations based on the initial data it read, and those decisions might not be valid anymore due to changes made by T2. It's an "unrepeatable read" because the same read operation produces different results at different points in time.

### Phantom Read

The "phantom read" problem is a concept in database management systems (DBMS) that occurs when a transaction reads a set of records that satisfy a certain condition, but during the course of the transaction, another transaction inserts or deletes records that also satisfy that condition. As a result, when the first transaction tries to read the same set of records again, it encounters new records that weren't there initially, or some of the records it read initially might be missing.

Here's a breakdown:

1. **Transaction 1 (T1) starts:** It reads a set of records from the database that satisfy a certain condition (e.g., all records where a certain attribute has a specific value).

2. **Transaction 2 (T2) inserts or deletes records that satisfy the same condition:** T2 changes the set of records that meet the criteria specified by T1.

3. **Transaction 1 reads the same set of records again:** When T1 tries to read the same set of records that it read initially, it encounters new records inserted by T2 or may miss some records that T2 deleted.

This situation can lead to unexpected and inconsistent results because the set of records that T1 thought it was working with has changed due to the actions of T2.

# DATABASE SYSTEM ARCHITECTURE & DATA MODELS
