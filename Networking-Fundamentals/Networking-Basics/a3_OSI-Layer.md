
# OSI Model (Open Systems Interconnection Model)

**CCNA Notes**

---

## 1. Introduction to the OSI Model

The OSI Model is not a practically implemented networking model. It is a reference model that helps us understand how data communication takes place between two devices over a network.

We have practically implemented the TCP/IP Model, whereas the OSI Model is mainly used as a reference to understand network communication.

### The Seven Layers of the OSI Model

- I. Application Layer
- II. Presentation Layer
- III. Session Layer
- IV. Transport Layer
- V. Network Layer
- VI. Data Link Layer
- VII. Physical Layer

---

## 2. Sender's and Receiver's Perspectives

### Sender's Perspective

When we send data from one device to another, the data travels from the Application Layer down to the Physical Layer.

The order is:

- I. Application Layer
- II. Presentation Layer
- III. Session Layer
- IV. Transport Layer
- V. Network Layer
- VI. Data Link Layer
- VII. Physical Layer

For example, when I use a website and send some data to its server, I interact with the Application Layer first. Then, the data passes through the remaining layers until it reaches the Physical Layer, where it is transmitted in the form of bits.

This process is called **Encapsulation**.

### Receiver's Perspective

When another device receives the data, the process happens in the reverse order.

The order is:

- A. Physical Layer
- B. Data Link Layer
- C. Network Layer
- D. Transport Layer
- E. Session Layer
- F. Presentation Layer
- G. Application Layer

For example, when the website's server receives my data, it first receives it at the Physical Layer in the form of bits. Then, the data travels upward through all the layers until it reaches the Application Layer.

This process is called **Decapsulation**.

Therefore, the layers are the same for both the sender and the receiver, but the order of data processing is reversed.

- Sender: Application Layer → Physical Layer (Encapsulation).
- Receiver: Physical Layer → Application Layer (Decapsulation).

---

## 3. Real-World Working of the Seven OSI Layers

Now let's understand what actually happens inside each layer when data is transferred over a network.

### Layer I: Application Layer

The Application Layer provides an interface through which users interact with network applications and services.

Whenever a user wants to perform an activity over a network, they generally interact with an application that uses Application Layer protocols.

For example:

- If I want to send an email, I interact with Gmail.
- If I want to order food, I interact with the Swiggy application.
- If I want to browse a website, I interact with a web browser.

Therefore, the user generally interacts with the Application Layer through applications.

#### Main Responsibility of the Application Layer

The main responsibility of the Application Layer is to provide network services to applications.

These services allow users to access websites, send emails, transfer files, and perform other network-related activities.

#### Common Application Layer Protocols

- HTTP
- HTTPS
- Telnet
- SSH
- FTP

These protocols define how applications communicate over a network.

For example:

- HTTP and HTTPS are used for web communication.
- Telnet and SSH are used for remote access.
- FTP is used for file transfer.

The Application Layer provides the services and protocols through which applications can communicate with other applications over a network.

### Layer II: Presentation Layer

The Presentation Layer is responsible for representing data in a format that the receiving system can understand.

It has three main responsibilities:

#### A. Data Formatting / Translation

The sender and receiver need to understand the format in which data is exchanged.

Therefore, both sides use compatible data formats and encoding standards.

The Presentation Layer converts data received from the Application Layer into an appropriate agreed format.

For example, data can be represented using:

- JSON
- XML
- UTF-8

JSON and XML are data formats, whereas UTF-8 is a character encoding standard.

The main purpose is to ensure that the receiver can correctly interpret the received data.

#### B. Encryption and Decryption

The second responsibility of the Presentation Layer is encryption and decryption.

Suppose I am sending data from a sender to a receiver through a network.

I do not want anyone in between to intercept my data and read its contents.

Therefore, the data can be encrypted before transmission.

Encryption converts readable information (plaintext) into an unreadable form (ciphertext).

The receiver, who has the appropriate decryption key, can decrypt the data and recover the original information.

For example, TLS provides encryption for secure communication.

Cryptographic libraries can also be used to perform encryption and decryption.

#### C. Compression and Decompression

The third responsibility of the Presentation Layer is compression and decompression.

Suppose a sender wants to transfer a 100 GB file over a network.

Transferring such a large file can consume significant network bandwidth and take a considerable amount of time.

Therefore, the sender can compress the file before transmission.

Compression reduces the size of the data.

The compressed data is then transferred over the network.

The receiver decompresses the data to recover the original information.

This can reduce the amount of data that needs to be transferred and help save network bandwidth.

Examples of compression technologies:

- Gzip
- Brotli
- ZIP

When HTTP is used, HTTP compression commonly uses Gzip and Brotli.

### Layer III: Session Layer

The Session Layer is responsible for establishing, managing, and terminating communication sessions between applications.

It has three main responsibilities:

#### A. Session Establishment

When two applications want to communicate with each other, a communication session needs to be established.

The Session Layer is responsible for establishing the session so that the applications can communicate and exchange information.

#### B. Session Maintenance

The second responsibility is session maintenance.

Session maintenance means managing the communication session while it is active.

There are two important concepts associated with session maintenance:

##### A. Dialogue Control

Dialogue Control manages how two applications communicate with each other.

It helps coordinate which application can send data and when.

For example, suppose I am ordering something from Amazon.

When I enter my name, phone number, and address, I send data from my application to Amazon's server.

On the other hand, when I open Amazon's application and scroll through products, Amazon's server sends data back to my application.

Dialogue Control is conceptually responsible for managing the communication dialogue between the two applications.


### Synchronization

Synchronization is another important responsibility of the Session Layer.

It helps track the progress of an ongoing communication session by establishing synchronization points (checkpoints) at specific stages of data exchange.

**Core Purpose:**

When devices are involved in long communication sessions, especially when transferring large amounts of data, the communication is divided into smaller stages so that its progress can be tracked.

Synchronization helps identify how much data has been successfully transferred, keeps both sides aware of the established progress, and supports recovery if communication gets interrupted.

Suppose Application A is transferring 4,000 records to Application B in batches of 1,000 records.

- Batch 1: Records 0–1,000
- Batch 2: Records 1,001–2,000
- Batch 3: Records 2,001–3,000
- Batch 4: Records 3,001–4,000

Both the sender and receiver maintain their communication progress and the last established synchronization point.

Suppose Batch 1 and Batch 2 are successfully transferred, and a synchronization point is established after Batch 2. However, communication gets interrupted while transferring Batch 3.

The receiver knows that data up to Batch 2 has been successfully received, while Batch 3 is incomplete. During recovery, the receiver can communicate its known progress to the sender.

Both sides can then coordinate using their last established synchronization point and resume communication from the next stage, instead of repeating the entire transfer from the beginning.

**Therefore, the core purpose of Synchronization is to divide long communication into manageable stages, track communication progress, and support recovery after an interruption.**

**Important:** This is a conceptual OSI Session Layer example. In modern TCP/IP networks, resumable transfers, checkpoints, and recovery are generally handled by application protocols or other mechanisms rather than a dedicated Session Layer.


#### C. Session Termination

The third responsibility of the Session Layer is session termination.

When data transfer is complete, or when a user logs out, the communication session can be terminated.

This closes the communication session between the applications.

---

### Layer IV: Transport Layer

The main responsibility of the Transport Layer is to provide communication between the source application and the destination application.

It provides end-to-end communication between applications running on different devices.

For example, suppose I use Gmail to send an email to another person.

The Transport Layer helps deliver the data from my source application to the destination application.

#### Main Functions of the Transport Layer

#### A. Segmentation and Reassembly

The first responsibility of the Transport Layer is segmentation and reassembly.

When a sender wants to transmit data, the Transport Layer divides that data into smaller units called segments or datagrams.

For example, suppose I want to send a large file.

The Transport Layer divides the data into smaller parts and sends them through the network.

When the receiver receives these smaller parts, the Transport Layer reassembles them into the original data.

**Protocol Data Units (PDUs):**

- TCP: Segment
- UDP: Datagram

Both represent transport-layer data units, but their structures and functions differ.

#### B. Sequencing and Reordering

After dividing large data into smaller segments, the sender transmits them over the network.

However, the receiver may not receive the segments in the same order in which they were sent.

For example, the sender transmits:

1 → 2 → 3 → 4

But the receiver may receive:

1 → 3 → 2 → 4

TCP uses sequence numbers to identify the order of data.

The receiving TCP implementation uses these sequence numbers to arrange the received data correctly.

Therefore, the data can be reassembled in the correct sequence.

UDP does not provide built-in sequencing and reordering in the same way as TCP. If an application using UDP needs ordering, it must implement that functionality itself.

#### C. End-to-End Delivery

The Transport Layer provides end-to-end communication between applications.

For example, suppose I use Gmail to send an email.

My application communicates with the destination application through the Transport Layer.

The Transport Layer is responsible for delivering data between the source and destination application endpoints.

It uses transport protocols such as TCP and UDP.

#### D. Port Addressing

Port addressing is one of the most important functions of the Transport Layer.

Suppose I am using multiple applications on my device:

- YouTube
- Gmail
- Yahoo
- WhatsApp
- Telegram

All these applications may communicate with different servers, and my device may receive data from multiple sources simultaneously.

Now, how does my device know which application should receive which data?

The Transport Layer uses port numbers to identify the appropriate application or service endpoint.

For example, when I send a request to YouTube to watch a video, my request contains a source port number and a destination port number.

When the YouTube server responds, the response contains the appropriate destination port number so that my device can deliver the data to the correct application endpoint.

At a broader level, network communication involves different types of addressing:

- IP Address: Identifies the source and destination at the network layer.
- MAC Address: Identifies network interfaces for communication over a local network link.
- Port Number: Identifies the source and destination application endpoints at the transport layer.

These addresses work together, but they have different responsibilities.

#### E. Multiplexing and Demultiplexing

Multiplexing and demultiplexing are closely related to port addressing.

First, let's understand what a port number is.

A port number is a logical number used by the Transport Layer to identify an application endpoint.

##### A. Multiplexing

Multiplexing means accepting data from multiple applications, adding the necessary transport-layer information, and forwarding it towards the Network Layer.

**Example 1:**

- Amazon sends some data.
- YouTube sends some data.
- Flipkart sends some data.

Now, what will the Transport Layer do?

1. It receives data from multiple applications.
2. It adds the respective port number to each application's data.
   - Amazon → Amazon's Port Number
   - YouTube → YouTube's Port Number
   - Flipkart → Flipkart's Port Number
3. After adding the port numbers, it forwards the data to the Network Layer.

**Example 2:**

Suppose I am using WhatsApp, YouTube, and Telegram simultaneously.

All three applications generate data.

The Transport Layer handles data from these different applications and uses appropriate port information to distinguish their communication streams.

This process of collecting data from multiple applications, adding port numbers, and forwarding it to the Network Layer is called **Multiplexing**.

##### B. Demultiplexing

Demultiplexing is the reverse process.

When data arrives at the receiving device, the Transport Layer checks the destination port number and delivers the data to the appropriate application endpoint.

For example:

- Data intended for WhatsApp is delivered to WhatsApp's communication endpoint.
- Data intended for YouTube is delivered to YouTube's communication endpoint.
- Data intended for Telegram is delivered to Telegram's communication endpoint.

This process is called Demultiplexing.

**Important:** Port numbers are not fixed application numbers such as Port 1 for WhatsApp and Port 2 for YouTube. Applications use actual port numbers, and multiple applications can use different transport connections and ports.

#### F. Flow Control

Flow Control is another important function of the Transport Layer.

Suppose the sender's server is very powerful and can send data at a very high speed.

However, my receiving device may not be able to process the incoming data at the same speed.

If the sender continuously sends data faster than the receiver can handle, the receiver's buffers may become full, and data may be lost.

To prevent this situation, flow control manages the amount of data that the sender can transmit based on the receiver's capacity.

For example, TCP uses a mechanism called the Receive Window (rwnd).

The receiver communicates how much data it can currently accept, and the sender adjusts its transmission accordingly.

Therefore, the sender does not overwhelm the receiver.

TCP provides built-in flow control, whereas UDP does not provide TCP-style built-in flow control.

#### G. TCP and UDP

The Transport Layer mainly uses two important protocols:

##### A. TCP (Transmission Control Protocol)

TCP is a connection-oriented and reliable transport protocol.
It establishes the connection using three way handshake.

It provides mechanisms to ensure reliable data delivery.

Its important features include:

- Connection establishment.
- Segmentation and reassembly.
- Sequence numbers.
- Acknowledgements.
- Retransmission of lost data.
- Flow control.
- Congestion control.
- Ordered delivery.

TCP uses a connection before exchanging application data.

##### B. UDP (User Datagram Protocol)

UDP is a connectionless transport protocol.

Unlike TCP, UDP does not guarantee reliable data delivery.

Its important characteristics include:

- No connection establishment like TCP.
- No built-in acknowledgement mechanism for reliable delivery.
- No built-in retransmission of lost datagrams.
- No built-in sequencing and ordered delivery.
- No TCP-style built-in flow control.

UDP is useful when applications prefer lower overhead and can handle reliability or ordering themselves if needed.

##### What Does Connection-Oriented and Connectionless Mean?

When we say TCP is connection-oriented, it means TCP establishes a logical connection (three way handshake) between the communicating endpoints before transferring application data.

When we say UDP is connectionless, it means UDP does not establish a TCP-style connection before sending datagrams.

Connection-oriented does not mean that two devices must be physically connected to each other. Both TCP and UDP communicate over a network.

At the Transport Layer:

- TCP uses Segments.
- UDP uses Datagrams.

---

### Layer V: Network Layer

The main responsibility of the Network Layer is to forward data packets from the source device to the destination device across different networks.

For example, suppose I request a video from YouTube.

YouTube's server needs to send data packets towards my device.

The Network Layer is responsible for **logical addressing, routing, and packet forwarding** so that the data can reach the destination IP address.

#### Main Functions of the Network Layer

#### A. Logical Addressing (IP Addressing)

The Network Layer uses IP addresses to identify the source and destination devices.

When the Transport Layer passes its data to the Network Layer, the Network Layer adds an IP header.

The IP header contains important information, including:

- Source IP Address.
- Destination IP Address.
- Other control and routing-related information.

The transport-layer segment or datagram becomes the payload of the IP packet.

Therefore, the basic structure of an IP packet is:

**IP Header + Payload**

The payload contains the Transport Layer's segment or datagram.

The actual application data is carried inside that segment or datagram.

#### B. Routing (Best Path Selection)

After adding the source and destination IP addresses, the Network Layer needs to determine how the packet should reach its destination.

This is where routing comes into the picture.

Routing determines the appropriate path that packets should follow through a network.

There are two main types of routing:

##### A. Static Routing

Static Routing is a routing method in which the network administrator manually configures routes.

For example, a network administrator can configure a particular route for reaching a destination network.

The router follows the configured route unless the administrator changes it or another mechanism modifies route selection.

##### B. Dynamic Routing

Dynamic Routing uses routing protocols to exchange routing information between routers.

Routers learn about available networks and update their routing tables based on routing information and routing metrics.

For example, routers can use protocols such as:

- OSPF.
- BGP.
- RIP.

Dynamic routing does not mean that a server checks the shortest path every time it sends data.

Instead, routers use routing information to determine suitable paths towards destination networks.

The best path depends on routing protocols, routing metrics, and network configuration.

#### C. Forwarding

Routing and forwarding are closely related, but they are not the same.

**Routing:** Determines the paths available to reach different destination networks and builds routing information.

**Forwarding:** Moves a packet from an incoming interface to the appropriate outgoing interface based on the forwarding table.

#### Real-World Example of Routing and Forwarding

Suppose I upload a video on YouTube from my mobile phone.

The data travels through multiple network devices.

A simplified path looks like this:

A. My mobile phone sends data through my home Wi-Fi network.

B. The data reaches my home Wi-Fi router.

C. My router forwards the packet towards my ISP.

D. The packet travels through multiple routers across different networks.

E. Eventually, the packet reaches the network containing YouTube's server.

The routers use their routing and forwarding information to move packets towards the destination.

The actual path can contain many intermediate routers and can change depending on network conditions and routing decisions.

#### Structure of an IP Packet

An IP packet mainly consists of:

A. IP Header.

B. Payload.

The IP Header contains the source and destination IP addresses along with other necessary information.

The Payload contains the Transport Layer's segment or datagram.

When the Network Layer adds an IP header to the transport-layer data, this process is called Encapsulation.

---

### Layer VI: Data Link Layer

The main responsibility of the Data Link Layer is to deliver frames between devices over a local network link.

For example, suppose multiple devices are connected to the same network switch.

The Data Link Layer helps devices communicate with each other through the switch using frames and MAC addresses.

#### Main Functions of the Data Link Layer

#### A. Framing

The Data Link Layer receives an IP packet from the Network Layer.

It adds a Data Link Layer header and trailer around the packet to create a frame.

This process is called Framing.

For example, when Ethernet is used, the Ethernet frame contains:

- Destination MAC Address.
- Source MAC Address.
- Type/Length Field.
- Data (Payload).
- Frame Check Sequence (FCS).

The IP packet becomes the payload of the Ethernet frame.

This means that the entire IP packet, including its IP header and transport-layer data, is carried inside the Ethernet frame's data field.

The Ethernet frame can be represented as:

**Ethernet Header + IP Packet (Payload) + FCS**

The Ethernet header contains the destination MAC address, source MAC address, and Type/Length field.

The FCS is used for error detection.

#### B. MAC Addressing

MAC stands for Media Access Control.

A MAC address is used to identify a network interface at the Data Link Layer.

For example, suppose multiple devices are connected to a local area network.

The switch uses MAC addresses to identify devices and forward Ethernet frames to the appropriate ports.

MAC addresses are associated with network interfaces, commonly provided by Network Interface Cards (NICs).

A device with multiple network interfaces can have multiple MAC addresses.

#### C. Frame Check Sequence (FCS) and Error Detection

FCS stands for Frame Check Sequence.

It is used for error detection in Ethernet frames.

Suppose a sender transmits a frame to a receiver.

During transmission, electrical interference, signal noise, or other transmission problems may cause some bits to change.

As a result, the received frame may become corrupted.

The FCS helps the receiver detect whether the frame has been corrupted during transmission.

##### How Does FCS Work?

Ethernet uses a mechanism called CRC (Cyclic Redundancy Check) for error detection.

The process works as follows:

**At the Sender's Side:**

A. The sender calculates a CRC value for the frame.

B. It places the calculated CRC value in the FCS field.

C. The frame is transmitted to the receiver.

**At the Receiver's Side:**

A. The receiver receives the Ethernet frame.

B. It performs the CRC calculation on the received frame.

C. It checks the calculated result against the received FCS value.

If the CRC check fails, it indicates that the frame has likely been corrupted during transmission.

The receiver generally discards the corrupted frame.

If the check passes, the frame is accepted at the Data Link Layer.

#### D. Flow Control

Flow control can also exist at the Data Link Layer, but it depends on the particular Data Link Layer protocol.

Some Data Link Layer protocols provide flow control, while others do not.

For example, certain link-layer protocols use mechanisms to control how quickly frames are transmitted and received.

Therefore, Data Link Layer flow control is protocol-dependent.

#### E. Data Link Layer Sub-Layers

The Data Link Layer has two sub-layers:

A. LLC – Logical Link Control.

B. MAC – Media Access Control.

##### A. LLC (Logical Link Control)

LLC stands for Logical Link Control.

It is responsible for logical link control functions and helps identify or multiplex Network Layer protocols over the Data Link Layer.

##### B. MAC (Media Access Control)

MAC stands for Media Access Control.

It handles MAC addressing and controls how devices access the shared transmission medium.

---

### Layer VII: Physical Layer

Its main responsibility is to transmit raw bits from one device to another through a physical or wireless transmission medium.

When data reaches the Physical Layer, it is represented as a sequence of bits (0s and 1s).

The Physical Layer converts these bits into appropriate signals for transmission.

These signals can travel through:

- Electrical signals over copper cables.
- Light signals over optical fiber.
- Radio waves through wireless communication.

The receiving device receives these signals and converts them back into bits.

Therefore, the Physical Layer is responsible for the actual transmission and reception of bits over the communication medium.

---

## 4. Software-Oriented and Hardware-Oriented Layers

The OSI Model can be broadly divided into software-oriented and hardware-oriented layers.

### Software-Oriented Layers

The following three layers are generally considered software-oriented:

I. Application Layer

II. Presentation Layer

III. Session Layer

These layers deal mainly with application-level communication, data representation, and session management.

### Transport Layer

The Transport Layer acts as a bridge between the upper three layers and the lower three layers.

It provides end-to-end communication between source and destination applications.

### Hardware-Oriented Layers

The following three layers are generally considered hardware-oriented:

I. Network Layer

II. Data Link Layer

III. Physical Layer

These layers deal mainly with addressing, packet delivery, local network communication, and the physical transmission of data.

---

## 5. Understanding the OSI Model with a Real-World Example

Let's understand how all seven layers of the OSI Model work through a real-world example.

Suppose I have a company with seven employees, and each employee represents one layer of the OSI Model.

The employees are:

- Application Layer: Andy
- Presentation Layer: Parvesh
- Session Layer: Sameer
- Transport Layer: Tanvir
- Network Layer: Navin
- Data Link Layer: Dinesh
- Physical Layer: Pawan

### Sender-Side Process

#### I. Application Layer – Andy

Andy is the CEO of the company, and he is French. He only understands the French language.

One day, Andy asks Parvesh to transfer an important 400-page document to another company named XYZ.

Andy tells Parvesh:

"This is a very important 400-page document written in French. You need to transfer this document to XYZ Company."

After giving these instructions, Andy hands over the French document to Parvesh, who works at the Presentation Layer.

#### II. Presentation Layer – Parvesh

Now, Parvesh receives the document.

After looking at the document, he realizes that it is written in French. However, the receiving company, XYZ, does not understand French. They only understand English.

So, Parvesh translates the entire document from French into English so that the receiving company can understand it.

After translating the document, Parvesh hands it over to Sameer, who works at the Session Layer.

#### III. Session Layer – Sameer

Now, Sameer receives the document.

He sees that it is an important 400-page document that needs to be transferred to XYZ Company.

So, he calls S1, the employee working at the Session Layer of XYZ Company.

Sameer tells S1:

"Your company is going to receive an important 400-page document from our company. Is your company ready to receive it?"

S1 replies:

"Yes, our company is ready to receive the document."

Then Sameer says:

"Okay, thank you. Once you receive the document, please inform me that you have received it successfully."

S1 replies:

"Sure, I will inform you once I receive it."

After establishing this communication and agreeing on the notification, Sameer hands over the document to Tanvir, who works at the Transport Layer.

#### IV. Transport Layer – Tanvir

Now, Tanvir receives the document.

He sees that it contains 400 pages.

He thinks:

"If I send this entire 400-page document as one piece and it gets lost during transportation, the entire document will be lost.

But if I divide it into smaller parts, even if one part gets lost, the remaining parts will still be available."

Therefore, Tanvir divides the 400-page document into four smaller documents, each containing 100 pages.

He creates the following four parts:

- Document 1: Pages 1–100
- Document 2: Pages 101–200
- Document 3: Pages 201–300
- Document 4: Pages 301–400

After dividing the document, he assigns an order number to each part:

- 1 on the first document.
- 2 on the second document.
- 3 on the third document.
- 4 on the fourth document.

This helps the receiving company identify the correct order of all four documents.

After dividing and numbering the documents, Tanvir hands them over to Navin, who works at the Network Layer.

#### V. Network Layer – Navin

Now, Navin receives all four documents.

He writes the following information on each document:

- To: The address of XYZ Company.
- From: The address of our French company.

This information helps identify the destination and source of the documents.

After writing the addresses, Navin gives some instructions to Pawan, the delivery person who works at the Physical Layer.

He tells Pawan:

"Look, you need to deliver these documents to XYZ Company. There are multiple routes available to reach XYZ Company. You can use Road A, Road B, Road C, or Road D.

However, you should use Road B because it is the fastest route.

If you find traffic or congestion on Road B, then take Road C because it is the second-fastest route."

After providing these routing instructions, Navin hands over all four documents to Dinesh, who works at the Data Link Layer.

#### VI. Data Link Layer – Dinesh

Now, Dinesh receives all four documents.

He realizes that these are important and confidential documents.

So, he puts the official seal of the French company on all four documents to identify that they belong to the French company.

He also applies a special seal that helps detect whether someone has opened or tampered with the documents during transportation.

This way, if someone tries to open the documents, the receiving company can identify that they have been tampered with.

After applying the seals, Dinesh hands over all four documents to Pawan, who works at the Physical Layer.

#### VII. Physical Layer – Pawan

Now, Pawan receives all four documents.

He already has the routing instructions from Navin.

He knows that Road B is the fastest route and that he should use Road C if Road B is congested.

So, Pawan takes all four documents and physically delivers them to the Physical Layer employee of XYZ Company.

This completes the sender-side process.

### Receiver-Side Process

Now, let's understand what happens when XYZ Company receives these documents.

#### I. Physical Layer

Pawan delivers all four documents to the employee working at the Physical Layer of XYZ Company.

The employee receives the documents and passes them to the employee working at the Data Link Layer.

#### II. Data Link Layer

The Data Link Layer employee receives all four documents.

He checks whether the official seals are intact or have been broken.

He verifies that nobody has opened or tampered with the confidential documents during transportation.

After checking the seals, he confirms that the documents appear to be intact and hands them over to the Network Layer employee.

#### III. Network Layer

The Network Layer employee receives all four documents.

He checks the destination address written on the documents.

He sees that the documents are addressed to XYZ Company.

Since the destination address belongs to his company, he accepts the documents and passes them to the Transport Layer employee.

#### IV. Transport Layer

The Transport Layer employee receives all four documents.

He realizes that all four are parts of the same original document.

He checks their sequence numbers:

- Document 1
- Document 2
- Document 3
- Document 4

Using these sequence numbers, he arranges all four documents in the correct order and combines them to reconstruct the original 400-page document.

After reconstructing the document, he hands it over to the Session Layer employee.

#### V. Session Layer

The Session Layer employee receives the document.

He realizes that this is the same document that was supposed to arrive from the French company.

He remembers that Sameer, the Session Layer employee of the French company, had called him earlier and asked him to confirm once the document was received.

So, S1 calls Sameer and informs him:

"We have successfully received your document."

After confirming the successful receipt, S1 hands over the document to the Presentation Layer employee.

#### VI. Presentation Layer

The Presentation Layer employee receives the document.

He checks the document and realizes that it is already written in English.

Since XYZ Company understands English, there is no need to translate it.

Therefore, he passes the document directly to the Application Layer employee.

#### VII. Application Layer

Finally, the Application Layer employee receives the document.

The document has successfully reached the destination company, XYZ.

This completes the receiver-side process.

### Session Termination

As soon as S1 informs Sameer that the document has been successfully received, their communication session is terminated.

The communication session between Sameer and S1 is closed.

---

## 6. Difference Between Network Layer and Transport Layer

The Network Layer and Transport Layer have different responsibilities.

### Network Layer

The Network Layer provides packet delivery from the source device to the destination device across networks.It works with IP addresses.

For example, when YouTube's server sends data towards my device, the Network Layer is responsible for forwarding packets towards my destination IP address.

### Transport Layer

The Transport Layer provides communication between source and destination applications.It works with port numbers.

For example, when data reaches my device, the Transport Layer checks the destination port number and delivers the data to the appropriate application.

---

## 7. Complete Data Transfer Process – From Application to Physical Layer

When a sender transmits data to a receiver, the data passes through all seven layers.

### The sender-side process:

I. Application Layer: The application generates the data.

II. Presentation Layer: Data is formatted, encrypted, or compressed where required.

III. Session Layer: Communication sessions are established and managed.

IV. Transport Layer: Data is segmented, port information is added, and transport mechanisms are applied.

V. Network Layer: Source and destination IP addresses are added to create an IP packet.

VI. Data Link Layer: Source and destination MAC addresses and FCS are added to create a frame.

VII. Physical Layer: The frame is transmitted as bits through the communication medium.

### At the receiver's side, the reverse process takes place.

I. Physical Layer: Receives signals and converts them into bits.

II. Data Link Layer: Receives the frame and performs error detection.

III. Network Layer: Processes the IP packet and checks the destination IP address.

IV. Transport Layer: Processes the segment or datagram and delivers data to the appropriate application endpoint.

V. Session Layer: Manages the communication session.

VI. Presentation Layer: Performs the required decoding, decryption, or decompression.

VII. Application Layer: Delivers the data to the receiving application.

This is the overall working of the OSI Model.

## 8. References

**Video:** OSI MODEL in easiest Way in Hindi/Urdu-Bhupinder Rajput

**Channel:** Technical Guftugu

**Link:** https://youtu.be/Dppl6iA2G8Q?si=wGSaI-gwecGr5G4Y