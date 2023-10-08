## Data communication
Physical transfer of data can be 
- Point to point 
- Point to multipoint

Components 
- Message
- Sender 
- Receiver 
- Medium 
- Encoder and decoder:- computer works with digital signals and communication channel work with analog signals . it converts
features of data communication
- Delivery
- Accuracy 
- Timeliness 
- Jitter :- Variation in packet arrival time . uneven delay in audio , video

![[Pasted image 20230918165551.png]]

### Transmission mode
- Transmission mode refers to the mechanism of transferring of data between two
devices connected over a network. It is also called Communication Mode.
types of transmission mode 
- simplex 
- Half duplex 
- Full duplex
![[Pasted image 20230918165703.png]]

## Computer network
- Elements 
	- Hardware devices
	- Software 
	- Communication channel
	- Protocol
	- message

Topology 
- Mesh 
	- Lets say we have n devices in the network then each device must be connected with (n-1)devices of the network. Number of links in a mesh topology of n devices would be nC2 i.e., n(n-1)/2.
	- techniques to transmit data
		- routing :- In routing, the nodes have a routing logic, as per the network	requirements.
		- Flooding
	- Type of mesh
		- Partial :- some system are connected in same fashion as mesh topology
		- Full
	- +ve
		- No data traffic issues as there is dedicated link
		- reliable and robust 
		- fault detection easy
		- secure because of point to point link
	- -ve
		- complex install
		- expensie
		- More space req
		- Large space to run cables
- Star
	- all computer connected to single device
	- feature
		- every node dedicated connection to hub
		- hub act as repeater 
	- +ve
		- fast performance 
		- easily upgraded 
		- easy to troubleshoot
		- easy to setup and modify
	- -ve 
		- cost 
		- expensive to use
		- single point of failure
- Bus
	- single cable connects all nodes
	- feature
		- transmits data only in one direction
		- every device is connected to single cable
	- +ve
		- cost effective
		- used in small network
		- easy to expand
		- less cable req
	- -ve
		- cable fails then whole network fails
		- not able to handle heavy network traffic
		- expandability limited
- Ring
	-  The following operations takes place in ring topology
			are :
			 One station is known as monitor station which takes all the
			responsibility to perform the operations.
			 To transmit the data, station has to hold the token. After the
			transmission is done, the token is to be released for other
			stations to use.
			 When no station is transmitting the data, then the token will
			circulate in the ring.
			 There are two types of token release techniques : Early
			token release releases the token just after the transmitting
			the data and Delay token release releases the token after
			the acknowledgement is received from the receiver.
	- +ve
		- Cheap to install and expand
		- transmitting network is not affected by high traffic or by adding more nodes , as only the nodes having token can transmit data
	- -ve
		- trobuleshooting difficult
		- less fault tolerance
		- less upgradability 
- Tree :- root node and all other nodes are connected to it forming a hierarchy
- hybrid
### Use of computer network
- information and resource sharing
- retriving remote info
- speedy interpersonal communication
- E-commerce
- Cost effective system- CN have reduced cost of establishment of computer system in organisation

### Computer network services
- Directory service :- these services are mapping b/w name and its value. like DNS, accounting
- File services:- like file sharing and file transfer
- communication service
- Application service like databases , web service, resource sharing 

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

## Switching 
- technique by which nodes control or switch data to transmit it b/w specific points on a network
- types 
	- Circuit switching (connection oriented)
		- it establish dedicated path b/w sender and receiver 
		- once connection established then the dedicated path wil remain to exist until connection terminated
		- complete end to end path must exist before comm take place
		- used in public telephone network
		- +ve
			- no problem of congestion
		- -ve
			- long set up time is req
			- line may be held up for long time
	- Packet switching( connectionless)
		- data is broken into small packets with each packet having source and destin address and sequence number, travelling from one router to next router 
		- packets will travel accross the network , taking the shortest path as possible 
		- All packets are reassembled at the receiving end in correct order
		- +ve
			- Cost effective 
			- reliable
			- Efficient
		- -ve
			- cannont be implemented where low delay and high quality service required
		- types 
			- Datagram approach
			- Virtual circut switching 
	- Message switching 
		- message is transferred as complete unit and routed through intermediate nodes at which it is stored and forwareded
		- there is no establishment of dedicated path b/w the sender and receiver
		- Each and every node stores the entire message and then forward it to next node . This type is known as store and forward network
## Transmission
- communication channel that caries the infomation from sender to receiver . data is transmitted through the electromeagnetic signals 
- cause of trasmission impairment
	- Attenuation :- loss of energy
	- distortion:- there is change in shape of signal
	- noise :- some unwanted signal is added to it which create the noise
- classification of transmission 
	- guided media
		- Coaxial
		- Fibre optics
		- Twisted
			- Unshielded and shielded
	- Unguided 
		- Radiowaves used in FM, can penetrate walls , frequency from 3 Hz to 300 GHz
		- Microwaves can not penetrate walls. freq from 300 MHz to 300 GHz
		- infrared , high rate transfer , used in TV remote. freq from 300 GHz to 400 THz

## Multiplexing 
Multiplexing is a technique used in telecommunications and networking to share a single communication channel or medium for transmitting multiple signals simultaneously. It allows efficient utilization of resources and is widely used in various applications. There are several types of multiplexing, each with its unique characteristics and use cases. Here are some notes on multiplexing and its types:

1. **Multiplexing Definition**: Multiplexing is the process of combining multiple data streams or signals into a single composite signal for transmission over a shared medium and then separating them at the receiving end.

2. **Types of Multiplexing**:

   a. **Time-Division Multiplexing (TDM)**:
      - In TDM, multiple input signals take turns using the transmission medium.
      - Time slots are allocated to each signal, and data is transmitted in a round-robin fashion.
      - Commonly used in digital voice and data communication systems.

   b. **Frequency-Division Multiplexing (FDM)**:
      - FDM divides the available bandwidth into multiple frequency bands.
      - Each input signal is allocated a distinct frequency band for transmission.
      - FDM is used in radio and television broadcasting, as well as in some cable TV systems.

   c. **Wavelength-Division Multiplexing (WDM)**:
      - WDM is a variation of FDM used in optical fiber communication.
      - It utilizes different wavelengths (colors of light) to transmit multiple signals simultaneously over a single optical fiber.

3. **Advantages of Multiplexing**:

   - Efficient use of communication channels or resources.
   - Cost-effective by allowing multiple signals to share the same infrastructure.
   - Increased capacity and scalability for communication systems.
   - Support for various types of data and services.

4. **Applications**:

   - Multiplexing is used in telecommunications, including telephone networks and broadband internet.
   - Broadcasting, such as TV and radio, relies on multiplexing techniques.
   - Data centers and computer networks use multiplexing to optimize data transmission.
   - Optical networks depend on WDM for high-capacity data transmission.

5. **Challenges**:

   - Crosstalk: Signals can interfere with each other, leading to data corruption.
   - Synchronization: Precise timing is crucial in TDM and other multiplexing methods.
   - Scalability: As the number of signals increases, managing multiplexing becomes more complex.
## Network devices
1. **Hub**:
   - A hub is a basic networking device that connects multiple devices in a network.
   - It operates at the physical layer of the OSI model and simply broadcasts incoming data to all connected devices.
   - Hubs are less efficient than switches and are rarely used in modern networks due to their limited intelligence.

2. **Switch**:
   - A switch is a smarter networking device that operates at the data link layer (Layer 2) of the OSI model.
   - It uses MAC addresses to forward data only to the device that needs it, improving network efficiency.
   - Switches are widely used in local area networks (LANs) for faster and more controlled data transmission.

3. **Router**:
   - A router is a networking device that operates at the network layer (Layer 3) of the OSI model.
   - It forwards data between different networks, making decisions based on IP addresses.
   - Routers are essential for connecting multiple LANs or connecting a LAN to the internet.

4. **Bridge**:
   - A bridge is a device that operates at the data link layer (Layer 2) and connects two or more network segments to form a larger network.
   - It filters and forwards data based on MAC addresses, effectively dividing collision domains.
   - Bridges are used to segment and improve the performance of LANs.

5. **Modem**:
   - A modem (short for modulator-demodulator) converts digital data from a computer into analog signals for transmission over telephone lines (for DSL) or cable systems.
   - It also converts incoming analog signals back into digital data for the computer.
   - Modems are crucial for broadband internet and older dial-up connections.

6. **Gateway**:
   - A gateway is a device or software that connects two different networks with different communication protocols.
   - It acts as a translator, facilitating data exchange between networks that use different standards.
   - Gateways are commonly used in connecting local networks to the internet.

7. **Network Interface Card (NIC)**:
   - A Network Interface Card, or NIC, is a hardware component installed in a computer or device that allows it to connect to a network.
   - It provides the physical connection to the network medium, such as Ethernet or Wi-Fi.
   - NICs have unique MAC addresses for identification on the network and can be integrated or add-on components.
