# Network layer
## Intro 
-  main work is Routing and providing service to Transport layer.
- It manages options pertaining to host and network addressing, managing
sub-networks, and internetworking.
- Network layer takes the responsibility for routing packets from source to
destination within or outside a subnet.
- It also has the responsibility to route the packets from source to destination,
mapping different addressing schemes and protocols.
- It also helps to communicate two different subnet may be operating on
different protocols which are not compatible with each other.

## Desired properties of routing algo
- Fairness and optimality
- Simplicity
- Robustness
- Stability 
- Correctness
## Functionalities
- Routing
	- It determine which route is suitable from source to destination and this function of network layer is known as routing. Routing may include following goals:
		- Addressing devices and networks.
		- Populating routing tables or static routes.
		- Queuing incoming and outgoing data and then forwarding them according to quality of service constraints set for those packets.
		- Internetworking between two different subnets.
		- Delivering packets to destination with best efforts.
		- Provides connection oriented and connection less mechanism.
- Logical Addressing: In order to identify each device on internetwork uniquely, network layer defines an addressing scheme. The sender & receiver’s IP address are placed in the header by network layer.
## Design issues 
The network layer in a computer network is responsible for routing data packets from the source to the destination. It plays a critical role in ensuring that data is transmitted efficiently and reliably across the network. To achieve this, the network layer needs to address various design issues and provide a range of services. Here's an explanation of these design issues:

1. Routing:
   Routing is the process of determining the path that data packets should follow to reach their destination. The network layer is responsible for making decisions about which intermediate routers or switches the data should traverse to reach the target.

2. Flow Control:
   Flow control mechanisms are used to regulate the rate of data transmission to prevent congestion and ensure that data is sent at a manageable pace. The network layer can implement flow control to avoid overloading the network.

3. Error Control:
   Error control involves detecting and correcting errors that can occur during data transmission. The network layer may implement error detection and correction techniques to ensure data integrity.

4. Addressing:
   Addressing is the process of assigning unique addresses to devices on the network. These addresses are used for routing and identifying the source and destination of data packets.

5. Reliability:
   The network layer plays a crucial role in ensuring the reliability of data transmission. It may implement protocols and mechanisms to guarantee that data reaches its destination without loss or corruption.

6. Scalability:
   Scalability refers to the network's ability to grow and accommodate an increasing number of devices and users. The network layer should be designed to handle network expansion gracefully.

7. Quality of Service (QoS):
   QoS mechanisms allow the network to prioritize different types of traffic. It ensures that critical applications, like video conferencing or real-time voice calls, receive the necessary bandwidth and low latency.

8. Resource Allocation:
   Resource allocation involves managing network resources efficiently, such as bandwidth and processing power. The network layer can determine how resources are distributed among competing network traffic.

9. Statistical Multiplexing:
   Statistical multiplexing is a technique that allows multiple data streams to share a common network resource, like a link or channel. The network layer may use statistical multiplexing to optimize resource utilization.

10. Security:
    Security is a critical concern in network design. The network layer should implement security measures to protect data from unauthorized access, eavesdropping, and other threats.

These design issues are essential for designing and implementing a network that can effectively transmit data while considering factors like reliability, efficiency, and security. Network protocols and technologies are developed to address these issues and ensure that data is delivered accurately and efficiently across the network.
## Service type
### Connection-oriented 
- A connection-oriented service is one that establishes a dedicated connection between the communicating entities for data transmission. To use a connection-oriented service, we follow three phases:
	- Connection establishment
	- Data transfer
	- Connection release
- In connection-oriented services, the data packets are delivered to the receiver in the same order in which they have been sent by the sender. For example – A telephone system.
- It uses circuit switching technique for connection and data transmission.
- It provides reliable data transmission.
- [[CN Minor 1st#Switching]]
Connection-oriented services and connectionless services are two fundamental communication paradigms in networking. Each has its own advantages and disadvantages. Here are the advantages and disadvantages of connection-oriented services in networking:

**Advantages of Connection-Oriented Services:**

1. **Reliability:** Connection-oriented services are highly reliable because they establish a dedicated connection or session before data transfer begins. This ensures that data is delivered in the correct order and without loss or corruption.

2. **Error Handling:** These services provide robust error detection and correction mechanisms. If data packets are lost or corrupted during transmission, they can be retransmitted, ensuring data integrity.

3. **Flow Control:** Connection-oriented services often include flow control mechanisms, which prevent network congestion by regulating the rate of data transmission. This is particularly important in scenarios with limited bandwidth.

4. **Predictable Performance:** Since a connection is established and resources are reserved before data transfer, the performance is generally more predictable and consistent, making it suitable for real-time applications.

5. **Sequencing:** Connection-oriented services maintain the sequence of data packets. This is crucial for applications like video streaming or voice calls, which require data to arrive in the correct order.

**Disadvantages of Connection-Oriented Services:**

1. **Overhead:** Establishing and maintaining a connection requires additional overhead in terms of signaling, setup, and teardown processes. This overhead can be inefficient for short and infrequent communications.

2. **Latency:** Due to the connection setup and teardown processes, connection-oriented services can introduce additional latency compared to connectionless services. This may not be suitable for delay-sensitive applications.

3. **Resource Consumption:** Resources (such as bandwidth and memory) are reserved for the duration of the connection, even if data transmission is not continuous. This can lead to inefficient resource utilization.

4. **Complexity:** Implementing and managing connection-oriented services can be more complex, as it requires tracking and managing the state of active connections.

5. **Scalability:** Connection-oriented services can face challenges in scaling to accommodate a large number of simultaneous connections, as each connection requires resources.
### Connection-less service
- A Connectionless service is a data communication between two nodes where the sender sends data without ensuring whether the receiver is available to receive the data.
- Here, each data packet (datagram) has the destination address and is routed independently irrespective of the other packets
- Data packets may follow different paths to reach the destination. There’s no need to setup connection before sending a message and relinquish it after the message has been sent. The data packets in a connectionless service are usually called datagrams.
- use packet switching technique
Connectionless services, also known as datagram services, offer a different set of advantages and disadvantages compared to connection-oriented services in networking. Here are the advantages and disadvantages of connectionless services:

**Advantages of Connectionless Services:**

1. **Low Overhead:** Connectionless services have minimal setup and teardown overhead because they do not require the establishment of a dedicated connection. This makes them more efficient for short and sporadic communications.

2. **Low Latency:** Since there is no need to establish a connection before sending data, connectionless services can provide lower latency, making them suitable for real-time applications where low delay is critical.

3. **Scalability:** Connectionless services are well-suited for scenarios with a large number of devices and short-lived connections. They can easily accommodate a high volume of datagrams without the overhead of maintaining connection state.

4. **Resource Efficiency:** Resources are not reserved for the duration of a connection. Bandwidth and memory are only used when actual data transmission occurs, resulting in efficient resource utilization.

5. **Simplicity:** Implementing and managing connectionless services is generally simpler and requires less administrative overhead because there are no connections to set up or maintain.

**Disadvantages of Connectionless Services:**

1. **Unreliable:** Connectionless services do not guarantee the reliable delivery of data. Packets may be lost, duplicated, or delivered out of order, and there are no built-in mechanisms for error detection and correction.

2. **No Flow Control:** Connectionless services lack built-in flow control mechanisms. This can lead to network congestion in scenarios with high traffic, potentially affecting the quality of service.

3. **Data Integrity:** Since there is no built-in error correction, data integrity relies on higher-layer protocols or applications to handle error detection and retransmission, if necessary.

4. **No Guaranteed Order:** Packets may arrive at the destination out of order. Applications that rely on sequential data delivery must handle reordering themselves.

5. **Limited Applicability:** Connectionless services are better suited for applications where the occasional loss or out-of-order delivery of data is acceptable, such as web browsing or email. They may not be appropriate for applications with strict reliability requirements.
## Routing Algo
- Routing is the process of forwarding of a packet in a network so that it reaches its intended destination
- ![[Pasted image 20231022160813.png]]
### Adaptive 
- Adaptive Routing Algorithms: Algorithms which change their routing decisions whenever network topology or traffic load changes. The changes in routing decisions are reflected in the topology as well as traffic of the network
- These algorithms are also known as dynamic routing.
- These make use of dynamic information such as current topology, load, delay, etc. to select routes.
- Optimization parameters are distance, number of hops and estimated transit time.
#### Centralised 
In this method, a centralized node has entire information about the network
and makes all the routing decisions. Advantage of this is only one node is required to keep the information of entire network and disadvantage is that if central node goes down the entire network is done.
#### Distributed
In this method, the node receives information from its neighbors and then
takes the decision about routing the packets. Disadvantage is that the packet may be delayed if there is change in between interval in which it receives information and sends packet.
#### Isolated
n this method each, node makes its routing decisions using the information it has
locally without seeking information from other nodes. The sending nodes doesn’t have
information about status of particular link. Disadvantage is that packet may be sent through a congested network which may result in delay. Examples: Hot potato routing, backward
learning
### Non-adaptive Algo
hese are the algorithms which do not change
their routing decisions once they have been selected. This is also known as static
routing as route to be taken is computed in advance and downloaded to routers when
router is booted.
#### Flooding
his adapts the technique in which every incoming packet is sent on every
outgoing line except from which it arrived. One problem with this is that packets may go in
loop and as a result of which a node may receive duplicate packets. These problems can be
overcome with the help of sequence numbers, hop count and spanning tree.

#### Random-walk
In this method, packets are sent host by host or node by node to one of its
neighbors randomly. This is highly robust method which is usually implemented by sending
packets onto the link which is least queued

![[Pasted image 20231022161242.png]]

### Hierarchical Routing
In this method of routing the nodes are divided into regions based on
hierarchy
A particular node can communicate with nodes at the same hierarchical level or the nodes at
a lower level and directly under it.
Here, the path from any source to a destination is fixed and is exactly one if the hierarchy is a tree.

**In Hierarchical routing, the interfaces need to store information about:**
- All nodes in its region which are at one level below it.
- Its peer interfaces.
- At least one interface at a level above it, for outgoing packages.
**+ves**
- smaller size of routing tables
- substaintially lesser calculations and updates of routing tables
**-ves**
- Once the hierarchy is imposed on the network, it is followed and possibility of direct paths is ignored.
- This may lead to sub optimal routing.
### Optimality principle 
- We can make a general statement about optimal routes without regard to network topology or traffic which is known as optimality principle.
- it states that if router J is on optimal path from I to K then optimal path from J to K also fall on same route
- if the path b/w I and K is optimal then, if any router exist b/w I and K i.e J . so the path b/w from I to J and J to K is also optimal
![[Pasted image 20231022163723.png]]
![[Pasted image 20231022163805.png]]
## Static routing algo
### Shortest path Routing algo
We need to calculate a shortest path that is optimal.
A network is represented as a graph, with its terminals as nodes and the links as edges. A
'length' is associated with each edge, which represents the cost of using the link for
transmission.
- Lower the cost, more suitable is the link. The cost is determined depending upon the criteria to be optimized. 
	- Minimum number of hops:- If each link is given a unit cost, the shortest path is the one with minimum number of hops. 
	- Transmission and Propagation Delays: If the cost is fixed as a function of transmission and propagation delays, it will reflect the link capacities and the geographical distances. 
	- Queuing Delays: If the cost of a link is determined through its queuing delays, it takes care of the varying load conditions, but not of the propagation delays.
- Common shortest path algorithms are:
	- Dijkstra's algorithm
	- Bellman Ford algorithm
	- Floyd Warshall’s algorithm
## Distance vector routing algo
- Distance Vector Routing is one of the dynamic routing algorithm.
- It is suitable for packet switched network.
- In distance vector routing, each router maintains a routing table.
- It contains one entry for each router in the subnet. This entry has two parts:
	- The first part shows the preferred outgoing line to be used to reach the destination.
	- Second part gives an estimate of the time or distance to the destination
- In distance vector routing, a node tells its neighbor about its distance to every other node in the network.
- Distance vector algorithm is iterative, asynchronous and distributed in nature.
	- Distributed: It is distributed in that each node receives information from one or more of its directly attached neighbors, performs calculation and then distributes the result back to its neighbors.
	- Iterative: It is iterative in that its process continues until no more information is available to be exchanged between neighbors.
	- Asynchronous: It does not require that all of its nodes operate in the lock step with each other
- Keys to understand the working of Distance Vector Routing Algorithm:
	-  Knowledge about the whole network: Each router shares its knowledge through the entire network. The Router sends its collected knowledge about the network to its neighbors.
	- Routing only to neighbors: The router sends its knowledge about the network to only those routers which have direct links. The router sends whatever it has about the network through the ports. The information is received by the router and uses the information to update its own routing table.
	- Information sharing at regular intervals: Within 30 seconds, the router sends the information to the neighboring routers.