### IP addressing: Network mask

* A network mask helps you know which portion of the address identifies the network and which portion of the address identifies the node. Class A, B, and C networks have default masks, also known as natural masks, as shown here:
Class A: 255.0.0.0
Class B: 255.255.0.0
Class C: 255.255.255.0
An IP address on a Class A network that has not been subnetted would have an address/mask pair similar to: 8.20.15.1 255.0.0.0. In order to see how the mask helps you identify the network and node parts of the address, convert the address and mask to binary numbers.
8.20.15.1 = 00001000.00010100.00001111.00000001
255.0.0.0 = 11111111.00000000.00000000.00000000
Once you have the address and the mask represented in binary, then identification of the network and host ID is easier. Any address bits which have corresponding mask bits set to 1 represent the network ID. Any address bits that have corresponding mask bits set to 0 represent the node ID.
8.20.15.1 = 00001000.00010100.00001111.00000001
255.0.0.0 = 11111111.00000000.00000000.00000000
-----------------------------------
net id | host id

netid = 00001000 = 8
hostid = 00010100.00001111.00000001 = 20.15.1

* The following table summarizes the hosts and networks for the different classes of address:
 <p align="center">   
 <img src="https://i.imgur.com/0ORfOYy.jpg"/>
 </p>
 

### Understanding subnet

Subnetting allows you to create multiple logical networks that exist within a single Class A, B, or C network.
If you do not subnet, you are only able to use one network from your Class A, B, or C network, which is unrealistic.
Each data link on a network must have a unique network ID, with every node on that link being a member of the same network. If you break a major network (Class A, B, or C) into smaller subnetworks, it allows you to create a network of interconnecting subnetworks. Each data link on this network would then have a unique network/subnetwork ID. Any device, or gateway, that connects n networks/subnetworks has n distinct IP addresses, one for each network / subnetwork that it interconnects.

In order to subnet a network, extend the natural mask with some of the bits from the host ID portion of the address in order to create a subnetwork ID. For example, given a Class C network of 204.17.5.0 which has a natural mask of 255.255.255.0, you can create subnets in this manner:

204.17.5.0 - 11001100.00010001.00000101.00000000
255.255.255.224 - 11111111.11111111.11111111.11100000
--------------------------|sub|----

By extending the mask to be 255.255.255.224, you have taken three bits (indicated by "sub" ) from the original host portion of the address and used them to make subnets. With these three bits, it is possible to create eight subnets(2^3). With the remaining five host ID bits, each subnet can have up to 32(2^5) host addresses, 30 of which can actually be assigned to a device since host ids of all zeros or all ones are not allowed (it is very important to remember this). So, with this in mind, these subnets have been created

204.17.5.0 255.255.255.224 host address range 1 to 30
204.17.5.32 255.255.255.224 host address range 33 to 62
204.17.5.64 255.255.255.224 host address range 65 to 94
204.17.5.96 255.255.255.224 host address range 97 to 126
204.17.5.128 255.255.255.224 host address range 129 to 158
204.17.5.160 255.255.255.224 host address range 161 to 190
204.17.5.192 255.255.255.224 host address range 193 to 222
204.17.5.224 255.255.255.224 host address range 225 to 254

### Assessment: Quiz
For the Class A , the number of the network bits equal to
- [x] 8
- [ ] 16
- [ ] 24

we have this mask 255.128.0.0 belongs to class a so how many subnets and hosts per subnet we have ?
- [ ] 2 subnet with 16,777,214 hosts each
- [x] 2 subnet with 8,388,606 hosts each
- [ ] 1 subnet with 16,777,214 hosts
===========

#LINK
* [IP addressing](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)
