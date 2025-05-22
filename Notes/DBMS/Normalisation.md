## 1NF
- Each column contains atomic values
- Each column contains values of same type
- Each row is unique (typically ensured by primary key)
- No Repeating groups of column (for example phone no 1 , phone no 2)


## 2NF
- It must be in 1NF
- All non-key attributes must be functionally dependent on the entire primary key, means no non-key column should depend on only part of primary key![](../statics/Pasted%20image%2020250522205721.png)
- in above primary key is order_id and book isbn , but customer address is only depend on order id
- No partial dependecy

## 3NF
- It must be in 2NF
- It must not have transitive dependency , a transitive dependency occurs when a non-key attributes depends on another non-key attribute , rather than depending directly on primary key

## BCNF
