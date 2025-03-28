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
- Data conversion
- Character Code Translation
- Compress
- Encryption & Decryption

