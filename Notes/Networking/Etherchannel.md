## Why it is needed
- ![[Screenshot 2023-06-09 044830.png]]
- admin notice that network congerstion is there due to over request from host , so he add another link from ASW1 to DSW1
- When the bandwidth of interface connected to end host is greater than the bandwidth of connection to the distribution switches , this is called oversubscription. Some oversubscription is acceptable , but too much will cause congestion
- ![[Screenshot 2023-06-09 045316.png]]
- Dispite multiple connected congestion is still there , due to STP . 

## Ether channel 
- etherchannel groups multiple interfaces together to act as a single interface 
- STP will treat this group as single interface
- ![[Screenshot 2023-06-09 051706.png]]
- ![[Screenshot 2023-06-09 051711.png]]
- alternative name for etherchannel are Port channel , Link aggregation group
- Upto to 8 interfaces can be formed into single Etherchannel (LACP (link aggregation control protocol) allows up to 16, but only 8 will be active , the other 8 will be in standby mode , waiting for an active interface to fail)
- LACP :- method of etherChannel configuration
- ![[Screenshot 2023-06-09 052601.png]]
- 