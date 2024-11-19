# Nodes and Cluster in ES
- In Elasticsearch, a **node** is an individual instance that stores data and performs search/indexing operations. Nodes can serve different roles such as master, data, ingest, and coordinating. 
- A **cluster** is a group of nodes working together to share and distribute data, ensuring scalability and fault tolerance. Each cluster has a unique name and a master node managing cluster-wide operations like shard allocation. Nodes in a cluster communicate and collaborate to balance the workload, ensuring high availability. Adding more nodes to a cluster improves performance, allowing the system to handle larger datasets and higher traffic.

# Sharding
- Breaking an index into small peice is callled sharding , by default a single shard is created for an index.
- Shards of an index can be stored in a single node or multiple node

# Replication
- Copying of shards is called replication to cope up with data lose
- ![](../statics/Pasted%20image%2020241003091311.png)
- In Elasticsearch, a **replication group** consists of a **primary shard** and its **replica shards**. This group ensures high availability and fault tolerance for the data stored in an index. Elasticsearch automatically replicates data across multiple nodes by copying the primary shard into one or more replica shards. If the node containing the primary shard fails, a replica shard can be promoted to the primary, ensuring continued data availability.
	- **Primary Shard**: The original shard where data is indexed.
	- **Replica Shard**: A copy of the primary shard for redundancy.
	- **Replication Group**: The primary shard and all its replicas.
- **Some time health of a index show yellow because both replica and primary shard is on same node.**
