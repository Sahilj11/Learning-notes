## JPA (Jakarta Persistence API)
- it is a specification of how you should implement ORM framework
## Hibernate (implementation of JPA)
- Dependency that fulfil all requirement imposed by JPA specification
- Query are not executed directly on database but there is a context
- This has instance of objects (when operation are executed thru framework they are not executed on database but on objects in context)
- ![](../../statics/Pasted%20image%2020240607114121.png)
- We want to keep the context as small as possible

### Persistence XML
![](../../statics/Pasted%20image%2020240607114719.png)

### Entity Manager
![](../../statics/Pasted%20image%2020240607114920.png)
- Manager of collection of objects in context , thru this we operate on the context

### Entities
- Describing the tables as class in java
- em.persist() is not always result into insert query , in the end when transaction is commited the context is mirrored to database