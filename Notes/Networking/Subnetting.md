
## CIDR
- why was CIDR introduced
	- to avoid IP address wastage 
	- for example lets say a company need IP to host 5000 end devices , here class C wont work as it allows only 254 devices , so it needs to get class B , but in class B we can connect 65,000 end device. this means 60,000 IP gets wasted
- the requirement of Class A = /8, Class B = /16 , Class C = /24 were removed 
- Allowed larger network to be split into smaller network , allowing greater efficiency 
- these smaller network are called subnetworks or subnets
- netmask represent the network portion
- CIDR allow us to use different prefix length(subnet mask), here we are trying to find the subnet mask which is closest to our host ip need, which is 2 in above example for each network
	- like /25 , 
		- in this case netmask will be 255.255.255.128 (1 bit of last octet part of network portion)
		- as it shows that 7 bits are available for generating host IP address
		- apart from last 7 bits , all other bits are 1 in netmask
		- here if we see the possible IP for host it is 126 usable address(2^7 - 2)
	- /26 , 
	- /27 ,
	- /28 , 
	- /29 , 
	- /30, 
		- it contains IP range in IP alloted 203.0.113.0 is = 203.0.113.0 - 203.0.113.3 . remaining address block (203.0.113.4 - 203.0.113.255) are now available to be used in other subnets
	- /31 ,
		- it allow 0 usable addreess . but it can be used in point to point connection
	- /32
- One practice problem to understand subnets
	- Find the subnets address of given subnets
		- here the network address is 19.168.1.0/24. means that we can have 256 IP
		- now first subnet has netmask of /26 , means that it has last 6 bits for host portion. which gives us 64 IPs 
			- this is the range of subnet in the network 192.168.1.0
			- 192.168.1.0-192.168.1.63
		- 2nd subnet network address is 1+ of broadcast address of 1st subnet which is 192.168.1.63. so the network address of 2nd subnet is 192.168.1.64
		- interesting obersvation in this problem is that the network portion bits(which is 2 in this case) in last octet can have 4 possible combination(which is also the number of subnets it can support)
			- All possible arrangement of bits in network portion are 
				- 0 0 :- 192.168.1.0
				- 0 1:- 192.168.1.64
				- 1 0 :- 192.168.1.128
				- 1 1:- 192.168.1.192
			- you can see here that every subnet is get by adding 64 (which is also the last bit value (64, which is thru 2^)in network portion of last octet)
### Finding Subnet thru host address
- host address is 192.168.5.57/27
	- which in binary in last octet 00111001 (each bit value in decimal system is 1,2,4,8,16,32,64,128. if we add decimal number which is at 1s place , we get 57), as it has /27 netmask so the first three bits are part of network portion
	- **001 :- now by converting the 1s bit into number we get 32(remember the table which tells what each bit in byte represent . it is 1,2,4,8,16,32,64,128 {here the first number is one because 2^0 is 1 as in computer we start counting with 0})** 
![[WhatsApp Image 2023-06-08 at 08.21.18.jpg]]

## Subnetting Class B network
- given network is 172.16.0.0/16. here asked to create 80 subnets , what will be the prefix length
- ![[Screenshot 2023-06-08 083622.png]]
- here the subnet will starting from left most bit allowed for hosting according to the class netmask
- start moving from left to right to a point where you get requried subnet
- you can also extend the subnet network portion to last octet ![[Screenshot 2023-06-08 092918.png]]
- ![[Screenshot 2023-06-08 093338 1.png]]
- ![[Screenshot 2023-06-08 093359.png]]
- 

## Point to point network
- look in Chatgpt

## Variable-Length Subnet masks
- Until now we subnetting was thru Fixed length subnet masks
- means that all of subnets use the same prefix length (ie subnetting a class C network into 4 subnets using /26)
- VLSM is process of creating subnets of differnet size to make your use of network addresses more efficient
- it allows to assign custom amount of host to each subnet rather than same to all , as was the case in FLSM
- ![[Screenshot 2023-06-08 100951.png]]
- 
- Steps(you can see that subnet mask is not same accross various subnet)
	- assign the largest subnet at start of address space
		- ![[Screenshot 2023-06-08 100136.png]]
		- ![[Screenshot 2023-06-08 100746.png]]
		- as tokyo is the largest subnet so first address to this is provided, using the same method before
	- assign the second largest subnet after it 
		- now toronto LAN B is the second largest
			- ![[Screenshot 2023-06-08 100602.png]]
			- ![[Screenshot 2023-06-08 100615 1.png]]
			- 
	- repeat the process until all subnet have been assigned
	- 