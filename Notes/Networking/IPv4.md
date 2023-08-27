## Intro to routing
- ![[Screenshot 2023-06-07 120844.png]]
- this is a single network , note that the IP is same for all , just last digit is different 
- In this network all the host receives the frame 
- ![[Screenshot 2023-06-07 121020.png]]
- adding a router split the network into 2, now u can see both network have different initial IP , / in this represent which is network address and which part of IP is host address . here /24 means 3 part belong to network and last part is host IP
- here in this picture IP address of router is missing , so from both side it will recevive an IP , which is 192.168.1.254 and 192.168.2.254
- ![[Screenshot 2023-06-07 121412.png]]
- broadcast is limited to a single network , as u can see 
## IPv4 addresses (network portion,host portion)
- ![[Screenshot 2023-06-07 121548.png]]
## IPv4 addresses class
- ![[Screenshot 2023-06-07 121821.png]]
![[Screenshot 2023-06-07 122042 2.png]]
- Loopback Ip address:- PC is sending request to and from itself
- ![[Screenshot 2023-06-07 121922.png]]
- 
- class C can have 256 address :- out of which one is network address and one is broadcast address leaving 254 address per network
- 
## Netmask
- Imagine you have a group of friends who live in different houses on the same street. Each friend has their own address, right? Now, the netmask is like a special tool that helps you figure out which houses are on the same street.
- Think of the netmask as a mask or filter that you can put on top of the addresses to see which part of the address is important for determining the street. It's like looking through a window with holes in it that only show certain parts of the address.
- The netmask consists of a series of numbers, and each number tells you how many digits in the address are important for determining the street. Let's say the netmask is 255.255.0.0. This means that the first two parts of the address (each part separated by a dot) are important for determining the street. The last two parts can be different for each house.
- For example, let's say you have two addresses: 192.168.1.10 and 192.168.2.20. When you apply the netmask 255.255.0.0, you only look at the first two parts of the address, which are 192.168. In this case, both addresses have the same first two parts, so you know that these houses are on the same street.
- However, if you had another address like 10.0.0.5 and applied the same netmask, you would see that the first two parts (10.0) are different from the previous addresses. So, you can tell that this house is on a different street
## Network and broadcast address
- Host portion of address is all 0's = network address
- Network address cannot be assigned to host
- Host portion of the address is all 1's =Broadcast address
	- it is used to send packet to all local host in a network
## IPv4 configuration
- ![[Screenshot 2023-06-07 124211.png]]
- ![[Screenshot 2023-06-07 124936.png]]
- we need to add IP for router based on type of network it is connecting to here Class A ,B ,C network are present . so 3 IP will be set for each interface 
- command line to add Ip address ,is first the IP of interface and then the netmask

## IPv4 Header (Network layer dealing)
- ![[Screenshot 2023-06-07 133602.png]]
- Version field (length 4 bits):- identifies version of IP used . IPv4 = 4 , IPv6 = 6.
- Internet header length(length 4 bits):- final field of IPv4 header(options) is variable in length, so this field necessary to indicate total length of header . identifies length of header in 4 byte increments
	- value of 5 = 5 X 4 bytes = 20 bytes
	- minimum value is 5 = (20 bytes), without options field
- DSCP field(field length = 6):- differentiated services code point, used for quality of service. used to prioritise delay sensitive data(streaming voice,video)
- ECN field:- explicit congestion notification , length 2 bits. provides end to end (b/w to endpoints) notification of network congestion without dropping packets. normally in network if it is busy , it is shown by dropping packets
- Total length (length 16 bits ):- indicate total length of packet (L3 header + L4 segment)
	- Minimum value is 20 bytes
	- Maximum value is 65000 bits
- Identification field (length: 16 bits):- if a packet is fragmented due to being too large , this field is used to identify which packet the fragment belongs to '
	- All fragments of same packet will have their own IPv4 header with same value in this field (means the identification field)
	- Fragment if it is larger than MTU (maximum transmission unit) , MTU is usually 1500 bytes
- Flags field:- Used to control/identify fragments
	- Bit 0:- reserved , always set to 0
	- Bit 1 :- Dont fragment (DF bit), used to indicate a packet that should not be fragmented
	- Bit 2:- More fragments (MF bit), set to 1 if there are more fragments in the packet set to 0 for the last fragment
	- Unfragmented packets will always have their MF bit set to 0
- Fragment offset field (length 13 bits):- used to indicate the position of fragment within the original, unfragmented IP packet 
	- Allows fragmented packets to be reassembled even if the fragments arrive out of order
- TTL (length : 8 bits):- a router will drop packet with a TTL of 0
	- used to prevent infinite loops
	- Originally designed to indicate the packet maximum lifetime in seconds 
	- In practice , indicate a 'hop count':- each time the packet arrives at router , the router decrease the TTL by 1
- Protocol field (length : 8 bits):- indicates the protocol of encapsulated L4 PDU
	- Value of 6 :- TCP
	- Value of 17 :- UDP
	- Value of 1 :- ICMP
	- Value of 89 :- OSPF (dynamic routing protocol)
- Header checksum field (length : 16 bits):- calculated checksum , used to check for error in the IPv4, when router receives a packet , it calculates the checksum of header and compare it to the one in this field of header , if they do not match , router drops the packet
	- used only to check error in IPv4 header , not the encapsulated data
- ![[Screenshot 2023-06-08 043641.png]]
- use `ping (ip address) size (how many bytes)`\
- ![[Screenshot 2023-06-08 043938.png]]
- use `ping (ip address) df-bit` to avoid fragmentation of packet