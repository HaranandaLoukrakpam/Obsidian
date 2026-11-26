## Data Communication & Computer Networks — 1st Sessional Examination (24BCSM3101R)

### Section A: Short Answer Questions (2 Marks × 4 = 8 Marks)

#### 1. Why are both a MAC address and an IP address needed in every frame instead of just one?

Both addresses operate at different layers with distinct scopes in [[packet switching]] networks:

  

- **[[MAC Address]] (Physical / Link-Local Scope):** Operates at the [[Data Link Layer]] to identify a specific [[Network Interface Card (NIC)]] within the immediate local network segment ([[LAN]]). Because [[MAC addresses]] are flat, burned-in hardware identifiers without hierarchical location info, routers cannot scale global [[routing tables]] using them.
    
- **[[IP Address]] (Logical / End-to-End Scope):** Operates at the [[Network Layer]] to provide hierarchical, location-based global addressing from the original source to the final destination across multiple interconnected networks. As a packet traverses [[routers]], the [[IP address]] remains constant (end-to-end), whereas the source and destination [[MAC addresses]] are rewritten at every intermediate hop.
    

#### 2. Name the OSI layer responsible for each delivery type:

- **(i) Hop-to-hop delivery of a frame:** [[Data Link Layer]] (Layer 2)
    
- **(ii) Source-to-destination delivery of a packet:** [[Network Layer]] (Layer 3)
    
- **(iii) Process-to-process delivery of a message:** [[Transport Layer]] (Layer 4)
    

#### 3. Periodic Signal Frequency and Period Calculation

_(Note: The OCR character `&` corresponds to `8` cycles, matching standard numerical patterns for a $4\text{ ms}$ window)._

  

Given:

  

- Number of cycles ($N$) = $8\text{ cycles}$
    
- Total time ($t$) = $4\text{ ms} = 4 \times 10^{-3}\text{ s}$
    

1. **[[Frequency]] ($f$):**
    
    $$f = \frac{\text{Number of cycles}}{\text{Time}} = \frac{8}{4 \times 10^{-3}\text{ s}} = 2,000\text{ Hz} = \mathbf{2\text{ kHz}}$$
    
2. **[[Period]] ($T$):**
    
    $$T = \frac{1}{f} = \frac{1}{2,000\text{ Hz}} = 0.0005\text{ s} = \mathbf{0.5\text{ ms}}$$
    
3. **Effect of Doubling Frequency:** Because [[Period]] and [[frequency]] are inversely proportional ($T = \frac{1}{f}$), doubling the frequency ($f' = 4\text{ kHz}$) **halves the period** ($T' = \frac{0.5\text{ ms}}{2} = \mathbf{0.25\text{ ms}}$).
    

#### 4. Differentiate between a Protocol and a Standard. Name two standards organizations.

|**Feature**|**[[Protocol]]**|**[[Standard]]**|
|---|---|---|
|**Definition**|A set of formal rules and conventions that govern how data is formatted, transmitted, and received between communicating devices.|A documented, universally agreed-upon technical specification established to ensure [[interoperability]] across different vendors and systems.|
|**Key Elements**|Defined by **[[Syntax]]** (structure/format), **[[Semantics]]** (meaning of bits), and **[[Timing]]** (when and how fast data is sent).|Categorized as **[[De Facto]]** (adopted by widespread market usage) or **[[De Jure]]** (legislated by an officially recognized body).|

- **Two Networking Standards Organizations:**
    
    1. [[Institute of Electrical and Electronics Engineers (IEEE)]]
        
    2. [[Internet Engineering Task Force (IETF)]] _(or [[International Organization for Standardization (ISO)]], [[International Telecommunication Union (ITU)]])_
        

### Section B: Descriptive Questions (4 Marks × 3 = 12 Marks)

#### 5. Wavelength ($\lambda$) Calculation and Frequency–Wavelength Relationship

Given:

  

- [[Frequency]] ($f$) = $1\text{ GHz} = 1 \times 10^9\text{ Hz}$
    
- Formula: $\lambda = \frac{c}{f}$, where $c$ is the [[propagation speed]] in the medium.
    

**(a) Propagation in Air ($c = 3 \times 10^8\text{ m/s}$):**

  

$$\lambda_{\text{air}} = \frac{3 \times 10^8\text{ m/s}}{1 \times 10^9\text{ Hz}} = \mathbf{0.3\text{ m}} \text{ (or } 30\text{ cm)}$$

**(b) Propagation in Optical Fibre ($c = 2 \times 10^8\text{ m/s}$):**

  

$$\lambda_{\text{fibre}} = \frac{2 \times 10^8\text{ m/s}}{1 \times 10^9\text{ Hz}} = \mathbf{0.2\text{ m}} \text{ (or } 20\text{ cm)}$$

**What This Proves About Frequency and Wavelength:**

  

- **[[Frequency]] is an invariant property of the source:** When a signal transitions from air into an [[optical fibre]], its [[frequency]] ($1\text{ GHz}$) remains completely unchanged.
    
- **[[Wavelength]] depends on the transmission medium:** Because $\lambda = \frac{v}{f}$, [[Wavelength]] is directly proportional to the [[propagation speed]] ($v$) in the medium. When the signal slows down in glass fibre, its cycles compress spatially, shortening the [[Wavelength]] from $0.3\text{ m}$ to $0.2\text{ m}$.
    

#### 6. Bit Rate vs. Signal Rate, Bandwidth vs. Throughput, and Nyquist Capacity

##### (a) Distinctions

1. **[[Bit Rate]] vs. [[Signal Rate]]:**
    
    - **[[Bit Rate]] ($N$):** The number of data bits transmitted per second, measured in **bits per second (bps)**.
        
    - **[[Signal Rate]] ($S$):** The number of signal elements (voltage/phase/frequency changes) sent per second across the physical medium, measured in **[[baud]]**. They are related by $S = \frac{N}{r}$, where $r$ is the number of data bits carried per signal element ($r = \log_2 L$).
        
2. **[[Bandwidth]] vs. [[Throughput]]:**
    
    - **[[Bandwidth]]:** The theoretical maximum capacity of a communication medium—either the range of frequencies it can pass (in **Hz**) or its peak rated bit capacity (in **bps**).
        
    - **[[Throughput]]:** The actual, real-world rate at which data is successfully delivered over a channel at a given moment (in **bps**), which is always less than or equal to the physical [[bandwidth]] due to [[latency]], network congestion, protocol overhead, and packet loss.
        

##### (b) Maximum Data Rate Using [[Nyquist Bit Rate Formula]]

Given:

  

- Channel [[bandwidth]] ($B$) = $3\text{ kHz} = 3,000\text{ Hz}$
    
- Number of discrete signal levels ($L$) = $4$
    

$$\text{Max Data Rate} = 2 \times B \times \log_2(L)$$

$$\text{Max Data Rate} = 2 \times 3,000 \times \log_2(4) = 6,000 \times 2 = \mathbf{12,000\text{ bps}} \text{ (or } \mathbf{12\text{ kbps}}\text{)}$$

#### 7. Telephone Channel Passband ($300\text{ Hz} – 3400\text{ Hz}$) and Composite Signals

According to [[Fourier Analysis]], any complex [[analog signal]] (voice or music) is a **[[composite signal]]** made up of a sum of simple sine waves at different frequencies, amplitudes, and phases.

  

##### (a) Why a Voice on a Phone Call is Still Recognizable

- **[[Fundamental Frequency]] and Formants:** The core energy and intelligibility of human speech—including the [[Fundamental Frequency]] (pitch, typically $85\text{ Hz} – 255\text{ Hz}$) and the primary [[formants]] (resonant frequencies that distinguish vowels and consonants)—are concentrated below $3,400\text{ Hz}$.
    
- **[[Harmonics]] Retention:** Although frequencies below $300\text{ Hz}$ and above $3,400\text{ Hz}$ are filtered out by the [[band-pass filter]], the brain reconstructs missing fundamental pitches from the remaining lower [[Harmonics]] present inside the $300\text{ Hz} – 3,400\text{ Hz}$ voiceband, preserving speaker identity and word clarity.
    

##### (b) Why Music Over a Phone Call Sounds Poor

- **Wide [[Frequency Spectrum]]:** Musical instruments produce rich, wide-band [[composite signals]] spanning roughly $20\text{ Hz}$ to $20,000\text{ Hz}$.
    
- **Loss of Bass and Timbre:** Passing music through a narrow $3.1\text{ kHz}$ [[band-pass filter]] strips away all low-frequency bass fundamentals (below $300\text{ Hz}$) and all high-frequency overtones/harmonics (above $3,400\text{ Hz}$). Because upper [[Harmonics]] define an instrument's unique **[[timbre]]** (tonal color), truncating them makes music sound thin, muffled, and distorted.
    

### Section C: In-Depth Long Answer Questions (5 Marks × 2 = 10 Marks)

#### 8. Protocol Layering Explained Through the Indian Postal System

##### Why [[Protocol Layering]] is Required

Modern network communication involves dozens of complex, interdependent tasks—application formatting, reliable delivery, global routing, local addressing, and physical electrical signaling. [[Protocol Layering]] divides this complexity into modular, hierarchical layers where:

  

1. Each layer performs a well-defined function and provides services to the layer immediately above it while hiding implementation details ([[abstraction]]).
    
2. Changes in one layer (e.g., switching from [[Wi-Fi]] to [[Ethernet]] or [[optical fibre]]) do not require rewriting upper-layer software (e.g., web browsers).
    
3. Peer layers at sender and receiver communicate logically using standardized rules.
    

##### Analogy with the Indian Postal System

Suppose a sender in Guwahati writes a letter to a recipient in Imphal:

  

Plaintext

```
SENDER (Guwahati)                                              RECEIVER (Imphal)
┌──────────────────────────────────┐                          ┌──────────────────────────────────┐
│ Application: Writes letter       │ ◄── Logical Content ───► │ Application: Reads letter        │
├──────────────────────────────────┤                          ├──────────────────────────────────┤
│ Transport: Puts in envelope +    │ ◄── Registered Mail ───► │ Transport: Opens envelope +      │
│ PIN code / Speed Post tracking   │                          │ signs delivery receipt           │
├──────────────────────────────────┤                          ├──────────────────────────────────┤
│ Network: RMS sorting by PIN code │ ◄── City-to-City Route ─► │ Network: Arrives at Imphal GPO   │
│ (Guwahati RMS ──► Imphal RMS)    │                          │ via regional sorting hub         │
├──────────────────────────────────┤                          ├──────────────────────────────────┤
│ Data Link & Physical: Mail bag   │ ◄── Physical Transit ──► │ Data Link & Physical: Postman    │
│ loaded onto flight / mail van    │                          │ delivers to local street address │
└──────────────────────────────────┘                          └──────────────────────────────────┘
```

|**Postal Stage**|**Corresponding [[IP 3]] / [[OSI]] Layer**|**Functional Comparison**|
|---|---|---|
|**1. Writing the Letter**|**[[Application Layer]]**|The sender composes the message in a mutually understood language (e.g., English or Manipuri), just as HTTP/SMTP formats user data.|
|**2. Envelope & Speed Post Receipt**|**[[Transport Layer]]**|Placing the letter inside an envelope with recipient/sender names and opting for Speed Post tracking mirrors adding [[port numbers]] (process delivery) and [[TCP]] sequence/acknowledgment reliability.|
|**3. PIN Code Sorting (RMS)**|**[[Network Layer]]**|India Post routes mail bags across cities using hierarchical **6-digit PIN codes** via Railway Mail Service (RMS) hubs, directly mirroring [[routers]] forwarding packets across networks using hierarchical [[IP addresses]].|
|**4. Mail Bags & Local Postman**|**[[Data Link Layer]]**|At each intermediate hub and final post office, letters are bundled into hop-specific mail bags and handed to a local postman who knows the physical house location—mirroring hop-by-hop [[Framing]] and local [[MAC addressing]].|
|**5. Road, Rail, or Air Transport**|**[[Physical Layer]]**|Mail vans, trains, and cargo aircraft physically move the bags across geography, analogous to copper cables, [[optical fibres]], and radio waves carrying raw bits ($0$s and $1$s).|

#### 9. End-to-End Trace of a Web Request Through the TCP/IP Protocol Suite

When a student enters a URL (e.g., `[http://example.com](http://example.com)`) into a browser, the request travels **down** the [[IP Protocol Suite]] at the client ([[encapsulation]]) and **up** the stack at the web server ([[decapsulation]]).

  

Plaintext

```
CLIENT (Sender)                                                       WEB SERVER (Receiver)
┌───────────────────────────┐                                         ┌───────────────────────────┐
│ Application Layer (HTTP)  │ ── Data (HTTP GET)                      │ Application Layer (HTTP)  │
│            │ (Encapsulate)│                                         │            ▲ (Decapsulate)│
│            ▼              │                                         │            │              │
│ Transport Layer (TCP)     │ ── [TCP Hdr | Data] = Segment           │ Transport Layer (TCP)     │
│            │ (Encapsulate)│                                         │            ▲ (Decapsulate)│
│            ▼              │                                         │            │              │
│ Internet Layer (IP)       │ ── [IP Hdr | Segment] = Packet          │ Internet Layer (IP)       │
│            │ (Encapsulate)│                                         │            ▲ (Decapsulate)│
│            ▼              │                                         │            │              │
│ Network Access (Ethernet) │ ── [MAC Hdr | Packet | FCS] = Frame     │ Network Access (Ethernet) │
│            │              │                                         │            ▲              │
└────────────┼──────────────┘                                         └────────────┼──────────────┘
             │                    Physical Medium (Bits: 10110...)                 │
             └─────────────────────────────────────────────────────────────────────┘
```

##### Step 1: Down the Sender Stack — [[Encapsulation]]

At the sender, each layer wraps the payload received from the layer above with its own control **header** (and trailer at Layer 2):

1. **[[Application Layer]]:**
    
    - **Protocol:** [[Hypertext Transfer Protocol (HTTP)]] (after [[Domain Name System (DNS)]] resolves the domain name to an IP address).
        
    - **Address Used:** [[Uniform Resource Locator (URL)]] / Domain Name.
        
    - **[[Protocol Data Unit (PDU)]]:** **Message / Data** (an `HTTP GET` request).
        
    - **Action:** Passes the HTTP message down to the Transport Layer.
        
2. **[[Transport Layer]]:**
    
    - **Protocol:** [[Transmission Control Protocol (TCP)]].
        
    - **Address Used:** **[[Port Numbers]]** (ephemeral source port e.g., `51420`, destination port `80` for HTTP or `443` for HTTPS).
        
    - **[[Protocol Data Unit (PDU)]]:** **[[Segment]]**.
        
    - **Action (Encapsulation):** Prepends a [[TCP Header]] containing source/destination ports, sequence numbers, and checksums to the HTTP data.
        
3. **[[Internet Layer]] (Network Layer):**
    
    - **Protocol:** [[Internet Protocol (IPv4/IPv6)]].
        
    - **Address Used:** **Logical [[IP Addresses]]** (Client Source IP and Web Server Destination IP).
        
    - **[[Protocol Data Unit (PDU)]]:** **[[Packet]]** (or [[Datagram]]).
        
    - **Action (Encapsulation):** Prepends an [[IP Header]] containing source and destination IP addresses and [[Time to Live (TTL)]] to the TCP segment.
        
4. **[[Network Access Layer]] (Data Link + Physical):**
    
    - **Protocol:** [[Ethernet (IEEE 802.3)]] or [[Wi-Fi (IEEE 802.11)]].
        
    - **Address Used:** **Physical [[MAC addresses]]** (Client NIC Source MAC and Local Default Gateway Router Destination MAC, obtained via [[Address Resolution Protocol (ARP)]]).
        
    - **[[Protocol Data Unit (PDU)]]:** **[[Frame]]** (Data Link) $\rightarrow$ **[[Bits]]** (Physical).
        
    - **Action (Encapsulation):** Prepends a [[MAC Header]] and appends a [[Frame Check Sequence (FCS)]] trailer to form a frame, then encodes it into electrical/optical/radio **bits** onto the transmission medium.
        

##### Step 2: Intermediate Routing & Up the Server Stack — [[Decapsulation]]

- **Across Intermediate [[routers]]:** Each router decapsulates the incoming frame up to the [[Internet Layer]], inspects the destination [[IP address]], consults its [[routing table]], and re-encapsulates the packet into a new frame with updated next-hop [[MAC addresses]].
    
- **At the Web Server (Decapsulation):**
    
    1. **[[Network Access Layer]]:** Receives raw **bits**, reassembles the **[[Frame]]**, verifies error integrity using the [[Frame Check Sequence (FCS)]], checks its own destination [[MAC address]], strips off the MAC header/trailer, and passes the [[Packet]] upward.
        
    2. **[[Internet Layer]]:** Verifies its destination **[[IP address]]**, strips the [[IP Header]], and delivers the [[Segment]] to the Transport Layer.
        
    3. **[[Transport Layer]]:** Reads destination **[[Port Number]]** (`80`), verifies [[TCP]] sequence ordering, sends an acknowledgment (`ACK`), strips the [[TCP Header]], and hands the raw HTTP message to the web server process.
        
    4. **[[Application Layer]]:** The web server software (e.g., Nginx or Apache) processes the `HTTP GET` **Message** and initiates the `HTTP 200 OK` response containing the requested webpage back down the stack to the student's browser.
        

### Related Topics

- [[OSI Reference Model]]
    
- [[IP Protocol Suite]]
    
- [[Encapsulation and Decapsulation]]
    
- [[Nyquist and Shannon Channel Capacity]]