
# Concurrency in dbms

concurrency is the ability of a database to allow users to access data at the same time. It is used to 
manipulated the data several process or user without resulting in data concurrency 

# Methods of concurrency 

## Optimistic

Delay the checking of whether a transaction meets the isolation meets the isolation and other integrity rules 
until its end , without blocking any of its operation and then abort a transaction  prevent the violation.
if the desired rules are to be violation upon it commit.

## Pessimistic

Block an operation of a transaction in some situation if they may cause violent o some,rules until the possibility 
of violation disappears blocking operation is typically involved with performance reduction. 

## Semi Optimistic

Block operations in some situation if they may cause violence of some rules, and do not block in other situation
while delaying rules checking to transaction end as done with optimistic

## Locking

Controlling access to data by locks assigned to the data . Access  of a transaction to a data item locked by
another transaction may be blocked until may be blocked release.

## Serialization  graph checking 

Checking for cycle in the schedule graph and breaking them by aborts.

## Timestamp ordering

Assigning timestamps to transaction and controlling or checking access to data by timestamp order.

## Commitment Ordering

Controlling or checking transaction chronological order of commit events to be compatible 
with their respectively precedence order.

## Transaction
Transaction represents a unit of work performed within a database against which consistency , isolation durability and atomicity are maintained . It's a sequence of database operations (CRUD) that must be executed as single , indivisible unit . if any part of the transaction fails , the entire transaction should be rolled back , ensuring the database remains in a consistent state.

### Transaction control commands
1. COMMIT:
   - COMMIT command is used to permanently save any transaction into the database .
   - To avoid that , COMMIT is used to mark the charges as permanent 
2. ROLLBACK:
   - It is a transactional control command used to undo transaction that have not already been saved to the database 
3. SAVEPOINT:
   - A SAVEPOINT is a point in a transaction when you can roll the transaction back to a certain point without rolling back the entire transaction
