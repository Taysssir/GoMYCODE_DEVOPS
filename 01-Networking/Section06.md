### Network Service : NAT

#### Network Address Translation (NAT)
To access the Internet, one public IP address is needed, but we can use a private IP address in our private network. The idea of NAT is to allow multiple devices to access the Internet through a single public address. To achieve this, the translation of private IP address to a public IP address is required(registered on the internet). Network Address Translation (NAT) is a process in which one or more local IP address is translated into one or more Global IP address and vice versa in order to provide Internet access to the local hosts. Also, it does the translation of port numbers i.e. masks the port number of the host with another port number, in the packet that will be routed to the destination. It then makes the corresponding entries of IP address and port number in the NAT table. NAT generally operates on router or firewall.

How does Network Address Translation (NAT) work ?

Generally, the border router is configured for NAT i.e the router which has one interface in local (inside) network and one interface in the global (outside) network. When a packet traverse outside the local (inside) network, then NAT converts that local (private) IP address to a global (public) IP address. When a packet enters the local network, the global (public) IP address is converted to a local (private) IP address.
If NAT run out of addresses, i.e., no address is left in the pool configured then the packets will be dropped and an Internet Control Message Protocol (ICMP) host unreachable packet to the destination is sent.

 <p align="center">   
 <img src="https://i.imgur.com/Im6BORB.jpg"/>
 </p>

Note:

* 10.0.0.[1..3] is a private :@IP not registered publicly .
* 66.94.234.13 is a public @IP adress registred on the internet.

#### Network Service Port Forwarding

A port forward is a way of making a computer on your home or business network accessible to computers on the internet, even though they are behind a router. It is commonly used in gaming, security camera setup, voice over ip, and downloading files. After you have forwarded a port you are said to have an open port.
A Port is a logical connection that is used by programs and service to exchange information.
Example: Your friend is going to connect your Desktop using RDC (Remote Desktop Connection)

* Without any port forwarding , your router does not know what to do with this request.
* we are going to tell our router to send or forward any requests that come in the port (8080 for example ) and send the request to our computer.
* we need to log into the router’s configuration page by typing the router’s internal @IP. Address using q web browser.

A Port is a logical connection that is used by programs and service to exchange information
<p align="center">   
 <img src="https://i.imgur.com/lFjxIxq.png"/>
 </p>

Note:

* 66.94.234.13 ⇒ Public IP adress
* 8080 ⇒ Port Number

#### Network Service : DHCP

Definition : DHCP stands for dynamic host configuration protocol and is a network protocol used on IP networks where a DHCP server automatically assigns an IP address and other information to each host on the network so they can communicate efficiently with other endpoints.

In addition to the IP address, DHCP also assigns the subnet mask, default gateway address, domain name server (DNS) address and other pertinent configuration parameters. Request for comments (RFC) 2131 and 2132 define DHCP as an Internet Engineering Task Force (IETF)- defined standard based on the BOOTP protocol.
DHCP simplifies IP address management

The primary reason DHCP is needed is to simplify the management of IP addresses on networks. No two hosts can have the same IP address, and configuring them manually will likely lead to errors. Even on small networks manually assigning IP addresses can be confusing, particularly with mobile devices that require IP addresses on a non-

permanent basis. Also, most users aren’t technically proficient enough to locate the IP address information on a computer and assign it. Automating this process makes life easier for users and the network administrator.

DHCP with static @IP address

* When we create a static @IP manually we can a problem with a large internet connection also an @IP address conflict because each host must have a unique @IP address
<p align="center">   
 <img src="https://i.imgur.com/o9zxBcY.png"/>
 </p>

* host2 and host3 can’t access to the network because he have the same @IP address (10.0.0.2)
* A dynamic @IP address is where a device get the I.P address from a DHCP address.

<p align="center">   
 <img src="https://i.imgur.com/jGNXnP2.png"/>
 </p>
 
 ### Assessment: Quiz
Is there is a concept of NAT in IPv6?
 - [ ] Yes
 - [x] No

How NAT works?
 - [ ] Translating IP into MAC
 - [x] Translating Public IP into Private and vice versa
 - [ ] Translating Hostname into IP
 - [ ] None

You saw that your router R7 is not working correctly with NAT, what will be your first action?
 - [ ] Call Cisco
 - [ ] Reboot
 - [x] Check the configuration
 - [ ] All of the above

wo computers are directly using Public IP’s, did they still need NAT to communicate with each other?
 - [ ] Yes
 - [x] No
