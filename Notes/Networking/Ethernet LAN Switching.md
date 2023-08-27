## LAN
- Router used to connect separate LANs , switches do not separate LAN as the case in 2nd because the switches are connected to each other, 
- ![[Screenshot 2023-06-07 080406.png]]
- Ethernet protocol is used in data link layer in virtually every LAN that exist today

## Ethernet
- Ethernet is a widely used networking protocol that defines the rules and specifications for transmitting data over a wired local area network (LAN). It is the most common method for connecting computers and other devices in a network, such as printers, routers, and switches.
- The Ethernet protocol specifies the physical and data link layers of the networking stack. It defines the electrical and mechanical characteristics of the cables and connectors used, as well as the signaling methods for transmitting data packets. Ethernet uses a bus or star topology, where multiple devices are connected to a central hub or switch.
- The Ethernet protocol also governs how data is packaged into frames and transmitted over the network. It specifies the frame structure, including fields for the source and destination MAC addresses, as well as a type or length field to identify the higher-level protocol being carried (such as IP or ARP). It also defines the rules for collision detection and collision avoidance in shared media networks.
- Ethernet has evolved over time to support higher data rates and different physical media types. The most common Ethernet standard today is Gigabit Ethernet (IEEE 802.3ab), which provides data rates of up to 1 gigabit per second (Gbps) over twisted-pair copper cables. Other variants include Fast Ethernet (IEEE 802.3u) and 10 Gigabit Ethernet (IEEE 802.3ae), which offer faster speeds.
- Ethernet is a fundamental technology in modern computer networks and is used in various settings, from small home networks to large enterprise networks. It provides a reliable and efficient means of transmitting data between devices, enabling communication and data sharing in local networks and connection to the wider internet
## Ethernet Frame (maximum size of the frame is 1500 bytes)
- ![[Screenshot 2023-06-07 080741 1.png]]
### Eth. Header
- Preamble and SFD(not included in header):- 
	- Preamble: The preamble is a sequence of alternating 0s and 1s that precedes the actual data in an Ethernet frame. It consists of 7 bytes (56 bits) and is used for synchronization and timing purposes. The purpose of the preamble is to allow the receiving device to synchronize its internal clock with the incoming data stream.
		- By transmitting a predictable pattern of 0s and 1s in the preamble, the receiving device can detect the start of an Ethernet frame and adjust its clock accordingly. This synchronization ensures that the receiving device can accurately interpret the incoming bits and properly process the subsequent data in the Ethernet frame.
	- Start Frame Delimiter (SFD): The SFD immediately follows the preamble in an Ethernet frame. It is a specific bit pattern that marks the end of the preamble and signals the beginning of the actual data within the frame.
		- The SFD consists of a fixed pattern of 8 bits, which is usually the value 10101011 (hexadecimal 0xAB). The SFD acts as a delimiter, separating the synchronization preamble from the data payload. When the receiving device detects the SFD, it knows that the subsequent bits represent the Ethernet frame data.
	- Together, the preamble and SFD in an Ethernet frame enable the synchronization of the receiving device's clock with the incoming data stream and indicate the start of the actual data within the frame. This synchronization ensures reliable and accurate transmission and reception of Ethernet frames in a network environment.
- Destination MAC address:- where the message is been sent
- Source MAC address:- sender
	- ![[Screenshot 2023-06-07 081555.png]]
- Type:- indicate the layer 3 protocol used during encapsulation mostly it is IP (IPv4 or IPv6)
- ![[Screenshot 2023-06-07 081719.png]]
### Eth. Trailer
- Frame Check sequence:- 
	- ![[Screenshot 2023-06-07 082000.png]]

## MAC Address
- ![[Screenshot 2023-06-07 082218.png]]
- In a MAC (Media Access Control) address, each digit represents 4 bits
- Since each hexadecimal digit represents 4 bits, and there are two digits in each group, the total number of bits represented by a MAC address is 4 bits/digit × 2 digits/group × 6 groups = 48 bits.
- For example, a MAC address like "00:1A:2B:3C:4D:5E" represents a total of 48 bits
- ![[Screenshot 2023-06-07 093402.png]]
- here the switch is storing the mac of sender in a table dynamically (as it was not manually entered during setting up switch), here dictionary is created with interface (ports) . you can also clear MAC address from the switch using CLI
- ![[Screenshot 2023-06-07 093646.png]]
- when switch not have entry of mac adrress then it sends the frame to all devices. switch only adds source address 
- dynamic MAC addresses are remove after some inactivity time

## Eth frame more
- ![[Screenshot 2023-06-07 093207.png]]
- ![[Screenshot 2023-06-07 094300.png]]
- Eth frame includes these , here you can see sender does not know receiver MAC address, so how does sender will know the MAC address 
- it use ARP :- address resolution protocol

## Address resolution protocol
- ARP is used to discover the layer 2 address (MAC address) of a known Layer 3 address (IP address)
- Consists of two messages: - ARP request , ARP reply 
- ARP request is broadcast:- sent to all hosts on network
- ARP reply is unicast:- sent only to one host (host that sent the request)
- ![[Screenshot 2023-06-07 094912.png]]
- ![[Screenshot 2023-06-07 095050.png]]
- here you can see the Src and Dst IP are reversed and now receiver became sender
- when the ARP reply reach the original sender it store the MAC address of sender in ARP table
- ARP table :- stored in a PC to store accosication b/w IP address and MAC address . use `arp -a` in Cmd to see this table

## Ping 
- a network utility that is used to test reachability 
- Measures round-trip time
- Use two messages :- ICMP Echo request(this is not broadcasted as was the case in ARP request , but is send to specific host. it has to know the mac address of receiving host. this is why ARP must be used first) and ICMP Echo reply 
- Command to use ping:- ping (ip-address)
- Use ping 255.255.255.255 for broadcast ping
- ![[Screenshot 2023-06-07 100823.png]]
- . represent failed and ! represent reached request. first failed because MAC address was not available , ARP is used to know this 
- here 5 request was given
- ![[Screenshot 2023-06-07 101006.png]]
- screen shot of wireshark of above case