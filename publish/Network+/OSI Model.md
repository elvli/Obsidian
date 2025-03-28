## What is a Protocol?

 A protocol is a standard set to procedures/rules that governs communication. Computer within a network may user different software and hardware, flowing the same protocol will allow all of them to communicate.

## Layered Approach

![[OSI-model.png]]

### **Interoperability & OSI Model**

**Interoperability** → The ability for all kinds of machines to communicate with each other. We live in an **interoperable** world.

### **The OSI Model**

The **Open Systems Interconnection (OSI) Model** is an **internetworking model** used to **organize and describe network functions**. Each layer represents a unique set of functions.

#### **OSI Model - 7 Layers**

##### **Mnemonics**
- **All People Seem To Need Data Processing** _(backward order)_
- **Please Do Not Throw Sausage Pizza Away**

|**Layer**|**Name**|**Function**|
|---|---|---|
|**Layer 1**|**Physical**|Converts bits into **electrical signals, pulses of light, or radio frequencies**|
|**Layer 2**|**Data Link**|Enables communication **within the same network** using **MAC addresses**|
|**Layer 3**|**Network**|Handles **communication between different networks** using **IP addresses**|
|**Layer 4**|**Transport**|Manages **end-to-end communication** using **TCP or UDP**|
|**Layer 5**|**Session**|Controls dialog by **synchronizing multiple persistent connections**|
|**Layer 6**|**Presentation**|Prepares data for the application layer by **translating, encoding, compressing, or encrypting**|
|**Layer 7**|**Application**|Generate|



## Encapsulation

![[OSI-Encap.png]]

Encapsulation is the process of **adding headers (and sometimes trailers)** as data moves **down** the OSI layers before transmission. Each layer wraps the data from the layer above into its own **Protocol Data Unit (PDU)**.

NOTE: Trailers and footers are different things.
- **Trailer** → Added at the **end** of a data frame at **Layer 2 (Data Link Layer)** (e.g., Ethernet FCS for error detection).
- **Footer** → A general term for anything appended at the end of a file or document, but **not used in OSI encapsulation**.

**Mnemonics**
- Don't Stop Pouring Free Beer
- Data, Segment/Datagram, Packet, Frame, Bits



## Application Layer *- 7*

This is the entry door to network services. Apps sit on top of this layer. It's responsible for interfacing user applications, network management services, remote access etc. (Hacker's playground)

- Where users **interact** with the network through applications like **web browsers, email clients, and file transfer programs**.  
- **Identifies and establishes** communication with the intended partner.  
- **Checks resource availability** to ensure the communication request can be processed.  
- **Does not handle data transport directly**—relies on the **Transport Layer (Layer 4 - UDP/TCP)** to establish connections and manage data transmission.  

| **Protocol** | **Full Name** | **Port(s)** | **Description** |
|-------------|-------------|-----------|----------------|
| **HTTP** | Hypertext Transfer Protocol | 80 | Web browsing (unencrypted) |
| **HTTPS** | Hypertext Transfer Protocol Secure | 443 | Secure web browsing (TLS/SSL) |
| **FTP** | File Transfer Protocol | 20 (Data), 21 (Control) | File transfer between systems |
| **SFTP** | Secure File Transfer Protocol | 22 | Secure file transfer (via SSH) |
| **FTPS** | File Transfer Protocol Secure | 990 | FTP over SSL/TLS |
| **SMTP** | Simple Mail Transfer Protocol | 25 | Sending emails |
| **SMTPS** | Simple Mail Transfer Protocol Secure | 465 | Secure SMTP (deprecated, use STARTTLS) |
| **IMAP** | Internet Message Access Protocol | 143 | Retrieving emails (keeps messages on server) |
| **IMAPS** | Internet Message Access Protocol Secure | 993 | Secure IMAP |
| **POP3** | Post Office Protocol v3 | 110 | Retrieving emails (downloads messages) |
| **POP3S** | Post Office Protocol v3 Secure | 995 | Secure POP3 |
| **DNS** | Domain Name System | 53 | Resolves domain names to IP addresses |
| **DHCP** | Dynamic Host Configuration Protocol | 67 (Server), 68 (Client) | Assigns IP addresses dynamically |
| **TELNET** | Teletype Network | 23 | Remote command-line login (insecure) |
| **SSH** | Secure Shell | 22 | Secure remote login |
| **RDP** | Remote Desktop Protocol | 3389 | Remote desktop access |
| **SNMP** | Simple Network Management Protocol | 161 (Queries), 162 (Traps) | Network monitoring and management |
| **LDAP** | Lightweight Directory Access Protocol | 389 | Directory services (e.g., Active Directory) |
| **LDAPS** | Lightweight Directory Access Protocol Secure | 636 | Secure LDAP (encrypted) |
| **NTP** | Network Time Protocol | 123 | Time synchronization between devices |
| **TFTP** | Trivial File Transfer Protocol | 69 | Simple file transfer (no authentication) |
| **SIP** | Session Initiation Protocol | 5060 (UDP/TCP), 5061 (TLS) | VoIP call setup and management |



## Presentation Layer - *6*

Concern about the format, apps must use a common format.
This layer does:
- **Prepares data for the Application Layer** (Layer 7).
- Handles data translation, encryption, compression, and encoding.
- Ensures compatibility between different systems by converting data formats.

A few common encoding formats:

| **Encoding Format** | **Full Name**                          | **Description** |
|---------------------|----------------------------------------|-----------------|
| ASCII               | American Standard Code for Information Interchange | Character encoding standard for text. |
| Unicode             | Unicode                                | Universal character encoding standard supporting multiple languages and symbols. |
| JPEG                | Joint Photographic Experts Group       | Image compression format for pictures. |
| GIF                 | Graphics Interchange Format            | Image format that supports animations and compression. |
| MPEG                | Moving Picture Experts Group           | Video compression standard for video files. |
| Base64              | Transmission Control Protocol/Internet Protocol | Encoding scheme for representing binary data in an ASCII string format. |
| TLS/SSL             | Transport Layer Security/Secure Sockets Layer | Protocols for encrypting data during transmission for secure communication. |
| XML                 | Extensible Markup Language             | Format for encoding documents and data for easy sharing. |
| HTML                | HyperText Markup Language              | Format used for structuring content on the web. |
| MP3                 | MPEG Audio Layer III                   | Audio compression format widely used for music and audio files. |



## Session Layer - 5

Creates session for communications, maintains it, then tears it down.
- **Manages sessions** between two communicating devices.
- Responsible for **establishing, maintaining, and terminating** connections.
- Provides **dialog control** by determining whether the communication is **half-duplex** (one-way) or **full-duplex** (two-way).
- Ensures that data is properly **synchronized** during communication.
- Manages **session checkpoints** to allow recovery if the communication is interrupted.

| **Protocol** | **Full Name**                                      | **Description**                                        |
|--------------|----------------------------------------------------|--------------------------------------------------------|
| **RPC**      | Remote Procedure Call                              | Allows programs to execute procedures on other machines. |
| **NetBIOS**  | Network Basic Input/Output System                  | Provides communication services within a local network. |
| **SMB**      | Server Message Block                               | Protocol used for file sharing, network browsing, and printing. |
| **PPTP**     | Point-to-Point Tunneling Protocol                  | Used for creating VPNs and secure connections. |
| **X.225**    | ITU-T Recommendation X.225                         | Provides services for session initiation and management in network communication. |
| **SAP**      | Session Announcement Protocol                      | Used for announcing multimedia sessions in a network. |



## Transport Layer - *4*

One of the busiest layers
- **Responsible for end-to-end communication** between devices.
- Manages the **flow of data** between sender and receiver, ensuring it is delivered correctly and in order.
- Provides **error detection and correction** to ensure data integrity.
- **Segmentation and reassembly**: Breaks large messages into smaller segments and reassembles them on the receiving end.

There are many well known ports (0 - 1023)
Companies can also register ports.

| **Protocol** | **Full Name**                        | **Description**                                                                                                                           |
| ------------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **TCP**      | Transmission Control Protocol        | Reliable, connection-oriented protocol that ensures data is delivered accurately and in order.                                            |
| **UDP**      | User Datagram Protocol               | Connectionless, faster, but unreliable protocol; used for applications that can tolerate data loss (e.g., streaming, VoIP).               |
| **SCTP**     | Stream Control Transmission Protocol | Combines the best features of TCP and UDP, providing reliable, message-oriented communication with additional features like multi-homing. |



## Network Layer - *3*

Moves data between two hosts that aren't physically connected using logical address, Internet Protocol (IP).
Devices - Routers

- **Responsible for routing** data packets between devices across different networks (internetworking).
- Manages **logical addressing** (IP addresses) to ensure data reaches the correct destination.
- Provides **packet forwarding** and **routing** to determine the best path for data transfer.
- Handles **fragmentation** and **reassembly** of data packets to fit the maximum transmission unit (MTU) of the network.
- It is connectionless, each packet is treated independently, and there is no guarantee of delivery, ordering, or error correction.

| **Protocol** | **Full Name**                                | **Description**                                                                 |
|--------------|----------------------------------------------|---------------------------------------------------------------------------------|
| **IP**       | Internet Protocol                            | Responsible for addressing and routing packets across networks.                 |
| **ICMP**     | Internet Control Message Protocol            | Used for sending error messages and operational information (e.g., "ping" requests). |
| **ARP**      | Address Resolution Protocol                  | Resolves IP addresses to MAC addresses for local communication within a network. |
| **RIP**      | Routing Information Protocol                 | A distance-vector routing protocol used to determine the best route in a network. |
| **OSPF**     | Open Shortest Path First                     | A link-state routing protocol used in large-scale networks to find the most efficient routing paths. |



## Data Link Layer - *2*

Devices - Switches, NIC cards, Access Points, Bridges, Hubs

- **Responsible for the reliable transfer of data** between two devices over the physical layer (Layer 1), ensuring error-free communication.
- Handles the **framing** of data into packets (frames) for transmission.
- **Performs error detection** and **error correction** (e.g., using checksums, CRC) to ensure data integrity.
- Provides **flow control** to prevent data overload at the receiver.
- **MAC (Media Access Control)**: Manages access to the physical transmission medium and resolves conflicts (e.g., Ethernet, Wi-Fi).
- **Logical Link Control (LLC)**: Handles communication between the Data Link Layer and higher layers, such as Network Layer.

| **Protocol** | **Full Name**                               | **Description**                                                                 |
|--------------|---------------------------------------------|---------------------------------------------------------------------------------|
| **Ethernet** | Ethernet                                    | The most common LAN protocol, using MAC addresses for device identification and managing shared network access. |
| **Wi-Fi**    | IEEE 802.11 (Wi-Fi)                        | A set of wireless protocols providing local network access via wireless communication, using MAC addresses. |
| **PPP**      | Point-to-Point Protocol                     | Used for point-to-point connections, providing framing, error detection, and link control. |
| **HDLC**     | High-Level Data Link Control                | A bit-oriented protocol for communication over point-to-point and multipoint links, offering framing and error detection. |
| **ARP**      | Address Resolution Protocol                 | Resolves IPv4 addresses to MAC addresses within a local network. |
| **MAC**      | Media Access Control                        | A protocol that governs how devices access and share the physical transmission medium, e.g., Ethernet’s CSMA/CD or Wi-Fi’s CSMA/CA. |



## Physical Layer - *1*

The **Physical Layer** is responsible for the **transmission and reception of raw data** bits over a physical medium. It deals with the **hardware aspects** of networking, ensuring that data is converted into signals and transmitted across the network.

- **Transmission of Raw Bits**: Converts data into signals (electrical, optical, or radio) for transmission.
- **Media and Connector Types**: Defines the physical medium (e.g., cables, connectors).
- **Signal Encoding**: Converts digital data into signals for transmission.
- **Data Rate Control**: Determines the speed of transmission (in bits per second).
- **Topology and Media Access**: Defines network structure and how devices access the medium.
- **Physical Addressing**: Relies on MAC addresses from the Data Link Layer.

| **Technology**       | **Description**                                                   |
|----------------------|-------------------------------------------------------------------|
| **Ethernet cables**   | Cables like Cat 5, Cat 6 used for wired network connections.     |
| **Fiber optic cables**| Cables that use light signals for high-speed, long-distance transmission. |
| **Wi-Fi**             | Wireless technology using radio waves for local area networks.   |
| **Bluetooth**         | Short-range wireless communication technology for devices.       |
| **Radio signals**     | Used in wireless communication for technologies like Wi-Fi and mobile networks. |
| **Network Interface Cards (NICs)** | Hardware that connects devices to a network, either wired or wireless. |




## Summary

Move from 7 - 1 on your end and 1 - 7 on the other end.