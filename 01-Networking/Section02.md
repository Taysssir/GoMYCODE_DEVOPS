### OSI Model

When most non-technical people hear the term “seven layers”, they either think of the popular Super Bowl bean dip or they mistakenly think about the seven layers of Hell, courtesy of Dante’s Inferno (there are nine). For IT professionals, the seven layers refer to the Open Systems Interconnection (OSI) model, a conceptual framework that describes the functions of a networking or telecommunication system.

The model uses layers to help give a visual description of what is going on with a particular networking system. This can help network managers narrow down problems (Is it a physical issue or something with the application?), as well as computer programmers (when developing an application, which other layers does it need to work with?). Tech vendors selling new products will often refer to the OSI model to help customers understand which layer their products work with or whether it works “across the stack”.

#### 7- Application layer :

 <p align="center">   
 <img src="https://i.imgur.com/JwSgVUE.png"/>
 </p>

Human-computer interaction layer , where applications can access the network services.

#### 6- Presentation layer
 <p align="center">   
 <img src="https://i.imgur.com/3FDipJV.png"/>
 </p>
Ensures that data is in a usable format and is where data encryption occurs.

#### 5- Session layer 
 <p align="center">   
 <img src="https://i.imgur.com/e3QbL0U.png"/>
 </p>

Maintains connections and is responsible for controlling ports and sessions.

#### 4- Transport layer
 <p align="center">   
 <img src="https://i.imgur.com/Csllyhe.png"/>
 </p>

Transmits data using transmission protocols including TCP and UDP.

#### 3- Network layer
 <p align="center">   
 <img src="https://i.imgur.com/WuLlpt2.png"/>
 </p>

Decides which physical path the data will take.

#### 2- Data Link layer
 <p align="center">   
 <img src="https://i.imgur.com/ZzHfgh2.png"/>
 </p>
Defines the format of data on the network.

#### 1- Physical layer
 <p align="center">   
 <img src="https://i.imgur.com/T0ZjYPB.png"/>
 </p>

Transmits row bit stream over the physical medium.
Each layer of the OSI model handles a specific job and communicates with the layers above and below itself. DDoS attacks target specific layers of a network connection; application layer attacks target layer 7 and protocol layer attacks target layers 3 and 4.

Why does the OSI model matter?

Although the modern Internet doesn’t strictly follow the OSI model (it more closely follows the simpler Internet protocol suite), the OSI model is still very useful for troubleshooting network problems. Whether it’s one person who can’t get their laptop on the Internet, or a web site being down for thousands of users, the OSI model can help to break down the problem and isolate the source of the trouble. If the problem can be narrowed down to one specific layer of the model, a lot of unnecessary work can be avoided.

### Application layer
 <p align="center">   
 <img src="https://i.imgur.com/QEs5E7Q.png"/>
 </p>
This is the only layer that directly interacts with data from the user. Software applications like web browsers and email clients rely on the application layer to initiate communications. But it should be made clear that client software applications are not part of the application layer; rather the application layer is responsible for the protocols and data manipulation that the software relies on to present meaningful data to the user. Application layer protocols include [HTTP](https://www.cloudflare.com/fr-fr/learning/ddos/glossary/hypertext-transfer-protocol-http/) as well as SMTP (Simple Mail Transfer Protocol is one of the protocols that enables email communications).

### Presentation layer
 <p align="center">   
 <img src="https://i.imgur.com/fF02eyy.png"/>
 </p>

This layer is primarily responsible for preparing data so that it can be used by the application layer; in other words, layer 6 makes the data presentable for applications to consume. The presentation layer is responsible for translation, encryption, and compression of data.

Two communicating devices communicating may be using different encoding methods, so layer 6 is responsible for translating incoming data into a syntax that the application layer of the receiving device can understand.

If the devices are communicating over an encrypted connection, layer 6 is responsible for adding the encryption on the sender’s end as well as decoding the encryption on the receiver's end so that it can present the application layer with unencrypted, readable data.

Finally the presentation layer is also responsible for compressing data it receives from the application layer before delivering it to layer 5. This helps improve the speed and efficiency of communication by minimizing the amount of data that will be transferred.

### Session layer

 <p align="center">   
 <img src="https://i.imgur.com/uBj6FhB.png"/>
 </p>

This is the layer responsible for opening and closing communication between the two devices. The time between when the communication is opened and closed is known as the session. The session layer ensures that the session stays open long enough to transfer all the data being exchanged, and then promptly closes the session in order to avoid wasting resources.
The session layer also synchronizes data transfer with checkpoints. For example, if a 100 megabyte file is being transferred, the session layer could set a checkpoint every 5 megabytes. In the case of a disconnect or a crash after 52 megabytes have been transferred, the session could be resumed from the last checkpoint, meaning only 50 more megabytes of data need to be transferred. Without the checkpoints, the entire transfer would have to begin again from scratch.

### Transport layer


 <p align="center">   
 <img src="https://i.imgur.com/ow7dxxg.png"/>
 </p>

Layer 4 is responsible for end-to-end communication between the two devices. This includes taking data from the session layer and breaking it up into chunks called segments before sending it to layer 3. The transport layer on the receiving device is responsible for reassembling the segments into data the session layer can consume.

The transport layer is also responsible for flow control and error control. Flow control determines an optimal speed of transmission to ensure that a sender with a fast connection doesn’t overwhelm a receiver with a slow connection. The transport layer performs error control on the receiving end by ensuring that the data received is complete, and requesting a retransmission if it isn’t.

### Network layer

 <p align="center">   
 <img src="https://i.imgur.com/zRGvYUX.png"/>
 </p>

The network layer is responsible for facilitating data transfer between two different networks. If the two devices communicating are on the same network, then the network layer is unnecessary. The network layer breaks up segments from the transport layer into smaller units, called packets, on the sender’s device, and reassembling these packets on the receiving device. The network layer also finds the best physical path for the data to reach its destination; this is known as routing.

### Data link layer

 <p align="center">   
 <img src="https://i.imgur.com/pavtyxS.png"/>
 </p>

The data link layer is very similar to the network layer, except the data link layer facilitates data transfer between two devices on the SAME network. The data link layer takes packets from the network layer and breaks them into smaller pieces called frames. Like the network layer, the data link layer is also responsible for flow control and error control in intra-network communication (The transport layer only does flow control and error control for inter-network communications).

### Physical layer

 <p align="center">   
 <img src="https://i.imgur.com/9BryqaD.png"/>
 </p>

This layer includes the physical equipment involved in the data transfer, such as the cables and switches. This is also the layer where the data gets converted into a bit stream, which is a string of 1s and 0s. The physical layer of both devices must also agree on a signal convention so that the 1s can be distinguished from the 0s on both devices.

### Assessment: Quiz
What is the purpose of Presentation Layer?
 - [x] Translation of data between networking service and an application
 - [ ] Remote file accessing
 - [ ] Transmission of data
 - [ ] It may define the protocol for flow control

Which protocol used to be first established the connection before any data is transmitted?
 - [ ] BGP
 - [ ] IP
 - [x] TCP
 - [ ] UDP

What does OSI stands for?
 - [ ] Open Shortest Interconnection
 - [x] Open Systems Interconnection
 - [ ] Open Solution Interconnection
 - [ ] Open Slowest Interconnection

You are IT support engineer, your IT manager wants you to Telnet R7 which is in LA, Which is the highest layer used to get access to LA’s router from Telnet?
 - [x] Layer 7
 - [ ] Layer 1
 - [ ] Layer 4
 - [ ] Layer 5










