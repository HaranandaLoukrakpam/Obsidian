# 1. [[Introduction to Data Communication]]

## 1.1 [[Data Communication]]

**Definition:**  
Data communication is the process of exchanging data between two or more devices through a transmission medium such as cables or wireless signals.

### Effectiveness Criteria of Data Communication

A data communication system is effective when it satisfies four criteria:

1. **[[Delivery]]:** Data must reach the correct destination.
    
2. **[[Accuracy]]:** Data must be delivered without errors or modification.
    
3. **[[Timeliness]]:** Data must reach the destination within the required time.
    
4. **[[Jitter]]:** Variation in packet arrival time should be minimum, especially in audio and video communication.

## 1.2 [[Five Components of Data Communication]]

1. **[[Message]]:** Information being communicated, such as text, images, audio or video.
    
2. **[[Sender]]:** Device that sends the information.
    
3. **[[Receiver]]:** Device that receives the information.
    
4. **[[Transmission Medium]]:** Physical or wireless path through which data travels.
    
5. **[[Protocol]]:** Set of rules governing communication between devices.

**Example:** When sending an email, the email is the message, your computer is the sender, the recipient's computer is the receiver, the network is the medium, and protocols control communication.

## 1.3 [[Data Representation]]

Computers represent all types of data in binary form (0s and 1s).

|Data Type|Representation|
|---|---|
|Text|[[ASCII]] and [[Unicode]] encoding|
|Numbers|[[Binary Representation]]|
|Images|[[Pixels]] represented by binary values|
|Audio|[[Sampling]] and [[Quantisation]]|
|Video|Sequence of digital image frames with audio|

### Important Terms

- **[[ASCII]]:** Character encoding standard that originally uses 7 bits to represent 128 characters.
    
- **[[Unicode]]:** Universal character encoding standard supporting characters from different languages.
    
- **[[Pixel]]:** Smallest individual element of a digital image.
    
- **[[Sampling]]:** Converting an analogue signal into discrete-time samples.
    
- **[[Quantisation]]:** Assigning discrete values to sampled signals.
    

## 1.4 [[Data Flow Modes]]

Data flow refers to the direction in which data travels between two communicating devices.

### 1. [[Simplex Mode]]

- Communication takes place in only one direction.
    
- One device sends data, and the other only receives it.
    
- Example: Traditional television broadcasting and keyboard-to-computer communication.
    

### 2. [[Half-Duplex Mode]]

- Communication takes place in both directions, but not simultaneously.
    
- Only one device can transmit at a time.
    
- Example: Walkie-talkie.
    

### 3. [[Full-Duplex Mode]]

- Communication takes place in both directions simultaneously.
    
- Both devices can send and receive data at the same time.
    
- Example: Telephone conversation.
    

### Comparison

|Feature|Simplex|Half-Duplex|Full-Duplex|
|---|---|---|---|
|Direction|One-way|Both ways|Both ways|
|Simultaneous transmission|No|No|Yes|
|Communication|One direction|Alternate|Simultaneous|
|Example|TV broadcast|Walkie-talkie|Telephone|

---

# 2. [[Computer Networks Basics]]

## 2.1 [[Computer Network]]

**Definition:**  
A computer network is a collection of interconnected computers and devices that communicate and share resources through communication links.

### Important Terms

- **[[Node]]:** Any device connected to a network, such as a computer, printer or server.
    
- **[[Link]]:** A communication path connecting two or more nodes.
    

## 2.2 [[Goals of Computer Networks]]

1. **[[Resource Sharing]]:** Sharing hardware, software and files between devices.
    
2. **[[Communication]]:** Enabling users to exchange information.
    
3. **[[Reliability]]:** Providing alternative resources and communication paths during failures.
    
4. **[[Scalability]]:** Allowing the network to expand as users and devices increase.
    

## 2.3 [[Network Criteria]]

A good computer network is evaluated using three major criteria.

### 1. [[Performance]]

Performance refers to how efficiently a network transfers data.

It is measured using:

- **[[Throughput]]:** Actual amount of data successfully transferred per unit time.
    
- **[[Delay]] / [[Latency]]:** Time taken for data to travel from source to destination.
    
- **[[Response Time]]:** Total time taken by a system to respond to a request.
    

### 2. [[Reliability]]

Reliability refers to the ability of a network to operate continuously without failure.

It depends on:

- Frequency of failures.
    
- Recovery time after failure.
    
- Robustness against faults and disruptions.
    

### 3. [[Network Security]]

Security protects network resources and information from unauthorised access.

It includes three main principles, known as the [[CIA Triad]]:

- **[[Confidentiality]]:** Preventing unauthorised access to information.
    
- **[[Integrity]]:** Ensuring data is not modified without permission.
    
- **[[Availability]]:** Ensuring network resources remain accessible when required.
    

## 2.4 [[Types of Network Connections]]

### 1. [[Point-to-Point Connection]]

- A dedicated communication link connects exactly two devices.
    
- Example: Direct connection between two computers.
    

### 2. [[Multipoint Connection]]

- A single communication link is shared by multiple devices.
    
- Also called a multidrop connection.
    
- Example: Multiple devices sharing a common communication channel.
    

## 2.5 [[Network Topologies]]

**Definition:**  
Network topology refers to the physical or logical arrangement of devices and communication links in a network.

### 1. [[Mesh Topology]]

In mesh topology, every device is connected to every other device through dedicated links.

**Advantages:**

- Highly reliable.
    
- Failure of one link does not affect other links.
    
- Provides better fault tolerance.
    

**Disadvantages:**

- Expensive installation.
    
- Requires more cables and ports.
    
- Difficult to maintain.
    

**Formula for a Full Mesh:**

[  
L=\frac{n(n-1)}{2}  
]

Where:

- L = Number of links.
    
- n = Number of devices.
    

### 2. [[Star Topology]]

In star topology, all devices are connected to a central device such as a switch or hub.

**Advantages:**

- Easy to install and manage.
    
- Easy to add new devices.
    
- Failure of one cable affects only one device.
    

**Disadvantages:**

- Failure of the central device stops the entire network.
    
- Requires more cable than bus topology.
    

### 3. [[Bus Topology]]

In bus topology, all devices are connected to a single main communication cable called the backbone.

**Advantages:**

- Low installation cost.
    
- Requires less cable.
    
- Simple for small networks.
    

**Disadvantages:**

- Backbone failure affects the entire network.
    
- Difficult to troubleshoot.
    
- Performance decreases with increased traffic.
    

### 4. [[Ring Topology]]

In ring topology, every device is connected to two neighbouring devices, forming a circular path.

**Advantages:**

- Orderly data transmission.
    
- Reduced chances of collision in token-based systems.
    

**Disadvantages:**

- Failure of a node or link can disrupt a basic ring.
    
- Difficult to modify and troubleshoot.
    

### 5. [[Hybrid Topology]]

Hybrid topology combines two or more different network topologies, such as star and bus.

**Advantages:**

- Flexible and scalable.
    
- Can provide better reliability.
    
- Suitable for large organisations.
    

**Disadvantages:**

- Expensive.
    
- Complex design and maintenance.
    

### Comparison of Network Topologies

|Topology|Cost|Reliability|Scalability|
|---|---|---|---|
|Mesh|Very high|Very high|Difficult|
|Star|Moderate|High|Easy|
|Bus|Low|Low|Limited|
|Ring|Moderate|Moderate|Moderate|
|Hybrid|High|High|High|

## 2.6 [[Types of Computer Networks]]

Networks are classified according to their geographical coverage.

### 1. [[PAN – Personal Area Network]]

- Covers a very small area around an individual.
    
- Used for connecting personal devices.
    
- Example: Bluetooth connection between a phone and earbuds.
    

### 2. [[LAN – Local Area Network]]

- Covers a small geographical area, such as a home, office or college.
    
- Usually provides high-speed communication.
    
- Example: College computer laboratory network.
    

### 3. [[MAN – Metropolitan Area Network]]

- Covers a city or large town.
    
- Connects multiple LANs.
    
- Example: City-wide cable network.
    

### 4. [[WAN – Wide Area Network]]

- Covers large geographical areas, such as countries and continents.
    
- Connects multiple LANs and MANs.
    
- Example: The Internet.
    

### Comparison of PAN, LAN, MAN and WAN

|Network|Coverage|Example|
|---|---|---|
|PAN|Personal space|Bluetooth|
|LAN|Building/campus|College network|
|MAN|City|City-wide network|
|WAN|Country/world|Internet|

## 2.7 [[Evolution of the Internet]]

The Internet evolved from a small research network into a global network connecting billions of devices.

### Major Stages

1. **[[ARPANET]] (1969):** Developed by the US Department of Defense's ARPA to connect research institutions.
    
2. **[[IP 2]] (1983):** Adopted as the standard communication protocol for ARPANET, helping establish the modern Internet.
    
3. **[[World Wide Web]] (1989–1991):** Tim Berners-Lee developed the Web, enabling access to linked documents through browsers.
    
4. **Commercial Internet:** Internet services expanded to businesses and the general public.
    
5. **Modern Internet:** Uses high-speed broadband, mobile networks, cloud computing, data centres and autonomous systems.
    

### Important Terms

- **[[Autonomous System (AS)]]:** A collection of IP networks operated by a single organisation under a common routing policy.
    
- **[[ISP – Internet Service Provider]]:** An organisation that provides Internet connectivity to individuals and businesses.
    

---

# 3. [[Protocols, Standards and Layered Architecture]]

## 3.1 [[Network Protocol]]

**Definition:**  
A protocol is a set of rules that governs communication and data exchange between network devices.

### Three Elements of a Protocol

1. **[[Syntax]]:** Defines the structure and format of data.
    
2. **[[Semantics]]:** Defines the meaning of each section of data and the actions to be performed.
    
3. **[[Timing]]:** Defines when data should be sent and at what speed.
    

## 3.2 [[Standards Organisations]]

Standards organisations develop rules and specifications to ensure compatibility between different network devices and technologies.

|Organisation|Full Form / Role|
|---|---|
|[[ISO]]|International Organization for Standardization|
|[[IEEE]]|Institute of Electrical and Electronics Engineers|
|[[IETF]]|Internet Engineering Task Force|
|[[ITU]]|International Telecommunication Union|
|[[W3C]]|World Wide Web Consortium|

### Important Contributions

- **[[ISO]]:** Developed the [[OSI Reference Model]].
    
- **[[IEEE]]:** Developed networking standards such as [[IEEE 802.3]] Ethernet and [[IEEE 802.11]] Wi-Fi.
    
- **[[IETF]]:** Develops Internet standards through [[RFC – Request for Comments]].
    
- **[[ITU]]:** Develops international telecommunications standards.
    
- **[[W3C]]:** Develops standards for web technologies such as [[HTML]] and [[CSS]].
    

## 3.3 [[Layered Architecture]]

Layered architecture divides network communication into multiple layers, where each layer performs a specific function.

Each layer provides services to the layer above it and uses services from the layer below it.

### Advantages

1. Reduces complexity.
    
2. Makes network design easier.
    
3. Supports standardisation.
    
4. Simplifies troubleshooting.
    
5. Allows independent development of layers.
    

### Limitations

1. Additional processing overhead.
    
2. Some functions may be duplicated across layers.
    
3. Strict layering can reduce performance.
    
4. Interaction between layers can be complex.
    

## 3.4 [[OSI Reference Model]]

The [[OSI – Open Systems Interconnection]] model is a seven-layer reference model developed by ISO to standardise network communication.

### Seven Layers of the OSI Model

#### Layer 7 – [[Application Layer]]

- Provides network services directly to user applications.
    
- Allows users to access network resources.
    
- Examples: [[HTTP]], [[FTP]], [[SMTP]] and [[DNS]].
    

#### Layer 6 – [[Presentation Layer]]

- Responsible for data translation and formatting.
    
- Performs encryption, decryption and compression.
    
- Example: Data format conversion and encryption.
    

#### Layer 5 – [[Session Layer]]

- Establishes, manages and terminates communication sessions.
    
- Controls dialogue between applications.
    
- Example: Session management.
    

#### Layer 4 – [[Transport Layer]]

- Provides end-to-end communication.
    
- Performs segmentation, reassembly and error recovery.
    
- Uses [[Port Numbers]].
    
- Protocols: [[TCP]] and [[UDP]].
    

#### Layer 3 – [[Network Layer]]

- Responsible for logical addressing and routing.
    
- Determines the best path for data transmission.
    
- Uses [[IP Addresses]].
    
- Protocol: [[IP 2]].
    

#### Layer 2 – [[Data Link Layer]]

- Provides node-to-node data delivery.
    
- Performs framing, [[MAC Addressing]] and error detection.
    
- Uses MAC addresses.
    
- Example: [[Ethernet]].
    

#### Layer 1 – [[Physical Layer]]

- Transmits raw binary bits through the communication medium.
    
- Defines cables, connectors, voltage levels and data rates.
    
- Examples: Cables, hubs and repeaters.
    

### OSI Layers and PDU

|Layer|Name|Data Unit|
|---|---|---|
|7|Application|Data|
|6|Presentation|Data|
|5|Session|Data|
|4|Transport|Segment (TCP) / Datagram (UDP)|
|3|Network|Packet|
|2|Data Link|Frame|
|1|Physical|Bits|

**Remember:**

Data → Segment → Packet → Frame → Bits.

## 3.5 [[TCP/IP Reference Model]]

TCP/IP stands for [[Transmission Control Protocol]] / [[Internet Protocol]].

It is the protocol suite used for communication over the Internet.

### Four Layers of TCP/IP Model

#### 1. [[Application Layer – TCP/IP]]

- Provides services to user applications.
    
- Combines the functions of OSI Application, Presentation and Session layers.
    
- Protocols: HTTP, HTTPS, FTP, SMTP and DNS.
    

#### 2. [[Transport Layer – TCP/IP]]

- Provides process-to-process communication.
    
- Handles segmentation and reliability.
    
- Protocols: TCP and UDP.
    

#### 3. [[Internet Layer]]

- Responsible for logical addressing and routing.
    
- Protocols: IP, ICMP and IGMP.
    

#### 4. [[Network Access Layer]]

- Handles transmission of data over the physical network.
    
- Responsible for framing and hardware addressing.
    
- Technologies: Ethernet and Wi-Fi.
    

### Difference Between OSI and TCP/IP Models

|OSI Model|TCP/IP Model|
|---|---|
|Seven layers|Four layers|
|Developed by ISO|Developed through DARPA research|
|Reference model|Protocol suite and architecture|
|Session and Presentation are separate|Included in Application|
|Physical and Data Link are separate|Combined in Network Access|
|Protocol-independent model|Based on Internet protocols|

## 3.6 [[Encapsulation and Decapsulation]]

### Encapsulation

Encapsulation is the process of adding headers and sometimes trailers to data as it moves from the upper layers to the lower layers before transmission.

### Decapsulation

Decapsulation is the reverse process in which headers and trailers are removed at the receiving end.

### Steps of Encapsulation

1. Application layer generates data.
    
2. Transport layer adds a header, creating a segment.
    
3. Network layer adds an IP header, creating a packet.
    
4. Data Link layer adds a frame header and trailer, creating a frame.
    
5. Physical layer converts the frame into binary bits for transmission.
    

At the receiving end, the reverse process takes place. This is called decapsulation.

**Data transformation:**

`Data → Segment → Packet → Frame → Bits`

## 3.7 [[Network Addressing]]

Network addressing identifies devices and applications involved in communication.

### 1. [[MAC Address]]

- Stands for Media Access Control address.
    
- Used to identify a network interface within a local network.
    
- Usually 48 bits in Ethernet.
    
- Example: `00:1A:2B:3C:4D:5E`.
    
- Operates at [[Data Link Layer]] (Layer 2).
    

### 2. [[IP Address]]

- Stands for Internet Protocol address.
    
- Identifies a device or network interface logically.
    
- Used for routing packets across networks.
    
- [[IPv4]] uses 32 bits.
    
- [[IPv6]] uses 128 bits.
    
- Example: `192.168.1.10`.
    
- Operates at [[Network Layer]] (Layer 3).
    

### 3. [[Port Number]]

- Identifies a specific application or process on a device.
    
- Uses 16 bits.
    
- Range: 0–65535.
    
- Operates at [[Transport Layer]] (Layer 4).
    

Examples:

|Protocol|Port|
|---|---|
|HTTP|80|
|HTTPS|443|
|FTP|21|

### Difference Between MAC, IP and Port Address

|Feature|MAC|IP|Port|
|---|---|---|---|
|Layer|Data Link|Network|Transport|
|Purpose|Interface identification|Logical addressing|Application identification|
|Size|Usually 48 bits|32/128 bits|16 bits|
|Example|00:1A:2B:3C:4D:5E|192.168.1.10|443|

---

# 4. [[Physical Layer, Transmission and Switching]]

## 4.1 [[Transmission Media]]

Transmission media refers to the physical path through which data travels from the sender to the receiver.

It is classified into two major categories:

1. [[Guided Transmission Media]]
    
2. [[Unguided Transmission Media]]
    

### A. [[Guided Transmission Media]]

Guided media uses physical cables to transmit data signals.

#### 1. [[Twisted Pair Cable]]

- Consists of two insulated copper wires twisted together.
    
- Twisting reduces electromagnetic interference and crosstalk.
    
- Commonly used in telephone lines and Ethernet networks.
    

**Types:**

- [[UTP – Unshielded Twisted Pair]]
    
- [[STP – Shielded Twisted Pair]]
    

**Advantages:**

- Low cost.
    
- Easy to install.
    
- Flexible and lightweight.
    

**Disadvantages:**

- Limited transmission distance.
    
- More susceptible to interference than fibre optic cable.
    

#### 2. [[Coaxial Cable]]

- Consists of a central copper conductor surrounded by insulation, a metallic shield and an outer protective covering.
    
- Provides better shielding against interference than ordinary twisted pair cable.
    
- Used in cable television and broadband connections.
    

**Advantages:**

- Better noise resistance.
    
- Higher bandwidth than traditional twisted pair systems.
    

**Disadvantages:**

- More expensive than basic twisted pair cable.
    
- Less flexible and harder to install.
    

#### 3. [[Optical Fibre Cable]]

- Transmits data in the form of light signals.
    
- Made of glass or plastic fibres.
    
- Uses the principle of [[Total Internal Reflection]].
    
- Commonly used in high-speed Internet and long-distance communication.
    

**Types:**

- [[Single-Mode Fibre]]
    
- [[Multimode Fibre]]
    

**Advantages:**

- Very high bandwidth.
    
- Low signal attenuation.
    
- Immune to electromagnetic interference.
    
- Suitable for long-distance communication.
    

**Disadvantages:**

- Expensive installation.
    
- Difficult to repair and splice.
    
- Requires specialised equipment.
    

### B. [[Unguided Transmission Media]]

Unguided media transmits data through air or space using electromagnetic waves without physical cables.

#### 1. [[Radio Waves]]

- Can travel in different directions.
    
- May penetrate walls and other obstacles.
    
- Used in Wi-Fi, radio broadcasting and mobile communication.
    

#### 2. [[Microwaves]]

- Travel mainly in straight lines.
    
- Generally require line-of-sight communication.
    
- Used in satellite communication and cellular networks.
    

#### 3. [[Infrared Waves]]

- Used for short-distance communication.
    
- Generally cannot penetrate walls.
    
- Used in television remote controls and some short-range communication systems.
    

### Comparison of Guided and Unguided Media

|Feature|Guided Media|Unguided Media|
|---|---|---|
|Transmission|Through cables|Through air/space|
|Direction|Cable-dependent|Antenna-dependent|
|Security|Generally higher|More exposed to interception|
|Mobility|Limited|High|
|Examples|Fibre, coaxial, twisted pair|Radio, microwave, infrared|

## 4.2 [[Multiplexing]]

**Definition:**  
Multiplexing is a technique used to combine multiple independent signals and transmit them through a single communication channel.

At the receiving end, the signals are separated using a [[Demultiplexer]].

### [[Frequency Division Multiplexing (FDM)]]

FDM is a multiplexing technique in which the available bandwidth of a communication channel is divided into multiple frequency bands.

Each signal is assigned a separate frequency band, allowing multiple signals to be transmitted simultaneously.

### Working of FDM

1. Multiple input signals are received.
    
2. Each signal is modulated using a different carrier frequency.
    
3. Different frequency bands are allocated to each signal.
    
4. All signals are combined and transmitted through a common medium.
    
5. The receiver separates the signals using filters.
    

### Important Terms

- **[[Carrier Signal]]:** A high-frequency signal used to carry information.
    
- **[[Frequency Band]]:** A specific range of frequencies allocated to a signal.
    
- **[[Guard Band]]:** A small unused frequency range between adjacent channels that prevents interference.
    

**Advantages:**

- Multiple signals can be transmitted simultaneously.
    
- Continuous transmission is possible.
    
- Suitable for radio and television broadcasting.
    

**Disadvantages:**

- Requires larger bandwidth.
    
- Guard bands waste some bandwidth.
    
- Interference can occur if frequency separation is insufficient.
    

**Applications:** Radio broadcasting, cable television and satellite communication.

## 4.3 [[Switching Techniques]]

Switching is the process of transferring data from a source to a destination through intermediate network devices.

The two important switching techniques are:

1. [[Circuit Switching]]
    
2. [[Packet Switching]]
    

### A. [[Circuit Switching]]

Circuit switching establishes a dedicated communication path between sender and receiver before data transmission begins.

### Working

1. Connection establishment.
    
2. Data transmission.
    
3. Connection termination.
    

**Advantages:**

- Dedicated communication path.
    
- Predictable bandwidth during the connection.
    
- Suitable for continuous real-time communication.
    

**Disadvantages:**

- Resources remain reserved even when no data is transmitted.
    
- Connection establishment takes time.
    
- Less efficient for bursty data traffic.
    

**Example:** Traditional telephone networks.

### B. [[Packet Switching]]

Packet switching divides data into small units called packets. These packets are transmitted independently through the network and reassembled at the destination.

### Working

1. Data is divided into packets.
    
2. Each packet contains addressing information.
    
3. Packets travel through intermediate routers.
    
4. Packets reach the destination.
    
5. Data is reassembled into its original form.
    

**Advantages:**

- Efficient utilisation of network resources.
    
- Multiple users can share the same network.
    
- No dedicated connection is required.
    
- Can route around network failures.
    

**Disadvantages:**

- Packets may experience variable delays.
    
- Packets may arrive out of order.
    
- Congestion can cause packet loss.
    

**Example:** Internet communication.

**Important:** In [[Datagram Packet Switching]], each packet is routed independently and may follow a different path.

### Difference Between Circuit Switching and Packet Switching

|Feature|Circuit Switching|Packet Switching|
|---|---|---|
|Connection|Dedicated|No dedicated path in datagram networks|
|Data transmission|Continuous stream|Divided into packets|
|Resource usage|Reserved|Shared|
|Delay|Setup delay, then predictable transmission|Variable delay|
|Efficiency|Less efficient for bursty traffic|More efficient for bursty traffic|
|Example|Traditional telephone|Internet|

## 4.4 [[Bandwidth and Throughput]]

### [[Bandwidth]]

Bandwidth refers to the maximum data-carrying capacity of a communication channel.

It is measured in bits per second (bps) for digital communication, or in hertz (Hz) when referring to frequency range.

### [[Throughput]]

Throughput refers to the actual amount of data successfully transmitted through a network per unit time.

It is measured in bits per second.

### Difference Between Bandwidth and Throughput

|Bandwidth|Throughput|
|---|---|
|Maximum channel capacity|Actual data transfer rate|
|Theoretical or configured limit|Depends on actual network conditions|
|Usually higher|Usually lower|
|Example: 100 Mbps link|Actual speed: 75 Mbps|

**Example:** If a network has a bandwidth of 100 Mbps but transfers data at 80 Mbps, its throughput is 80 Mbps.

## 4.5 [[Network Delay]]

Network delay is the time taken for data to travel from the sender to the receiver.

There are four major components of network delay.

### 1. [[Transmission Delay]]

Transmission delay is the time required to place all bits of a packet onto the transmission link.

[  
D_{trans}=\frac{\text{Packet Size (bits)}}{\text{Bandwidth (bps)}}  
]

### 2. [[Propagation Delay]]

Propagation delay is the time taken by a signal to travel from sender to receiver through the transmission medium.

[  
D_{prop}=\frac{\text{Distance}}{\text{Propagation Speed}}  
]

### 3. [[Processing Delay]]

Processing delay is the time taken by a network device to examine a packet, check its header and determine where to forward it.

### 4. [[Queuing Delay]]

Queuing delay is the time a packet waits in a queue before being transmitted.

It generally increases during network congestion.

### Total Network Delay

[  
D_{total}=D_{trans}+D_{prop}+D_{proc}+D_{queue}  
]

### [[Round-Trip Time (RTT)]]

RTT is the total time taken for a signal or packet to travel from the source to the destination and for a response to return to the source.

[  
RTT=T_{\text{request}}+T_{\text{response}}  
]

RTT is commonly used to measure network responsiveness.

**Example:** The `ping` command measures round-trip time.

## 4.6 [[Transmission Impairments]]

Transmission impairment refers to the degradation or alteration of a signal while travelling through a communication medium.

There are three major types.

### 1. [[Attenuation]]

Attenuation is the loss of signal strength as it travels through a transmission medium.

- Signal strength decreases with distance.
    
- It can be reduced using repeaters or amplifiers.
    

### 2. [[Delay Distortion]]

Delay distortion occurs when different frequency components of a signal travel at different speeds, causing the received signal to become distorted.

- Different frequency components may arrive at different times.
    
- Common in guided transmission media.
    

### 3. [[Noise]]

Noise refers to unwanted electrical or electromagnetic signals that interfere with the original transmitted signal.

**Types of Noise:**

- **[[Thermal Noise]]:** Caused by random movement of electrons.
    
- **[[Induced Noise]]:** Caused by external electrical sources.
    
- **[[Crosstalk]]:** Interference from neighbouring communication channels.
    
- **[[Impulse Noise]]:** Sudden high-energy disturbances.
    

## 4.7 [[Channel Capacity – Shannon's Theorem]]

Channel capacity is the maximum theoretical data rate at which information can be transmitted over a communication channel with an arbitrarily low error probability under the ideal assumptions of Shannon's theorem.

### [[Shannon's Capacity Formula]]

[  
\boxed{C=B\log_2(1+SNR)}  
]

Where:

- C = Channel capacity in bits per second (bps).
    
- B = Bandwidth in Hertz (Hz).
    
- SNR = Signal-to-Noise Ratio (linear value).
    

### [[Signal-to-Noise Ratio (SNR)]]

SNR is the ratio of signal power to noise power.

[  
SNR=\frac{P_{signal}}{P_{noise}}  
]

### SNR in Decibels

[  
SNR_{dB}=10\log_{10}(SNR)  
]

### Convert SNR from dB to Linear Value

[  
SNR=10^{SNR_{dB}/10}  
]

### Solved Numerical 1

**Question:** A communication channel has a bandwidth of 3000 Hz and an SNR of 30 dB. Calculate its maximum channel capacity using Shannon's theorem.

**Given:**

[  
B=3000\ Hz  
]

[  
SNR_{dB}=30\ dB  
]

**Step 1: Convert SNR into linear form.**

[  
SNR=10^{30/10}  
]

[  
SNR=1000  
]

**Step 2: Apply Shannon's formula.**

[  
C=B\log_2(1+SNR)  
]

[  
C=3000\log_2(1001)  
]

[  
C=3000\times9.967  
]

**Final Answer:**

[  
\boxed{C\approx29,901\ bps}  
]

Therefore, the maximum theoretical channel capacity is approximately **29.9 kbps**.

### Solved Numerical 2

**Question:** A channel has a bandwidth of 4000 Hz and a linear SNR of 15. Calculate the channel capacity.

**Given:**

[  
B=4000\ Hz,\quad SNR=15  
]

Using Shannon's formula:

[  
C=4000\log_2(1+15)  
]

[  
C=4000\log_2(16)  
]

[  
C=4000\times4  
]

**Final Answer:**

[  
\boxed{C=16,000\ bps=16\ kbps}  
]

### Important Points for Numericals

1. If SNR is given in dB, convert it into linear form first.
    
2. If SNR is already given as a ratio, use it directly.
    
3. Bandwidth must be in Hz.
    
4. Final capacity is expressed in bps.
    
5. Remember:
    
    - (\log_2(16)=4)
        
    - (\log_2(8)=3)
        
    - (\log_2(32)=5)
        

## 4.8 [[Networking Hardware]]

Networking devices are used to connect computers and transfer data between network devices.

The three important devices are:

1. [[Hub]]
    
2. [[Switch]]
    
3. [[Router]]
    

### 1. [[Hub]]

A hub is a basic networking device that operates at the [[Physical Layer]] (Layer 1) of the OSI model.

**Functions:**

- Connects multiple devices in a LAN.
    
- Receives data from one port.
    
- Broadcasts the incoming signal to all other ports.
    
- Does not examine MAC or IP addresses.
    

**Characteristics:**

- One collision domain.
    
- One broadcast domain.
    
- Does not perform intelligent forwarding.
    
- Generally operates in half-duplex mode.
    

### 2. [[Switch]]

A switch is a networking device that generally operates at the [[Data Link Layer]] (Layer 2).

**Functions:**

- Connects multiple devices in a LAN.
    
- Uses MAC addresses to forward frames.
    
- Learns MAC addresses and maintains a MAC address table.
    
- Sends frames to the appropriate destination port when the destination is known.
    

**Characteristics:**

- Each port is a separate collision domain.
    
- Normally one broadcast domain per VLAN.
    
- Supports full-duplex communication.
    
- Reduces unnecessary network traffic compared with a hub.
    

### 3. [[Router]]

A router is a networking device that operates at the [[Network Layer]] (Layer 3).

**Functions:**

- Connects different networks.
    
- Uses IP addresses to forward packets.
    
- Maintains a [[Routing Table]].
    
- Selects suitable paths for packet transmission.
    

**Characteristics:**

- Each interface is a separate broadcast domain.
    
- Separates broadcast domains.
    
- Can connect LANs to WANs and the Internet.
    
- May support NAT, firewall and other routing functions.
    

### Difference Between Hub, Switch and Router

|Feature|Hub|Switch|Router|
|---|---|---|---|
|OSI Layer|Layer 1|Layer 2|Layer 3|
|Address used|None|MAC|IP|
|Data unit|Bits|Frames|Packets|
|Working|Broadcasts signals|Forwards frames|Routes packets|
|Collision domain|One shared|One per port|One per interface|
|Broadcast domain|One|One per VLAN|Separate per interface|
|Forwarding|All other ports|Based on MAC table|Based on routing table|
|Main purpose|Connect devices|Connect LAN devices|Connect networks|

**Important Examination Points:**

- Hub works with signals and does not understand MAC addresses.
    
- Switch forwards frames based on MAC addresses.
    
- Router forwards packets based on IP addresses.
    

---

# 5. [[Important Formulas – Unit I]]

|Topic|Formula|
|---|---|
|Mesh topology links|(L=\frac{n(n-1)}{2})|
|Transmission delay|(D_t=\frac{\text{Packet Size}}{\text{Bandwidth}})|
|Propagation delay|(D_p=\frac{\text{Distance}}{\text{Propagation Speed}})|
|Total delay|(D=D_t+D_p+D_{proc}+D_{queue})|
|SNR|(SNR=\frac{P_s}{P_n})|
|SNR in dB|(10\log_{10}(SNR))|
|Linear SNR|(10^{SNR_{dB}/10})|
|Shannon capacity|(C=B\log_2(1+SNR))|
|Round-trip time|Request time + Response time|

---

# 6. [[Important Examination Questions – Unit I]]

## 6.1 [[Long Answer Questions]] (5–10 Marks)

1. Explain the five components of data communication and its effectiveness criteria.
    
2. Explain Simplex, Half-Duplex and Full-Duplex communication modes with diagrams.
    
3. Explain different network topologies with their advantages and disadvantages.
    
4. Explain PAN, LAN, MAN and WAN with suitable examples.
    
5. Explain all seven layers of the OSI reference model with their functions.
    
6. Explain the TCP/IP model and compare it with the OSI model.
    
7. Explain encapsulation and decapsulation with a suitable diagram.
    
8. Explain guided and unguided transmission media with their advantages and disadvantages.
    
9. Explain Frequency Division Multiplexing (FDM), including carrier signals and guard bands.
    
10. Explain circuit switching and packet switching with diagrams.
    
11. Explain the four components of network delay with formulas.
    
12. Explain transmission impairments: attenuation, delay distortion and noise.
    
13. State and explain Shannon's channel capacity theorem with a numerical.
    
14. Differentiate between Hub, Switch and Router.
    

## 6.2 [[Short Answer Questions]] (2–3 Marks)

1. Define data communication.
    
2. What is jitter?
    
3. What are the five components of data communication?
    
4. Differentiate between ASCII and Unicode.
    
5. What is a network node?
    
6. Define throughput and latency.
    
7. What is point-to-point connection?
    
8. Define multipoint connection.
    
9. What is network topology?
    
10. What is an autonomous system?
    
11. Define network protocol.
    
12. Explain syntax, semantics and timing.
    
13. What is an RFC?
    
14. What is the OSI model?
    
15. What is the function of the Transport Layer?
    
16. Define encapsulation.
    
17. Differentiate between MAC and IP addresses.
    
18. What is a port number?
    
19. What is optical fibre?
    
20. Define multiplexing.
    
21. What is a guard band?
    
22. Define circuit switching.
    
23. What is packet switching?
    
24. Define attenuation.
    
25. What is SNR?
    
26. Define channel capacity.
    
27. What is a collision domain?
    
28. What is a broadcast domain?
    

## 6.3 [[Important Numericals]]

|Numerical Topic|Priority|
|---|---|
|Shannon channel capacity|Very High|
|SNR conversion (dB to linear)|Very High|
|Transmission delay|High|
|Propagation delay|High|
|Total network delay|High|
|RTT calculation|Medium|
|Number of mesh connections|Medium|

---

# 7. [[Last-Minute Revision – Unit I]]

## Communication Fundamentals

- 5 components: Message, Sender, Receiver, Medium, Protocol.
    
- 4 effectiveness criteria: Delivery, Accuracy, Timeliness, Jitter.
    
- 3 data flow modes: Simplex, Half-Duplex, Full-Duplex.
    

## Computer Networks

- 4 network types: PAN, LAN, MAN, WAN.
    
- 5 topologies: Mesh, Star, Bus, Ring, Hybrid.
    
- 3 network criteria: Performance, Reliability, Security.
    
- CIA: Confidentiality, Integrity, Availability.
    

## Network Architecture

- OSI: 7 layers.
    
- TCP/IP: 4 layers.
    
- Protocol elements: Syntax, Semantics, Timing.
    
- Addressing: MAC (L2), IP (L3), Port (L4).
    
- Encapsulation: Data → Segment → Packet → Frame → Bits.
    

## Physical Layer

- Guided: Twisted Pair, Coaxial, Optical Fibre.
    
- Unguided: Radio, Microwave, Infrared.
    
- FDM: Frequency Division Multiplexing.
    
- Switching: Circuit and Packet.
    
- Impairments: Attenuation, Delay Distortion, Noise.
    
- Delay: Transmission, Propagation, Processing, Queuing.
    

## Networking Hardware

- Hub: Layer 1, broadcasts signals.
    
- Switch: Layer 2, MAC-based forwarding.
    
- Router: Layer 3, IP-based forwarding.
    

---

# 8. [[Unit I – Examination Preparation Checklist]]

- [[Data Communication]] and its effectiveness criteria.
    
- [[Five Components of Data Communication]].
    
- [[Data Flow Modes]].
    
- [[Network Criteria]] and [[CIA Triad]].
    
- [[Network Topologies]] with diagrams.
    
- [[PAN]], [[LAN]], [[MAN]] and [[WAN]].
    
- [[Protocols and Standards Organisations]].
    
- [[OSI Reference Model]] – all seven layers.
    
- [[TCP/IP Reference Model]] and comparison.
    
- [[Encapsulation and Decapsulation]].
    
- [[MAC Address]], [[IP Address]] and [[Port Number]].
    
- [[Guided Transmission Media]] and [[Unguided Transmission Media]].
    
- [[Frequency Division Multiplexing (FDM)]].
    
- [[Circuit Switching]] and [[Packet Switching]].
    
- [[Bandwidth]], [[Throughput]] and [[Network Delay]].
    
- [[Transmission Impairments]].
    
- [[Shannon's Capacity Formula]] and numericals.
    
- [[Hub]], [[Switch]] and [[Router]].
    

---

**Recommended Study Order:**

1. OSI and TCP/IP models.
    
2. Network topologies.
    
3. Transmission media.
    
4. Switching techniques.
    
5. Hub, Switch and Router.
    
6. Shannon's theorem and delay numericals.
    
7. Remaining definitions and short-answer topics.