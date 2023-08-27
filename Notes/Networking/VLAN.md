## LAN
- a single broadcast domain including all devices in that broadcast domain
- broadcast domain is the group of devices which will receive a broadcast frame = destination MAC FFFF.FFFF.FFFF sent by any one of the members
- important thing to note that router do not forward broadcast frame
- ![[Screenshot 2023-06-08 101857.png]]
- here you can see that R1 and R2 also make broadcast domains . hence there are 4 LANs here

## VLAN
- Switches are not aware of Layer 3 or 4 , they only know layer 2
- are configured on switches on per interface basis . logically separate end hosts at Layer 2
- An access port is a switch port which belong to single VLAN and usually connects to end hosts like PC
- switch ports which carry multiple VLAN are called trunk ports
- ![[Screenshot 2023-06-08 103958.png]]
- this is not the best network as if the PC in engineering dept wants to send message to Sales PC . then the message will be broadcasted to all 
	- ![[Screenshot 2023-06-08 104205.png]]
- Lets divide the network into subnets
	- ![[Screenshot 2023-06-08 104254.png]]
	- router need IP of each subnet so it will need each subnet in its interface ,
- ![[Screenshot 2023-06-08 104421.png]]
- sending data , notice the destination MAC address
- ![[Screenshot 2023-06-08 104431.png]]
- Notice the source and destination MAC address
- ![[Screenshot 2023-06-08 104439.png]]
- But in above case the sender knows the destination MAC , what if the eth. frame not contain the destination MAC (FFFF.FFFF.FFFF)
- ![[Screenshot 2023-06-08 104744.png]]
- ![[Screenshot 2023-06-08 104753.png]]
- One solution is to buy 3 switches but it will be expensive 
- other solution is VLAN
- ![[Screenshot 2023-06-08 105300.png]]
- how do we assign them VLAN, we configure it on switch, more specifically on switch interfaces , configur switch interface on specific VLAN and end host connected to that interface is part of that VLAN. switch consider each VLAN as sepearate LAN and will not forward traffic b.w VLAN including broadcast/unknown unicast traffic
- ![[Screenshot 2023-06-08 105627.png]]
- above picture showing how broadcast frame been limited to VLAN10
- ![[Screenshot 2023-06-08 105658.png]]
- ![[Screenshot 2023-06-08 105716.png]]
- ![[Screenshot 2023-06-08 105810.png]]
- switch never forward traffic b/w VLAN directly 
- even if PC1 and PC2 were in same subnet but differenet VLAN switch would not transfer traffic directly though it
## trunk port
- ![[Screenshot 2023-06-08 111228.png]]
- above is using access port, HR PC wants to send message to PC in engineering , it first go to switch 2  then request goes to router from router to sw2 
- ![[Screenshot 2023-06-08 111116.png]]
- ![[Screenshot 2023-06-08 111852.png]]
- ![[Screenshot 2023-06-08 112108.png]]
- now how will SW1 will know which VLAN does the message belong to , as one interface is connected to multiple VLAN (in this case it is VLAN 30 and VLAN 10)
- ![[Screenshot 2023-06-08 112231.png]]
- ![[Screenshot 2023-06-08 112251.png]]
## VLAN Tagging
- 2 main trunking protocols :- ISL(inter-switch Link. it was used in old cisco equipment now redundant) and IEEE 802.1Q(dot1q)
- ![[Screenshot 2023-06-08 112735.png]]
- ![[Screenshot 2023-06-08 112757.png]]
- TPID :- 16 bits (2 bytes ) in length
	- always set to a value of 0x8100 (0x = hexa). this indicate that frame is 802.1Q tagged
	- when switch sees 8100 it knows it is a 802.1Q tagged
- Tag control information (TCI):- 
	- Priority code point (PCP):- 3 bits in length, used for class of service(CoS), which prioritize important traffic in congested network
	- Drop eligible indicator(DEI):- 1 bit in length, used to indicate frames that can be dropped if the network is congested
	- VLAN ID:- 12 bits in length, identified the VLAN the frame belongs to 

## VLAN Ranges
- Range of VLAN (1-4094) is divided into two section
	- normal VLAN :- 1-1005
	- Extended VLAN :- 1006-4094 (some older switches might not support extended range)
## Native VLAN
- ![[Screenshot 2023-06-08 121927.png]]
- A native VLAN (Virtual LAN) is a concept in computer networking that refers to a VLAN that is configured on a trunk port of a switch but is not tagged with a VLAN ID. Trunk ports are used to carry traffic for multiple VLANs between switches.
- ![[Screenshot 2023-06-08 122045.png]]
- ![[Screenshot 2023-06-08 122111.png]]
- ![[Screenshot 2023-06-08 122137.png]]
- best practice is to set native VLAN to an unused VLAN , as there are some security issue
- Wireshark capture ( SW2 -> R1):- 
	- ![[Screenshot 2023-06-08 123551.png]]
	- echo request is been sent to R1 for inter VLAN routing
	- ![[Screenshot 2023-06-08 123603.png]]
	- Type :- 802.1Q added, and VLAN ID is mention (this tells that the pc is not the native VLAN)
- Wireshark (R1 -> SW2 )
	- ![[Screenshot 2023-06-08 123426 1.png]]
	- VLAN 10 is configured as native in both R1 and SW2 
	- ![[Screenshot 2023-06-08 123504 1.png]]
	- here you can see in Type , no 802.1Q tag.
	- ![[Screenshot 2023-06-08 123936 2.png]]
	- from there on it will reach PC in VLAN10 without the VLAN tag
## Multilayer switch
- ![[Screenshot 2023-06-08 124051.png]]
- a multilayer switch is capable of both switching and routing
- it is Layer 3 aware :- means you can assign IP address to its interfaces like a router
- It can be used for inter VLAN routing
- SVI (switch virutal interfaces) are virtual interfaces you can assign IP addresses to in a multilayer switch
- configure each PC to use the SVI as their gateway address
