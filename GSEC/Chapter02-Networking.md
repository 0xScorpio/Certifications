 > [!NOTE]
You will need to know details about what the packets look like at the byte level and how they operate in the context of the architectural models that define their use and functionality.

# OSI Model
### Layer 1 - Physical
Physical layer is everything about the physical connection, from wires and jacks to electricity and light.
### Layer 2 - Data Link
Data Link layer describes how all of the data that has been flowing down from the top of the stack gets translated onto the physical transmission medium.
> [!TIP]
>  The collection of systems that communicates using layer 2 is called a **broadcast domain** or a **collision domain**. If you send a message to the broadcast MAC address and a system receives it, that system is in the same broadcast or collision domain as your system. 
### Layer 3 - Network
This is where logical addressing occurs - in order to get traffic between systems on separate IP networks (different LANs), that traffic has to pass through a layer 3 gateway, which means that it is routed.
### Layer 4 - Transport
Depending on the protocol in use, the Transport layer may provide connection services as well as reliable delivery and the guaranteed ordering of messages. Additionally, the Transport layer offers multiplexing. This is done through the use of ports, which are the means of addressing at layer 4. Each system has 65,536 ports for both User Datagram Protocol (UDP) and TCP. This allows your system to be able to have multiple communication sessions open at any given time because, rather than just connecting to a logical address, like an IP address, an application can connect to an address and port combination, allowing multiple applications to communicate simultaneously.
### Layer 5 - Session
The Session layer offers authentication and authorization as well. It makes sure you are who you say you are but also ensures that you have the right permissions to access a particular resource. One of the protocols that falls into this layer is NetBIOS, which provides service-sharing services on Windows systems. NetBIOS establishes identity and permissions and also makes sure the session stays open until it is no longer needed.
### Layer 6 - Presentation
The Presentation layer is responsible for the representation of data. As a result, the XML and JPEG formats are at this layer. This is where the data gets converted from a structured representation to strictly a series of bits and bytes. Encrypting and decrypting data are examples of functions that would take place at the Presentation layer.
### Layer 7 - Application
 Simple Mail Transfer Protocol (SMTP), Internet Message Access Protocol (IMAP), and Post Office Protocol (POP) are all Application layer protocols responsible for allowing users to send and receive e-mail. The protocols specify how to direct the application on what to do with particular chunks of data.

 # IPv4 Headers
 > [!NOTE]
> The IP header is defined as 24 bytes of data, though commonly you’ll see 20 bytes since the other 4 bytes are options and padding.

![image](https://github.com/0xScorpio/Certifications/assets/140411254/8563664e-8bc2-4650-a99b-8e7f8e5c5cac)

IPv4 headers as seen via Wireshark:
![image](https://github.com/0xScorpio/Certifications/assets/140411254/7d32bd8b-b067-4f22-9475-d2826d7ced2c)
The hexadecimal in the top line is the **raw packet**. Each hexadecimal digit uses 4 bits -  hence two hex digits make up 1 byte. 
> [!NOTE]
> The first byte, 45, includes the IP version (4) and the header length in 32-bit words. There are five 32-bit words in the header, which translates to 20 bytes since there are four bytes in a 32-bit word. The next byte (00) is the DiffServ Code Point and the Explicit Congestion Notification, which converts to a 0 for both values. The total length of the datagram as seen in byte locations 3 and 4 is 03 3D, which is 829 bytes in decimal. The IP ID field has 1E EB for the hexadecimal values. The ID field is two bytes long. There is no particular need to convert the ID field to decimal, so we’ll leave it alone at 1EEB. Flags take up the next three bits, and bit 2 is set there.

> [!TIP]
> You will need to know how to convert hex to decimal in the exam.
> For example:
> 
> 0xCD would be -> C = 12, D = 13
> 
> 0xCD = (12 x 16^1) + (12 x 16^0)
> 
> 0xCD = 192 + 12 = 204
>
> Though no one in the real world will actually do this - just use CyberChef, lmao.

*IP is also a best-effort delivery protocol. Since IP has no capability to retransmit or even track messages through the network, the best it can do is say that it will get a message out onto the network and hope that the network does the right thing in getting the message to the recipient. This is why it’s called best-effort. If an application needs something better than that, either it can use an upper layer protocol like TCP to ensure messages get delivered in the right order or it can implement mechanisms in the Application layer protocols to accomplish the tasks that need to be accomplished.*
