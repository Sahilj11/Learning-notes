## What is routing
- process used by routers to determine the path IP packets should take over a network to reach their destination
- router store routes to all their known destination in routing table
- when routers receive packets , they look into routing table to find the best route to forward that packet
- there are two main routing methods (methods that router use to learn routes)
	- Dynamic routing :- routers use dynamic routing protocol (OSPF) to share routing info with each other automatically and build their routing tables
	- Static routing :- when admin manually configures routes on router
- route tells the router 
	- to send a packet to destination X , you should send the packet to next hop(the next router in the path to destination)Y
	- if destination is directly connected to router , send to the destination
	- if destination is router own IP , recieve it yourself (dont forward it)


## routers table
- ![[Screenshot 2023-06-08 045254.png]]
- ![[Screenshot 2023-06-08 045413.png]]
- ![[Screenshot 2023-06-08 045047.png]]
- 
## Static routing
- ![[Screenshot 2023-06-08 050847.png]]
-  ![[Screenshot 2023-06-08 052053.png]]
- here you can see each router is been set for both source and destination IP, this is to ensure two-way reachability this is important as if receiver is not able to send the response to sender then communication will not be completed
### Default route
- ![[Screenshot 2023-06-08 052717.png]]
- 

### Default gateway
- ![[Screenshot 2023-06-08 050517.png]]
- default gateway is just an alternative term for router
- here you can see that destination MAC is of R1 router , this reinforce the earlier information that to send packets to destination outside of their local network , they must send the packet to their default gateway

## Traveling of packet
- ![[Screenshot 2023-06-08 052410.png]]
- The reason the destination MAC address is set to that of the next-hop router, rather than the ultimate destination device, is because of the way Ethernet-based networks operate at the data-link layer.
- When a device sends a packet over an Ethernet network, it constructs an Ethernet frame that encapsulates the packet. The Ethernet frame contains both the source MAC address and the destination MAC address.
- Ethernet operates based on MAC addresses, which are unique identifiers assigned to each network interface. When a device wants to send data to another device within the same local network (same subnet), it uses the destination device's MAC address directly in the Ethernet frame.
- However, when the destination device is located on a different network (different subnet), the sender's device needs to send the packet to the appropriate router that will forward it towards the destination. The router is responsible for routing the packet between different networks.
- To accomplish this, the sender's device sets the destination MAC address in the Ethernet frame to the MAC address of the next-hop router. The sender's device determines the MAC address of the router by performing an Address Resolution Protocol (ARP) request, which resolves the router's IP address to its MAC address.
- By setting the destination MAC address to that of the next-hop router, the Ethernet frame is delivered to the router, which examines the packet's IP destination address, performs its own routing decisions, and repeats the process of determining the next-hop router's MAC address until the packet reaches the ultimate destination device.
- In summary, the destination MAC address is set to that of the next-hop router because routers play a critical role in interconnecting different networks, and the Ethernet frame needs to be delivered to the appropriate router for further routing towards the ultimate destination device.