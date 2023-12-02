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
![](../../../statics/Pasted%20image%2020231122091409.png)
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
![](../../../statics/Pasted%20image%2020231122094654.png)

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
![](../../../statics/Pasted%20image%2020231122100740.png)
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
![](../../../statics/Pasted%20image%2020231122173430.png)
#### Carrier sense multiple access protocol
Protocols in which stations listen for a carrier (i.e., a transmission) and act accordingly are called carrier sense protocols.
1. 1-presistent method:- it is a simple method . in this , after the station finds the line idle, it sends its frame immediately (with probability 1) . This method has highest chance of collision because two or more ]station may find the medium idle and send frame immediately 
![](../../../statics/Pasted%20image%2020231122163821.png)

2. Non-persistent :- in this a station that has frame to send senses the line. if line is idle , it sends immediately . if line is not idle , it waits a random amount time and then sense the line again. this approach reduce the chance of collision because it is unlikely that two or more stations will wait the same amount of time and retry to send simultaneously. however , this method reduce the efficiency of network because the medium remains idle when there may be stations with frames to send. 
![](../../../statics/Pasted%20image%2020231122164309.png)
3. P-Persistent:- it combines advantages of other two strategies . reduce chance of collision and improve efficiency. 
- With probability p , the station sends its frame.
- With probabilty q = 1 - p , the station waits for the beginning of next time slot and checks the line again
	- if the line is idle , it goes to step 1
	- if line is busy , it acts as though collision has occured
![](../../../statics/Pasted%20image%2020231122164653.png)
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

# Data Link Layer
The main task of the data link layer is to take a raw transmission facility and transform it into a line that appears free of transmission errors in the network layer.

## Functions 
1. Providing a well-defined service interface to the network layer.
2. Dealing with transmission errors.
3. Regulating the flow of data so that slow receivers are not swamped by fastvsenders.

## Requirement and obj of effective data communication 
- Frame synchronization-Data are sent in blocks called frames. The beginning and end of each frame must be recognizable.
- Flow control-The sending station must not send frames at a rate faster then the receiving station can absorb them. 
- Error control-Any bit errors introduced by the transmission system must be corrected.
- Addressing-On a multipoint line, such as a local area network (LAN), the identity of the two stations involved in a transmission must be specified.
- Control and data on same link- It is usually not desirable to have a physically separate communications path for control information. Accordingly, the receiver must be able to distinguish control information from the data being transmitted.
- Link management-The initiation, maintenance, and termination of a sustained data exchange requires a fair amount of coordination and cooperation among stations. Procedures for the management of this exchange are required
## Services provided to network layer
Three possible service provided 
1. Unacknowledged connectionless service.:- Unacknowledged connectionless service consists of having the source machine send independent frames to the destination machine without having the destination machine acknowledge them. No logical connection is established beforehand or released afterward.
2. Acknowledged connectionless service.:- Acknowledged connectionless service, there are still no logical connections used, but each frame sent is individually acknowledged. In this way, the sender knows whether a frame has arrived correctly. If it has not arrived within a specified time interval, it can be sent again
3. Acknowledged connection-oriented service:- Connection-oriented service, the source and destination machines establish a connection before any data is transferred. Each frame sent over the connection is numbered, and the data link layer guarantees that each frame sent is indeed received.
## Framing 
framing is a process of encapsulating data into frames for reliable transmission over a communication link.

![](../../../statics/Pasted%20image%2020231123204838.png)

The usual approach is for the data link layer to break the bit stream up into discrete frames and compute the checksum for each frame. When a frame arrives at the destination, the checksum is recomputed. If the newly computed checksum is different from the one contained in the frame, the data link layer knows that an error has occurred and takes steps to deal with it.

### Methods of framing 
1. **Character Count:**
   - In the character count framing method, a field in the frame header indicates the number of characters (or bytes) in the data field of the frame. The receiving end uses this count to identify the boundaries of the frame. This method is straightforward and does not involve the insertion of additional control characters.

2. **Flag Bytes with Byte Stuffing:**
   - This method uses special flag bytes (delimiters) to mark the beginning and end of a frame. Byte stuffing is employed to handle instances where the data field contains the same byte sequence as the flag. To distinguish between actual flags and data that might be mistaken for flags, an escape character is inserted before any occurrence of the flag in the data. This escape character signals that the following byte is not a flag but part of the data.

3. **Starting and Ending Flags, with Bit Stuffing:**
   - Similar to the flag bytes method, this approach uses special start and end flag sequences to mark the beginning and end of a frame. Bit stuffing is employed to handle cases where the data portion of the frame contains consecutive bits that match the flag sequence. If a specific bit pattern is detected in the data that corresponds to the flag, an extra bit is inserted to avoid confusion between data and flags.

4. **Physical Layer Coding Violations:**
   - This method involves violating the normal coding rules of the physical layer to indicate the start and end of frames. An example is Manchester encoding, where a transition in the middle of a bit period signifies the start of a frame, and the absence of a transition signifies the end. This approach doesn't rely on specific byte sequences but rather on changes in the physical encoding.

## Error Control

The usual way to ensure reliable delivery is to provide the sender with some feedback about what is happening at the other end of the line. Typically, the protocol calls for the receiver to send back special control frames bearing positve or negative acknowledgements about the incoming frames. If the sender receives a positive acknowledgement about a frame, it knows the frame has arrived safely. On the other hand, a negative acknowledgement means that something has gone wrong and the frame must be transmitted again.

Error control in data link layer is the process of detecting and correcting data frames that have been corrupted or lost during transmission.

Data link layer follows a technique to detect transit errors and take necessary actions, which is retransmission of frames whenever error is detected or frame is lost.

### The process is called Automatic Repeat Request (ARQ).
Automatic Repeat reQuest (ARQ) is a protocol used in communication networks to ensure the reliable delivery of data over unreliable channels. The primary purpose of ARQ protocols is to detect and recover from errors that may occur during the transmission of data. 

ARQ protocols operate by sending data frames from the sender to the receiver, and the receiver sends acknowledgments (ACKs) back to the sender. If the sender does not receive the expected ACK within a specified time (timeout period), it assumes that the frame was lost or corrupted and retransmits the frame.

There are several types of ARQ protocols, including:

1. **Stop-and-Wait ARQ:**
   - The sender sends a single frame and waits for an acknowledgment before sending the next frame.
   - Simple but not efficient, as the sender cannot utilize the channel fully.

2. **Go-Back-N ARQ:**
   - The sender can transmit multiple frames (a window of frames) before receiving acknowledgments.
   - If an acknowledgment is not received within a timeout period, the sender retransmits all frames in the window starting from the unacknowledged frame.

3. **Selective Repeat ARQ:**
   - Similar to Go-Back-N, but the sender only retransmits the frames that have not been acknowledged, allowing for more efficient use of the channel.

ARQ protocols are crucial for ensuring data integrity in communication systems where errors may occur due to noise, interference, or other factors. The choice of a specific ARQ protocol depends on the characteristics of the communication channel, the level of reliability required, and the desired efficiency in utilizing the available bandwidth.
### Phases of error control
- Error Detection
- Acknowledgement (ACK)
	- +ve or -ve ACK
- Retransmission

### Error Control Protocols
- STOP and Wait Protocol
- Sliding Window
	- GO Back N 
	- Selective Repeat

#### GO Back N
"Go-Back-N" (GBN) is a type of automatic repeat request (ARQ) protocol used for error control in data transmission. It is commonly employed in network communication protocols, especially in the context of reliable data transfer over unreliable channels, such as in computer networks.

here N represent the window size
##### Features 
1. **Sliding Window:**
    - GBN uses a sliding window mechanism on the sender's side to manage the transmission of multiple frames.
    - The sender can transmit a window of frames before waiting for acknowledgments.
2. **Sequence Numbers:**
    - Each frame sent by the sender is assigned a unique sequence number.
    - The sequence numbers help in ordering and identifying frames at the receiver and allow the sender to keep track of the acknowledgment status of each frame.
3. **Cumulative Acknowledgments:**
    - The receiver sends cumulative acknowledgments, indicating the highest correctly received and in-order frame.
    - The sender can use this acknowledgment to advance the window.
4. **Timeout and Retransmission:**
    - The sender sets a timer when it sends the first frame in the window.
    - If the timer expires before an acknowledgment is received, the sender assumes that one or more frames are lost and retransmits all frames in the window.
5. **Selective Repeat:**
    - While Go-Back-N is a specific variant, it exhibits a form of selective repeat behavior in that the sender retransmits multiple frames rather than just the lost frame.
##### Here's a brief overview of how the Go-Back-N protocol works:

1. **Sender Side:**
   - The sender maintains a window of frames that it can send.
   - Each frame is assigned a sequence number.
   - The sender sends frames within the current window to the receiver.
   - It starts a timer for the oldest unacknowledged frame.

2. **Receiver Side:**
   - The receiver receives frames and sends acknowledgments (ACKs) for correctly received frames.
   - The receiver only accepts frames that arrive in order within a specific window.

3. **Sender Timeout:**
   - If the sender's timer expires before receiving an ACK for the oldest unacknowledged frame, it assumes that the frame (or one of the preceding frames) was lost.
   - The sender retransmits all frames in the window from the oldest unacknowledged frame.

4. **Receiver Handling:**
   - The receiver discards out-of-order frames and accepts only frames that arrive within the current window.
   - Duplicate frames are discarded.

5. **Acknowledgments:**
   - The receiver sends cumulative ACKs, indicating the highest correctly received frame.
   - The sender uses the ACK to advance the window.

6. **Error Handling:**
   - GBN is designed to handle errors by retransmitting frames when the sender's timer expires.

One of the main advantages of Go-Back-N is its simplicity. However, it has some limitations, such as the potential for unnecessary retransmissions when only one frame is lost.

It's worth noting that there are other ARQ protocols, such as Selective Repeat, which can be more efficient in certain situations. Selective Repeat allows the receiver to individually acknowledge correctly received frames, reducing the need for retransmitting frames that have already been successfully received.

#### Selective Repeat ARQ 
- In this only the erroneous or lost frames are retransmitted , while correct frames are received and buffered 
- receiver while keeping track of sequence numbers , buffer the frames in memory and sends NACK for only frame which is missing or damaged.
- Sender will retransmit/send packet for which NACK(negative ACK) is received 

![](../../../statics/Pasted%20image%2020231123213509.png)

## Error 
#### Types of error 
- Bit Error:- aka single bit error , in this only 1 bit in data unit has been changed 
![](../../../statics/Pasted%20image%2020231123214250.png)
- Burst error:- in this 2 or more bits in data unit have changed 
![](../../../statics/Pasted%20image%2020231123214416.png)

### Error Detection 
- means to decide whether the received data is correct or not without having a copy of original message
- to detect or correct error , some extra bit need to be send with data 
- extra bit are called as redundant bit

  
In the context of error detection in networking, redundancy refers to the inclusion of extra information or bits in data transmission to detect errors that may occur during the communication process. The idea is to add redundant bits to the original data so that the recipient can identify and correct errors introduced by noise, interference, or other factors during transmission.

![](../../../statics/Pasted%20image%2020231123214730.png)

#### There are different types of redundancy techniques used for error detection in networking:
##### Vertical redundancy check (Parity Check)
- Parity check is done by adding an extra bit, called parity bit to the data to make a number of 1s either even in case of even parity or odd in case of odd parity.
- While creating a frame, the sender counts the number of 1s in it and adds the parity bit in the following way.
- In case of even parity: If a number of 1s is even then parity bit value is 0. If the number of 1s is odd then parity bit value is 1.
- In case of odd parity: If a number of 1s is odd then parity bit value is 0. If a number of 1s is even then parity bit value is 1.
- At the receiving end, the parity bit is calculated from the received data bits and compared with the received parity bit. Even parity example
- This technique generates the total number of 1s even, so it is known as even-parity checking.

![](../../../statics/Pasted%20image%2020231123215914.png)

#### Single bit vs 2D parity
**Single Bit Parity:**

1. **Concept:**
   - Single bit parity involves adding one additional bit to a data word to ensure that the total number of bits set to '1' is even (even parity) or odd (odd parity).

2. **Calculation:**
   - For even parity, the additional bit is set to make the total number of '1' bits (including the parity bit) even.
   - For odd parity, the additional bit is set to make the total number of '1' bits odd.

3. **Error Detection:**
   - Single bit parity can detect the presence of an odd number of errors.
   - If an odd number of bits are flipped, the parity check will fail.

4. **Example:**
   - Suppose you have a data word "1101" and you want to use even parity. The parity bit would be set to '0' to make the total number of '1' bits even, resulting in "01101."

**Two-Dimensional Parity:**

1. **Concept:**
   - Two-dimensional parity extends the concept of single bit parity to two dimensions, creating a matrix of data and parity bits.

2. **Structure:**
   - Data is organized into rows and columns, and parity bits are calculated for each row and column.

3. **Calculation:**
   - Parity bits for rows and columns are calculated independently.
   - The parity of each row is determined, and an additional parity bit for the row is added.
   - Similarly, the parity of each column is determined, and an additional parity bit for the column is added.

4. **Error Detection:**
   - Two-dimensional parity can detect and locate errors in both rows and columns.
   - It can detect and correct single-bit errors and detect multiple-bit errors within a row or column.

5. **Example:**
   - Consider a 3x3 matrix with data bits:
     ```
     1 0 1
     0 1 1
     1 1 0
     ```
     Parity bits for rows and columns are calculated and added:
     ```
     1 0 1 0
     0 1 1 0
     1 1 0 1
     1 0 0 1
     ```
     The final matrix is transmitted, and the receiver can use row and column parity checks for error detection.

**Comparison:**

- **Single Bit Parity:**
  - Detects and signals the presence of an odd number of errors.
  - Simple and easy to implement.
  - Limited error detection capability.

- **Two-Dimensional Parity:**
  - Detects and locates errors in both rows and columns.
  - Can detect and correct single-bit errors within a row or column.
  - More complex but provides enhanced error detection capabilities.

#### Checksum
- They are mathematical values calculated from a set of data, such as a sequence of bits or bytes, and are used to verify the integrity of the data. The basic idea is to generate a checksum at the sender's end and send it along with the data. The receiver then recalculates the checksum based on the received data and compares it with the sent checksum to detect any errors that might have occurred during transmission or storage.
- Process
	- Data is divided into fixed sized frames or segments.
	- The sender adds the segments using 1’s complement arithmetic to get the sum. It then complements the sum to get the checksum and sends it along with the data frames.
	- The receiver adds the incoming segments along with the checksum using 1’s complement arithmetic to get the sum and then complements it.
	- If the result is zero, the received frames are accepted; otherwise, they are discarded.

#### Cyclic Redundancy check
- In CRC technique, a string of n 0s is appended to the data unit, and this n number is less than the number of bits in a predetermined number, known as division which is n+1 bits.
- Secondly, the newly extended data is divided by a divisor using a process is known as binary division. The remainder generated from this division is known as CRC remainder.
- Thirdly, the CRC remainder replaces the appended 0s at the end of the original data. This newly generated unit is sent to the receiver.
- The receiver receives the data followed by the CRC remainder. The receiver will treat this whole unit as a single unit, and it is divided by the same divisor that was used to find the CRC remainder.
- If the resultant of this division is zero which means that it has no error, and the data is accepted.
- If the resultant of this division is not zero which means that the data consists of an error. Therefore, the data is discarded.
![](../../../statics/Pasted%20image%2020231124084503.png)

### Error Correction
- Error correction techniques find out the exact number of bits that have been corrupted and as well as their locations. There are two principle ways
- Backward Error Correction (Retransmission) − If the receiver detects an error in the incoming frame, it requests the sender to retransmit the frame.
- It is a relatively simple technique. But it can be efficiently used only where retransmitting is not expensive as in fiber optics and the time for retransmission is low relative to the requirements of the application.
- Forward Error Correction − If the receiver detects some error in the incoming frame, it executes error-correcting code that generates the actual frame.
- This saves bandwidth required for retransmission.
- It is inevitable in real-time systems. However, if there are too many errors, the frames need to be retransmitted.
## Flow Control 
**Flow control** is a mechanism used in networking to manage the rate of data transmission between two devices to prevent congestion or overloading of the receiving system. It ensures that a fast sender does not overwhelm a slow receiver, providing a balance in the data transfer process.

In the context of the Data Link Layer of the OSI model, flow control is particularly important for the following reasons:

1. **Speed Mismatch:**
   - Devices on a network may operate at different speeds or have varying processing capabilities. For example, a fast sender might be capable of transmitting data at a rate much higher than what the slower receiver can process. Flow control helps regulate the flow of data to match the speed of the slower receiver.

2. **Limited Buffer Capacity:**
   - The receiving device typically has limited buffer space to store incoming data. If data arrives too quickly for the receiver to process or store, it can lead to buffer overflow and data loss. Flow control helps manage the rate of incoming data to prevent such overflow situations.

3. **Preventing Congestion:**
   - Flow control helps prevent network congestion, where an excessive amount of data overwhelms the capacity of intermediate network devices or links. Congestion can lead to delays, packet loss, and reduced overall network performance.

4. **Reliability and Quality of Service (QoS):**
   - Flow control contributes to the reliability and quality of service in a network. By preventing the sender from transmitting data at a rate that the receiver or the network cannot handle, it ensures a more consistent and reliable data transfer experience.

5. **Acknowledgment Mechanisms:**
   - Flow control often involves the use of acknowledgment mechanisms. The sender waits for acknowledgment from the receiver before sending more data. If acknowledgments are not received within a certain timeframe, it may trigger a slowdown in the transmission rate or retransmission of data.

### Flow Control Approaches are as:
- Feedback Based flow control:- sender sends frames after it has received acknowledgments from the user. This is used in the data link layer.
- Rate Based Flow Control:- It have built in mechanisms to restrict the rate of transmission of data without requiring acknowledgment from the receiver. This is used in the network layer and the transport layer.
 
### Data Link Layer uses feedback based flow control mechanism which mainly uses the techniques as follows:

####  **Stop-and-Wait:** The sender waits for an acknowledgment before sending the next frame.
![](../../../statics/Pasted%20image%2020231123143106.png)
1. **Sender Transmits a Frame:**
    - The sender transmits a data frame to the receiver.
2. **Sender Waits for Acknowledgment:**
    - After sending the frame, the sender waits for an acknowledgment (ACK) from the receiver.
3. **Receiver Receives Frame:**
    - The receiver receives the frame and checks for errors. If the frame is error-free, the receiver sends an acknowledgment back to the sender.
4. **Sender Receives Acknowledgment:**
    - The sender receives the acknowledgment. If the acknowledgment indicates successful receipt, the sender can then proceed to send the next frame. If there's an indication of an error or if the acknowledgment is not received within a specified time (timeout), the sender assumes that the frame was lost or corrupted and retransmits the same frame.
5. **Receiver Processes Frame and Waits:**
    - After successfully receiving a frame and sending an acknowledgment, the receiver processes the data and waits for the next frame.
#### **Sliding Window:** The sender can have multiple frames in transit before receiving acknowledgments.

![](../../../statics/Pasted%20image%2020231123212626.png)

![](../../../statics/Pasted%20image%2020231123143918.png)
![](../../../statics/Pasted%20image%2020231123143937.png)
notice here that sliding window shifted because the ack is received for 0 frame


The Sliding Window flow control mechanism is a more sophisticated approach compared to the Stop-and-Wait method. It allows the sender to transmit multiple frames before receiving acknowledgments, which can significantly improve the efficiency of data transfer. The process involves several steps:

1. **Initialization:**
   - Both the sender and the receiver initialize their respective windows. The window size represents the number of frames that can be in transit at any given time.

2. **Sender's Perspective:**
   - The sender maintains a "send window," which is a range of sequence numbers for frames that it is allowed to send without waiting for acknowledgments.

3. **Receiver's Perspective:**
   - The receiver maintains a "receive window," representing the range of sequence numbers it is willing to accept. The receive window helps the receiver handle out-of-order frames.

4. **Frame Transmission:**
   - The sender can transmit frames within the current send window without waiting for acknowledgments. Each frame is assigned a sequence number.

5. **Acknowledgments:**
   - The receiver receives the frames, checks for errors, and sends acknowledgments for the received frames. The acknowledgment includes information about the highest correctly received frame.

6. **Advancing the Send Window:**
   - As acknowledgments are received, the sender advances its send window. This advancement allows the sender to transmit new frames with higher sequence numbers.

7. **Sliding the Window:**
   - The sender's window "slides" forward as acknowledgments are received, allowing the sender to transmit new frames. This sliding action is what gives the method its name.

8. **Retransmission on Timeout or Negative Acknowledgment (NAK):**
   - If a frame is not acknowledged within a specified time (timeout) or if a negative acknowledgment (NAK) is received, the sender retransmits the frame. In Selective Repeat, only the frames with errors are retransmitted.

9. **Handling Out-of-Order Frames at Receiver:**
   - The receiver's receive window helps handle out-of-order frames. It acknowledges correctly received frames and signals the sender to retransmit frames that are missing or corrupted.

10. **Continuous Process:**
    - The process of frame transmission, acknowledgment reception, and window management continues as long as there is data to be transmitted.
