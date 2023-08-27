## Definition
- set of nodes connected by communication links
	- nodes:- any device which can send/receive data or do both
		- End devices:- it is the starting device or the end device of a network 
		- Intermediary device:- other than end devices
	- communication links:- medium through which information is been carried . can be wired or wireless
- Server:- device that provide function or service to clients
- Client:- a device that access a service made available by server
- switches:- have many network interfaces/ports for end host to connect to(usually 24+) . provide connectivity to hosts within the same LAN, do not provide connectivity b/w LANs/over the internet.
- ![[sw.png]]
- Router:- have fewer network interfaces than switches , are used to provide connectivity b/w LANs ,are used to send data over internet

## Features of good network
- Fault tolerance:- continue working despite failures
- Scalability :- even if more nodes gets added
- Quality of service:- knowing what request to serve first , for eg giving priority to VoIP Phone(voice over internet like whatsapp call) than an email
- Security:- ability to prevent, unauthorized access, misuse, forgery
	- ability to provide :- confidentiality , integrity and availability 
	- Firewall:- monitor and control network traffic based on configured rules 
		- ![[ff.png]]
		- ![[fire.png]]
		- Can be placed inside the network or outside the network
		- are known as Next generation firewalls when they include more modern and advance filtering capabilities
		- What about computer firewalls 
			- previous example of firewalls are network firewalls , hardware devices that filter traffic b/w networks
			- Host-based firewalls:- software application that filter traffic entering and exiting host like PC
## Network Protocols & Communication
- Data flow:- moving of data from one to another node
	- Simplex:- unidirectional , like keyboard , mouse
	- Half Duplex:- both ways(sending and receiving) but not simultaneously , eg wakie takie
	- Duplex or full duplex:- send and receive at same time For eg , telephone 
- All communcication have these things
	- Source / sender
	- Destination/receiver
	- Chanel or media
- Protocols (set of rules governing data communication. how , when , what is communicated )
	- Elements
		- Message encoding:- Message encoding refers to the process of converting a message from its original format into a different representation that can be transmitted or stored efficiently. Encoding ensures that the message can be accurately conveyed and interpreted by the recipient.
		- Below is example of wired encoding . in case of wireless encoder (waves)
		- ![[encoding.png]]
		- Message formatting and encapsulation:- involve structuring the message content in a standardized manner. This includes organizing the information into appropriate sections, defining the data types and lengths, and specifying the order of the data elements within the message. Encapsulation involves encapsulating the formatted message into a protocol-specific container or wrapper(adding IP of source and destination, port number etc.), which provides additional information for routing and handling the message.
		- Message Timing:- flow control mechanism necessary to match speed of sending and receiving , for example if server can only handle 10 packets and sender giving 50 packets then it is an issue. response timeout can occur if timing is not dealt with  properly 
		- Message size (breaking the message in small packets):- refers to the amount of data that is included in a message. It is important to consider message size when designing communication protocols to optimize bandwidth usage and minimize transmission delays. Large messages can consume more network resources and may introduce higher latency. Message size can be managed by compressing the data, using efficient encoding schemes, or breaking down large messages into smaller, manageable units.
		- Message delivery options:- refer to the various mechanisms and protocols available for transmitting messages from the sender to the recipient. There are different delivery options depending on the requirements of the communication system or application. Some common message delivery options include unicast, multicast, and broadcast. Unicast delivers a message to a single recipient, multicast delivers a message to a group of recipients, and broadcast delivers a message to all recipients within a network. The choice of delivery option depends on factors such as the intended audience, network topology, and scalability requirements.
## Peer to Peer Network
- A peer-to-peer (P2P) network is a decentralized computer network architecture in which individual devices, known as peers, communicate and share resources directly with each other without relying on a central server. In a P2P network, every peer has equal capabilities and can act as both a client and a server.
- In a traditional client-server network model, communication is typically facilitated through a central server that manages and coordinates the network activities. In contrast, a P2P network eliminates the need for a central server and allows peers to directly interact with each other.
- In a peer-to-peer network, each peer can contribute its own resources, such as processing power, storage space, and bandwidth, to be shared with other peers in the network. This enables efficient utilization of resources and can result in improved scalability and fault tolerance.
- P2P networks are commonly associated with file sharing applications, where peers can directly exchange files with each other. However, P2P networks can be used for various purposes, including collaborative computing, distributed storage, content distribution, and communication systems.
## Client-server network
- A client-server network is a common network architecture where devices, known as clients, request services or resources from a central server. The server is a powerful computer or system that provides services, manages resources, and responds to client requests. This network model is widely used in various applications and services, including web browsing, email, file sharing, and database management.
- In a client-server network, the roles of clients and servers are distinct:
	1. Client: A client is a device or software application that accesses and utilizes services or resources provided by the server. Clients can be computers, smartphones, tablets, or any other network-enabled device. Clients initiate requests for services or information and then wait for the server's response. Common examples of clients include web browsers, email clients, and file transfer programs.
	2. Server: The server is a centralized system that provides services or resources to clients. It is typically a high-performance computer with specialized hardware and software configurations. Servers are designed to handle multiple client requests simultaneously and manage various tasks efficiently. Servers can provide services such as hosting websites, managing databases, handling email, or serving files to clients.
- The communication between clients and servers follows a request-response model:
	1. Client Request: The client sends a request to the server, specifying the desired service or resource. The request can be in the form of a Hypertext Transfer Protocol (HTTP) request, a Simple Mail Transfer Protocol (SMTP) request, or any other protocol specific to the service being accessed.	    
	2. Server Processing: Upon receiving the client's request, the server processes it by performing the necessary operations or accessing the required resources. This may involve executing scripts, retrieving data from databases, or performing complex computations.	    
	3. Server Response: After processing the client's request, the server generates a response containing the requested information or the result of the operation. The response is then sent back to the client over the network.	    
	4. Client Reception: The client receives the server's response and interprets it according to the protocol or application. For example, a web browser may render an HTML page received from a web server, or an email client may display a received email message.

## Component of network
- Nodes
- Media:- the link , 
	- wired
		- Ethernet cable(data carried in term of electric signals)
			- Straight-through cable (when two different type of node)
			- Crossover cable :- when wants to connect 2 same type of nodes(like 2 computer, 2 switches etc)
		- Fiber optic cable (data carried in form of light waves)
		- Coaxial cable :- setbox wire
	- wireless(unguided medium)
		- infrared:- short range of communication like tv remote
		- Radio:- example Wifi, bluetooth
		- Microwaves :- like cellular system
		- Satellite
- Services:- e-mail, online games, VoIP,storage service, messaging etc

# Network Topology
- Arrangmenet of nodes of computer network
- Topology = layout
- Physical topology :- placement of various nodes
- Logical topo :- deals with data flow in network
- types
	- Bus:- all data transmitted b/w nodes in network is trasmitted over this common transmission medium and is able to be received by all nodes in network simulataneously . A signal containing address of intended receiviing machine travels from a source machine in both direction to all machines connected to bus until it finds the intended recipient 
		- ![[bus.png]]
	- Ring:- bus topology in closed loop
		- node who has the token has the turn to send data 
		- data transfer is unidirectional
		- ![[ring.png]]
	- Star:- every node connected to a central node , hub or switch
		- ![[star.png]]
		- ![[ex.png]]
		- 
	- Mesh:- each node is directly connected to every other nodes in network
		- ![[mesh.png]]
## Interface and cables
- Switch has lots of interfaces/ports
- ![[interface.png]]
- ![[Rj.png]]
	- like the one in my computer, these are used at end of copper ethernet cable
- Ethernet:- collection of network protocols/standards
	- Variation in electrical signal interpret as 0 or 1
	- Ethernet standard defined in IEEE 802.3 standard
		- ![[co.png]]
		- Cable used in ethernet copper is UTP (unshielded twisted pair), unshielded means they have no metalic shield whcih make them vulnerable electricomagnetic inference although twist in these cable help protect from these
		- pins in RJ 45 there are 8 pins
			- ![[asdf.png]]
		- Not all ethernet standards use all wire , 10BASE T and 100BASE T use 2 pair(4 wires) . 1000BASE T and 10GB BASE T use 4 pair (8wires)
		- ![[qwe.png]]
		- This picture shows which points of RJ 45 is connected with wire
		- ![[jh.png]]
		- here stratight through cable not work due to same point used devices for doing same action , so crossover cable used
		- ![[kj.png]]
		- Auto MDI-X overcome these problem and it automatically change the transmit and receive places to overcome abov problem
-  fiber cables:- use light waves to transmit data
	- ![[az.png]]
	- ![[cvc.png]]
- ![[gd.png]]
- look at last point
- 