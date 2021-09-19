### IP Routing

The term IP routing refers to the process of taking a packet from one host and sending it to another host on a different network. The routing process is the usually done by devices called routers. You probably have this device at home, providing you with the Internet access.

Routers examine the destination IP address and make their routing decisions accordingly. To determine out which interface the packet will be forwarded, routers use routing tables which list all networks for which routes are known. Consider the following example:

 <p align="center">   
 <img src="https://i.imgur.com/lBF6qqp.jpg"/>
 </p>

Networks in the internet are connected to each other via routers. Routers carry traffic from one network/subnet to another. Routers maintain a routing table to decide how to route the IP packets. Each routing entry consists of the destination address, subnet mask and "route to" field. When a message needs to be routed to an IP address, the following steps are followed:

1. The destination IP address is masked with the subnet mask and then compared with the destination field for all entries in the routing table.

2. This comparison may yield a match with more than one entry the entry with the longest subnet mask will be selected. E.g. , a packet destined for 128.8.1.2 reaching Host A would match the entries corresponding to 128.8.1.2 and 128.8.0. The entry corresponding to 128.8.1.2 will be selected, as it has a longer subnet mask.

3. Once an entry has been selected, the "route to" field is consulted and the action taken depends on the contents of this field:

* If the "route to" field contains SELF the packet is meant for this node. The IP packet is passed to the OS for application processing
* If the "route to" field contains a LAN interface id, the packet is destined for a LAN that is directly connected to the router/host. In this case, the packet is routed directly on the LAN.
* If the "route to" field contains an IP address, the packet is forwarded to the IP address specified. Further routing of the packet will be carried out by the specified IP address.

Note:

* IP routing also supports a default entry. If the packet does not match any other entry, it is routed according to the default entry and the router drop the packet.

 <p align="center">   
 <img src="https://i.imgur.com/HGKDAJX.gif"/>
 </p>
 
#### Multiple IP Addresses:

Another important aspect of internets is a node in the internet can have multiple IP addresses. There will be one IP address per interface. For example, the Router in the figure above has three IP addresses, viz. 128.8.1.1, 128.9.1.1 and 128.9.2.1.

#### Routing of a Packet from Host A to Host C:

Here we will trace the path taken by an IP packet sent from Host A to Host C. Routing related fields in the Ethernet MAC header and IP header are shown.

#### Host A originates an IP packet towards Host C:

1. Application sends a message to Host C by sending it to 128.9.2.2 IP address (Host C's IP address).
2. This IP address matches the entry corresponding to 128.9.0.0. The "route to" field for the selected entry contains another IP address - 128.8.1.1. This is the IP address of the Router.
3. The IP routing table is accessed again for 128.8.1.1.
4. The entry that matches 128.8.1.1 contains LAN 0 interface id. This specifies that the destination node is directly connected to the host.
5. This packet is passed to the device driver.
6. Device driver consults the ARP cache to identify the Ethernet MAC address corresponding to the 128.8.1.1. (ARP is covered in another article).
7. Ethernet frame is sent to the MAC address found by ARP.

The packet sent on the 128.8 LAN is:
<p align="center">   
 <img src="https://i.imgur.com/lT8eZRu.png"/>
 </p>

Router send the IP packet to Host C

1. Router receives the Ethernet frame and passes it to the IP layer.
2. IP routing table is consulted and a matching entry is found corresponding to 128.9.2 subnet.
3. Packet is routed on the LAN 2 interface.
4. Host C's MAC address is found from the ARP cache.
5. Ethernet frame is addressed to Host C MAC Address.

The packet sent over the 128.9.2 LAN is:

<p align="center">   
 <img src="https://i.imgur.com/lbJZUj9.png"/>
 </p>
#### Host C receives the IP packet

Host C receives the Ethernet frame and passes it to the IP layer.
IP routing table is searched and a match is detected with 128.9.2.2 entry.
The "route to" field contains SELF, so the message is passed to the higher layer for delivery to the application.

### Assessment: Quiz

IP routing is done at which layer of OSI model?
 - [ ] Layer 1
 - [ ] Layer 2
 - [x] Layer 3
 - [ ] Layer 4

You have received a packet from R2 which do not match to get to its destination, what will the router do?
 - [x] Drop the packet
 - [ ] Broadcast the packet
 - [ ] Unicast the packet
 - [ ] Anycast the packet

From how IP routing protocol enable router to send packets to its destinations?
 - [ ] By its MAC table
 - [x] By its routing table
 - [ ] By its Routed table
 - [ ] None
