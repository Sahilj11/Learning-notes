## Define 
- Dynamic routing is a network routing technique where routers exchange routing information with each other in order to dynamically update and maintain routing tables. It allows routers to automatically discover and select the best paths for forwarding network traffic based on real-time network conditions.
- In a dynamic routing environment, routers use routing protocols such as Routing Information Protocol (RIP), Open Shortest Path First (OSPF), Border Gateway Protocol (BGP), and Intermediate System to Intermediate System (IS-IS) to exchange routing information. These protocols enable routers to share information about network reachability, network topology, and the best available paths to different destinations.

## Network Route / Host route
- A route to a network / Subnet (mask length </32)
- [[Routers#routers table]] 
- Host route :- route to a specific host (/32 mask)

## Dynamic vs static
- ![[Screenshot 2023-06-09 053912.png]]
- here R4 is advertising itself to other router 
- you can see that in routing table entry is been added
- if R4 interface gets damaged , R2 will stop sending traffic to this interface in case of dynamic routing , but in case of static routing this will not happen
![[Screenshot 2023-06-09 054228.png]]

## Dynamic routing protocol types 
- Interior gateway protocol 
	- Used to share routes within a single autonomous system , which is a single organisation 
- Exterior Gateway protocol
	- used to share routes b/w different autonomous system
- ![[Screenshot 2023-06-09 054516.png]]
- 
- 
## IGP/EGP algorithm types 
- algo means to share routing info and select the best route for each destination
- ![[Pasted image 20230609133812.png]]
- ![[Pasted image 20230609134119.png]]
- ![[Pasted image 20230609134206.png]]
- ![[Pasted image 20230609134306.png]]
## Metric 
- ![[Pasted image 20230609134417.png]]
- ![[Pasted image 20230609134510.png]]
- ECMP stands for Equal-Cost Multi-Path. It is a routing technique used in computer networks to distribute traffic evenly across multiple paths that have the same cost or metric. ECMP allows for efficient load balancing and improved network performance by utilizing multiple parallel paths simultaneously.
- In traditional routing, when multiple paths are available to reach a destination with equal cost, only one path is selected based on the routing algorithm's decision. However, with ECMP, the routing algorithm can distribute traffic across all available paths, rather than selecting a single best path. This enables better utilization of network resources and increased throughput.
- this can also be done in static routes
- ![[Pasted image 20230609134809.png]]
- ![[Pasted image 20230609135248.png]]
- here RIP use hop count , to communicate b/w R4 and R1 , as hop count is similary so 2 path. OSPF takes into consideration bandwidth which G has more

## Administrative Distance 
- ![[Pasted image 20230609135454.png]]

## Floating Static Routes
- Floating static routes, also known as backup static routes or floating static default routes, are a routing configuration technique used to provide redundancy and failover in computer networks. They are typically used as a backup option when the primary routes become unavailable or unreachable.
- In a network, static routes are manually configured routes that define how traffic should be forwarded from one network to another. Each static route has an associated administrative distance, which is a value that determines the priority of the route. When multiple routes exist to reach the same destination, the route with the lowest administrative distance is preferred.
- Floating static routes work by configuring a secondary static route with a higher administrative distance compared to the primary route. The secondary route is only used when the primary route becomes unavailable or fails. This allows for automatic failover to the backup route without manual intervention.