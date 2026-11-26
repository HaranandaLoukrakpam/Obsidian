## 1. [[IP Addressing and Subnetting]]

### 1.1 [[IP Address]]

An [[IP Address]] is a logical address assigned to a device connected to a network. It is used to identify devices and enable communication across networks.

**Main functions:**

- Identifies a device on a network.
    
- Identifies the network to which the device belongs.
    
- Helps routers forward packets to their destinations.
    

There are two main versions:

- [[IPv4]]
    
- [[IPv6]]
    

### 1.2 [[Public IP Address]] vs [[Private IP Address]]

#### A. [[Public IP Address]]

A public IP address is globally unique and used to communicate over the Internet.

- Assigned by an Internet Service Provider (ISP) or an authorised organisation.
    
- Routable over the public Internet.
    
- Used by servers, routers and Internet-connected networks.
    

#### B. [[Private IP Address]]

A private IP address is used within a local network.

- Not directly routable over the public Internet.
    
- Can be reused in different private networks.
    
- Usually accesses the Internet through [[Network Address Translation (NAT)]].
    

**Private IPv4 Address Ranges:**

|Class|Private IP Range|
|---|---|
|Class A|10.0.0.0 – 10.255.255.255|
|Class B|172.16.0.0 – 172.31.255.255|
|Class C|192.168.0.0 – 192.168.255.255|

**Example:**

- `192.168.1.10` → Private IP.
    
- `8.8.8.8` → Public IP.
    

### 1.3 [[Classful Addressing]]

[[Classful Addressing]] is an older IPv4 addressing system that divides IP addresses into five classes.

|Class|First Octet Range|Default Subnet Mask|Purpose|
|---|---|---|---|
|A|1–126|255.0.0.0 (/8)|Large networks|
|B|128–191|255.255.0.0 (/16)|Medium networks|
|C|192–223|255.255.255.0 (/24)|Small networks|
|D|224–239|Not applicable|Multicast|
|E|240–255|Not applicable|Experimental|

**Important:**

- Class A uses 8 network bits.
    
- Class B uses 16 network bits.
    
- Class C uses 24 network bits.
    
- Class D is used for multicast.
    
- Class E is reserved for experimental purposes.
    

**Note:** `127.0.0.0/8` is reserved for loopback, so it is not used as an ordinary Class A network.

### 1.4 [[Classless Inter-Domain Routing (CIDR)]]

[[CIDR]] is a modern IP addressing method that allows flexible allocation of IP addresses using prefix lengths.

It removes the fixed class boundaries of classful addressing.

**CIDR Notation:**

An IP address followed by a slash and a number.

Example:

`192.168.1.0/24`

Here:

- IP address = `192.168.1.0`
    
- Prefix length = 24
    
- Network bits = 24
    
- Host bits = 8
    

### 1.5 [[Subnet Mask]]

A [[Subnet Mask]] separates the network portion and host portion of an IP address.

**Example:**

IP Address: `192.168.1.10`

Subnet Mask: `255.255.255.0`

Binary representation:

```
IP:    11000000.10101000.00000001.00001010
Mask:  11111111.11111111.11111111.00000000
```

The first 24 bits represent the network portion, while the remaining 8 bits represent the host portion.

### 1.6 [[CIDR Prefix Length]]

The prefix length indicates how many bits are used for the network portion of an IPv4 address.

Examples:

|CIDR Prefix|Subnet Mask|Host Bits|
|---|---|---|
|/8|255.0.0.0|24|
|/16|255.255.0.0|16|
|/24|255.255.255.0|8|
|/25|255.255.255.128|7|
|/26|255.255.255.192|6|
|/27|255.255.255.224|5|
|/28|255.255.255.240|4|
|/29|255.255.255.248|3|
|/30|255.255.255.252|2|

### 1.7 [[Subnetting]]

[[Subnetting]] is the process of dividing a large network into smaller logical networks called subnets.

**Advantages:**

- Efficient use of IP addresses.
    
- Reduces broadcast traffic within each subnet.
    
- Improves network management.
    
- Helps organise large networks.
    
- Supports network segmentation.
    

### 1.8 [[Subnetting Formulas]]

For an IPv4 network with prefix length `$n$`:

**Number of Host Bits:**

$$  
h=32-n  
$$

**Total Number of Addresses:**

$$  
2^{32-n}  
$$

**Usable Host Addresses:**

$$  
2^{32-n}-2  
$$

The subtraction of 2 accounts for the network and broadcast addresses in a conventional IPv4 subnet with at least two host bits.

**Block Size:**

$$  
\text{Block Size}=256-\text{Subnet Mask Value}  
$$

Use the subnet-mask value in the octet where subnetting occurs.

**Number of Subnets:**

If `$s$` bits are borrowed from the original host portion:

$$  
\text{Number of Subnets}=2^s  
$$

**Important:** The formula for usable hosts does not apply in the usual way to `/31` point-to-point networks and `/32` host routes.

### 1.9 [[Subnetting Numerical Example 1]]

**Question:**

Find the network address, broadcast address and usable host range for:

`192.168.1.0/24`

**Step 1: Identify the prefix.**

Prefix = `/24`

Host bits:

$$  
h=32-24=8  
$$

**Step 2: Calculate total addresses.**

$$  
2^8=256  
$$

**Step 3: Calculate usable hosts.**

$$  
256-2=254  
$$

**Answer:**

- Network Address: `192.168.1.0`
    
- First Usable Address: `192.168.1.1`
    
- Last Usable Address: `192.168.1.254`
    
- Broadcast Address: `192.168.1.255`
    
- Total Addresses: 256
    
- Usable Hosts: 254
    

### 1.10 [[Subnetting Numerical Example 2]]

**Question:**

Find the subnet details for:

`192.168.1.0/26`

**Step 1: Calculate host bits.**

$$  
h=32-26=6  
$$

**Step 2: Calculate total addresses.**

$$  
2^6=64  
$$

**Step 3: Calculate usable hosts.**

$$  
64-2=62  
$$

**Step 4: Find subnet mask.**

`/26` = `255.255.255.192`

**Step 5: Calculate block size.**

$$  
256-192=64  
$$

Therefore, the subnet ranges increase by 64 in the last octet.

|Subnet|Network Address|Usable Host Range|Broadcast|
|---|---|---|---|
|1|192.168.1.0|.1 – .62|.63|
|2|192.168.1.64|.65 – .126|.127|
|3|192.168.1.128|.129 – .190|.191|
|4|192.168.1.192|.193 – .254|.255|

**Final Answer for the first subnet:**

- Network: `192.168.1.0`
    
- First Host: `192.168.1.1`
    
- Last Host: `192.168.1.62`
    
- Broadcast: `192.168.1.63`
    
- Usable Hosts: 62
    

### 1.11 [[Subnetting Numerical Example 3]]

**Question:**

A network needs at least 50 usable host addresses. Find the required prefix length.

**Step 1: Use the host formula.**

$$  
2^h-2\geq50  
$$

**Step 2: Find the smallest suitable host-bit count.**

For `$h=5$`:

$$  
2^5-2=30  
$$

Not sufficient.

For `$h=6$`:

$$  
2^6-2=62  
$$

Sufficient.

**Step 3: Calculate the prefix length.**

$$  
n=32-6=26  
$$

**Answer:** The required subnet is `/26`, which provides 62 usable host addresses.

### 1.12 [[Classful Addressing]] vs [[CIDR]]

|Classful Addressing|CIDR|
|---|---|
|Uses fixed address classes|Uses variable prefix lengths|
|Fixed default subnet masks|Flexible subnet masks|
|Less efficient address allocation|More efficient address allocation|
|Limited flexibility|Supports VLSM|
|Older addressing method|Modern addressing method|

---

### 1.13 [[Network Address Translation (NAT)]]

[[Network Address Translation (NAT)]] is a technique that modifies IP address information in packet headers as packets pass through a router or firewall.

It allows devices using private IP addresses to communicate with public networks.

**Why is NAT used?**

- Conserves public IPv4 addresses.
    
- Allows private networks to access the Internet.
    
- Hides internal addressing structure from external networks.
    
- Allows multiple private devices to share public IP addresses.
    

#### A. [[Static NAT]]

Static NAT establishes a permanent one-to-one mapping between a private IP address and a public IP address.

**Example:**

```
Private IP       Public IP
192.168.1.10  →  203.0.113.10
```

**Features:**

- Fixed mapping.
    
- One private address uses one public address.
    
- Useful when an internal server needs a consistent public address.
    

#### B. [[Dynamic NAT]]

Dynamic NAT maps private IP addresses to public IP addresses selected from a pool.

**Working:**

1. A private device requests Internet access.
    
2. NAT selects an available public IP from the pool.
    
3. The router creates a temporary mapping.
    
4. The mapping is released when no longer needed according to the NAT implementation.
    

**Example:**

Public IP pool:

- `203.0.113.10`
    
- `203.0.113.11`
    
- `203.0.113.12`
    

Private devices receive available public IP addresses from this pool.

#### C. [[Port Address Translation (PAT)]]

PAT is also called [[NAT Overload]].

It allows multiple private devices to share a single public IP address by using different port numbers.

**Example:**

|Private Address|Public Address|
|---|---|
|192.168.1.10:5000|203.0.113.5:40001|
|192.168.1.11:5000|203.0.113.5:40002|
|192.168.1.12:5000|203.0.113.5:40003|

All devices use the same public IP address, but different port mappings distinguish their connections.

**Features:**

- Supports many devices using one public IPv4 address.
    
- Uses port numbers to identify individual connections.
    
- Commonly used in home and office routers.
    

#### D. [[NAT Translation Table]]

A NAT router maintains a translation table containing mapping information.

Example:

|Private IP:Port|Public IP:Port|
|---|---|
|192.168.1.10:5000|203.0.113.5:40001|
|192.168.1.11:5000|203.0.113.5:40002|
|192.168.1.12:5000|203.0.113.5:40003|

When a response arrives, the router checks the destination public IP and port, then forwards the packet to the correct private device.

#### E. [[Advantages of NAT]]

- Conserves public IPv4 addresses.
    
- Allows multiple devices to share one public IP.
    
- Makes internal addressing easier to change.
    
- Hides internal IP addressing from external networks.
    

#### F. [[Limitations of NAT]]

- Can complicate peer-to-peer communication.
    
- May interfere with applications that embed IP addresses in their payloads.
    
- Can complicate incoming connections and server hosting.
    
- Adds processing and connection-tracking overhead.
    
- Can complicate troubleshooting.
    
- NAT is not a substitute for a firewall or a complete security mechanism.
    

### 1.14 [[Types of NAT Comparison]]

| Static NAT                               | Dynamic NAT                    | PAT                     |
| ---------------------------------------- | ------------------------------ | ----------------------- |
| One-to-one mapping                       | Pool-based mapping             | Many-to-one mapping     |
| Fixed public IP                          | Public IP selected dynamically | Shared public IP        |
| Usually one public IP per private device | Uses a pool of public IPs      | Uses port numbers       |
| Useful for servers                       | Useful for temporary mappings  | Common in home networks |

---

## 2. [[IPv4 and IPv6]]

### 2.1 [[IPv4]]

[[Internet Protocol Version 4 (IPv4)]] is the fourth version of the Internet Protocol.

**Features:**

- Uses 32-bit addresses.
    
- Written in dotted-decimal notation.
    
- Supports approximately 4.3 billion addresses.
    
- Uses connectionless packet delivery.
    
- Supports fragmentation by routers and source hosts.
    

**Example:**

`192.168.1.1`

**Address Space:**

$$  
2^{32}=4,294,967,296  
$$

### 2.2 [[IPv4 Header]]

An IPv4 packet contains a header and payload.

Important header fields:

|Field|Function|
|---|---|
|Version|Identifies IP version|
|IHL|Specifies header length|
|Type of Service / DS field|Indicates service and traffic-handling information|
|Total Length|Total packet length|
|Identification|Identifies fragments belonging to the same original packet|
|Flags|Controls fragmentation|
|Fragment Offset|Indicates fragment position|
|TTL|Limits packet lifetime|
|Protocol|Identifies the upper-layer protocol|
|Header Checksum|Detects errors in the IPv4 header|
|Source Address|Sender's IP address|
|Destination Address|Receiver's IP address|

### 2.3 [[Time-to-Live (TTL)]]

[[Time-to-Live (TTL)]] is an 8-bit field in the IPv4 header that limits how long a packet can remain in the network.

**Working:**

1. Sender assigns an initial TTL value.
    
2. Each router decreases the TTL by at least one.
    
3. If TTL becomes zero, the router discards the packet.
    
4. The router usually sends an [[ICMP Time Exceeded]] message to the source.
    

**Purpose:**

- Prevents packets from circulating indefinitely.
    
- Helps avoid routing loops consuming network resources.
    

**Example:**

If a packet starts with TTL = 5:

|Router|TTL|
|---|---|
|Before first router|5|
|After first router|4|
|After second router|3|
|After third router|2|
|After fourth router|1|
|After fifth router|0 – Discarded|

### 2.4 [[ICMP Time Exceeded]]

[[Internet Control Message Protocol (ICMP)]] is used for error reporting and diagnostic messages in IP networks.

An [[ICMP Time Exceeded]] message is generated when a packet's TTL expires.

**Important:**

- The packet is discarded.
    
- The router sends an ICMP message to the original sender.
    
- The message helps identify routing problems.
    

**Use in [[Traceroute]]:**

Traceroute uses packets with increasing TTL values to discover routers along a path.

### 2.5 [[IPv4 Fragmentation]]

[[IPv4 Fragmentation]] occurs when an IP packet is larger than the [[Maximum Transmission Unit (MTU)]] of the outgoing network link.

The packet is divided into smaller fragments.

**Important IPv4 Fragmentation Fields:**

#### A. [[Identification]]

- A 16-bit field.
    
- Identifies fragments belonging to the same original packet.
    
- All fragments of a packet carry the same identification value.
    

#### B. [[More Fragments (MF) Flag]]

- A 1-bit flag.
    
- MF = 1 means more fragments follow.
    
- MF = 0 means this is the last fragment.
    

#### C. [[Fragment Offset]]

- Indicates the position of a fragment in the original packet.
    
- Measured in units of 8 bytes.
    

**Important:** All fragments except the final fragment normally contain a data payload whose length is a multiple of 8 bytes.

**Fragmentation Example:**

Suppose an IPv4 packet has:

- Original total size = 4000 bytes.
    
- Header size = 20 bytes.
    
- MTU = 1500 bytes.
    

Maximum data per full-sized fragment:

$$  
1500-20=1480\text{ bytes}  
$$

Original data size:

$$  
4000-20=3980\text{ bytes}  
$$

Fragmentation:

|Fragment|Data Size|Total Size|Fragment Offset|MF|
|---|---|---|---|---|
|1|1480|1500|0|1|
|2|1480|1500|185|1|
|3|1020|1040|370|0|

Offset calculations:

$$  
\frac{1480}{8}=185  
$$

$$  
\frac{2960}{8}=370  
$$

**Answer:** The packet is divided into three fragments.

**Note:** In IPv4, routers may fragment packets when allowed. If the Don't Fragment (DF) flag is set and fragmentation is required, the router discards the packet and can return an ICMP error.

### 2.6 [[IPv6]]

[[Internet Protocol Version 6 (IPv6)]] is the newer version of the Internet Protocol designed to overcome IPv4 address exhaustion and improve IP network operation.

**Features:**

- Uses 128-bit addresses.
    
- Written in hexadecimal notation.
    
- Provides a very large address space.
    
- Has a simplified fixed base header.
    
- Supports automatic address configuration.
    
- Does not use broadcast addressing.
    
- Routers do not fragment packets; fragmentation is performed by the source using an extension header.
    

**Example:**

`2001:db8:abcd:0012:0000:0000:0000:0001`

It can be shortened to:

`2001:db8:abcd:12::1`

**Address Space:**

$$  
2^{128}  
$$

### 2.7 [[IPv4 vs IPv6]]

|Feature|IPv4|IPv6|
|---|---|---|
|Address length|32 bits|128 bits|
|Address format|Decimal|Hexadecimal|
|Address example|192.168.1.1|2001:db8::1|
|Header size|Variable, 20–60 bytes|Fixed, 40 bytes|
|Address space|Limited|Extremely large|
|Configuration|Manual or DHCP|SLAAC and DHCPv6|
|Broadcast|Supported|Not supported|
|Fragmentation|Source and routers may fragment|Source only|
|Header checksum|Present|Not present|
|Security|IPsec support available|IPsec support standardised|
|NAT|Commonly used|Generally not required for address conservation|

### 2.8 [[IPv6 Address Configuration]]

IPv6 supports multiple methods of address configuration.

#### A. [[SLAAC (Stateless Address Autoconfiguration)]]

- A device automatically configures its IPv6 address.
    
- Uses information advertised by routers.
    
- Does not require a DHCPv6 server for address assignment.
    

#### B. [[DHCPv6]]

- Uses a DHCP server to provide IPv6 configuration information.
    
- Can assign addresses and other network settings.
    
- Can operate alongside SLAAC.
    

### 2.9 [[IPv6 Security]]

- IPv6 supports IPsec through standardised protocol specifications.
    
- IPsec can provide authentication, integrity and confidentiality.
    
- Security still depends on correct configuration.
    
- IPv6 does not automatically make a network secure.
    

---

## 3. [[Address Resolution and Routing]]

### 3.1 [[Address Resolution Protocol (ARP)]]

[[ARP]] is used in IPv4 networks to find the MAC address associated with a known IPv4 address on the local network.

**Purpose:**

It converts a known [[IPv4 Address]] into a corresponding [[MAC Address]].

**Example:**

A computer wants to send data to:

`192.168.1.20`

But it does not know the destination MAC address.

It uses ARP to discover it.

### 3.2 [[ARP Resolution Process]]

**Step 1: Check ARP Cache**

The sender checks its [[ARP Cache]] to see whether the destination IP-to-MAC mapping is already available.

**Step 2: Broadcast ARP Request**

If no mapping exists, the sender broadcasts an ARP request to the local network.

Example:

"Who has 192.168.1.20? Tell 192.168.1.10."

**Step 3: Unicast ARP Reply**

The device with the requested IP address sends an ARP reply containing its MAC address.

**Step 4: Update ARP Cache**

The sender stores the IP-to-MAC mapping in its ARP cache for future communication.

**Step 5: Send Ethernet Frame**

The sender uses the discovered MAC address to construct and transmit the Ethernet frame.

**Important:**

- ARP Request → Broadcast.
    
- ARP Reply → Usually Unicast.
    
- ARP Cache → Stores IP-to-MAC mappings.
    

### 3.3 [[Reverse Address Resolution Protocol (RARP)]]

[[RARP]] is an older protocol used by a device to discover its IP address when it knows its MAC address.

**Purpose:**

It performs the reverse operation of ARP.

- ARP: IP address → MAC address.
    
- RARP: MAC address → IP address.
    

**Working:**

1. A device sends a RARP request containing its MAC address.
    
2. A RARP server receives the request.
    
3. The server checks its configured mapping.
    
4. It returns the corresponding IP address.
    

**Limitations:**

- Requires a RARP server on the local network.
    
- Provides limited configuration information.
    
- Has largely been replaced by [[BOOTP]] and [[DHCP]].
    

### 3.4 [[ARP vs RARP]]

|ARP|RARP|
|---|---|
|Maps IP address to MAC address|Maps MAC address to IP address|
|Used in IPv4 local network communication|Historically used for IP address discovery|
|ARP request is broadcast|RARP request is broadcast|
|ARP reply usually unicast|RARP reply generally unicast|
|Still used in IPv4 networks|Obsolete in modern networks|

### 3.5 [[Forwarding and Routing]]

#### A. [[Forwarding]]

[[Forwarding]] is the process of moving an incoming packet from a router's input interface to the appropriate output interface.

- Happens inside a router.
    
- Uses the [[Forwarding Table]].
    
- Determines the next hop or outgoing interface.
    

#### B. [[Routing]]

[[Routing]] is the process of determining the best path for packets to travel from source to destination across networks.

- Uses [[Routing Algorithms]].
    
- Builds or updates routing tables.
    
- Determines suitable paths through a network.
    

**Remember:**

- Routing → Finds the path.
    
- Forwarding → Sends the packet through the selected interface.
    

### 3.6 [[Default Gateway]]

A [[Default Gateway]] is the router interface that a device uses to send packets to destinations outside its local subnet.

**Working Procedure:**

1. A device checks whether the destination IP belongs to its local subnet.
    
2. It compares the destination address with its own address using the subnet mask.
    
3. If the destination is local, it sends the frame directly to the destination.
    
4. If the destination is on another network, it sends the frame to the default gateway.
    
5. The router forwards the packet towards the destination network.
    

**Example:**

Computer:

- IP: `192.168.1.10`
    
- Subnet Mask: `255.255.255.0`
    
- Default Gateway: `192.168.1.1`
    

Destination: `8.8.8.8`

Since `8.8.8.8` is outside the local subnet, the computer sends the packet to `192.168.1.1`.

**Important:** The destination IP remains the final destination IP. The local Ethernet frame is addressed to the gateway's MAC address.

### 3.7 [[Static Routing]]

[[Static Routing]] is a routing method in which network routes are manually configured by a network administrator.

**Features:**

- Routes are entered manually.
    
- No automatic route discovery.
    
- Suitable for small and stable networks.
    
- Does not automatically adapt to network failures.
    

**Advantages:**

- Simple in small networks.
    
- Low routing overhead.
    
- Predictable routing behaviour.
    
- More administrative control.
    

**Disadvantages:**

- Manual configuration required.
    
- Difficult to maintain in large networks.
    
- Does not automatically adapt to topology changes.
    

### 3.8 [[Dynamic Routing]]

[[Dynamic Routing]] allows routers to automatically learn and update routes using routing protocols.

**Features:**

- Automatically discovers routes.
    
- Adjusts to network changes.
    
- Uses routing algorithms.
    
- Suitable for medium and large networks.
    

**Examples:**

- [[RIP]]
    
- [[OSPF]]
    
- [[BGP]]
    

**Advantages:**

- Automatically adapts to network changes.
    
- Reduces manual configuration.
    
- Supports large and complex networks.
    

**Disadvantages:**

- Requires additional processing and memory.
    
- Uses network bandwidth for routing updates.
    
- More complex to configure and troubleshoot.
    

### 3.9 [[Static Routing vs Dynamic Routing]]

|Static Routing|Dynamic Routing|
|---|---|
|Manually configured|Automatically learns routes|
|No routing protocol required|Uses routing protocols|
|Low overhead|Higher overhead|
|Suitable for small networks|Suitable for large networks|
|Does not automatically adapt|Adapts to topology changes|
|Simple configuration in small networks|More complex configuration|

### 3.10 [[Routing Algorithms]]

Routing algorithms determine the best path for packets to travel through a network.

Two important categories are:

- [[Distance Vector Routing]]
    
- [[Link State Routing]]
    

#### A. [[Distance Vector Routing]]

[[Distance Vector Routing]] is a routing method in which each router shares information about its known destinations and distances with neighbouring routers.

**Working Procedure:**

1. Each router maintains a routing table.
    
2. It shares its routing information with neighbouring routers.
    
3. Routers receive updates from neighbours.
    
4. They calculate the best route using distance information.
    
5. Routing tables are updated when a better route is found.
    

**Characteristics:**

- Uses information from neighbouring routers.
    
- Often uses hop count or another distance metric.
    
- Simpler than link-state routing.
    
- Can experience slow convergence and routing loops.
    

**Example: [[RIP (Routing Information Protocol)]]**

RIP is a distance-vector routing protocol.

- Uses hop count as its metric.
    
- Maximum usable hop count is 15.
    
- A hop count of 16 indicates an unreachable destination.
    
- Uses periodic routing updates.
    

#### B. [[Link State Routing]]

[[Link State Routing]] is a routing method in which routers build a map of the network topology and calculate the shortest paths.

**Working Procedure:**

1. Each router discovers its neighbouring routers.
    
2. It measures or determines the cost of its links.
    
3. It creates [[Link State Advertisements (LSAs)]].
    
4. LSAs are distributed throughout the routing area.
    
5. Routers build a topology database.
    
6. Each router calculates shortest paths using [[Dijkstra's Algorithm]].
    

**Characteristics:**

- Builds a network topology map.
    
- Uses link costs.
    
- Faster convergence in many network designs.
    
- Requires more memory and processing power than basic distance-vector routing.
    

**Example: [[OSPF (Open Shortest Path First)]]**

OSPF is a link-state routing protocol.

- Uses cost as its routing metric.
    
- Uses Dijkstra's shortest-path algorithm.
    
- Supports hierarchical routing areas.
    
- Commonly used in enterprise networks.
    

### 3.11 [[Distance Vector vs Link State Routing]]

|Distance Vector|Link State|
|---|---|
|Shares routing information with neighbours|Distributes link-state information|
|Knows routes from neighbour updates|Builds a topology map|
|Uses distance metrics|Uses link costs|
|Simpler implementation|More complex implementation|
|Generally slower convergence|Generally faster convergence|
|Lower resource requirements|Higher resource requirements|
|Example: RIP|Example: OSPF|

---

## 4. [[Important Formula Sheet]]

|Topic|Formula|
|---|---|
|IPv4 address space|$2^{32}$|
|IPv6 address space|$2^{128}$|
|Host bits|$h=32-n$|
|Total IPv4 addresses|$2^{32-n}$|
|Usable IPv4 hosts|$2^{32-n}-2$|
|Subnet block size|$256-\text{Mask Value}$|
|Number of subnets|$2^s$|
|Required host condition|$2^h-2\geq H$|
|CIDR prefix|$n=32-h$|
|Fragment offset|$\text{Bytes before fragment}/8$|

**Formula Variables:**

- `$n$` = CIDR prefix length.
    
- `$h$` = Number of host bits.
    
- `$s$` = Number of borrowed subnet bits.
    
- `$H$` = Required usable hosts.
    

---

## 5. [[Important Differences for Exams]]

### 5.1 [[Public IP]] vs [[Private IP]]

|Public IP|Private IP|
|---|---|
|Globally unique|Reusable across networks|
|Routable over Internet|Not directly Internet-routable|
|Assigned by ISP or authorised organisation|Assigned within private networks|
|Used for public communication|Used for local communication|

### 5.2 [[IPv4]] vs [[IPv6]]

|IPv4|IPv6|
|---|---|
|32-bit|128-bit|
|Decimal notation|Hexadecimal notation|
|Variable header|Fixed base header|
|Supports broadcast|No broadcast|
|Routers may fragment|Source performs fragmentation|
|Header checksum present|No header checksum|

### 5.3 [[ARP]] vs [[RARP]]

|ARP|RARP|
|---|---|
|IP to MAC|MAC to IP|
|Used for address resolution|Historically used for IP discovery|
|Still used in IPv4|Obsolete|

### 5.4 [[Routing]] vs [[Forwarding]]

|Routing|Forwarding|
|---|---|
|Determines the best path|Sends packets through an interface|
|Uses routing algorithms|Uses forwarding table|
|Network-wide path decision|Local router operation|
|Control-plane function|Data-plane function|

### 5.5 [[Distance Vector]] vs [[Link State]]

|Distance Vector|Link State|
|---|---|
|Shares information with neighbours|Shares link-state information|
|Uses distance metrics|Uses link costs|
|Example: RIP|Example: OSPF|
|Simpler|More complex|
|Generally slower convergence|Generally faster convergence|

---

## 6. [[Important Questions for Examination]]

### [[Long-Answer Questions]]

1. Explain [[Public IP Address]] and [[Private IP Address]] with examples.
    
2. Explain [[Classful Addressing]] and [[CIDR]].
    
3. Solve numerical problems on [[Subnetting]], including network address, broadcast address and usable host range.
    
4. Explain [[Network Address Translation (NAT)]] and its types.
    
5. Explain the [[IPv4 Header]] and its important fields.
    
6. Explain [[TTL]] and [[ICMP Time Exceeded]] messages.
    
7. Explain [[IPv4 Fragmentation]] with an example.
    
8. Compare [[IPv4]] and [[IPv6]].
    
9. Explain the [[ARP Resolution Process]] step by step.
    
10. Differentiate between [[ARP]] and [[RARP]].
    
11. Explain [[Default Gateway]] and packet forwarding across subnets.
    
12. Differentiate between [[Static Routing]] and [[Dynamic Routing]].
    
13. Explain [[Distance Vector Routing]] and [[Link State Routing]] with examples.
    

### [[Short-Answer Questions]]

1. What is an [[IP Address]]?
    
2. Define [[Subnet Mask]].
    
3. What is [[CIDR]]?
    
4. What is a [[Network Address]]?
    
5. What is a [[Broadcast Address]]?
    
6. Define [[NAT]].
    
7. What is [[PAT]]?
    
8. What is [[TTL]]?
    
9. What is [[ICMP]]?
    
10. What is [[Fragment Offset]]?
    
11. What is [[MTU]]?
    
12. What is [[ARP]]?
    
13. What is [[RARP]]?
    
14. What is a [[Default Gateway]]?
    
15. Define [[Static Routing]].
    
16. What is [[Dynamic Routing]]?
    
17. What is [[RIP]]?
    
18. What is [[OSPF]]?
    

---

## 7. [[Quick Revision Checklist]]

- [[IP Addressing]]
    
- [[Public IP Address]] and [[Private IP Address]]
    
- [[Classful Addressing]]
    
- [[CIDR]]
    
- [[Subnet Mask]] and [[Prefix Length]]
    
- [[Subnetting]] numericals
    
- [[Network Address]] and [[Broadcast Address]]
    
- [[Network Address Translation (NAT)]]
    
- [[Static NAT]], [[Dynamic NAT]] and [[PAT]]
    
- [[IPv4]] and [[IPv4 Header]]
    
- [[Time-to-Live (TTL)]]
    
- [[ICMP Time Exceeded]]
    
- [[IPv4 Fragmentation]]
    
- [[IPv6]] and [[IPv4 vs IPv6]]
    
- [[ARP]] and [[RARP]]
    
- [[ARP Resolution Process]]
    
- [[Forwarding]] and [[Routing]]
    
- [[Default Gateway]]
    
- [[Static Routing]] and [[Dynamic Routing]]
    
- [[Distance Vector Routing]]
    
- [[Link State Routing]]
    
- [[RIP]] and [[OSPF]]
    

---

## 8. [[Recommended Study Order]]

1. **Addressing fundamentals:** Study [[Public IP]], [[Private IP]], [[Classful Addressing]] and [[CIDR]].
    
2. **Practise subnetting:** Focus on [[Subnet Mask]], [[Block Size]], [[Network Address]], [[Broadcast Address]] and usable host calculations.
    
3. **Understand NAT:** Learn [[Static NAT]], [[Dynamic NAT]] and [[PAT]] with translation-table examples.
    
4. **Study IP versions:** Understand [[IPv4]], [[IPv6]], [[TTL]] and [[IPv4 Fragmentation]].
    
5. **Learn address resolution:** Practise the [[ARP Resolution Process]] and understand [[RARP]].
    
6. **Finish routing:** Study [[Default Gateway]], [[Static Routing]], [[Dynamic Routing]], [[Distance Vector Routing]] and [[Link State Routing]].
    

**Exam priority:** Give particular attention to [[Subnetting]] numericals, [[CIDR]], [[NAT]] types, [[IPv4 Fragmentation]], [[ARP]] working, and the comparison between [[Distance Vector Routing]] and [[Link State Routing]].