# Introduction to CN
## What is Network
- Tenenbaum defines a network as an interconnected collection of autonomous computers.Two computers are said to be interconnected if they are capable of exchanging information. computers are autonomous. This means that no computer on the network can start, stop, or control another.
## Benefits of network
- Resource Sharing:- 
- Reliability:- A file can have copies on two or three different machines, so if one of them is unavailable (hardware crash), the other copies could be used
- Cost Factor: Personal computers have better price/performance ratio than micro computers. So it is better to have PC's, one per user, with data stored on one shared file server machine.
- Communication Medium: Using a network, it is possible for managers, working far apart, to prepare financial report of the company.
## important terminology
- Nodes:- The term nodes refers to the computers that are attached to a network and are seeking to share the resources of the network
- Server: A computer that facilitates "the sharing of data" software" and hardware - resources (e.g. "printers" modems etc,) on the network" is termed as a SERVER.
	- types of server
		- Non-dedicated Servers: On small networks, a workstation that can double up as a server, is known as non-dedicated server since it is not completely dedicated to the cause of serving.
		- Dedicated server
- Network Interface Unit (NIU): A network interface unit is an interpreter that helps to establish communication between the server and workstations. network-interface-unit is a device that is attached to each of the workstations and the server, and helps the workstation to establish the all-important connection with the network. Each network-interface-unit that is attached to a workstation has a unique number identifying it which is known as the node address. The NIU is also called Terminal Access Point (TAP). Different manufacturers have different names for the interface

## Application and use of network
Networks play a crucial role in various aspects of modern technology and communication. Here are some common applications and uses of networks:

1. **Communication:**
   - **Email and Messaging:** Networks enable the exchange of emails and messages, facilitating communication over long distances.
   - **Voice and Video Calls:** Voice over Internet Protocol (VoIP) and video conferencing rely on networks for real-time communication.

2. **Internet Browsing:**
   - Networks allow users to access information on the World Wide Web through browsers, enabling activities such as research, entertainment, and online shopping.

3. **Business Operations:**
   - **File Sharing:** Networks enable the sharing of files and resources within a business or organization, improving collaboration and productivity.
   - **Intranet:** Internal networks facilitate the creation of intranets for organizations to share information and resources among employees.

4. **Education:**
   - **E-Learning:** Networks support online learning platforms, allowing students to access educational materials and interact with instructors and peers remotely.

5. **Entertainment:**
   - **Streaming Services:** Platforms like Netflix, YouTube, and Spotify rely on networks to deliver content to users in real-time.
   - **Online Gaming:** Multiplayer online games depend on networks to connect players and facilitate real-time interactions.

6. **Healthcare:**
   - **Telemedicine:** Networks enable remote healthcare services, allowing patients to consult with healthcare professionals over video calls.
   - **Electronic Health Records (EHR):** Healthcare providers use networks to access and update patient records securely.

7. **Finance:**
   - **Online Banking:** Networks support online banking systems, enabling users to access their accounts, transfer funds, and conduct financial transactions.
   - **E-commerce:** Online shopping platforms rely on networks for secure transactions and communication between buyers and sellers.
## Computer network vs Distributed sytem
A computer network and a distributed system are related concepts, but they have distinct characteristics and purposes. Here are the key differences between a computer network and a distributed system:

1. **Definition:**
   - **Computer Network:** A computer network is a set of interconnected computers and devices that are capable of sharing resources and information with each other. The primary goal of a computer network is to facilitate communication and data exchange between devices.
   - **Distributed System:** A distributed system refers to a collection of independent computers that work together to solve a common problem. In a distributed system, each computer (or node) operates independently, and they communicate and coordinate with each other to achieve a specific task or goal.

2. **Purpose:**
   - **Computer Network:** The main purpose of a computer network is to enable communication and resource sharing. Networks can be local (LAN), connecting devices within a limited geographic area, or wide (WAN), connecting devices across larger distances.
   - **Distributed System:** Distributed systems are designed to solve computational problems that are too large or complex for a single computer. They distribute the workload among multiple computers to improve performance, reliability, and scalability.

3. **Coordination:**
   - **Computer Network:** In a computer network, devices communicate for the purpose of sharing information or resources. However, the devices typically operate independently and may not have a shared understanding of the overall system state.
   - **Distributed System:** Coordination is a fundamental aspect of distributed systems. Nodes in a distributed system work together to achieve a common goal, and they often need to synchronize their actions and share a global understanding of the system state.

4. **Resource Sharing:**
   - **Computer Network:** Resource sharing in a computer network involves sharing files, printers, or other peripheral devices. The focus is on making resources accessible to users across the network.
   - **Distributed System:** Resource sharing in a distributed system involves distributing computational tasks across multiple nodes to improve efficiency and performance. Each node may contribute to the processing power or storage capacity of the overall system.

5. **Fault Tolerance:**
   - **Computer Network:** While some fault tolerance mechanisms exist in networks, the primary focus is on connectivity and efficient communication.
   - **Distributed System:** Distributed systems often incorporate fault tolerance mechanisms to ensure continued operation even if some nodes fail. Redundancy and replication are common strategies in distributed systems.

6. **Examples:**
   - **Computer Network:** The internet is a prime example of a computer network where devices are connected to share information globally.
   - **Distributed System:** Google's infrastructure, which includes distributed file systems and data processing frameworks, is an example of a distributed system designed to handle large-scale computations and data storage.
## Propogation time vs Transmission Time 
- Propagation delay:- it is time it takes for a bit to travel from point A to point B in the trasmission media
	- T<sub>p</sub> = (Distance) / Propagation speed
- Transmission delay:- A sender needs to put the bits in a packet on the line one by one . if first bit of packet is put on line at time t<sub>1</sub> and last bit is put on the line at time t<sub>2</sub> , transmission delay of packet is (t2 - t1).
	- T<sub>t</sub> = (Packet length) / (Transmission rate or bandwidth) = L / B
## Network Hardware
There is no generally accepted taxonomy into which all computer networks fit, but two dimensions stand out as important: transmission technology and scale.
### There are two types of transmission technology that are in widespread use
- Broadcast links:- Broadcast networks have a single communication channel that is shared by all the machines on the network. Short messages, called packets in certain contexts, sent by any machine are received by all the others.
- **point-to-point networks** consist of many connections between individual pairs of machines. To go from the source to the destination, a packet on this type of network may have to, first visit one or more intermediate machines

### On basis of scale
wireless network connecting a computer with its mouse, keyboard, and printer is a **personal area network**. Also, a PDA that controls the user's hearing aid or pacemaker fits in this category. Beyond the personal area networks come longer range networks. These can be divided into local, metropolitan, and wide area networks.
Connection of two or more network is called internetwork (World wide internet is well known example of internetwork)

### Wireless network can be divided into 3 categories
System interconnection is all about interconnecting the components of a computer using short-range radio.
Wireless LAN
Wireless WAN

## Network Software 
### Layers can offer two different types of service to the layers above them: connection-oriented and connectionless.
- Connection-oriented service is modeled after the telephone system. To talk to someone, you pick up the phone, dial the number, talk, and then hang up.
- connectionless service is modeled after the postal system. Each message (letter) carries the full destination address, and each one is routed through the system independent of all the others.
## OSI
- Open system interconnection model . describes how information from a software application in one computer moves through a physical medium to the software application in another computer.
- model divides the whole task into seven smaller and manageable tasks. Each layer is assigned a particular task
- Application 
	- directly interact with data from user
	- software applications like web browser rely on application layer to initiate communication
	- responsibile for protocols(like Http and SMTP) and data manipulation
- Presentation
	- responsible for preparing data so that it can be used by upper layer
	- responsible for translation, encryption and compression of data
- Session 
	- responsible for opening and closing communication b/w two devices
	- function like session establishment , synchronisation and dialog controller
- Transport 
	- responsible for end to end communication b/w two devices
	- taking data from session layer and breaking it up into chunks called segments
	- function segmentation , transport and reassembly
	- responsible for flow control and error control
- Network 
	- responsible for facilitating data transfer b/w two different networks 
	- function are routing and logical addressing 
	- segment in network layer called packet
- Data link layer
	- facilitates data transfer b.w two devices on same network
	- packets broken into frames
	- also responsible for flow control and error control
	- two sub layer
		- Logical link control
			- responsible for transferring packets to network layer of receiver that is receiving 
			- identifies the address of the network layer protocol from the header
			- also provides flow control
		- Media access control layer
			- link b/w logical link control layer and the network physical layer
			- used for transferring packets over network
- Physical 
	- data gets converted into bit stream , 
### Service , interface and protocol
1. **Services:**
   - **Meaning (in OSI context):** Services in the OSI model refer to the functionalities provided by each layer of the model. Each layer offers specific services to the layer above it, and these services are designed to facilitate communication and data exchange between devices on a network.
   - **Example:** In the OSI model, the transport layer provides end-to-end communication services, ensuring that data is delivered reliably and in the correct order.

2. **Interfaces:**
   - **Meaning (in OSI context):** Interfaces in the OSI model represent the boundaries or points of connection between adjacent layers. These interfaces define how the services provided by one layer are accessed by the layer above or below it.
   - **Example:** The interface between the data link layer and the physical layer involves how frames are encoded into bits for transmission over the physical medium.

3. **Protocols:**
   - **Meaning (in OSI context):** Protocols in the OSI model refer to the specific rules and conventions that govern communication within a particular layer. These protocols ensure that devices on a network can understand each other's signals and data format.
   - **Example:** At the network layer of the OSI model, the Internet Protocol (IP) is a protocol that defines how data packets should be addressed and routed between devices on different networks.
![[Pasted image 20231122091409.png]]
### Comparison of OSI Reference Model and TCP/IP Model:

**OSI Reference Model:**

1. **Layers:** The OSI model consists of seven layers: Physical, Data Link, Network, Transport, Session, Presentation, and Application.
2. **Development:** Developed by the International Organization for Standardization (ISO).
3. **Flexibility:** The OSI model is more flexible and comprehensive but can be considered more of a theoretical model.
4. **Strict Hierarchy:** Each layer has distinct functions, and the model follows a strict hierarchy.

**TCP/IP Model:**

1. **Layers:** The TCP/IP model has four layers: Link, Internet, Transport, and Application.
2. **Development:** Developed by the U.S. Department of Defense and is widely used in the development of the Internet.
3. **Practical Implementation:** TCP/IP is more commonly implemented and used in real-world networking scenarios.
4. **Integration:** The TCP/IP model is often seen as more integrated, with some of its layers combining functionalities that are separate in the OSI model.

**Comparison:**

- Both models provide a conceptual framework for understanding network protocols, but the TCP/IP model is more commonly used in practice, especially in the context of the Internet.
- The OSI model offers a more detailed and comprehensive approach, while the TCP/IP model is simpler and more closely aligned with real-world networking implementations.

# Media Access Control sub Layer
## Intro
it deals how to determine that who may use the network next when the network consists of a single shared channel, as in most networks. This layer is also known as the Medium Access Control Sub-layer.

The protocols used to determine who goes next on a multi-access channel belong to a sub-layer of the data link layer called the MAC (Medium Access Control) sub-layer. The MAC sub-layer is especially important in LANs, many of which use a multi-access channel as the basis for communication.

## Functions 
- It provides an abstraction of the physical layer to the LLC and upper layers of the OSI network.
- It is responsible for encapsulating frames so that they are suitable for transmission via the physical medium.
- It resolves the addressing of source station as well as the destination station, or groups of destination stations.
- It performs multiple access resolutions when more than one data frame is to be transmitted. It determines the channel access methods for transmission.
- It also performs collision resolution and initiating retransmission in case of collisions.
- It generates the frame check sequences and thus contributes to protection against transmission errors.
## Channel Allocation problem
### Static Channel allocation
The traditional way of allocating a single channel, eg. a telephone line, among multiple competing users is Frequency Division Multiplexing (FDM). If there are N users, the bandwidth is divided into N equal-sized portions, each user being assigned one portion

If the spectrum is cut up into N regions and fewer than N users are currently interested in communicating, a large piece of valuable spectrum will be wasted. If more than N users want to communicate, some of them will be denied permission for lack of bandwidth, even if some of the users who have been assigned a frequency band hardly ever transmit or receive anything.

- Time Division Multiple Access (TDMA) – With TDMA the time axis is divided into time slots of a fixed length.
	- Each user is allocated a fixed set of time slots at which it can transmit.
	- TDMA requires that users be synchronized to a common clock. Typically extra overhead bits are required for synchronization.
- Frequency Division Multiple Access (FDMA) – With FDMA the available frequency bandwidth is divided into disjoint frequency bands.
	- A fixed band is allocated to each user. FDMA requires a guard band between user frequency bands to avoid cross-talk.
	- Another static allocation technique is Code Division Multiple Access (CDMA), which is used in many wireless networks
### Dynamic channel allocation

**Dynamic Channel Allocation:**
- This is a system where multiple independent stations (think of them like individual computers or devices) share a single communication channel.
- When a station wants to send information (frames), it generates a message. But, it can't do anything else until that message is successfully sent.
Dynamic Channel Allocation (DCA) is a technique used in communication systems, especially in networking, where the assignment of communication channels is not fixed or predetermined. In dynamic allocation, channels are assigned on a need basis and can be changed over time based on the current demand or conditions of the network. This dynamic approach allows for more flexible and efficient use of resources.

**Key Assumptions:**
1. **Station Model:**
   - There are N independent stations, each with its own program or user.
   - The chance of a station creating a message in a small amount of time (dt) is F dt, where F is a constant (how fast messages are made).

2. **Single Channel Assumption:**
   - All stations share one channel for communication. They can all send and receive on this channel.
   - Even though the stations are equal in terms of hardware, the software may give them different priorities.

3. **Collision Assumption:**
   - If two stations try to send messages at the same time, their signals mix up, causing a collision.
   - Stations can detect collisions, and if it happens, the message has to be sent again later. There are no errors other than collisions.

4. **Continuous Time:**
   - Messages can start sending at any moment. There's no fixed schedule.

5. **Slotted Time:**
   - Time is split into chunks called slots. Whenever a message is sent, it starts at the beginning of a slot.
   - A slot can be empty, have one successful message, or have a collision (when two messages overlap).

6. **Carrier Sense:**
   - Stations can check if the channel is busy before trying to use it. If it's in use, they wait until it's free.

7. **No Carrier Sense:**
   - Stations can't check if the channel is busy before sending. They just go ahead and send. Only afterward, they find out if it worked.

## Multiple access protocol
![[Pasted image 20231122094654.png]]

### Random access protocols
Random Access Protocols refer to a class of communication protocols in networking where multiple nodes or devices have access to a shared communication channel, and each node has an equal opportunity to transmit data without a fixed schedule or predefined order. The primary characteristic of random access protocols is that nodes contend for access to the channel, and the contention resolution mechanism involves randomness or probabilistic methods.

Here are some key points about random access protocols:

1. **Contending for Access:** In a random access protocol, multiple nodes share a common communication channel. When a node has data to transmit, it contends for access to the channel, indicating its intention to send.

2. **Equal Opportunity:** Each node in the network has an equal chance of gaining access to the channel. There is no predefined order or hierarchy among nodes.

3. **No Fixed Schedule:** Unlike scheduled or controlled access protocols, there is no fixed time slot or schedule for nodes to transmit. Nodes transmit whenever they have data to send.

4. **Collision Handling:** Since multiple nodes may attempt to transmit simultaneously, collisions can occur. Collision detection and resolution mechanisms are implemented to manage these situations.

5. **Examples of Random Access Protocols:**
   - **ALOHA:** One of the earliest examples of a random access protocol is the ALOHA protocol, where nodes can transmit data at any time. Collisions are detected, and retransmissions are attempted after random backoff periods.
   - **Carrier Sense Multiple Access (CSMA):** CSMA protocols listen to the channel before transmitting. If the channel is sensed as busy, the node defers its transmission. Variants include CSMA/CD (Collision Detection) and CSMA/CA (Collision Avoidance).

6. **Efficiency and Throughput:** Random access protocols are often efficient in scenarios with variable and unpredictable data transmission patterns. However, as the network becomes more congested or the number of contending nodes increases, the likelihood of collisions also rises, potentially affecting throughput.

Many algorithms for allocating a multiple access channel are known , some of them are:
#### ALOHA 
There are two versions of ALOHA here: pure and slotted. They differ with respect to whether time is divided into discrete slots into which all frames must fit. Pure ALOHA does not require global time synchronization; slotted ALOHA does.

throughput of ALOHA systems is maximized by having a uniform frame size rather than by allowing variable length frames.

##### Pure ALOHA(the original ALOHA is called pure aloha)
The basic idea of an ALOHA system is simple: let users transmit whenever they have data to be sent. There will be collisions, of course, and the colliding frames will be damaged. However, due to the feedback property of broadcasting, a sender can always find out whether its frame was destroyed by listening to the channel, the same way other users do. If the frame was destroyed, the sender just waits a random amount of time and sends it again. The waiting time must be random or the same frames will collide over and over, in lockstep. Vulnerable time , in which there is a possibility of collision (it is vulnerable time = 2 X T<sub>1</sub>)
![[Pasted image 20231122100740.png]]
Advantages:
- Superior to fixed assignment when there are large number of bursty stations.
- Adapts to varying number of stations.
Disadvantages:
- Theoretically proven throughput maximum of 18.4%.
- Requires queuing buffers for retransmission of packets.
##### Slotted aloha
This is to divide time into discrete intervals, each interval corresponding to one frame. This approach requires the users to agree on slot boundaries

One way to achieve synchronization would be to have one special station emit a pip at the start of each interval, like a clock. It is required to wait for the beginning of the next slot. Thus, the continuous pure ALOHA is turned into a discrete one.
Vulnerable time is halfed here which is T
Advantages:
- Doubles the efficiency of Aloha.
- Adaptable to a changing station population.
Disadvantages:
- Theoretically proven throughput maximum of 36.8%.
- Requires queuing buffers for retransmission of packets.
Synchronization required.
- Synchronous system: time divided into slots
- Slot size equals fixed packet transmission time
![[Pasted image 20231122173430.png]]
#### Carrier sense multiple access protocol
Protocols in which stations listen for a carrier (i.e., a transmission) and act accordingly are called carrier sense protocols.
1. 1-presistent method:- it is a simple method . in this , after the station finds the line idle, it sends its frame immediately (with probability 1) . This method has highest chance of collision because two or more ]station may find the medium idle and send frame immediately 
![[Pasted image 20231122163821.png]]

2. Non-persistent :- in this a station that has frame to send senses the line. if line is idle , it sends immediately . if line is not idle , it waits a random amount time and then sense the line again. this approach reduce the chance of collision because it is unlikely that two or more stations will wait the same amount of time and retry to send simultaneously. however , this method reduce the efficiency of network because the medium remains idle when there may be stations with frames to send. 
![[Pasted image 20231122164309.png]]
3. P-Persistent:- it combines advantages of other two strategies . reduce chance of collision and improve efficiency. 
- With probability p , the station sends its frame.
- With probabilty q = 1 - p , the station waits for the beginning of next time slot and checks the line again
	- if the line is idle , it goes to step 1
	- if line is busy , it acts as though collision has occured
![[Pasted image 20231122164653.png]]
https://youtu.be/HyPiw5XWV0c?t=418 link for its explanation

#### CSMA/CD
Another improvement is for stations to abort their transmissions as soon as they detect a collision. In other words, if two stations sense the channel to be idle and begin transmitting simultaneously, they detect the collision almost immediately. Rather than finish transmitting their frames, which are irretrievably garbled anyway, they should abruptly stop transmitting as soon as the collision is detected. Quickly terminating damaged frames saves time and bandwidth. This protocol, known as CSMA/CD (CSMA with Collision Detection)

Collisions can be detected by looking at the power or pulse width of the received signal and comparing it to the transmitted signal.

After a station detects a collision, it aborts its transmission, waits for a random period of time, and then tries again, assuming that no other station has started transmitting in the meantime.

Frame transmission time should be at least twice the maximum propagation time (Tr = 2 X Tp) this is to ensure that packet size is large enough so that collision can be dedected at the earlier before transmission of packet happen 

#### CSMA/CA (Collision Avoidance) Remaining 
- In wireless network , much of the sent energy is lost 

## LAN Standards

Covered in PPT 
