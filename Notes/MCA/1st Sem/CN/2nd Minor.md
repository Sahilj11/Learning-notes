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
## Link state routing algo
Link state is a dynamic routing algorithm in which each router shares knowledge of its neighbors with every other router in the network.

A router sends its information about its neighbors only to all the routers through flooding.
Information sharing takes place only whenever there is a change.
It makes use of Dijkistra’s Algorithm for making routing tables.
Keys to understand Link state routing:
- Knowledge about the neighborhood: Instead of sending its routing table, a router sends the information about its neighborhood only. A router broadcast its identities and cost of the directly attached links to other routers.
- Flooding: Each router sends the information to every other router on the internetwork except its neighbors. This process is known as Flooding. Every router that receives the packet sends the copies to all its neighbors. Finally, each and every router receives a copy of the same information.
- Information sharing: A router sends the information to every other router only when the change occurs in the information.

Link State Routing Phases:
- Reliable Flooding
	- Initial state: Each node knows the cost of its neighbors.
	- Final state: Each node knows the entire graph.
- Route Calculation
	- Each node uses Dijkstra's algorithm on the graph to calculate the optimal routes to all nodes.
	- The Link state routing algorithm is also known as Dijkstra's algorithm which is used to find the shortest path from one node to every other node in the network.
	- The Dijkstra's algorithm is an iterative, and it has the property that after kth iteration of the algorithm, the least cost paths are well known for k destination nodes.
![[Pasted image 20231022182812.png]]

## count to infinity
- Problem with distance vector routing is whenever a link is broken, other routers unknowingly gives information that they know how to reach a disconnected node. This false information will propagate to all routers. This problem is known as count to infinity.
- One of the important issue in Distance Vector Routing is Count to Infinity Problem.
- Counting to infinity is just another name for a routing loop.
- In distance vector routing, routing loops usually occur when an interface goes down.
- It can also occur when two routers send updates to each other at the same time.

## Congestion control
A state occurring in network layer when the message traffic is so heavy that it slows down
network response time is called as congestion.
#### Principles of congestion control
Congestion control in networking is a critical aspect of managing data traffic to ensure that the network operates efficiently and fairly. The primary goal of congestion control is to prevent network congestion, which can lead to packet loss, delays, and reduced quality of service. Here are some of the key principles of congestion control in networking:

1. **Load Monitoring**: Networks should continuously monitor the level of congestion. This can be done by measuring factors such as packet loss, delay, or the utilization of network links.
    
2. **Feedback Mechanisms**: Feedback mechanisms are essential for congestion control. They provide information about network conditions to endpoints. Common feedback mechanisms include Explicit Congestion Notification (ECN) and packet loss signals.
    
3. **Resource Allocation**: Effective congestion control involves allocating network resources fairly and efficiently. This can include prioritizing certain types of traffic or ensuring that no single flow consumes an unfair share of resources.
    
4. **Traffic Policing and Shaping**: Network traffic can be shaped and policed to conform to certain traffic profiles and to prevent bursty traffic from overloading network resources.
    
5. **Congestion Avoidance**: Rather than waiting for congestion to occur, congestion avoidance techniques aim to predict and preemptively prevent congestion. One well-known algorithm for this is the Transmission Control Protocol (TCP) congestion control.
    
6. **Flow Control**: Flow control mechanisms ensure that a sender does not overwhelm a receiver with data. TCP, for example, uses a sliding window approach to control the rate at which data is sent based on feedback from the receiver.
    
7. **Quality of Service (QoS)**: QoS mechanisms can be used to prioritize different types of traffic, giving more resources to critical applications like VoIP or video streaming while limiting resources for less critical traffic.

Effects of Congestion:
- As delay increases, performance decreases.
- If delay increases, retransmission occurs, making situation worse

Congestion control algorithms:
- Leaky Bucket Algorithm
- Token bucket Algorithm
#### Leaky bucket algo
- each network interface contains a leaky bucket and the following steps are involved in leaky bucket algorithm:
	- When host wants to send packet, packet is thrown into the bucket.
	- The bucket leaks at a constant rate, meaning the network interface transmits packets at a constant rate.
	- Bursty traffic is converted to a uniform traffic by the leaky bucket.
	- In practice the bucket is a finite queue that outputs at a finite rate.
![[Pasted image 20231022183651.png]]
#### Token bucket algo
The leaky bucket algorithm enforces output pattern at the average rate, no matter how bursty the traffic is.

In order to deal with the bursty traffic we need a flexible
algorithm so that the data is not lost.
- One such algorithm is token bucket algorithm.
- Steps of this algorithm can be described as follows:
	- In regular intervals tokens are thrown into the bucket. 
	- The bucket has a maximum capacity.
	- If there is a ready packet, a token is removed from the bucket, and the packet is sent.
	- If there is no token in the bucket, the packet cannot be sent.
- ![[Pasted image 20231022183941.png]]
#### Congestion control technique
Congestion control refers to the techniques used to control or prevent congestion

- Congestion control techniques can be broadly classified into two categories:
	- Open Loop Congestion Control
	-  Closed Loop Congestion Control
- Open loop congestion control policies are applied to prevent congestion before it happens. The congestion control is handled either by the source or the destination. Open loop control loop have following policies:
	- Retransmission Policy
	- Window Policy
	- Discarding Policy
	- Acknowledgment Policy
	- Admission Policy
- Closed Loop Congestion Control: Closed loop congestion control technique is used to treat or alleviate congestion after it happens. Several techniques are used by different protocols; some of them are:
	- Backpressure
	- Choke Packet Technique
	- Implicit Signaling
	- Explicit Signaling

# IP
## What is it 
- It is a numerical representation that uniquely identifies a specific interface on the network. It is a logical identifier for an interface that is connected to the network.
## Special IPv4 Address
- [[1. IP address#Special address]]
### Feature of IPv4
- Connectionless
- Datagram service(meaning no fixed path , can use any route)
### IPv4 addressing modes
- Unicast Addressing Mode- In this mode, data is sent only to one destined host.
- The Destination Address field contains 32-bit IP address of the destination host. Here the client sends data to the targeted server.
- Broadcast Addressing Mode- In this mode, the packet is addressed to all the hosts in a network segment. The Destination Address field contains a special broadcast address, i.e. 255.255.255.255. When a host sees this packet on the network, it is bound to process it. Here the client sends a packet, which is entertained by all the Servers.
- Multicast Addressing mode - This mode is a mix of the previous two modes, i.e. th packet sent is neither destined to a single host nor all the hosts on the segment. In this packet, the Destination Address contains a special address which starts with 224.x.x.x and can be entertained by more than one host.
### IPv4 Header format
![[Pasted image 20231022185356.png]]
![[Pasted image 20231022190029.png]]
- Version: Version is a 4 bit field that indicates the IP version used always contain value (0100).
	- The most popularly used IP versions are version-4 (IPv4) and version-6 (IPv6).
	- Only IPv4 uses the above header.
- Header Length: Header length is a 4 bit field that contains the length of the IP header.
- Types of Service:
	- Type of service is a 8 bit field that is used for Quality of Service (QoS).
	- The datagram is marked for giving a certain treatment using this field.
- Identification is a 16 bit field.
	- It is used for the identification of the fragments of an original IP datagram.
	- When an IP datagram is fragmented,
	- Each fragmented datagram is assigned the same identification number.
	-  This number is useful during the re assembly of fragmented datagrams.
- DF Bit :DF bit stands for Do Not Fragment bit.
	-  Its value may be 0 or 1.
	-  DF 0, means fragment allow, if required.
	- DF 1, means fragmentation not allowed.
- MF Bit: MF bit stands for More Fragments bit.
	-  Its value may be 0 or 1.
	-  MF 0, indicates last or only fragment.
	-  MF 1, indicates current datagram is fragment of other larger datagram.
-  fragment Offset: Fragment Offset is a 13 bit field.
	- It indicates the position of a fragmented datagram in the original unfragmented IP datagram.
	-  The first fragmented datagram has a fragment offset of zero.
- Header Checksum: Header checksum is a 16 bit field.
	- It contains the checksum value of the entire header.
	-  The checksum value is used for error checking of the header.
	-  At each hop: -
	-  The header checksum is compared with the value contained in this field.
	-  If header checksum is found to be mismatched, then the datagram is discarded.
	-  Router updates the checksum field whenever it modifies the datagram header.
### Type of IPv6 address
- Unicast: An identifier for a single interface. A packet sent to a unicast address is delivered to the interface identified by that address. (E.g. Telephone communication).
- Anycast: An identifier for a set of interfaces (typically belonging to different nodes). A packet sent to an anycast address is delivered to one of the interfaces identified by that address (the "nearest" one, according to the routing protocols' measure of distance). (E.g. –Google established various servers all around the world having same anycast IP address. When we send any request on google, it will be delivered to nearest server to us and the response will delivered back.)
- Multicast: An identifier for a set of interfaces (typically belonging to different nodes). A packet sent to a multicast address is delivered to all interfaces identified by that address. (E.g.- Whatsapp group, A message sent in a group will be delivered to all contacts in group, but not to all contacts in your phone.
- There are no broadcast addresses in IPv6, their function being superseded by multicast addresses.
### IPv6 structure
An IPv6 address is made of 128 bits divided into eight 16-bits blocks. Each block is then
converted into 4-digit Hexadecimal numbers separated by colon symbols.
       2001:0000:3238:DFE1:0063:0000:0000:FEFB
Rule.1: Discard leading Zero(es):
- In Block 5, 0063, the leading two 0s can be omitted, such as (5th block):
      2001:0000:3238:DFE1:63:0000:0000:FEFB
-  Rule.2: If two of more blocks contain consecutive zeroes, omit them all and replace with double colon sign ::, such as (6th and 7th block):
      2001:0000:3238:DFE1:63::FEFB
- Consecutive blocks of zeroes can be replaced only once by :: so if there are still blocks of zeroes in the address, they can be shrunk down to a single zero, such as (2nd block):
    2001:0:3238:DFE1:63::FEFB
![[Pasted image 20231022222635.png]]

### IPv6 feature
Certainly, here are the 8 salient features of IPv6:

1. **Expanded Address Space**: IPv6 uses a 128-bit address format, providing a vast number of unique IP addresses.

2. **Simplified Header Format**: IPv6's streamlined header reduces processing overhead.

3. **Elimination of NAT**: IPv6 removes the need for Network Address Translation, offering end-to-end connectivity.

4. **Improved Security**: Built-in IPsec support enhances network security.

5. **Autoconfiguration**: IPv6 allows devices to generate their own addresses without DHCP.

6. **Mobility Support**: IPv6 supports mobile device roaming.

7. **Quality of Service (QoS)**: IPv6 offers better traffic prioritization.

8. **Multicasting**: Improved support for efficient data transmission to multiple recipients.
### IPv6 +ves -ves
Certainly, here are five advantages and five disadvantages of IPv6:

**Advantages of IPv6:**

1. **Vast Address Space**: IPv6 provides an enormous address space, ensuring a virtually unlimited supply of unique IP addresses for devices and networks.

2. **Simplified Header**: IPv6's streamlined header format reduces the processing overhead on routers and devices, improving network efficiency.

3. **No NAT Requirement**: IPv6 eliminates the need for Network Address Translation (NAT), allowing every device to have a unique, globally routable IP address and simplifying end-to-end connectivity.

4. **Built-In Security**: IPv6 includes integrated IPsec support, enhancing network security with authentication, encryption, and data integrity features.

5. **Autoconfiguration**: IPv6 allows devices to automatically configure their own IP addresses, reducing the reliance on DHCP servers and simplifying network setup.

**Disadvantages of IPv6:**

1. **Compatibility Challenges**: The transition from IPv4 to IPv6 can be complex and requires mechanisms for coexistence, potentially leading to compatibility issues.

2. **Legacy System Support**: Older hardware, software, and network equipment may lack full IPv6 support, necessitating the maintenance of IPv4 compatibility and dual-stack configurations.

3. **Limited Adoption**: IPv6 adoption is not universal, and many networks still primarily rely on IPv4, causing interoperability challenges.

4. **Learning Curve**: IPv6 introduces new concepts and features, requiring network administrators and IT professionals to adapt and learn, which can be a steep learning curve.

5. **Potential Security Concerns**: While IPv6 incorporates security features, it also introduces new potential security challenges and attack vectors, necessitating careful security measures and monitoring.

### IPv4 vs IPv6
IPv4 (Internet Protocol version 4) and IPv6 (Internet Protocol version 6) are both protocols used for identifying and addressing devices on a network, but they have several key differences. Here are some of the primary distinctions:

**1. Address Length:**

   - IPv4: IPv4 uses 32-bit addresses, allowing for approximately 4.3 billion unique addresses. This limited address space has led to IPv4 address exhaustion.
   
   - IPv6: IPv6 uses 128-bit addresses, which provides a vastly larger address space, accommodating approximately 340 undecillion unique addresses. This large address space is necessary to support the growing number of devices and the Internet of Things (IoT).

**2. Address Notation:**

   - IPv4: IPv4 addresses are represented in dotted-decimal format (e.g., 192.168.1.1).

   - IPv6: IPv6 addresses are represented in hexadecimal notation with colons separating groups of 16 bits (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334).

**3. Header Size:**

   - IPv4: IPv4 headers are 20 to 60 bytes in length and contain various fields, some of which are optional.

   - IPv6: IPv6 headers are fixed at 40 bytes, containing a simplified set of fields, reducing processing overhead.

**4. NAT (Network Address Translation):**

   - IPv4: NAT is commonly used in IPv4 networks to conserve IPv4 addresses by allowing multiple devices to share a single public IP address. This can complicate end-to-end communication.

   - IPv6: IPv6's large address space eliminates the need for NAT, as each device can have a unique global address, simplifying end-to-end connectivity.

**5. Autoconfiguration:**

   - IPv4: Autoconfiguration is not a built-in feature of IPv4, and devices often rely on DHCP servers for address assignment.

   - IPv6: IPv6 includes stateless address autoconfiguration, allowing devices to generate their own IP addresses without DHCP, simplifying network setup.

**6. IPsec Support:**

   - IPv4: IPsec is optional and can be added for security purposes.

   - IPv6: IPsec is a fundamental part of IPv6 and is often mandated, enhancing network security.

**7. Mobility Support:**

   - IPv4: Mobility support typically requires complex solutions like Mobile IP.

   - IPv6: IPv6 has built-in support for mobile devices, simplifying mobility.

**8. Quality of Service (QoS):**

   - IPv4: QoS support is possible but not standardized.

   - IPv6: IPv6 includes improved support for QoS, allowing for traffic prioritization.

**9. Fragmentation Handling:**

   - IPv4: Routers are responsible for fragmenting and reassembling packets.

   - IPv6: Fragmentation is generally handled by the source device, reducing the burden on routers.

**10. Header Checksum:**

   - IPv4: IPv4 headers include a checksum for error detection.

   - IPv6: IPv6 removes the header checksum, placing error checking at higher layers.

These are some of the key differences between IPv4 and IPv6, highlighting IPv6's improvements in terms of address space, header simplicity, security, and support for modern network requirements.