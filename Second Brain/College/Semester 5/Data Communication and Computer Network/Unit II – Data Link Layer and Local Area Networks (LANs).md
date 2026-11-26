## 1. [[Data Link Layer Fundamentals]]

### 1.1 [[Introduction to Data Link Layer]]

The [[Data Link Layer]] is the second layer of the [[OSI Model]]. It provides reliable **node-to-node communication** over a physical link.

- Receives [[Packets]] from the [[Network Layer]].
    
- Converts packets into [[Frames]].
    
- Adds headers and trailers for addressing and [[Error Detection]].
    
- Transfers frames between directly connected devices.
    
- At the receiver, checks the frame and extracts the network-layer packet.
    

**Example:** When data travels from your laptop to a router, the Data Link Layer handles communication between those two directly connected devices.

### 1.2 [[Node-to-Node Communication]]

- Communication takes place between two directly connected devices.
    
- Also called [[Hop-by-Hop Communication]].
    
- Each router removes the incoming frame and creates a new frame for the next link.
    
- The network-layer packet is generally forwarded across multiple hops, while the link-layer frame is rebuilt at each hop.
    

**Important:**

- [[Data Link Layer]] → Node-to-node delivery.
    
- [[Network Layer]] → Source-to-destination delivery.
    

### 1.3 [[Sublayers of Data Link Layer]]

The Data Link Layer is divided into two sublayers:

#### A. [[Data Link Control (DLC)]]

Responsible for controlling communication between directly connected devices.

Functions:

- [[Framing]].
    
- [[Flow Control]].
    
- [[Error Detection and Correction]].
    
- Reliable link management.
    

#### B. [[Media Access Control (MAC)]]

Controls how devices access and share a common transmission medium.

Functions:

- Physical addressing using [[MAC Addresses]].
    
- [[Channel Access Control]].
    
- [[Collision Handling]].
    
- Frame transmission over shared media.
    

|DLC|MAC|
|---|---|
|Controls the data link|Controls access to the medium|
|Framing and error control|Physical addressing and channel access|
|Manages link communication|Manages shared-medium communication|

### 1.4 [[Types of Links]]

#### A. [[Point-to-Point Link]]

A dedicated communication link between exactly two devices.

- No other device shares the link.
    
- Communication is generally simpler.
    
- Example: A direct connection between two routers.
    

#### B. [[Broadcast Link]]

A shared communication medium connected to multiple devices.

- Multiple devices use the same channel.
    
- Frames may be received by several devices.
    
- [[MAC Protocols]] control access to the medium.
    
- Example: Traditional shared Ethernet and wireless LANs.
    

### 1.5 [[Packet Delivery Behaviour]]

Packet delivery across a network may experience:

1. **[[Variable Delay]]:** Packets may take different amounts of time to reach the destination.
    
2. **[[Out-of-Order Arrival]]:** Packets may arrive in a different order from which they were sent.
    
3. **[[Packet Loss]]:** Packets may be dropped due to congestion, errors, or link failure.
    

**Important:** The Data Link Layer handles frame delivery on an individual link. End-to-end packet ordering and recovery are generally handled by higher layers.

---

## 2. [[Framing]]

### 2.1 [[Meaning of Framing]]

[[Framing]] is the process of dividing a continuous stream of bits into smaller units called [[Frames]].

The Data Link Layer uses framing to identify the beginning and end of each data unit.

### 2.2 [[Purpose of Framing]]

- Identifies frame boundaries.
    
- Organises data into manageable units.
    
- Supports addressing.
    
- Helps in error detection.
    
- Supports flow control and reliable transmission.
    

### 2.3 [[Basic Frame Structure]]

A frame generally contains three main parts:

| Component   | Function                                             |
| ----------- | ---------------------------------------------------- |
| [[Header]]  | Contains addressing and control information          |
| [[Payload]] | Contains the network-layer packet                    |
| [[Trailer]] | Contains error-detection information such as [[FCS]] |

**Structure:**

`Header | Payload | Trailer (FCS)`

- **[[Header]]:** Identifies the destination, source, and other control information.
    
- **[[Payload]]:** Carries actual data.
    
- **[[Trailer]]:** Often contains the [[Frame Check Sequence (FCS)]].
    

### 2.4 [[Frame Boundary Marking Methods]]

#### A. [[Length Field]]

- A length field in the header specifies the size of the frame or payload.
    
- The receiver reads the length and identifies where the frame ends.
    
- Simple to implement.
    
- If the length field becomes corrupted, frame synchronisation may be affected.
    

**Example:** If the length field specifies 100 bytes, the receiver reads the specified number of bytes.

#### B. [[Byte Stuffing]]

Used in byte-oriented protocols.

- Special bytes mark the beginning and end of a frame.
    
- If the same special byte appears inside the data, an [[Escape Byte]] is inserted before it.
    
- The receiver removes the inserted escape byte.
    

**Example:**

Original data:

`A FLAG B`

Transmitted data:

`A ESC FLAG B`

Here, `ESC` indicates that the following FLAG is part of the data, not a frame boundary.

#### C. [[Bit Stuffing]]

Used in bit-oriented protocols.

- A special bit pattern identifies frame boundaries.
    
- In [[HDLC]], the flag pattern is `01111110`.
    
- Whenever five consecutive 1s occur in the data, the sender inserts a 0.
    
- The receiver removes the inserted 0.
    

**Example:**

If five consecutive 1s occur in the data, a 0 is inserted after them to prevent confusion with the frame flag.

**Remember:**

- [[Byte Stuffing]] → Inserts an escape byte.
    
- [[Bit Stuffing]] → Inserts a 0 after five consecutive 1s.
    

---

## 3. [[Error Control: Detection and Correction]]

### 3.1 [[Types of Errors]]

During transmission, [[Noise]] may change the original bits.

#### A. [[Single-Bit Error]]

Only one bit in the transmitted data changes.

Example:

Sent: `1011001`

Received: `1010001`

Only one bit is incorrect.

#### B. [[Burst Error]]

Two or more bits within a sequence are affected.

Example:

Sent: `101100101`

Received: `100011101`

**[[Burst Length]]** is measured from the first corrupted bit to the last corrupted bit, including any unchanged bits between them.

**Important:** At a higher [[Data Rate]], more bits can be transmitted during the same noise duration. Therefore, the possible burst length increases.

### 3.2 [[Redundancy]]

[[Redundancy]] means adding extra bits to the original data to detect or correct transmission errors.

Example:

Original data: `1011`

Transmitted data: `10111`

The additional bit provides information that can help detect an error.

### 3.3 [[Error Detection]] vs [[Error Correction]]

|Error Detection|Error Correction|
|---|---|
|Identifies whether an error occurred|Identifies and corrects certain errors|
|Usually requires retransmission|Can correct errors without retransmission|
|Uses parity, checksum and CRC|Uses Hamming code and FEC|
|Less redundancy may be required|Usually requires more redundancy|

### 3.4 [[Forward Error Correction (FEC)]] vs [[Automatic Repeat reQuest (ARQ)]]

#### A. [[Forward Error Correction (FEC)]]

- Sender adds sufficient redundant bits.
    
- Receiver detects and corrects errors without requesting retransmission.
    
- Useful where retransmission is expensive or impossible.
    
- Example: Satellite communication and digital broadcasting.
    

#### B. [[Automatic Repeat reQuest (ARQ)]]

- Receiver detects an error or missing frame.
    
- It requests retransmission using acknowledgements.
    
- Sender retransmits the required frame.
    
- Example: [[Stop-and-Wait ARQ]].
    

|FEC|ARQ|
|---|---|
|Corrects errors using redundant bits|Corrects errors through retransmission|
|No retransmission required for correctable errors|Retransmission is required|
|Higher coding overhead|Requires feedback and retransmission|

### 3.5 [[Block Coding]]

[[Block Coding]] converts a group of data bits into a longer codeword by adding redundant bits.

Important terms:

- `$k$` = Number of original data bits.
    
- `$r$` = Number of redundant bits.
    
- `$n$` = Total number of codeword bits.
    

**Codeword Length:**

$$  
n = k + r  
$$

#### [[Code Rate]]

The fraction of transmitted bits that represent original data.

$$  
R = \frac{k}{n}  
$$

#### [[Redundancy Ratio]]

The fraction of transmitted bits used for redundancy.

$$  
\text{Redundancy Ratio} = \frac{r}{n}  
$$

**Example:**

Given:

- Data bits = 4
    
- Redundant bits = 3
    

Therefore:

$$  
n = 4+3=7  
$$

$$  
R = \frac{4}{7}=0.5714  
$$

$$  
\text{Redundancy Ratio} = \frac{3}{7}=0.4286  
$$

Code rate = 57.14%

Redundancy ratio = 42.86%

### 3.6 [[Error Detection Techniques]]

#### A. [[Parity Check (VRC)]]

[[Vertical Redundancy Check (VRC)]] is a simple error-detection technique that adds one parity bit to a group of data bits.

**1. [[Even Parity]]**

The parity bit is selected so that the total number of 1s becomes even.

Example:

Data: `1011`

Number of 1s = 3

Parity bit = 1

Transmitted data: `10111`

Total number of 1s = 4 (even).

**2. [[Odd Parity]]**

The parity bit is selected so that the total number of 1s becomes odd.

Example:

Data: `1011`

Number of 1s = 3

Parity bit = 0

Transmitted data: `10110`

Total number of 1s = 3 (odd).

**Limitations:**

- Detects all odd numbers of bit errors.
    
- Fails to detect an even number of bit errors.
    
- Cannot identify the exact location of an error.
    
- Cannot correct errors.
    

#### B. [[Checksum]]

A [[Checksum]] is an error-detection method that uses [[1's Complement Arithmetic]].

It is commonly associated with protocols such as [[IP]], [[TCP]] and [[UDP]].

**Working Procedure:**

1. Divide the data into fixed-size blocks.
    
2. Add [[Zero Padding]] if required to complete the final block.
    
3. Add all blocks using [[1's Complement Addition]].
    
4. If a carry is generated, wrap it around and add it to the result.
    
5. Take the 1's complement of the final sum.
    
6. Send the checksum along with the data.
    
7. The receiver adds all blocks, including the checksum.
    
8. If the final result contains all 1s, the data is considered valid.
    

**Example:**

Suppose two 4-bit data blocks are:

`1001` and `1100`

Step 1: Add them.

```
  1001
+ 1100
------
 10101
```

Step 2: Add the carry back to the result.

```
  0101
+ 0001
------
  0110
```

Step 3: Take the 1's complement.

```
0110 → 1001
```

Checksum = `1001`

**Limitations:**

- It may fail to detect certain error patterns.
    
- It is generally less powerful than CRC for detecting burst errors.
    
- It cannot correct errors.
    

#### C. [[Cyclic Redundancy Check (CRC)]]

[[Cyclic Redundancy Check (CRC)]] is a powerful error-detection technique used in data communication.

It treats binary data as a polynomial and uses [[Modulo-2 Division]].

**Important concepts:**

- [[Dataword]]: Original data bits.
    
- [[Generator Polynomial]]: A predefined binary divisor.
    
- [[CRC Bits]]: Remainder obtained from division.
    
- [[Frame Check Sequence (FCS)]]: Contains the CRC value.
    

**Working Procedure:**

1. Select a generator polynomial.
    
2. Append zeros to the original data.
    
3. The number of appended zeros equals the degree of the generator polynomial.
    
4. Divide the resulting bit sequence by the generator using [[XOR]].
    
5. The remainder is the CRC.
    
6. Append the remainder to the original data.
    
7. The receiver divides the received codeword by the same generator.
    
8. A non-zero remainder indicates an error.
    

**Important XOR Rules:**

|A|B|A XOR B|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

In CRC, subtraction is also performed using XOR.

**Example:**

Dataword = `1101`

Generator = `1011`

Generator length = 4 bits.

Therefore, append 3 zeros:

`1101000`

Perform modulo-2 division:

```
1101000 ÷ 1011
```

Remainder = `001`

Transmitted codeword:

`1101001`

At the receiver, divide the received codeword by `1011`.

- Remainder = `000` → No error detected.
    
- Non-zero remainder → Error detected.
    

**Note:** A zero remainder does not guarantee that no error occurred. Some error patterns may remain undetected.

**[[Ethernet]] and CRC:**

- Ethernet uses [[CRC-32]] for error detection.
    
- The CRC value is stored in the Ethernet [[Frame Check Sequence (FCS)]].
    
- The FCS is located in the frame trailer.
    

**[[CRC Efficiency and Overhead]]:**

If the original data contains `$k$` bits and the CRC contains `$r$` bits:

$$  
\text{Total Bits} = k+r  
$$

$$  
\text{Overhead} = \frac{r}{k+r}\times100  
$$

$$  
\text{Efficiency} = \frac{k}{k+r}\times100  
$$

**Example:**

If data = 1000 bits and CRC = 32 bits:

$$  
\text{Overhead}=\frac{32}{1032}\times100=3.10%  
$$

$$  
\text{Efficiency}=\frac{1000}{1032}\times100=96.90%  
$$

**Advantages:**

- Detects many common error patterns.
    
- Very effective for burst-error detection.
    
- Widely used in network protocols.
    

**Limitations:**

- Detects errors but does not correct them.
    
- Cannot identify the exact location of an error.
    

### 3.7 [[Error Correction: Hamming Code]]

[[Hamming Code]] is an error-correction technique that adds parity bits to data bits to detect and correct errors.

It is commonly used for [[Single-Bit Error Correction]].

#### A. [[Number of Redundant Bits]]

The number of parity bits is calculated using:

$$  
2^p \geq p+m+1  
$$

Where:

- `$p$` = Number of parity bits.
    
- `$m$` = Number of data bits.
    

**Example:**

For 4 data bits:

$$  
2^p \geq p+4+1  
$$

Try `$p=3$`:

$$  
2^3 \geq 3+4+1  
$$

$$  
8 \geq 8  
$$

Therefore, 3 parity bits are required.

Total codeword length:

$$  
n=m+p=4+3=7  
$$

This is called [[Hamming (7,4) Code]].

#### B. [[Parity Bit Positions]]

Parity bits are placed at positions that are powers of 2.

|Position|Bit Type|
|---|---|
|1|P1|
|2|P2|
|3|D1|
|4|P4|
|5|D2|
|6|D3|
|7|D4|

Therefore:

- P1 is at position 1.
    
- P2 is at position 2.
    
- P4 is at position 4.
    

#### C. [[Parity Checking]]

Each parity bit checks specific bit positions.

|Parity Bit|Positions Checked|
|---|---|
|P1|1, 3, 5, 7|
|P2|2, 3, 6, 7|
|P4|4, 5, 6, 7|

Assume [[Even Parity]].

Each parity group should contain an even number of 1s.

#### D. [[Syndrome and Error Detection]]

A [[Syndrome]] is a binary value obtained by checking the parity groups at the receiver.

- Syndrome `000` → No error detected.
    
- Non-zero syndrome → Indicates the position of a single-bit error.
    

**Example:**

Suppose the syndrome is:

`101`

Convert it into decimal:

$$  
(101)_2 = 5  
$$

Therefore, bit position 5 is incorrect.

The receiver corrects it by flipping the bit at position 5.

**Limitations:**

- Basic Hamming Code corrects single-bit errors.
    
- It cannot reliably correct multiple-bit errors.
    
- [[Extended Hamming Code]] adds an overall parity bit and can provide [[SECDED]] (Single Error Correction, Double Error Detection).
    

---

## 4. [[Flow Control and ARQ Protocols]]

### 4.1 [[Flow Control]]

[[Flow Control]] is a mechanism that regulates the speed of data transmission between sender and receiver.

Its main purpose is to prevent the sender from transmitting data faster than the receiver can process it.

**Why is it required?**

- Prevents [[Receiver Buffer Overflow]].
    
- Prevents frame drops.
    
- Maintains efficient communication.
    
- Handles differences in processing speeds.
    

### 4.2 [[ARQ (Automatic Repeat reQuest)]]

[[ARQ]] is an error-control technique that uses acknowledgements and retransmissions to ensure reliable frame delivery.

Main components:

- [[ACK (Acknowledgement)]]: Indicates successful reception.
    
- [[NAK (Negative Acknowledgement)]]: Indicates an error.
    
- [[Timeout]]: A period after which the sender retransmits if no expected ACK arrives.
    
- [[Sequence Number]]: Identifies individual frames.
    

### 4.3 [[Sliding Window Protocol]]

A [[Sliding Window Protocol]] allows multiple frames to be transmitted before receiving acknowledgements.

It improves [[Channel Utilisation]] compared with Stop-and-Wait.

**Important terms:**

- [[Sender Window]]: Frames that can be transmitted without waiting.
    
- [[Receiver Window]]: Frames that the receiver is prepared to accept.
    
- [[Sequence Number]]: Identifies each frame.
    
- [[ACK]]: Confirms successful reception.
    

### 4.4 [[Stop-and-Wait ARQ]]

The sender transmits one frame and waits for an acknowledgement before sending the next frame.

**Working Procedure:**

1. Sender transmits a frame.
    
2. Receiver receives and checks the frame.
    
3. Receiver sends an ACK if the frame is correct.
    
4. Sender receives the ACK and transmits the next frame.
    
5. If ACK is lost or a timeout occurs, the sender retransmits the frame.
    

**Example:**

```
Sender                 Receiver
  | ------ Frame 0 ------> |
  | <------- ACK 1 ------- |
  | ------ Frame 1 ------> |
  | <------- ACK 0 ------- |
```

**Advantages:**

- Simple to implement.
    
- Requires little buffer space.
    
- Easy to understand.
    

**Disadvantages:**

- Low channel utilisation on long-delay links.
    
- Sender remains idle while waiting for ACK.
    

### 4.5 [[Go-Back-N ARQ]]

[[Go-Back-N ARQ]] is a sliding window protocol that allows multiple frames to be transmitted before receiving acknowledgements.

If a frame is lost or damaged, the sender retransmits that frame and all subsequent unacknowledged frames.

**Working Procedure:**

1. Sender transmits multiple frames within its window.
    
2. Receiver accepts frames in order.
    
3. Receiver sends [[Cumulative ACKs]].
    
4. If a frame is lost, subsequent out-of-order frames are discarded.
    
5. Sender retransmits the missing frame and all later unacknowledged frames.
    

**Maximum Window Size:**

For `$m$` sequence-number bits:

$$  
W_{\max}=2^m-1  
$$

**Example:**

If sequence number bits = 3:

$$  
W_{\max}=2^3-1=7  
$$

Maximum sender window size = 7 frames.

**[[Cumulative ACK]]:**

An ACK confirms that all frames up to a particular point have been received correctly.

**Advantages:**

- Better utilisation than Stop-and-Wait.
    
- Simple receiver implementation.
    
- Requires less receiver buffering than Selective Repeat.
    

**Disadvantages:**

- Retransmits multiple frames even if only one frame is lost.
    
- Can waste bandwidth.
    

### 4.6 [[Selective Repeat ARQ]]

[[Selective Repeat ARQ]] is a sliding window protocol that retransmits only the specific frames that are lost or damaged.

**Working Procedure:**

1. Sender transmits multiple frames.
    
2. Receiver accepts and buffers frames, even if they arrive out of order.
    
3. Receiver sends [[Individual ACKs]].
    
4. Sender identifies missing frames.
    
5. Only lost or damaged frames are retransmitted.
    

**Maximum Window Size:**

For `$m$` sequence-number bits:

$$  
W_{\max}=2^{m-1}  
$$

This limit prevents ambiguity between old and new frames when sequence numbers are reused.

**Example:**

If sequence number bits = 3:

$$  
W_{\max}=2^{3-1}=4  
$$

Maximum window size = 4 frames.

**Advantages:**

- Retransmits only damaged or missing frames.
    
- More efficient when errors occur.
    
- Better bandwidth utilisation than Go-Back-N in many situations.
    

**Disadvantages:**

- More complex implementation.
    
- Requires more receiver buffer space.
    
- Requires individual frame tracking.
    

### 4.7 [[Comparison of ARQ Protocols]]

|Feature|Stop-and-Wait|Go-Back-N|Selective Repeat|
|---|---|---|---|
|Frames sent at once|1|Multiple|Multiple|
|ACK type|Individual|Cumulative|Individual|
|Retransmission|Lost frame|Lost frame and later unacknowledged frames|Only lost frames|
|Receiver buffering|Low|Usually minimal|Higher|
|Efficiency|Low|Medium to high|High|
|Complexity|Simple|Moderate|High|

### 4.8 [[Lost ACK Recovery]]

When an ACK is lost:

- Sender does not receive confirmation.
    
- Timer expires.
    
- Sender retransmits the frame.
    
- Receiver uses [[Sequence Numbers]] to identify duplicate frames.
    
- Duplicate data is not delivered again to the network layer.
    

**Important:** Sequence numbers prevent duplicate frame delivery.

### 4.9 [[Channel Utilisation]]

[[Channel Utilisation]] indicates how effectively a communication channel is being used.

For Stop-and-Wait, assuming negligible ACK transmission time:

$$  
U=\frac{T_t}{T_t+2T_p}  
$$

Where:

- $$T_t$$ = Frame transmission time.
    
- $$T_p$$ = One-way propagation delay.
    

If $$a=T_p/T_t$$:

$$  
U=\frac{1}{1+2a}  
$$

**Example:**

Given:

- Transmission time = 1 ms.
    
- Propagation delay = 5 ms.
    

$$  
U=\frac{1}{1+2(5)}  
$$

$$  
U=\frac{1}{11}=0.0909  
$$

Channel utilisation = 9.09%.

**Interpretation:** The sender spends most of its time waiting for acknowledgement.

For an ideal sliding-window protocol, utilisation can approach 100% when the sender window is sufficiently large and the channel is error-free.

---

## 5. [[Medium Access Control (MAC) and LAN Switching]]

### 5.1 [[Medium Access Control (MAC)]]

MAC is a sublayer of the Data Link Layer responsible for controlling access to a shared communication medium.

It determines which device can transmit data at a particular time.

Examples:

- [[CSMA/CD]].
    
- [[CSMA/CA]].
    
- [[Token Passing]].
    

### 5.2 [[CSMA/CD (Carrier Sense Multiple Access with Collision Detection)]]

[[CSMA/CD]] is a channel access method traditionally used in shared, half-duplex Ethernet networks.

It allows devices to detect collisions while transmitting.

**Working Procedure:**

1. A device listens to the channel.
    
2. If the channel is idle, it starts transmitting.
    
3. If the channel is busy, it waits.
    
4. If a collision occurs, the device detects it.
    
5. It sends a [[Jam Signal]].
    
6. It stops transmitting.
    
7. It waits for a random [[Backoff]] period.
    
8. It tries transmitting again.
    

**Important:** Modern switched full-duplex Ethernet does not use CSMA/CD because collisions do not occur on dedicated full-duplex links.

#### A. [[Slot Time]]

[[Slot Time]] is the minimum time required for a collision to be detected under the Ethernet network's specified conditions.

For traditional 10 Mbps Ethernet:

$$  
\text{Slot Time}=512\text{ bit times}  
$$

At 10 Mbps:

$$  
T=\frac{512}{10\times10^6}  
$$

$$  
T=51.2\ \mu s  
$$

#### B. [[Binary Exponential Backoff]]

After a collision, the device waits for a random number of slot times.

The backoff value is selected from:

$$  
K\in[0,2^n-1]  
$$

Where `$n$` is the collision attempt number, limited to 10 for the backoff exponent.

**Example:**

After the first collision:

$$  
K\in[0,1]  
$$

After the second collision:

$$  
K\in[0,3]  
$$

After the third collision:

$$  
K\in[0,7]  
$$

**Backoff Time:**

$$  
T_b=K\times\text{Slot Time}  
$$

If the third collision produces K = 5:

$$  
T_b=5\times51.2  
$$

$$  
T_b=256\ \mu s  
$$

**Remember:** The range of possible waiting times increases after each collision.

### 5.3 [[CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)]]

[[CSMA/CA]] is used in wireless LANs, particularly [[Wi-Fi]].

Unlike CSMA/CD, wireless devices generally cannot reliably detect collisions while transmitting. Therefore, CSMA/CA attempts to avoid collisions before transmission.

**Working Procedure:**

1. Device listens to the wireless channel.
    
2. If the channel is idle, it waits for [[DIFS]].
    
3. It selects a random [[Backoff]] time.
    
4. The backoff counter decreases while the channel remains idle.
    
5. If another device transmits, the counter freezes.
    
6. When the channel becomes idle again, the countdown resumes.
    
7. When the counter reaches zero, the device transmits.
    
8. Receiver sends an [[ACK]] after successful reception.
    

#### A. [[DIFS (Distributed Inter-Frame Space)]]

DIFS is a waiting period used by a wireless device before beginning contention for the channel.

It helps ensure that the channel has remained idle before transmission.

#### B. [[Random Backoff]]

A device selects a random number from its [[Contention Window]].

$$  
K\in[0,CW-1]  
$$

Where CW is the contention window size.

The device waits for the selected number of backoff slots.

#### C. [[Contention Window Doubling]]

If transmission fails, the contention window increases, generally by doubling its size until the configured maximum is reached.

This reduces the probability of repeated collisions.

#### D. [[RTS/CTS (Request to Send / Clear to Send)]]

RTS/CTS is an optional mechanism used to reduce collisions, especially due to [[Hidden Terminal Problem]].

**Working Procedure:**

1. Sender sends RTS to the receiver.
    
2. Receiver replies with CTS.
    
3. Other devices hearing RTS or CTS defer transmission.
    
4. Sender transmits data.
    
5. Receiver sends ACK.
    

#### E. [[Hidden Terminal Problem]]

The [[Hidden Terminal Problem]] occurs when two wireless devices cannot hear each other but can both communicate with the same access point.

**Example:**

- Device A can communicate with the access point.
    
- Device C can also communicate with the access point.
    
- A and C cannot hear each other.
    
- Both may transmit simultaneously.
    
- Their transmissions collide at the access point.
    

**Solution:** [[RTS/CTS]] helps reserve the channel and reduce hidden-terminal collisions.

### 5.4 [[CSMA/CD]] vs [[CSMA/CA]]

|CSMA/CD|CSMA/CA|
|---|---|
|Collision Detection|Collision Avoidance|
|Traditionally used in shared wired Ethernet|Used in wireless LANs|
|Detects collisions after they occur|Attempts to prevent collisions|
|Uses jam signals|Uses ACK and optional RTS/CTS|
|Uses binary exponential backoff|Uses random backoff and contention windows|

---

## 6. [[Bridges and Spanning Tree Protocol (STP)]]

### 6.1 [[Bridge]]

A [[Bridge]] is a Data Link Layer device used to connect multiple LAN segments.

It forwards or filters frames based on [[MAC Addresses]].

**Functions:**

- Connects LAN segments.
    
- Learns device MAC addresses.
    
- Filters unnecessary traffic.
    
- Forwards frames to the correct segment.
    
- Reduces unnecessary network traffic.
    

### 6.2 [[Learning Bridge]]

A [[Learning Bridge]] automatically builds a [[MAC Address Table]] by examining incoming frames.

The table contains:

- MAC address.
    
- Port number.
    
- Sometimes an ageing timer.
    

**Working Procedure:**

1. Bridge receives a frame.
    
2. It reads the source MAC address.
    
3. It records the source MAC address and incoming port.
    
4. It checks the destination MAC address in its table.
    
5. It decides whether to forward, filter or flood the frame.
    

### 6.3 [[Frame Forwarding Behaviour]]

A bridge uses three main actions:

#### A. [[Forwarding]]

If the destination MAC address is known and is located on another port, the bridge forwards the frame through that port.

#### B. [[Filtering]]

If the destination is on the same port from which the frame arrived, the bridge does not forward it.

#### C. [[Flooding]]

If the destination MAC address is unknown, the bridge sends the frame through all ports except the incoming port.

Broadcast frames are also flooded within the relevant LAN.

### 6.4 [[MAC Address Table]] Example

|MAC Address|Port|
|---|---|
|AA:AA:AA:AA:AA:01|1|
|BB:BB:BB:BB:BB:02|2|
|CC:CC:CC:CC:CC:03|3|

If a frame arrives on Port 1 for destination `BB:BB:BB:BB:BB:02`, the bridge forwards it through Port 2.

If the destination is unknown, the bridge floods the frame through all ports except Port 1.

### 6.5 [[Switching Loops]]

A [[Switching Loop]] occurs when multiple switches or bridges are connected in a cycle.

**Problems caused by switching loops:**

- [[Broadcast Storms]].
    
- Duplicate frames.
    
- MAC address table instability.
    
- Network congestion.
    
- Poor network performance.
    

### 6.6 [[Spanning Tree Protocol (STP)]]

[[Spanning Tree Protocol (STP)]] is a network protocol used to prevent switching loops in Ethernet networks.

It creates a loop-free logical topology by blocking redundant paths while keeping them available as backups.

STP is based on [[IEEE 802.1D]].

#### [[STP Working Procedure]]

1. Switches exchange [[Bridge Protocol Data Units (BPDUs)]].
    
2. They elect a [[Root Bridge]] based on the lowest Bridge ID.
    
3. Each non-root switch selects its best path towards the Root Bridge.
    
4. STP selects designated ports for network segments.
    
5. Redundant paths are placed in a non-forwarding state.
    
6. If an active link fails, STP can activate a previously blocked path.
    

#### [[Important STP Terms]]

- **[[Root Bridge]]:** The central reference switch selected by STP.
    
- **[[BPDU]]:** Messages exchanged between switches to calculate the spanning tree.
    
- **[[Root Port]]:** The port providing the best path towards the Root Bridge.
    
- **[[Designated Port]]:** The forwarding port selected for a network segment.
    
- **[[Blocked Port]]:** A port prevented from forwarding normal traffic to avoid loops.
    

**Advantages:**

- Prevents switching loops.
    
- Reduces broadcast storms.
    
- Provides redundancy.
    
- Maintains network stability.
    

---

## 7. [[Important Formula Sheet]]

|Topic|Formula|
|---|---|
|[[Codeword Length]]|$n=k+r$|
|[[Code Rate]]|$R=k/n$|
|[[Redundancy Ratio]]|$r/n$|
|[[Hamming Code]] parity bits|$2^p\geq p+m+1$|
|Hamming codeword length|$n=m+p$|
|[[Go-Back-N ARQ]] window|$W_{\max}=2^m-1$|
|[[Selective Repeat ARQ]] window|$W_{\max}=2^{m-1}$|
|[[Stop-and-Wait ARQ]] utilisation|$U=T_t/(T_t+2T_p)$|
|[[Backoff Time]]|$T_b=K\times\text{Slot Time}$|
|[[CRC]] overhead|$r/(k+r)\times100$|
|[[CRC]] efficiency|$k/(k+r)\times100$|

---

## 8. [[Important Differences for Exams]]

### 8.1 [[Parity]] vs [[Checksum]] vs [[CRC]]

|Parity|Checksum|CRC|
|---|---|---|
|Adds parity bit|Uses 1's complement sum|Uses modulo-2 division|
|Simple|Moderate complexity|More powerful detection|
|Weak error detection|Detects many common errors|Strong burst-error detection|
|Cannot correct errors|Cannot correct errors|Cannot correct errors|

### 8.2 [[Go-Back-N ARQ]] vs [[Selective Repeat ARQ]]

|Go-Back-N|Selective Repeat|
|---|---|
|Cumulative ACKs|Individual ACKs|
|Retransmits multiple frames|Retransmits only lost frames|
|Receiver usually discards out-of-order frames|Receiver buffers out-of-order frames|
|Less complex|More complex|
|Smaller receiver buffer requirement|Larger receiver buffer requirement|

### 8.3 [[Bridge]] vs [[Switch]]

|Bridge|Switch|
|---|---|
|Connects LAN segments|Connects multiple devices in a LAN|
|Usually has fewer ports|Usually has many ports|
|Operates at Data Link Layer|Traditionally operates at Data Link Layer|
|Often software-based forwarding|Commonly uses hardware-based forwarding|

### 8.4 [[CSMA/CD]] vs [[CSMA/CA]]

|CSMA/CD|CSMA/CA|
|---|---|
|Detects collisions|Avoids collisions|
|Shared wired Ethernet|Wireless LAN|
|Uses jam signal|Uses ACK and optional RTS/CTS|
|Stops after collision|Uses random backoff before transmission|

---

## 9. [[Important Questions for Examination]]

### [[Long-Answer Questions]]

1. Explain the functions and sublayers of the [[Data Link Layer]].
    
2. Explain [[Framing]] and its different techniques.
    
3. Differentiate between [[Single-Bit Error]] and [[Burst Error]].
    
4. Explain [[Parity Check]], [[Checksum]] and [[CRC]] with examples.
    
5. Explain [[Hamming Code]] and demonstrate single-bit error correction.
    
6. Explain [[Stop-and-Wait ARQ]], [[Go-Back-N ARQ]] and [[Selective Repeat ARQ]].
    
7. Compare [[Go-Back-N ARQ]] and [[Selective Repeat ARQ]].
    
8. Explain [[CSMA/CD]] and [[Binary Exponential Backoff]].
    
9. Explain [[CSMA/CA]] with [[DIFS]], [[RTS/CTS]] and the [[Hidden Terminal Problem]].
    
10. Explain the working of a [[Learning Bridge]].
    
11. Explain [[Spanning Tree Protocol (STP)]] and how it prevents switching loops.
    

### [[Short-Answer Questions]]

1. What is [[Framing]]?
    
2. Define [[Byte Stuffing]] and [[Bit Stuffing]].
    
3. What is [[Redundancy]]?
    
4. Differentiate [[FEC]] and [[ARQ]].
    
5. What is a [[Checksum]]?
    
6. What is [[CRC]]?
    
7. What is a [[Syndrome]]?
    
8. Define [[Cumulative ACK]].
    
9. What is a [[Sliding Window]]?
    
10. What is a [[Collision]]?
    
11. Define [[Slot Time]].
    
12. What is [[DIFS]]?
    
13. What is the [[Hidden Terminal Problem]]?
    
14. What is a [[BPDU]]?
    
15. What is a [[Root Bridge]]?
    
16. What is [[Flooding]] in a bridge?
    

---

## 10. [[Quick Revision Checklist]]

- [[Data Link Layer]] and [[Node-to-Node Communication]]
    
- [[Data Link Control (DLC)]] and [[Media Access Control (MAC)]]
    
- [[Point-to-Point Link]] and [[Broadcast Link]]
    
- [[Framing]] and [[Frame Structure]]
    
- [[Byte Stuffing]] and [[Bit Stuffing]]
    
- [[Single-Bit Error]] and [[Burst Error]]
    
- [[Redundancy]] and [[Block Coding]]
    
- [[Parity Check (VRC)]]
    
- [[Checksum]]
    
- [[Cyclic Redundancy Check (CRC)]]
    
- [[Hamming Code]]
    
- [[Flow Control]]
    
- [[Automatic Repeat reQuest (ARQ)]]
    
- [[Stop-and-Wait ARQ]]
    
- [[Go-Back-N ARQ]]
    
- [[Selective Repeat ARQ]]
    
- [[Sliding Window]] and [[Channel Utilisation]]
    
- [[CSMA/CD]]
    
- [[CSMA/CA]]
    
- [[Binary Exponential Backoff]]
    
- [[RTS/CTS]] and [[Hidden Terminal Problem]]
    
- [[Learning Bridge]]
    
- [[Spanning Tree Protocol (STP)]]
    

---

## 11. [[Recommended Study Order]]

1. **Understand the basics:** [[Data Link Layer]], sublayers and [[Framing]].
    
2. **Study error control:** [[Parity Check]], [[Checksum]], [[CRC]] and [[Hamming Code]]. Practise numerical problems.
    
3. **Study flow control:** Understand [[Stop-and-Wait ARQ]], [[Go-Back-N ARQ]] and [[Selective Repeat ARQ]] with diagrams.
    
4. **Study MAC protocols:** Focus on [[CSMA/CD]], [[CSMA/CA]] and [[Backoff]] calculations.
    
5. **Finish with LAN switching:** [[Bridges]], [[MAC Address Tables]], [[Flooding]] and [[STP]].
    

**Exam priority:** Give particular attention to [[CRC]] division, [[Hamming Code]] numericals, [[ARQ]] comparisons, [[Channel Utilisation]], [[Binary Exponential Backoff]] and [[CSMA/CA]]. These topics combine theory with problem-solving and are useful to prepare thoroughly.