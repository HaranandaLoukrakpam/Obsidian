## 1. Transport Layer Fundamentals

### 1.1 Introduction to the Transport Layer

The [[Transport Layer]] is the fourth layer of the [[OSI Model]]. It provides logical communication between application processes running on different hosts.

While the [[Network Layer]] handles host-to-host delivery, the Transport Layer provides **process-to-process delivery**.

**Main functions:**

- Process-to-process communication.
    
- [[Multiplexing]] and [[Demultiplexing]].
    
- Segmentation and reassembly.
    
- Reliable data transfer.
    
- [[Flow Control]].
    
- [[Congestion Control]].
    
- Error detection.
    

### 1.2 Process-to-Process Communication

A computer may run multiple applications simultaneously. The Transport Layer ensures that data reaches the correct application process.

It uses **port numbers** to identify application processes.

**Port Number:**

- A port number is a 16-bit logical address used to identify a process or application.
    
- Port numbers range from 0 to 65535.
    
- Source port identifies the sending application.
    
- Destination port identifies the receiving application.
    

**Types of port numbers:**

|Range|Category|Example|
|---|---|---|
|0–1023|Well-known ports|HTTP (80), HTTPS (443), FTP (21)|
|1024–49151|Registered ports|MySQL (3306)|
|49152–65535|Dynamic/Private ports|Temporary client ports|

### 1.3 Multiplexing and Demultiplexing

**Multiplexing:**

Multiplexing is the process of collecting data from multiple application processes and passing it to the Transport Layer for transmission.

**Demultiplexing:**

Demultiplexing is the process of delivering received data to the correct application process using port numbers.

**Example:**

A computer can simultaneously use:

- Browser – HTTPS (port 443).
    
- Email application – SMTP (port 25).
    
- DNS client – DNS (port 53).
    

The Transport Layer uses port information to deliver data to the appropriate process.

### 1.4 TCP vs UDP

The two major Transport Layer protocols are [[TCP]] and [[UDP]].

|Feature|TCP|UDP|
|---|---|---|
|Full form|Transmission Control Protocol|User Datagram Protocol|
|Connection|Connection-oriented|Connectionless|
|Reliability|Reliable|Best-effort delivery|
|Data delivery|Ordered byte stream|Independent datagrams|
|Error handling|Detection and retransmission|Checksum, but no built-in retransmission|
|Flow control|Yes|No built-in flow control|
|Congestion control|Yes|No built-in congestion control|
|Speed and overhead|Higher overhead|Lower overhead|
|Acknowledgement|Yes|No built-in ACK|
|Header size|Minimum 20 bytes|8 bytes|

**Applications of TCP:**

- Online banking.
    
- File transfer.
    
- Email.
    
- Web browsing using HTTP/1.1 and HTTP/2.
    

**Applications of UDP:**

- Video conferencing.
    
- Online gaming.
    
- Live streaming.
    
- DNS queries.
    

**Important:** UDP does not guarantee delivery, ordering, or retransmission. Applications can implement their own reliability mechanisms when required.

**Conclusion:** TCP is preferred when reliability and ordered delivery are important, whereas UDP is useful when low latency and reduced overhead are priorities.

---

## 2. Transmission Control Protocol (TCP)

### 2.1 Introduction to TCP

[[TCP]] is a connection-oriented and reliable Transport Layer protocol.

It establishes a connection before transferring data and ensures that data is delivered correctly and in order.

**Features of TCP:**

1. Connection-oriented communication.
    
2. Reliable data transmission.
    
3. Error detection using checksum.
    
4. Sequence numbers and acknowledgements.
    
5. Flow control using a sliding window.
    
6. Congestion control.
    
7. Full-duplex communication.
    
8. Ordered delivery of data.
    

### 2.2 TCP Segment Format

TCP transfers data in units called **segments**.

A TCP segment consists of a header and application data.

**Important TCP header fields:**

|Field|Purpose|
|---|---|
|Source Port|Identifies the sending application|
|Destination Port|Identifies the receiving application|
|Sequence Number|Identifies the position of data bytes|
|Acknowledgement Number|Indicates the next byte expected|
|Data Offset|Specifies TCP header length|
|Control Flags|Controls connection and data transfer|
|Window Size|Indicates the receiver's available buffer capacity|
|Checksum|Detects errors in the TCP segment|
|Urgent Pointer|Identifies urgent data when URG is set|
|Options|Provides additional TCP features|

**TCP Control Flags:**

|Flag|Meaning|Purpose|
|---|---|---|
|SYN|Synchronize|Establishes a connection|
|ACK|Acknowledgement|Acknowledges received data|
|FIN|Finish|Gracefully terminates a connection|
|RST|Reset|Abruptly resets a connection|
|PSH|Push|Requests immediate delivery of data to the application|
|URG|Urgent|Indicates urgent data|

**Important:** The TCP header has a minimum size of 20 bytes and a maximum size of 60 bytes.

### 2.3 TCP Connection Establishment – Three-Way Handshake

TCP uses a process called the [[Three-Way Handshake]] to establish a connection between a client and a server.

**Steps:**

1. **SYN:** The client sends a SYN segment to request a connection and provides its initial sequence number.
    
2. **SYN-ACK:** The server acknowledges the client's sequence number and sends its own SYN segment with an initial sequence number.
    
3. **ACK:** The client acknowledges the server's sequence number. The connection is established.
    

**Diagram:**

```
       CLIENT                         SERVER
          |                              |
          | -------- SYN, Seq=x -------->|
          |                              |
          | <--- SYN-ACK, Seq=y, Ack=x+1 |
          |                              |
          | -------- ACK, Ack=y+1 ------>|
          |                              |
          |       CONNECTION             |
          |        ESTABLISHED            |
```

**Sequence Number Consumption:**

- SYN consumes one sequence number.
    
- FIN also consumes one sequence number.
    
- A pure ACK does not consume a sequence number.
    
- If the initial sequence number is `x`, the acknowledgement after receiving SYN is `x + 1`.
    

**Purpose of the Three-Way Handshake:**

- Establishes a connection.
    
- Synchronizes initial sequence numbers.
    
- Confirms that both devices are ready to communicate.
    

### 2.4 Reliable Data Transfer

TCP provides reliable data transmission using several mechanisms.

**1. Sequence Numbers**

- TCP treats data as a continuous stream of bytes.
    
- Every byte is assigned a sequence number.
    
- The sequence number in a segment identifies the first data byte in that segment.
    

**2. Acknowledgements (ACK)**

- The receiver sends acknowledgements to confirm received data.
    
- TCP generally uses cumulative acknowledgements.
    
- An ACK number indicates the next byte expected.
    

**Example:**

If a receiver sends `ACK = 501`, it means all bytes up to 500 have been received successfully, and byte 501 is expected next.

**3. Checksum**

- TCP uses a checksum to detect errors in the header and data.
    
- If corruption is detected, the segment is discarded.
    
- Recovery occurs through retransmission mechanisms.
    

**4. Retransmission Timeout (RTO)**

- The sender starts a retransmission timer after sending data.
    
- If an acknowledgement is not received before the timeout, the data is retransmitted.
    
- The timeout is adjusted based on measured round-trip time.
    

**5. Fast Retransmit**

- TCP can retransmit a missing segment before the retransmission timer expires.
    
- When the sender receives three duplicate ACKs, it assumes that a segment has been lost.
    
- It retransmits the missing segment immediately.
    

**Example:**

```
Sender sends: 1, 2, 3, 4, 5

Receiver receives: 1, 2, 4, 5
Segment 3 is missing.

Receiver sends:
ACK 3
ACK 3
ACK 3
ACK 3

Sender receives 3 duplicate ACKs
and retransmits segment 3.
```

### 2.5 TCP Flow Control

[[Flow Control]] prevents a fast sender from overwhelming a slow receiver.

TCP uses a **Sliding Window Mechanism** to control how much data can be sent before receiving acknowledgements.

**Receiver Window (rwnd):**

- `rwnd` represents the available receiving buffer space.
    
- The receiver advertises its available buffer capacity to the sender.
    
- The sender must not exceed the advertised receiving window.
    

**Example:**

If the receiver advertises a window size of 5000 bytes, the sender can have up to 5000 unacknowledged bytes in flight, subject to the congestion window and other TCP limitations.

**Zero-Window Condition:**

When the receiver's buffer becomes full, it advertises a window size of zero.

- The sender temporarily stops sending normal data.
    
- The receiver later advertises a non-zero window when buffer space becomes available.
    
- The sender uses **zero-window probes** to check whether the receiver can accept more data.
    

### 2.6 TCP Congestion Control

[[Congestion Control]] prevents excessive traffic from overloading the network.

TCP uses a variable called the **Congestion Window (cwnd)** to control the amount of unacknowledged data that can be sent.

**Important Terms:**

|Term|Meaning|
|---|---|
|cwnd|Congestion Window, controlled by the sender|
|rwnd|Receiver Window, advertised by the receiver|
|ssthresh|Slow Start Threshold|
|MSS|Maximum Segment Size|

The effective TCP sending window is limited by both flow control and congestion control.

$$  
\text{Sending Window}=\min(\text{rwnd},\text{cwnd})  
$$

**Example:**

If:

- `rwnd = 8000 bytes`
    
- `cwnd = 5000 bytes`
    

Then:

$$  
\text{Sending Window}=\min(8000,5000)  
$$

$$  
=5000\text{ bytes}  
$$

### 2.7 TCP Reno Congestion Control

TCP Reno uses four important phases to control congestion.

**1. Slow Start**

- TCP begins with a small congestion window.
    
- The congestion window increases exponentially, approximately doubling every RTT while acknowledgements arrive.
    
- Growth continues until `cwnd` reaches `ssthresh` or congestion is detected.
    

**2. Congestion Avoidance**

- Begins when `cwnd` reaches the slow-start threshold.
    
- The congestion window increases approximately linearly.
    
- This reduces the risk of network congestion.
    

**3. Fast Retransmit**

- Triggered when the sender receives three duplicate ACKs.
    
- The sender immediately retransmits the suspected missing segment without waiting for the timeout.
    

**4. Fast Recovery**

- After fast retransmit, TCP Reno reduces its congestion window rather than returning immediately to the initial slow-start window.
    
- It sets a new threshold, approximately half of the previous congestion window.
    
- After recovery, it continues with congestion avoidance.
    

**Simplified Reno Behaviour:**

```
        Slow Start
             |
             v
    Congestion Avoidance
             |
             v
      Packet Loss Detected
             |
       ----------------
       |              |
   3 Duplicate ACK   Timeout
       |              |
       v              v
  Fast Retransmit   Slow Start
       |
       v
  Fast Recovery
       |
       v
  Congestion Avoidance
```

**Important:** The exact window updates depend on the congestion event and TCP implementation. In Reno, a timeout generally causes a more severe reduction than three duplicate ACKs.

### 2.8 Flow Control vs Congestion Control

These two mechanisms serve different purposes.

|Feature|Flow Control|Congestion Control|
|---|---|---|
|Purpose|Prevents receiver overload|Prevents network overload|
|Protects|Receiver|Network|
|Main variable|`rwnd`|`cwnd`|
|Controlled by|Receiver's advertised window|Sender's congestion algorithm|
|Problem addressed|Receiver buffer becoming full|Routers and network links becoming overloaded|

**Remember:**

- Flow Control = Protects the receiver.
    
- Congestion Control = Protects the network.
    

### 2.9 TCP Connection Termination – Four-Way Handshake

TCP uses a four-message process to gracefully terminate a connection.

**Steps:**

1. **FIN:** The client sends a FIN segment to indicate that it has finished sending data.
    
2. **ACK:** The server acknowledges the FIN.
    
3. **FIN:** When the server is ready to close its sending direction, it sends its own FIN.
    
4. **ACK:** The client acknowledges the server's FIN. The connection is closed after the required TCP state transitions.
    

**Diagram:**

```
       CLIENT                         SERVER
          |                              |
          | -------- FIN --------------->|
          |                              |
          | <------- ACK ----------------|
          |                              |
          | <------- FIN ----------------|
          |                              |
          | -------- ACK --------------->|
          |                              |
          |       CONNECTION             |
          |          CLOSED              |
```

**Important Points:**

- TCP supports full-duplex communication.
    
- Each direction is closed independently.
    
- FIN consumes one sequence number.
    
- The active closer normally enters the `TIME_WAIT` state after sending the final ACK.
    
- `TIME_WAIT` helps ensure that delayed segments do not interfere with a later connection and allows retransmission of the final ACK if needed.
    

---

## 3. Important Formula Sheet

### 3.1 TCP Sending Window

$$  
\text{Sending Window}=\min(\text{rwnd},\text{cwnd})  
$$

### 3.2 Sequence Number and Acknowledgement

$$  
\text{ACK Number}=\text{Next Expected Byte}  
$$

For a segment carrying `N` bytes starting at sequence number `x`:

$$  
\text{Next Sequence Number}=x+N  
$$

SYN and FIN each consume one sequence number.

### 3.3 TCP Header Size

$$  
\text{Minimum Header Size}=20\text{ bytes}  
$$

$$  
\text{Maximum Header Size}=60\text{ bytes}  
$$

### 3.4 UDP Header Size

$$  
\text{UDP Header Size}=8\text{ bytes}  
$$

---

## 4. Important Exam Questions

### Short Answer Questions

1. Define the Transport Layer.
    
2. What is process-to-process communication?
    
3. Define multiplexing and demultiplexing.
    
4. What is a port number?
    
5. Differentiate between TCP and UDP.
    
6. What is a TCP segment?
    
7. What is the purpose of sequence numbers?
    
8. What is an acknowledgement number?
    
9. What is the purpose of the TCP checksum?
    
10. Define the sliding window mechanism.
    
11. What is a zero-window condition?
    
12. Define `rwnd`, `cwnd`, and `ssthresh`.
    
13. What is fast retransmit?
    
14. What is the difference between flow control and congestion control?
    
15. What is the purpose of the TIME_WAIT state?
    

### Long Answer Questions

1. Explain the functions of the Transport Layer.
    
2. Compare TCP and UDP in detail with suitable applications.
    
3. Explain the TCP segment format and its important fields.
    
4. Explain the TCP three-way handshake with a diagram.
    
5. Describe the mechanisms used by TCP for reliable data transfer.
    
6. Explain TCP flow control using the sliding window mechanism.
    
7. Explain TCP Reno congestion control and its four phases.
    
8. Differentiate between flow control and congestion control.
    
9. Explain TCP connection termination using the four-way handshake.
    

---

## 5. Quick Revision Notes

|Topic|Key Point|
|---|---|
|Transport Layer|Process-to-process delivery|
|Port Number|Identifies an application process|
|Multiplexing|Collects data from multiple processes|
|Demultiplexing|Delivers data to the correct process|
|TCP|Reliable and connection-oriented|
|UDP|Connectionless and low overhead|
|TCP Segment|Unit of TCP data transmission|
|SYN|Starts connection establishment|
|ACK|Acknowledges received data|
|FIN|Graceful connection termination|
|RST|Resets a connection|
|Sequence Number|Identifies byte position|
|ACK Number|Indicates next expected byte|
|Fast Retransmit|Retransmits after 3 duplicate ACKs|
|rwnd|Receiver's available window|
|cwnd|Sender's congestion window|
|ssthresh|Slow-start threshold|
|Flow Control|Protects receiver|
|Congestion Control|Protects network|
|Three-Way Handshake|SYN → SYN-ACK → ACK|
|Four-Way Handshake|FIN → ACK → FIN → ACK|

---

## 6. Recommended Study Order

1. Understand [[Transport Layer]] fundamentals and port numbers.
    
2. Learn the differences between [[TCP]] and [[UDP]].
    
3. Study the TCP segment format and control flags.
    
4. Practise the three-way handshake and four-way termination diagrams.
    
5. Understand sequence numbers, ACKs, and reliable data transfer.
    
6. Study sliding-window flow control.
    
7. Learn TCP Reno congestion control and its four phases.
    
8. Revise the comparison tables and formula sheet.
    

**Exam priority:** TCP vs UDP, TCP segment format, three-way handshake, reliable data transfer, flow control, TCP Reno, and four-way termination.