
- Each interface has a separate MAC address, 
- As PC 1 does not know the MAC of its default  gateway , it will give the ARP request
- when it knows the MAC of R1 it attach eth.header with destination MAC of R1 and send the data to it for further processing
- When R1 receive it, it remove the eth. header, and looks up destination in routing table
- now R1 does the same thing done by PC1 while communicating with R1 , to R3
- , switch do not decapsulate or encapsulate data in this topology.