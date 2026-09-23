# [[Data Communication & Networking]] Notes

---

## [[Lecture 01]] — 23/07/26

> [!info] The Connected World  
> The planet is increasingly connected, with billions of people online and enormous amounts of data generated every year.
> 
> **Data Communication & Networking** forms the backbone of modern digital communication.

---

## [[Data Communication]]

> **Data Communication** is the exchange of data between two devices through a transmission medium.

```text
Sender → [Transmission Medium] → Receiver
```

### 5 Components of a Communication System

A communication system consists of:

1. [[Message]]
    
2. [[Sender]]
    
3. [[Receiver]]
    
4. [[Medium]]
    
5. [[Protocol]]

> **Key Idea:** Everything transmitted digitally is ultimately represented as **bits (`0` and `1`)**.

---

## [[Data Flow Modes]]

|[[Simplex]]|[[Half-Duplex]]|[[Full-Duplex]]|
|---|---|---|
|One direction only|Both directions, but one at a time|Both directions simultaneously|
|`A → B`|`A ⇄ B` _(one direction at a time)_|`A ↔ B`|
|**Example:** Keyboard → Computer/Monitor|**Example:** Walkie-talkies|**Example:** Phone call|

### Quick Comparison

```text
Simplex
A ─────────→ B

Half-Duplex
A ─────────→ B
A ←───────── B
(one at a time)

Full-Duplex
A ═════════↔ B
(simultaneously)
```

---

# [[Network]]

> A **Network** is a set of devices, called **nodes**, connected by communication links to share information and resources.

### Advantages / Goals of a Network

1. [[Resource Sharing]]
    
2. [[Communication]]
    
3. [[Reliability]]
    
4. [[Scalability]]
    

### Nodes and Links Representation

```text
       (Node)
         |
  (Node)-+----(Node)----(Node)
         |     | \     /
         |     |  \   /
         |    (Node)(Node)
         |       |
      (Node)-----+
```

> **Node:** A device connected to a network.
> 
> **Link:** A communication connection between two nodes.

---

# [[Lecture 02]] — 24/07/26

## What Makes Data Communication Good?

A good communication system should provide:

### [[Performance]]

Important performance measures include:

- [[Throughput]]
    
- [[Delay]] / [[Latency]]
    
- [[Response Time]]
### [[Reliability]]

Important reliability characteristics include:

- [[Failure Frequency]]
    
- [[Recovery Time]]
    
- [[Robustness]]
### [[Security]]

The three major security objectives are:

- [[Confidentiality]] — Prevent unauthorized access to information.
    
- [[Integrity]] — Ensure data is not improperly altered.
    
- [[Availability]] — Ensure authorized users can access resources when needed.

> These three objectives are commonly known as the **CIA Triad**.

---

# How Are Nodes Connected?

## [[Point-to-Point]]

A **Point-to-Point** connection provides a dedicated communication link between two devices.

```text
[Node] ───────────────── [Node]
```

**Example:**

```text
Laptop → Switch Port
```

---

## [[Multipoint]] / Multidrop

A **Multipoint** connection allows multiple devices to share a common communication medium.

```text
        [Node]
           |
[Node] ────+──── [Node]
           |
        [Node]
```

**Examples:**

- Shared bus
    
- Wireless communication channel
    
- Shared communication medium
    

---

# [[Network Topologies]]

A **Network Topology** describes how nodes and communication links are physically or logically arranged.

|[[Topology]]|Cabling Cost|Fault Tolerance|Scalability|Typical Use|
|---|---|---|---|---|
|[[Mesh Topology\|Mesh]]|High|Excellent|Poor|Backbones, critical links|
|[[Star Topology\|Star]]|Low–Medium|Good|High|Most modern LANs|
|[[Bus Topology\|Bus]]|Low|Poor|Low|Legacy / small setups|
|[[Ring Topology\|Ring]]|Medium|Medium|Medium|Some MAN / Token Ring networks|

### Quick Topology Summary

- **[[Mesh Topology|Mesh]]** → Many or all nodes have direct links to other nodes.
    
- **[[Star Topology|Star]]** → All nodes connect to a central device.
    
- **[[Bus Topology|Bus]]** → All nodes share a common communication backbone.
    
- **[[Ring Topology|Ring]]** → Each node is connected to two neighboring nodes, forming a ring.
    

---

# Networks by Scale / Area

|Category|Full Form|Typical Range / Area|Example|
|---|---|---|---|
|[[PAN]]|Personal Area Network|A few meters|Bluetooth|
|[[LAN]]|Local Area Network|Room, building, or campus|Ethernet, Wi-Fi|
|[[MAN]]|Metropolitan Area Network|City / metropolitan area|Metro-fibre|
|[[WAN]]|Wide Area Network|Large geographic area / country or beyond|Internet|

> **Note on [[The Internet]]:**  
> The Internet is a **network of networks** consisting of many independently operated networks, including Autonomous Systems (ASes) and ISPs, that interconnect and exchange traffic.

---

# [[Protocols and Standards]]

> **Protocol:** A set of rules that governs communication between devices.
> 
> **Standard:** An agreed specification or set of rules used to ensure compatibility and interoperability.

Standards can broadly be:

- **[[De Facto Standard]]** — Becomes widely used through adoption and practice.
    
- **[[De Jure Standard]]** — Formally established or approved by a recognized standards organization or authority.
    

---

## Elements of a Protocol

A protocol defines three major aspects:

### 1. [[Syntax]]

Defines the **format and structure** of data.

> **Question:** Which bits go where?

### 2. [[Semantics]]

Defines the **meaning of each field**.

> **Question:** What does an address, flag, or control field signify?

### 3. [[Timing]]

Defines **when data should be sent and how fast**.

It includes aspects such as:

- Speed matching
    
- Sequencing
    
- Synchronization
    

---

# Two Types of Network Models

Two important models used to understand network communication are:

1. [[OSI Model]]
    
2. [[IP Model 1]]
    

> These models divide network communication into layers, with each layer responsible for specific functions.

---

# [[Switching]]

> **Switching** is the process of determining how data is transferred from a source to a destination through a network.

The two major switching techniques are:

## 1. [[Circuit Switching]]

A **dedicated communication path** is established between the sender and receiver for the entire communication session.

```text
(Node) ─── (Node) ─── (Node) ─── (Node)
          Dedicated Path
```

### Characteristics

- Dedicated path is established before communication.
    
- Resources are reserved for the connection.
    
- The path remains reserved for the entire session.
    

**Example:** Traditional telephone networks.

---

## 2. [[Packet Switching]]

In **Packet Switching**, data is divided into smaller units called **packets**.

The packets are transmitted through shared network links and routed toward the destination.

```text
        (Node)──────(Node)
       /    \          \
(Source)   (Node)────(Node)──(Destination)
       \      \       /
        ─────(Node)──
```

### Characteristics

- Data is divided into packets.
    
- Network resources are shared.
    
- Packets are routed through the network.
    
- No dedicated end-to-end circuit is required.
    

**Example:** [[The Internet]]

---

## [[Circuit Switching]] vs [[Packet Switching]]

|Feature|[[Circuit Switching]]|[[Packet Switching]]|
|---|---|---|
|Path|Dedicated|Shared|
|Resource reservation|Yes|Generally no|
|Data unit|Continuous stream|Packets|
|Efficiency|Lower for bursty data|Higher for bursty data|
|Example|Traditional telephone network|Internet|

---
## [[Channel Capacity]] — 10/09/26

### Question: How fast can data be transmitted through a communication channel?

There are two important theoretical limits:

1. [[Nyquist Bit Rate Formula]]
    
2. [[Shannon Capacity Formula]]
    

### Factors Affecting Data Rate

Data rate mainly depends on three factors:

1. **[[Bandwidth]]** → The frequency range that the channel can carry.
    
2. **[[Signal Levels|Number of Signal Levels]]** → The number of different signal levels used to represent data.
    
3. **[[Noise]]** → The amount of unwanted disturbance present in the channel.
    

### General Relationship

More Bandwidth+More Signal Levels+Less Noise→Potentially Higher Data Rate\text{More Bandwidth} + \text{More Signal Levels} + \text{Less Noise} \rightarrow \text{Potentially Higher Data Rate}

However, there are mathematical limits on the maximum achievable data rate. These are described by **[[Nyquist Bit Rate Formula|Nyquist]]** and **[[Shannon Capacity Formula|Shannon]]**.

---

# 1. [[Nyquist Bit Rate Formula]] — Noiseless Channel

The **Nyquist Bit Rate Formula** gives the maximum theoretical bit rate for a **noiseless channel**.

Bit Rate=2Blog⁡2L\boxed{\text{Bit Rate} = 2B\log_2 L}

### Where:

- $B$ = [[Bandwidth]] in Hz
    
- $L$ = Number of distinct signal levels
    

### Explanation

The formula assumes an **ideal channel with no noise**.

For a noiseless channel with bandwidth $B$:

- The maximum signalling rate is $2B$ signal elements per second.
    
- Each signal element can represent $\log_2 L$ bits.
    

Therefore:

Bit Rate=2Blog⁡2L\text{Bit Rate} = 2B\log_2L

### Important Point

Increasing the number of signal levels theoretically increases the bit rate.

However, there is a practical limitation:

> More signal levels mean the receiver must distinguish between voltage levels that are closer together.

Noise can make this distinction difficult.

Therefore:

More Signal Levels→Smaller Level Separation→Greater Effect of Noise\text{More Signal Levels} \rightarrow \text{Smaller Level Separation} \rightarrow \text{Greater Effect of Noise}

This is where **Shannon's theorem** becomes important.

---

## Signal Separation & Noise Problem

### Two Signal Levels

Suppose we use only two signal levels:

```text
0 V ------------------------------------------------ 5 V
```

There is a large separation between the two levels.

### More Signal Levels

Now suppose we use several levels between the same voltage limits:

```text
0 V ------ 1 V ------ 2 V ------ 3 V ------ 4 V ------ 5 V
```

The levels are closer together.

Even a small amount of noise may cause the receiver to mistake one signal level for another.

> **Conclusion:** Noise limits how many signal levels can be reliably distinguished in practice. Shannon's theorem captures the fundamental effect of noise on channel capacity.

---

## [[Nyquist Bit Rate Formula|Nyquist]] Example

### Given:

- Bandwidth = $3000$ Hz
    
- Number of signal levels = $4$
    

### Formula

Bit Rate=2Blog⁡2L\text{Bit Rate} = 2B\log_2L

Substituting:

=2×3000×log⁡24=2\times3000\times\log_2 4

Since:

log⁡24=2\log_2 4=2

Therefore:

=2×3000×2=2\times3000\times2 =12000 bps=12000\text{ bps} Bit Rate=12 kbps\boxed{\text{Bit Rate}=12\text{ kbps}}

> **Conclusion:** Under the assumptions of the Nyquist model, a $3000$ Hz noiseless channel using 4 signal levels can theoretically carry up to **12,000 bits per second (12 kbps)**.

---

# 2. [[Shannon Capacity Formula]] — Noisy Channel

Real communication channels are never perfectly noiseless. They contain various sources of interference and noise, such as:

- [[Electrical Interference]]
    
- [[Thermal Noise]]
    
- [[Crosstalk]]
    
- Signal distortions
    
- Other unwanted disturbances
    

For a noisy channel, we use the **Shannon Capacity Formula**:

C=Blog⁡2(1+SNR)\boxed{C=B\log_2(1+\text{SNR})}

### Where:

- $C$ = Channel capacity in bps
    
- $B$ = Bandwidth in Hz
    
- $\text{SNR}$ = Signal-to-Noise Ratio
    

---

## [[Signal-to-Noise Ratio|SNR]]

The Signal-to-Noise Ratio compares the strength of the useful signal with the strength of the unwanted noise.

SNR=Signal PowerNoise Power\boxed{\text{SNR}= \frac{\text{Signal Power}} {\text{Noise Power}}}

### Interpretation

- **Higher SNR** → Signal is much stronger than noise → More reliable communication.
    
- **Lower SNR** → Noise is relatively stronger → More difficulty distinguishing the transmitted signal.
    

---

## [[SNR in Plain Ratio]]

If SNR is already given as a **plain ratio**, it can be substituted directly into Shannon's formula.

### Given:

- $\text{SNR}=3162$
    
- $B=3000$ Hz
    

### Formula

C=Blog⁡2(1+SNR)C=B\log_2(1+\text{SNR})

Substitute:

C=3000log⁡2(1+3162)C=3000\log_2(1+3162) C=3000log⁡2(3163)C=3000\log_2(3163)

Approximately:

log⁡2(3163)≈11.62\log_2(3163)\approx11.62

Therefore:

C≈3000×11.62C\approx3000\times11.62 C≈34860 bpsC\approx34860\text{ bps} C≈34.86 kbps\boxed{C\approx34.86\text{ kbps}}

---

# [[SNR in Decibels (dB)]]

When SNR is given in **decibels**, it must first be converted into a plain ratio before using Shannon's formula.

### Conversion Formula

SNRratio=10SNRdB10\boxed{ \text{SNR}_{\text{ratio}} = 10^{\frac{\text{SNR}_{\text{dB}}}{10}} }

### Example

Suppose:

SNRdB=30 dB\text{SNR}_{\text{dB}}=30\text{ dB}

Convert it to a ratio:

SNRratio=103010\text{SNR}_{\text{ratio}} = 10^{\frac{30}{10}} =103=10^3 SNRratio=1000\boxed{\text{SNR}_{\text{ratio}}=1000}

Then substitute into Shannon's formula:

C=Blog⁡2(1+1000)C=B\log_2(1+1000) C=Blog⁡2(1001)C=B\log_2(1001)

> **Important:** If the bandwidth is also provided, substitute its value to calculate the channel capacity in bps.

---

# Significance of [[Nyquist Bit Rate Formula|Nyquist]] and [[Shannon Capacity Formula|Shannon]]

### [[Nyquist Bit Rate Formula|Nyquist]] asks:

> Ignoring noise, how fast could we theoretically transmit using a given bandwidth and number of signal levels?

### [[Shannon Capacity Formula|Shannon]] asks:

> Considering the noise in the channel, what is the maximum theoretical reliable data rate possible?

### Practical Design

Both limits are important:

```text
Nyquist
   ↓
Noiseless-channel limit based on
Bandwidth + Signal Levels
   ↓
Shannon
   ↓
Noisy-channel capacity based on
Bandwidth + SNR
```

---

## [[Nyquist Bit Rate Formula|Nyquist]] vs [[Shannon Capacity Formula|Shannon]]

|[[Nyquist Bit Rate Formula\|Nyquist]]|[[Shannon Capacity Formula\|Shannon]]|
|---|---|
|Assumes a noiseless channel|Considers a noisy channel|
|Depends on bandwidth and number of signal levels|Depends on bandwidth and SNR|
|Number of signal levels explicitly matters|Number of signal levels does not explicitly appear in the formula|
|Gives the maximum theoretical bit rate for a noiseless channel|Gives the theoretical channel capacity in the presence of noise|
|Formula: $2B\log_2L$|Formula: $B\log_2(1+\text{SNR})$|

---

# [[Signal Degradations]]

> What we send is not always exactly what the receiver gets.

There are three major causes of signal degradation:

1. [[Attenuation]]
    
2. [[Distortion]]
    
3. [[Noise]]
    

---

# 1. [[Attenuation]]

> **Attenuation** is the loss of signal strength as a signal travels through a transmission medium.

```text
[Sender] ───────────── Long Distance ─────────────→ [Receiver]
 Strong Signal                ↓                     Weak Signal
                         Attenuation
```

### Key Points

- The longer the transmission distance, the greater the attenuation generally becomes.
    
- Attenuation causes the signal's amplitude or power to decrease.
    

### [[Guided Media]]

In guided media such as copper cables:

- The medium has electrical resistance.
    
- As the signal travels through the medium, some of its energy is lost.
    
- This energy is commonly dissipated as heat.
    

### [[Unguided Media]]

In unguided media such as wireless communication:

- Signals lose energy as they propagate through space.
    
- Atmospheric gases, including oxygen and water vapour, can absorb electromagnetic energy at certain frequencies.
    
- Wireless signals also spread through space rather than being confined to a physical conductor.
    
- Higher-frequency signals can be more susceptible to certain forms of absorption and scattering.
    

---

## Solutions for [[Attenuation]]

### 1. [[Amplifier]]

An **amplifier** is used to increase the strength of an **analog signal**.

### 2. [[Repeater]]

A **repeater** receives and regenerates/reshapes a **digital signal** so that it can continue travelling over a longer distance.

```text
[Sender]
    │
    ▼
Weakening Signal
    │
    ▼
[Repeater / Amplifier]
    │
    ▼
Restored / Strengthened Signal
    │
    ▼
[Receiver]
```

> **Simple distinction:**  
> **Amplifier → strengthens an analog signal**  
> **Repeater → regenerates a digital signal**

---

# 2. [[Distortion]]

> **Distortion** occurs when the shape of a signal changes as it travels through a transmission medium.

The signal may still have sufficient strength, but its **waveform is no longer the same as the original**.

---

## Example of Distortion

Suppose a signal consists of three frequency components.

Their arrival times are:

- Component 1 → arrives at **10 ms**
    
- Component 2 → arrives at **12 ms**
    
- Component 3 → arrives at **15 ms**
    

If the components were expected to maintain their original relative timing but the transmission medium causes different components to experience different delays, they no longer maintain the same time relationship.

When the components combine at the receiver, the resulting waveform has a different shape.

This is **distortion**.

### Key Idea

Distortion is not simply about the components having different **absolute arrival times**.

Instead, distortion occurs when the **relative timing or amplitude relationship between the signal components changes** during transmission.

```text
Original Signal Components
        ↓
Transmission Medium
        ↓
Different Delays / Changes
        ↓
Changed Relative Relationships
        ↓
Different Waveform
        ↓
Distortion
```

> **In short:**  
> **Attenuation → Signal strength changes**  
> **Distortion → Signal shape changes**  
> **Noise → Unwanted signal is added**