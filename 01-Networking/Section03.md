### IP addressing Basics

IP address is an address having information about how to reach a specific host, especially outside the LAN. An IP address is a 32 bit unique address having an address space of 232.

Generally, there are two notations in which IP address is written, dotted decimal notation and hexadecimal notation. Let's talk about Dotted Decimal Notation.

#### Dotted Decimal Notation:
Here is how binary octets convert to decimal: The right most bit, or least significant bit, of an octet holds a value of 20. The bit just to the left of that holds a value of 21. This continues until the left-most bit, or most significant bit, which holds a value of 27. So if all binary bits are a one, the decimal equivalent would be 255 as shown here:
1 1 1 1 1 1 1 1
128 64 32 16 8 4 2 1 ⇒ (128+64+32+16+8+4+2+1=255) ⇒ Notice 128 = 2^8 , 64 = 2^7 ….

<p align="center">   
 <img src="https://i.imgur.com/xcdRZfb.png"/>
 </p>
 
#### IP addressing Basics: Classful Addressing

The 32 bit IP address is divided into five sub-classes. These are:

* Class A (1.0.0.1 to 126.255.255.254)
* Class B (128.1.0.1 to 191.255.255.254)
* Class C (192.0.1.1 to 223.255.254.254)
* Class D (224.0.0.0 to 239.255.255.255)
* Class E (240.0.0.0 to 255.255.255.254)
Each of these classes has a valid range of IP addresses. Classes D and E are reserved for multicast and experimental purposes respectively. The order of bits in the first octet determine the classes of IP address.

IPv4 address is divided into two parts:

* Network ID
* Host ID
The class of IP address is used to determine the bits used for network ID and host ID and the number of total networks and hosts possible in that particular class. Each ISP or network administrator assigns IP address to each device that is connected to its network.
<p align="center">   
 <img src="https://i.imgur.com/WNYcFtN.jpg"/>
 </p>
 
### Assessment: Quiz
In which layer we have a transmission of TCP and UDP
 - [x] Transport Layer
 - [ ] Network Layer
 - [ ] Application Layer

In which layer we have a transmission of HTTP and SMTP
 - [ ] Software layer
 - [ ] Network Layer
 - [x] Application layer

we have this address 127.0.01 , this address belongs to
 - [ ] Class A
 - [ ] Class B
 - [x] None
------------------
LINK : 

* [IP Adressing basics](https://www.cisco.com/c/en/us/support/docs/ip/routing-information-protocol-rip/13788-3.html)
