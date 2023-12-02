## What is ACL

- ![](../statics/Pasted%20image%2020230610055000.png)
- ![](../statics/Pasted%20image%2020230610055110.png)
- ![](../statics/Pasted%20image%2020230610055843.png)
- Inbound ACL: An inbound ACL is applied to incoming traffic on an interface of a network device, such as a router or firewall. It determines what traffic is allowed to enter the network or device from external sources. Inbound ACLs are commonly used to enforce security policies, restrict access to specific services or hosts, or filter traffic based on IP addresses, protocols, ports, or other criteria. By configuring an inbound ACL, you can control the traffic coming into your network and protect it from potential threats or unauthorized access.
- Outbound ACL: An outbound ACL, on the other hand, is applied to outgoing traffic leaving an interface of a network device. It controls the traffic leaving the network or device and determines what is allowed to reach external destinations. Outbound ACLs are often used to enforce security policies, regulate the types of traffic allowed to leave the network, or apply traffic shaping or quality of service (QoS) rules. They can be used to filter outgoing traffic based on IP addresses, protocols, ports, or other criteria, providing control and customization over the flow of data leaving your network
- In above picture an issue is shown with ACL . as PC3 ping a IP means that traffic is entering G0/2 not exiting so it wont even check the ACL. and when reponse come from SRV1 . source IP already change and PC3 allowed to access server 1
- ![](../statics/Pasted%20image%2020230610060429.png)
- Now lets change the interface to Inbound. but here the issue is as the ACL says the if src IP is there IP itself . not allowed to leave network . so there cannot communicated to any of the host outside network
- ![](../statics/Pasted%20image%2020230610061719.png)
- ![](../statics/Pasted%20image%2020230610062005.png)
- although in above picture source IP is allowed in ACE but order of ACE is an issue. first entry is deny so it deny
- ![](../statics/Pasted%20image%2020230610062228.png)
- ![](../statics/Pasted%20image%2020230610062310.png)
- ![](../statics/Pasted%20image%2020230610062457.png)
- ![](../statics/Pasted%20image%2020230610063002.png)
- ![](../statics/Pasted%20image%2020230610063520.png)
- here the 0.0.0.255 represent the wildcard mask :- A wildcard mask is a mask of bits that indicates which parts of an IP address are available for examination.

## Extended ACL

-
