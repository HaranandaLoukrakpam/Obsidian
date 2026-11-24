## Data Communication & Computer Networks — Exam Solutions

### Section A: Short Answer Questions (2 Marks × 4 = 8 Marks)

#### 1. Which multiplexing technique is best when several signals must share a single optical fibre?

**[[Wavelength-Division Multiplexing (WDM)]]** is the optimal technique for sharing a single [[optical fibre]] among multiple signals.

  

- **Mechanism:** It operates on the same physical principle as [[Frequency-Division Multiplexing (FDM)]], but applies to light waves rather than radio frequencies. Multiple optical signals, each assigned a distinct [[wavelength]] (color) of light, are combined by an [[optical multiplexer]] (prism or [[diffraction grating]]) onto a single fibre core and separated at the receiver.
    
- **Advantage:** [[Wavelength-Division Multiplexing (WDM)]] exploits the massive [[bandwidth]] capacity of optical fibres (terabits per second) without requiring higher electronic switching speeds per channel.
    

#### 2. Differentiate between a single-bit error and a burst error.

|**Feature**|**[[Single-Bit Error]]**|**[[Burst Error]]**|
|---|---|---|
|**Definition**|Only **one bit** of a given data unit (byte, character, or packet) is altered from `1` to `0` or `0` to `1`.|**Two or more bits** in the data unit have changed from `1` to `0` or `0` to `1`.|
|**Measurement**|Counted as a single isolated bit flip.|Measured from the **first corrupted bit to the last corrupted bit** (intermediate bits may remain intact).|
|**Common Cause**|Short-duration noise spikes in [[parallel transmission]] or low-speed serial links.|[[Impulse noise]], lightning, or [[attenuation]]/fading in high-speed [[serial transmission]] where noise duration exceeds single-bit period ($T_b$).|

#### 3. Why can twisted-pair cable cancel noise, but two untwisted parallel wires cannot?

- **Untwisted Parallel Wires:** When two wires run parallel to an external [[electromagnetic interference (EMI)]] source, one wire is physically closer to the noise source than the other. Consequently, it absorbs more interference, creating an unequal noise voltage across the pair that the [[differential receiver]] cannot cancel.
    
- **[[Twisted-Pair Cable]]:** Twisting the two conductors ensures that over the length of the cable, both wires swap positions relative to the external noise source at regular intervals. Both wires experience nearly identical electromagnetic interference, producing **[[common-mode noise]]**. A [[differential receiver]] measures the voltage difference between the two wires ($V_+ - V_-$), thereby subtracting and canceling out the identical noise induced on both lines.
    

#### 4. Can other users share a circuit-switched connection while it is idle? Justify your answer.

**No**, other users cannot share a [[circuit-switched connection]] even when no data is being transmitted.

  

- **Justification:** [[Circuit switching]] establishes a **dedicated physical path** (a specific time slot in [[Time-Division Multiplexing (TDM)]] or a frequency band in [[Frequency-Division Multiplexing (FDM)]]) between the sender and receiver during the [[setup phase]]. The allocated [[bandwidth]] and switching resources remain exclusively reserved for that session until the [[teardown phase]] is executed. Any idle periods result in wasted link capacity because the network lacks dynamic packet-level [[statistical multiplexing]].
    

### Section B: Descriptive Questions (4 Marks × 3 = 12 Marks)

#### 5. Pulse Code Modulation (PCM) in Data Communication & Bit Rate Calculation

**Use of [[Pulse Code Modulation (PCM)]] in Data Communication:** [[Pulse Code Modulation (PCM)]] is the standard technique used to convert an [[analog signal]] (such as human voice in telephony or analog sensor outputs) into a [[digital bit stream]] for transmission over digital networks. It consists of three sequential stages:

  

1. **[[Sampling]]:** The continuous analog signal is measured at uniform time intervals ($T_s$), producing a [[Pulse Amplitude Modulation (PAM)]] signal. According to the [[Nyquist Theorem]], the [[sampling rate]] ($f_s$) must be at least twice the highest frequency component of the analog signal ($f_s \ge 2 \cdot f_{\max}$).
    
2. **[[Quantization]]:** Each continuous sample amplitude is mapped to the nearest discrete voltage level within a finite set of $L$ levels ($L = 2^n$, where $n$ is the number of bits per sample).
    
3. **[[Encoding]]:** Each quantized level is translated into an $n$-bit binary codeword, producing a serial digital bit stream ready for [[Line Coding]].
    

**[[Bit Rate]] Calculation:** Given:

  

- [[Sampling rate]] ($f_s$) = $10,000\text{ samples/second}$
    
- Bits per sample ($n$) = $6\text{ bits/sample}$
    

$$\text{Bit Rate} = \text{Sampling Rate} \times \text{Bits per Sample}$$

$$\text{Bit Rate} = 10,000 \times 6 = 60,000\text{ bps} = \mathbf{60\text{ kbps}}$$

#### 6. Forward Error Correction (FEC) vs. Automatic Repeat Request (ARQ)

|**Parameter**|**[[Forward Error Correction (FEC)]]**|**[[Automatic Repeat Request (ARQ)]]**|
|---|---|---|
|**Core Mechanism**|The sender adds structured redundant bits ([[error-correcting codes]]) to the data before transmission, allowing the receiver to detect **and reconstruct** corrupted bits independently.|The sender adds [[error-detection]] bits (e.g., [[Cyclic Redundancy Check (CRC)]]). Upon detecting an error, the receiver discards the frame and requests retransmission via a reverse channel.|
|**Feedback Channel**|**Not required** ([[simplex]] / unidirectional communication suffices).|**Mandatory** (requires a [[duplex]] / reverse channel for [[ACK]] and [[NAK]] control frames).|
|**Latency & Delay**|Low, deterministic [[latency]]; no round-trip retransmission delays.|Variable, higher latency due to [[Round-Trip Time (RTT)]] waiting for retransmissions.|
|**Bandwidth Overhead**|High constant overhead due to heavy [[redundancy]] in every packet, even on clean links.|Low overhead when the channel is clean; overhead increases only during high error rates.|
|**Example Use Case**|Real-time video/audio streaming, deep-space telemetry, and satellite broadcasts (e.g., [[Reed-Solomon Codes]] or [[Hamming Code]]).|Reliable file transfers and web browsing using [[Transmission Control Protocol (TCP)]] over [[Wi-Fi]] or [[Ethernet]].|

#### 7. Line Coding Signal Diagrams for Bit Stream `101100`

##### (a) [[NRZ-L]] (Non-Return-to-Zero Level)

- **Rule:** Bit `1` is represented by a negative voltage level ($-V$), and bit `0` is represented by a positive voltage level ($+V$) under standard [[polar encoding]] convention.
    

Plaintext

```
Bit Stream :   1       0       1       1       0       0
Voltage    :
    +V     |       +-------+               +-------+-------+
           |       |       |               |               |
     0 ----+-------+-------+-------+-------+---------------+----
           |       |       |       |       |
    -V     +-------+       +-------+-------+
```

##### (b) [[Manchester Encoding]]

- **Rule:** Every bit period has a transition at the middle for [[clock synchronization]].
    
    - Bit `0` = High-to-Low transition ($+V \rightarrow -V$).
        
    - Bit `1` = Low-to-High transition ($-V \rightarrow +V$).
        

Plaintext

```
Bit Stream :    1        0        1        1        0        0
Voltage    :
    +V     |     +---+ +---+        +---+    +---+ +---+    +---+
           |     |   | |   |        |   |    |   | |   |    |   |
     0 ----+-----+---+-+---+--------+---+----+---+-+---+----+---+---
           |     |         |        |   |    |         |    |
    -V     +-----+         +--------+   +----+         +----+
```

### Section C: Long Answer Questions (10 Marks × 1 = 10 Marks)

_(Both questions are answered completely below)._

  

#### Question 8: Frequency Division Multiplexing (FDM) Architecture and Guard Bands

##### 1. System Architecture and Working Mechanism

[[Frequency-Division Multiplexing (FDM)]] is an [[analog multiplexing]] technique used when the total [[bandwidth]] of a shared transmission medium exceeds the combined bandwidths of the individual signals to be transmitted.

  

Plaintext

```
Computer 1 ──► [Modulator f1] ──┐
Computer 2 ──► [Modulator f2] ──┼──► [ Combiner (MUX) ] ═══ Shared Link ═══► [ Splitter (DEMUX) ] ──┬──► [BPF f1] ──► [Demod] ──► Server Port 1
Computer 3 ──► [Modulator f3] ──┤                                                                 ├──► [BPF f2] ──► [Demod] ──► Server Port 2
Computer 4 ──► [Modulator f4] ──┘                                                                 ├──► [BPF f3] ──► [Demod] ──► Server Port 3
                                                                                                  └──► [BPF f4] ──► [Demod] ──► Server Port 4
```

- **Transmitting Side ([[Multiplexer]]):**
    
    1. Each of the four computers generates a [[baseband signal]] occupying a similar base frequency range (e.g., $0$ to $B\text{ Hz}$).
        
    2. Each signal feeds into a separate **[[modulator]]** driven by a distinct [[carrier frequency]] ($f_1, f_2, f_3, f_4$). [[Modulation]] shifts each computer's signal upward into a unique, non-overlapping frequency band.
        
    3. An analog **[[combiner]]** sums these four modulated carrier signals into a single [[composite signal]] and injects it onto the shared physical link.
        
- **Receiving Side ([[Demultiplexer]]):**
    
    1. At the server end, the composite signal enters the **[[demultiplexer]]**, which splits the signal equally across four parallel branches.
        
    2. Each branch passes through a **[[Band-Pass Filter (BPF)]]** tuned specifically to one carrier frequency band ($f_1, f_2, f_3,$ or $f_4$). Each [[Band-Pass Filter (BPF)]] allows only its designated frequency range to pass while attenuating all other channels.
        
    3. The filtered signal enters a **[[demodulator]]**, which strips away the carrier frequency and recovers the original baseband data stream for the server.
        

##### 2. Role of Guard Bands and Interference Without Them

- **[[Guard Bands]]:** Unused frequency strips placed between adjacent modulated channels to provide a safety margin.
    
- **Consequence of Omitting Guard Bands:**
    
    1. **Filter Roll-off Overlap:** Practical [[Band-Pass Filter (BPF)]] circuits do not have infinitely sharp vertical cutoffs; their attenuation slopes gradually at the band edges. Without [[guard bands]], the skirts of adjacent channels overlap, causing **[[Adjacent Channel Interference (ACI)]]** or **[[crosstalk]]**.
        
    2. **[[Carrier Drift]]:** Minor thermal or oscillator frequency drift in the modulators can push one channel's spectrum directly into the neighboring channel, corrupting the demodulated output at the server.
        

#### Question 9: Synchronous TDM & Line Coding Schemes

##### Part 1: [[Synchronous Time-Division Multiplexing (TDM)]]

- **Setup:**
    
    - Users: $A, B, C$ (3 users $\implies$ **3 [[time slots]] per frame**, ordered $[A, B, C]$).
        
    - User $A$ data units: $A_1, A_2, A_3$ (3 units)
        
    - User $B$ data units: $B_1$ (1 unit)
        
    - User $C$ data units: $C_1, C_2$ (2 units)
        
- **Frame Allocation:** Since User $A$ has the maximum number of data units ($3$), the [[multiplexer]] must transmit **3 [[frames]]** to clear all queues. In [[Synchronous Time-Division Multiplexing (TDM)]], slots remain strictly pre-assigned to users regardless of whether they have data ready.
    

Plaintext

```
             ┌────┬────┬────┐   ┌────┬────┬────┐   ┌────┬────┬────┐
Link Flow ◄──┤ C1 │ B1 │ A1 │◄──┤ C2 │ -- │ A2 │◄──┤ -- │ -- │ A3 │
             └────┴────┴────┘   └────┴────┴────┘   └────┴────┴────┘
                 Frame 1            Frame 2            Frame 3
```

|**Frame Number**|**Slot 1 (User A)**|**Slot 2 (User B)**|**Slot 3 (User C)**|**Empty Slots in Frame**|
|---|---|---|---|---|
|**Frame 1**|$A_1$|$B_1$|$C_1$|$0$|
|**Frame 2**|$A_2$|`Empty`|$C_2$|$1$|
|**Frame 3**|$A_3$|`Empty`|`Empty`|$2$|

- **Total Number of Empty Slots:** $0 + 1 + 2 = \mathbf{3\text{ empty slots}}$ (out of $9$ total slots transmitted).
    

##### Part 2: [[Line Coding]] for Bit Stream `11010010`

- **Initial Conditions:**
    
    - Line voltage before the first bit = $+V$ (positive level).
        
    - First `1` in [[Alternate Mark Inversion (AMI)]] is encoded as $+V$.
        

###### (a) [[NRZ-I]] (Non-Return-to-Zero Inverted)

- **Rule:** A `1` causes a **transition** ([[inversion]]) at the beginning of the bit interval; a `0` causes **no transition** (maintains previous voltage level).
    
- **State Trace:** Initial ($+V$) $\rightarrow$ `1` ($-V$) $\rightarrow$ `1` ($+V$) $\rightarrow$ `0` ($+V$) $\rightarrow$ `1` ($-V$) $\rightarrow$ `0` ($-V$) $\rightarrow$ `0` ($-V$) $\rightarrow$ `1` ($+V$) $\rightarrow$ `0` ($+V$).
    

Plaintext

```
Bit Stream :   1     1     0     1     0     0     1     0
Init (+V)  :
    +V     |--+     +-----+           +-----+     +-----+-----+
           |  |     |     |           |     |     |
     0 ----+--+-----+-----+-----------+-----+-----+-----------
           |  |     |     |           |     |     |
    -V     |  +-----+     +-----+-----+     +-----+
```

###### (b) [[Differential Manchester]]

- **Rule:** Always transitions at the **middle** of every bit period for [[self-clocking]] synchronization.
    
    - Bit `0` = **Transition** at the beginning of the bit interval.
        
    - Bit `1` = **No transition** at the beginning of the bit interval (continues from the end level of the previous bit).
        
- **State Trace (starting from $+V$):**
    
    1. `1`: No start transition (stays $+V$), mid transition to $-V$.
        
    2. `1`: No start transition (stays $-V$), mid transition to $+V$.
        
    3. `0`: Start transition to $-V$, mid transition to $+V$.
        
    4. `1`: No start transition (stays $+V$), mid transition to $-V$.
        
    5. `0`: Start transition to $+V$, mid transition to $-V$.
        
    6. `0`: Start transition to $+V$, mid transition to $-V$.
        
    7. `1`: No start transition (stays $-V$), mid transition to $+V$.
        
    8. `0`: Start transition to $-V$, mid transition to $+V$.
        

Plaintext

```
Bit Stream :   1      1      0      1      0      0      1      0
Init (+V)  :
    +V     |--+         +---+  +---+  +---+  +---+         +---+
           |  |         |   |  |   |  |   |  |   |         |   |
     0 ----+--+---------+---+--+---+--+---+--+---+---------+---+---
           |  |         |   |  |   |  |   |  |   |         |   |
    -V     |  +----+----+   +--+   +--+   +--+   +----+----+   +
```

###### (c) [[Alternate Mark Inversion (AMI)]]

- **Rule:** Bit `0` is represented by neutral zero voltage ($0\text{ V}$). Bit `1` alternates between $+V$ and $-V$ (starting with $+V$ as specified), eliminating [[DC component]] buildup.
    
- **State Trace:** `1` ($+V$), `1` ($-V$), `0` ($0\text{ V}$), `1` ($+V$), `0` ($0\text{ V}$), `0` ($0\text{ V}$), `1` ($-V$), `0` ($0\text{ V}$).
    

Plaintext

```
Bit Stream :   1     1     0     1     0     0     1     0
Voltage    :
    +V     +-----+           +-----+
           |     |           |     |
     0 ----+     +     +-----+     +-----+-----+     +-----+---
                 |     |                       |     |
    -V           +-----+                       +-----+
```

###### (d) Scheme with Mandatory Mid-Bit Transition

**[[Differential Manchester]]** always has a transition in the middle of every bit interval, regardless of whether the bit is `0` or `1`. This guarantees [[self-clocking]] synchronization between the transmitter and receiver even during long sequences of consecutive `0`s or `1`s, preventing [[clock drift]].

### Related Topics

- [[Data Link Layer]]
    
- [[Physical Layer]]
    
- [[Error Detection and Correction]]
    
- [[Multiplexing]]