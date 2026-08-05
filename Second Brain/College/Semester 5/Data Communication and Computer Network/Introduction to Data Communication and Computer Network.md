
# [[Data Communication and Computer Networks]] - Introduction

> [!info]  
> **Course:** [[Data Communication and Computer Networks]]  
> **Semester:** V  
> **Topic:** Introduction to Data Communication & Computer Networks  
> **Status:** #completed

---

# What is [[Data Communication]]?

**Data Communication** is the exchange of data between two or more devices through a transmission medium.

A communication system is considered effective when it satisfies:

- [[Delivery]] – Data reaches the correct destination.
    
- [[Accuracy]] – Data is received without errors.
    
- [[Timeliness]] – Data arrives on time.
    
- [[Jitter]] – Packets arrive with consistent delay (important for audio/video).
    

---

# Components of [[Data Communication]]

Every communication system consists of five components:

1. [[Message]] – The information being transmitted.
    
2. [[Sender]] – Device that sends the message.
    
3. [[Receiver]] – Device that receives the message.
    
4. [[Transmission Medium]] – Path through which data travels.
    
5. [[Protocol]] – Rules governing communication.
    

> [!important]  
> Machines from different manufacturers communicate successfully because they follow the same **protocols**.

---

# Data Representation

Different types of information are converted into **binary (0s and 1s)** before transmission.

|Data Type|Representation|
|---|---|
|Text|ASCII / Unicode|
|Numbers|Binary|
|Images|Pixels|
|Audio|Sampled digital signals|
|Video|Sequence of image frames|

---

# [[Data Flow Modes]]

## [[Simplex]]

- One-way communication only.
    
- Example:
    
    - Keyboard → Computer
        
    - Television broadcast
        

---

## [[Half-Duplex]]

- Communication occurs in both directions.
    
- Only one device transmits at a time.
    

Example:

- Walkie-talkie
    

---

## [[Full-Duplex]]

- Both devices transmit simultaneously.
    

Examples:

- Phone call
    
- Video conferencing
    

---

# [[Computer Network]]

A **computer network** is a collection of interconnected devices (nodes) that share information and resources.

Benefits:

- Resource sharing
    
- Communication
    
- Reliability
    
- Scalability
    

---

# Characteristics of a Good Network

## [[Performance]]

Measured using:

- Throughput
    
- Delay
    
- Response time
    

---

## [[Reliability]]

Measured using:

- Failure frequency
    
- Recovery time
    
- Robustness
    

---

## [[Security]]

Goals:

- Confidentiality
    
- Integrity
    
- Availability
    

> Also known as the [[CIA Triad]].

---

# Types of Connections

## [[Point-to-Point]]

- Dedicated link between exactly two devices.
    

Example:

- Laptop connected to a switch.
    

---

## [[Multipoint]]

- One communication link shared by multiple devices.
    

Examples:

- Bus topology
    
- Wireless communication
    

---

# [[Network Topologies]]

## [[Mesh Topology]]

- Every device connected to every other device.
    
- High reliability.
    
- Expensive.
    

---

## [[Star Topology]]

- All devices connected to a central switch or hub.
    
- Most common modern topology.
    
- Easy to troubleshoot.
    

---

## [[Bus Topology]]

- Single backbone cable.
    
- Cheap.
    
- Failure of backbone affects entire network.
    

---

## [[Ring Topology]]

- Each node connected to two neighbours.
    
- Data travels in a circular path.
    

---

# Comparison of Topologies

|Topology|Cost|Reliability|Scalability|
|---|---|---|---|
|Mesh|High|Excellent|Poor|
|Star|Medium|Good|High|
|Bus|Low|Poor|Low|
|Ring|Medium|Medium|Medium|

---

# Networks by Coverage Area

## [[PAN]] (Personal Area Network)

- Few meters
    
- Bluetooth
    
- Wearables
    

---

## [[LAN]] (Local Area Network)

- Building or campus
    
- Ethernet
    
- Wi-Fi
    

---

## [[MAN]] (Metropolitan Area Network)

- Covers a city.
    

---

## [[WAN]] (Wide Area Network)

- Covers countries and continents.
    

Example:

- [[Internet]]
    

---

# Evolution of the [[Internet]]

- **1969** – [[ARPANET]]
    
- **1983** – [[IP 1]]
    
- **1989–1991** – [[World Wide Web]]
    
- **2000s** – Broadband & Mobile Internet
    
- Today – Billions of users worldwide
    

---

# [[Protocols]]

Protocols define how devices communicate.

They specify:

- [[Syntax]] – Data format.
    
- [[Semantics]] – Meaning of information.
    
- [[Timing]] – When and how fast data is transmitted.
    

Important organizations:

- [[ISO]]
    
- [[IEEE]]
    
- [[IETF]]
    
- [[ITU]]
    
- [[W3C]]
    

---

# Layered Architecture

Networking uses layers to simplify communication.

Benefits:

- Easier maintenance
    
- Modularity
    
- Standardization
    
- Interoperability
    

---

# [[OSI Model]]

|Layer|Function|
|---|---|
|7. Application|User services|
|6. Presentation|Encryption, Compression|
|5. Session|Session management|
|4. Transport|End-to-end communication|
|3. Network|Routing & IP|
|2. Data Link|Framing & MAC|
|1. Physical|Transmission of bits|

### Mnemonic

**All People Seem To Need Data Processing**

---

# [[IP Model]]

|Layer|Protocols|
|---|---|
|Application|HTTP, DNS, SMTP, FTP|
|Transport|TCP, UDP|
|Internet|IP, ICMP, ARP|
|Network Access|Ethernet, Wi-Fi|

> The Internet actually uses the **TCP/IP Model**, while the **OSI Model** serves as a conceptual reference.

---

# [[Encapsulation]]

Data moves down the protocol stack:

```
Application Data
      ↓
Segment (TCP)
      ↓
Packet (IP)
      ↓
Frame
      ↓
Bits
```

At the receiver, the reverse process is called **[[Decapsulation]]**.

---

# [[Switching Techniques]]

## [[Circuit Switching]]

- Dedicated communication path.
    
- Used in traditional telephone systems.
    

Advantages:

- Guaranteed bandwidth.
    

Disadvantages:

- Inefficient resource utilization.
    

---

## [[Packet Switching]]

- Data divided into packets.
    
- Each packet can follow a different path.
    

Advantages:

- Efficient.
    
- Reliable.
    
- Used by the Internet.
    

---

# [[Transmission Media]]

## Guided Media

- [[Twisted Pair Cable]]
    
- [[Coaxial Cable]]
    
- [[Optical Fibre]]
    

---

## Unguided Media

- Radio Waves
    
- Microwaves
    
- Infrared
    

---

# [[Bandwidth]] vs [[Throughput]]

## Bandwidth

Maximum capacity of a communication channel.

---

## Throughput

Actual amount of data transmitted successfully.

> Analogy:
> 
> - **Bandwidth** = Number of highway lanes
>     
> - **Throughput** = Number of cars reaching destination
>     

---

# [[Delay]] (Latency)

Total delay consists of:

- [[Transmission Delay]]
    
- [[Propagation Delay]]
    
- [[Processing Delay]]
    
- [[Queuing Delay]]
    

Round Trip Time (RTT) is measured using **Ping**.

---

# Addressing in Networks

## [[MAC Address]]

- Layer 2
    
- Physical hardware address
    

---

## [[IP Address]]

- Layer 3
    
- Identifies a host on a network.
    

---

## [[Port Number]]

- Layer 4
    
- Identifies an application.
    

Example:

- HTTPS → Port **443**
    

---

# What Happens When You Open a Website?

1. Enter URL
    
2. [[DNS]] Lookup
    
3. [[TCP Three-Way Handshake]]
    
4. [[TLS]] Encryption
    
5. [[HTTP]] Request
    
6. Browser renders the webpage
    

---

# Wireless Technologies

- [[Wi-Fi]] (IEEE 802.11)
    
- [[Bluetooth]]
    
- [[4G LTE]]
    
- [[5G]]
    

---

# [[Network Security]]

## CIA Triad

- [[Confidentiality]]
    
- [[Integrity]]
    
- [[Availability]]
    

Common attacks:

- Eavesdropping
    
- Man-in-the-Middle (MITM)
    
- Spoofing
    
- Denial of Service (DoS)
    

Defenses:

- Encryption (TLS)
    
- Authentication
    
- Firewalls
    
- Intrusion Detection Systems
    

---

# Future of Networking

- [[Cloud Computing]]
    
- [[Data Centers]]
    
- [[Internet of Things (IoT)]]
    
- [[5G]]
    
- [[6G]]
    
- [[Software Defined Networking (SDN)]]
    
- [[Edge Computing]]
    
- [[AI-driven Networking]]
    

---

# Recommended Books

- [[Data Communications and Networking]] — Behrouz A. Forouzan
    
- [[Computer Networks]] — Andrew S. Tanenbaum
    
- [[Computer Networking: A Top-Down Approach]] — Kurose & Ross
    

---

# Recommended Tools

- [[Wireshark]]
    
- [[Cisco Packet Tracer]]
    
- [[GNS3]]
    
- [[ns-3]]
    

---

## Tags

[[DCN]] [[Networking]] [[Semester 5]] [[Computer Networks]] [[OSI]] [[IP 1]] [[Internet]] [[Protocols]] [[Network Security]] [[Obsidian]]
