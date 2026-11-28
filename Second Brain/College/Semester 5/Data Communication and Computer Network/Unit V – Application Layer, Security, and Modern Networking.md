## 1. Application Layer Protocols

### 1.1 Introduction to the Application Layer

The [[Application Layer]] is the seventh and topmost layer of the [[OSI Model]]. It provides network services directly to user applications.

It allows applications running on different devices to communicate over a network.

**Main functions:**

- Provides network services to applications.
    
- Supports web browsing and file transfer.
    
- Enables email communication.
    
- Provides domain name resolution.
    
- Supports remote access and network resource sharing.
    

**Examples of Application Layer Protocols:**

- [[DNS]] – Domain Name System.
    
- [[HTTP]] – Hypertext Transfer Protocol.
    
- [[HTTPS]] – Hypertext Transfer Protocol Secure.
    
- [[FTP]] – File Transfer Protocol.
    
- [[SMTP]] – Simple Mail Transfer Protocol.
    
- [[POP3]] – Post Office Protocol.
    
- [[IMAP]] – Internet Message Access Protocol.
    

---

### 1.2 Domain Name System (DNS)

[[DNS]] stands for Domain Name System. It is a distributed and hierarchical naming system that translates human-readable domain names into IP addresses.

**Example:**

When a user enters `www.google.com`, DNS finds the corresponding IP address so the browser can connect to the server.

#### Hierarchical Structure of DNS

DNS uses a hierarchical structure consisting of several levels.

**Main components:**

1. **Recursive Resolver**
    
    - Receives DNS queries from client devices.
        
    - Finds the required IP address by contacting other DNS servers if the answer is not cached.
        
2. **Root DNS Server**
    
    - Located at the top of the DNS hierarchy.
        
    - Directs the resolver to the appropriate Top-Level Domain server.
        
3. **Top-Level Domain (TLD) Server**
    
    - Handles domain extensions such as `.com`, `.org`, `.in`, and `.edu`.
        
    - Directs the resolver to the authoritative DNS server.
        
4. **Authoritative DNS Server**
    
    - Stores the actual DNS records for a domain.
        
    - Provides the requested DNS information, such as an IP address.
        

**DNS Hierarchy:**

```
              Root DNS Server
                     |
              .com TLD Server
                     |
          Authoritative DNS Server
                     |
              www.example.com
                     |
                IP Address
```

#### Step-by-Step DNS Resolution

Suppose a user enters `www.example.com`.

1. The browser checks its DNS cache.
    
2. The operating system checks its local DNS cache.
    
3. If no result is found, the query is sent to a recursive resolver.
    
4. The resolver contacts a root DNS server.
    
5. The root server directs it to the `.com` TLD server.
    
6. The TLD server provides the authoritative DNS server's information.
    
7. The authoritative server returns the requested IP address.
    
8. The resolver sends the IP address back to the client.
    
9. The result is cached for future use.
    

**DNS Resolution Diagram:**

```
       User / Browser
              |
              v
       Recursive Resolver
              |
              v
         Root Server
              |
              v
         TLD Server
              |
              v
     Authoritative Server
              |
              v
         IP Address
              |
              v
        User / Browser
```

**Important:** The resolver usually performs the lookup on behalf of the client. DNS responses may be cached at multiple levels to reduce lookup time.

#### DNS Caching and TTL

**DNS Caching:**

DNS caching temporarily stores previously resolved domain names and their corresponding DNS records.

**Advantages:**

- Reduces DNS lookup time.
    
- Decreases network traffic.
    
- Reduces the load on DNS servers.
    
- Improves browsing performance.
    

**TTL (Time to Live):**

TTL specifies how long a DNS record may remain cached before it should be refreshed.

For example, if a DNS record has a TTL of 3600 seconds, it can be cached for approximately one hour.

#### DNS Port Number

- DNS primarily uses UDP port 53 for ordinary queries.
    
- TCP port 53 is used for operations such as zone transfers and can also be used for queries and responses when required.
    

#### DNS Record Types

|Record|Purpose|Example|
|---|---|---|
|A|Maps a domain to an IPv4 address|example.com → 192.0.2.1|
|AAAA|Maps a domain to an IPv6 address|example.com → IPv6 address|
|CNAME|Creates an alias for another domain name|www → example.com|
|MX|Specifies mail servers for a domain|mail.example.com|
|NS|Identifies authoritative name servers|ns1.example.com|

**Remember:**

- A = IPv4 address.
    
- AAAA = IPv6 address.
    
- CNAME = Alias.
    
- MX = Mail server.
    
- NS = Name server.
    

---

### 1.3 HTTP and HTTPS

#### HTTP (Hypertext Transfer Protocol)

[[HTTP]] is an Application Layer protocol used for communication between web browsers and web servers.

It follows a request-response model.

**Working:**

1. The browser sends an HTTP request to the web server.
    
2. The server processes the request.
    
3. The server returns an HTTP response.
    
4. The browser displays the received content.
    

**HTTP Port:** TCP port 80 by default.

#### HTTP Request Structure

An HTTP request contains:

1. Request Line – Method, URL/path, and HTTP version.
    
2. Headers – Additional information about the request.
    
3. Blank Line – Separates headers from the message body.
    
4. Body – Optional data sent to the server.
    

**Example:**

```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Chrome
Accept: text/html
```

#### HTTP Response Structure

An HTTP response contains:

1. Status Line – HTTP version and status code.
    
2. Headers – Information about the response.
    
3. Blank Line – Separates headers from the body.
    
4. Body – Requested content or response data.
    

**Example:**

```
HTTP/1.1 200 OK
Content-Type: text/html

<html>
  <body>Hello World</body>
</html>
```

#### Common HTTP Methods

|Method|Purpose|
|---|---|
|GET|Retrieves data from a server|
|POST|Sends data to a server, often to create a resource|
|PUT|Creates or replaces a resource at a specified URI|
|DELETE|Deletes a specified resource|

#### Common HTTP Status Codes

|Code|Meaning|Description|
|---|---|---|
|200|OK|Request successful|
|201|Created|Resource successfully created|
|301|Moved Permanently|Resource has a new permanent URL|
|400|Bad Request|Invalid client request|
|401|Unauthorized|Authentication is required or has failed|
|403|Forbidden|Access is not permitted|
|404|Not Found|Requested resource does not exist|
|500|Internal Server Error|Server encountered an error|
|503|Service Unavailable|Server is temporarily unavailable|

#### HTTP Statelessness

HTTP is a **stateless protocol**, meaning each request is independent by default.

The server does not automatically remember previous requests from a client.

**Problem:**

For example, when a user logs into a website, the server needs a way to recognize that user during subsequent requests.

#### Session Management

Web applications use different mechanisms to maintain user sessions.

**1. Cookies**

- Small pieces of data stored by the browser.
    
- Sent with matching requests to the server.
    
- Commonly used to store session identifiers and preferences.
    

**2. Tokens**

- Digital credentials used to identify or authorize a user.
    
- Often stored and transmitted using mechanisms such as bearer tokens.
    
- JSON Web Token (JWT) is a common token format.
    

**3. URL Rewriting**

- Session information is included in the URL.
    
- The server uses the information to identify a session.
    
- Less preferred because URLs can be exposed through browser history, logs, and shared links.
    

#### HTTPS (HTTP Secure)

[[HTTPS]] is the secure version of HTTP. It uses [[TLS]] (Transport Layer Security) to protect communication between a browser and a web server.

**HTTPS = HTTP + TLS**

**HTTPS Port:** TCP port 443 by default.

**Security features:**

- **Confidentiality:** Encrypts transmitted data.
    
- **Integrity:** Detects unauthorized modification.
    
- **Authentication:** Uses digital certificates to help verify the server's identity.
    

**HTTP vs HTTPS**

|Feature|HTTP|HTTPS|
|---|---|---|
|Full form|Hypertext Transfer Protocol|Hypertext Transfer Protocol Secure|
|Security|No built-in transport encryption|Protected using TLS|
|Default port|80|443|
|Encryption|No TLS by default|Yes|
|Authentication|No TLS certificate authentication|Server authentication through certificates|
|Data protection|Not encrypted by HTTP itself|Encrypted in transit|

**Important:** HTTPS protects data while it travels between the client and server. It does not automatically protect a compromised device or server.

---

### 1.4 File Transfer Protocol (FTP)

[[FTP]] stands for File Transfer Protocol. It is an Application Layer protocol used to transfer files between a client and a server over a TCP connection.

**Main features:**

- Supports file uploading and downloading.
    
- Supports directory listing.
    
- Uses separate control and data connections.
    
- Provides user authentication through commands such as USER and PASS.
    

#### FTP Connections

FTP uses two separate TCP connections.

**1. Control Connection**

- Used to send commands and receive responses.
    
- Uses TCP port 21.
    
- Remains active during the FTP session.
    

**2. Data Connection**

- Used for transferring files and directory listings.
    
- Uses TCP port 20 in traditional active mode.
    
- Uses a server-selected port in passive mode.
    

#### Common FTP Commands

|Command|Purpose|
|---|---|
|USER|Specifies the username|
|PASS|Specifies the password|
|LIST|Lists directory contents|
|RETR|Downloads a file|
|STOR|Uploads a file|
|QUIT|Ends the FTP session|

#### Active vs Passive FTP

**Active Mode:**

- Client establishes the control connection to server port 21.
    
- Client tells the server which client-side port to use for data.
    
- Server initiates the data connection from its TCP port 20 to the client's specified port.
    
- Can cause problems with client-side firewalls and NAT.
    

**Passive Mode:**

- Client establishes the control connection to server port 21.
    
- Server provides an IP address and port for the data connection.
    
- Client initiates the data connection to that server-selected port.
    
- Works more easily with most client-side firewalls and NAT configurations.
    

|Feature|Active FTP|Passive FTP|
|---|---|---|
|Control connection|Client initiates|Client initiates|
|Data connection|Server initiates|Client initiates|
|Data port|Server TCP port 20|Server-selected port|
|Firewall compatibility|Often more difficult|Generally easier for clients|

#### Secure FTP Alternatives

**1. FTPS (FTP Secure)**

- FTP protected using TLS.
    
- Supports encryption and authentication.
    
- Uses FTP's separate control and data connections.
    

**2. SFTP (SSH File Transfer Protocol)**

- A separate file-transfer protocol that operates over SSH.
    
- Commonly uses TCP port 22.
    
- Provides encrypted file transfer and authentication.
    

**FTP vs FTPS vs SFTP**

|Protocol|Security|Common Port|
|---|---|---|
|FTP|No encryption by default|TCP 21|
|FTPS|TLS encryption|TCP 21 or 990, depending on mode|
|SFTP|SSH encryption|TCP 22|

**Important:** SFTP is not simply a secure version of FTP; it is a different protocol.

---

### 1.5 Email Protocols

Email communication uses different Application Layer protocols for sending and retrieving messages.

#### SMTP (Simple Mail Transfer Protocol)

[[SMTP]] is used to send emails from clients to mail servers and between mail servers.

**Common ports:**

- TCP 25 – Server-to-server mail transfer.
    
- TCP 587 – Message submission, commonly with STARTTLS.
    
- TCP 465 – Message submission using implicit TLS.
    

**Function:** Sending email.

#### POP3 (Post Office Protocol Version 3)

[[POP3]] is used to retrieve emails from a mail server.

**Common ports:**

- TCP 110 – Standard POP3.
    
- TCP 995 – POP3 over TLS.
    

**Features:**

- Downloads messages to the client.
    
- Often used for local email storage.
    
- May remove messages from the server depending on client settings.
    

#### IMAP (Internet Message Access Protocol)

[[IMAP]] allows users to access and manage emails stored on a mail server.

**Common ports:**

- TCP 143 – Standard IMAP.
    
- TCP 993 – IMAP over TLS.
    

**Features:**

- Keeps emails on the server.
    
- Synchronizes messages and folders across multiple devices.
    
- Supports server-side mailbox management.
    

#### SMTP vs POP3 vs IMAP

|Feature|SMTP|POP3|IMAP|
|---|---|---|---|
|Main purpose|Sending email|Retrieving email|Accessing and managing email|
|Direction|Outgoing|Incoming|Incoming|
|Storage|Transfers messages|Often downloads locally|Primarily server-based|
|Synchronization|Not its role|Limited|Supports synchronization|
|Common ports|25, 587, 465|110, 995|143, 993|

**Remember:**

- SMTP = Send email.
    
- POP3 = Download email.
    
- IMAP = Synchronize and manage email.
    

---

### 1.6 End-to-End Web Flow

When a user enters a website URL into a browser, several networking processes take place before the webpage appears.

**Example:** User enters `https://www.example.com`.

#### Step-by-Step Process

**Step 1: URL Entry**

The user enters a URL into the browser.

The browser identifies:

- Protocol: HTTPS.
    
- Domain: [www.example.com](http://www.example.com).
    
- Resource path: Requested webpage.
    

**Step 2: DNS Lookup**

- Browser checks its DNS cache.
    
- Operating system checks its local DNS cache.
    
- If needed, a recursive resolver performs DNS resolution.
    
- The browser obtains the server's IP address.
    

**Step 3: TCP Connection Establishment**

For traditional HTTPS over TCP, the browser establishes a TCP connection using the three-way handshake:

```
Client          Server
  |                |
  |---- SYN ------>|
  |<-- SYN-ACK ----|
  |---- ACK ------>|
  |                |
  | TCP Connected  |
```

**Step 4: TLS Handshake**

The browser and server perform a TLS handshake.

- The server presents its digital certificate.
    
- The browser validates the certificate.
    
- The parties establish shared session keys.
    
- Secure communication is established.
    

**Step 5: HTTP Request**

The browser sends an encrypted HTTP request through the TLS connection.

Example:

```
GET / HTTP/1.1
Host: www.example.com
```

**Step 6: Server Response**

The server processes the request and returns an HTTP response containing HTML, CSS, JavaScript, images, or other resources.

**Step 7: Browser Rendering**

The browser:

- Parses HTML to construct the DOM.
    
- Parses CSS to construct the CSSOM.
    
- Executes JavaScript.
    
- Combines the relevant structures to calculate layout and paint the webpage.
    
- Displays the final page.
    

**Complete Web Flow:**

```
      User Enters URL
             |
             v
         DNS Lookup
             |
             v
       Obtain IP Address
             |
             v
      TCP Three-Way Handshake
             |
             v
         TLS Handshake
             |
             v
       Encrypted HTTP Request
             |
             v
       Web Server Response
             |
             v
       HTML / CSS / JavaScript
             |
             v
       Browser Rendering
             |
             v
        Webpage Displayed
```

**Important:** This describes the traditional HTTPS-over-TCP flow, commonly associated with HTTP/1.1 and HTTP/2. HTTP/3 uses QUIC over UDP instead of TCP, with TLS 1.3 integrated into QUIC.

---

## 2. Network Security and Cryptography

### 2.1 Introduction to Network Security

[[Network Security]] refers to the practices and technologies used to protect computer networks, devices, and data from unauthorized access, misuse, modification, and attacks.

**Main objectives:**

- Protect sensitive information.
    
- Prevent unauthorized access.
    
- Maintain data integrity.
    
- Ensure network availability.
    
- Provide secure communication.
    

### 2.2 CIA Triad

The [[CIA Triad]] is a fundamental model of information security consisting of three principles.

**1. Confidentiality**

Ensures that information is accessible only to authorized users.

Examples:

- Encryption.
    
- Access control.
    
- Authentication.
    

**2. Integrity**

Ensures that information remains accurate and is not modified without authorization.

Examples:

- Cryptographic hashes.
    
- Digital signatures.
    
- Checksums.
    

**3. Availability**

Ensures that systems and data remain accessible when required.

Examples:

- Backups.
    
- Redundant servers.
    
- Disaster recovery.
    
- Protection against denial-of-service attacks.
    

|Principle|Meaning|Example|
|---|---|---|
|Confidentiality|Prevents unauthorized information access|Encryption|
|Integrity|Prevents unauthorized modification|Hashing and signatures|
|Availability|Ensures access to services|Backups and redundancy|

### 2.3 Common Network Security Threats

**1. Eavesdropping**

- An attacker secretly monitors network communication.
    
- Sensitive information may be captured.
    
- Example: Capturing unencrypted login credentials on an insecure network.
    

**2. Man-in-the-Middle (MITM) Attack**

- An attacker secretly positions themselves between two communicating parties.
    
- The attacker may intercept or modify communication.
    
- Example: Intercepting communication between a user and a website.
    

**3. Spoofing**

- An attacker impersonates a trusted device, user, or service.
    
- Example: IP spoofing, email spoofing, and DNS spoofing.
    

**4. Denial of Service (DoS)**

- An attacker overwhelms a system or network with excessive traffic or requests.
    
- The target becomes slow or unavailable to legitimate users.
    

**Distributed Denial of Service (DDoS):**

A DDoS attack uses multiple compromised devices to attack a target simultaneously.

### 2.4 Network Security Defences

**1. TLS (Transport Layer Security)**

- Encrypts data during transmission.
    
- Provides integrity protection.
    
- Supports authentication using digital certificates.
    

**2. Authentication**

- Verifies the identity of a user or device.
    
- Uses passwords, biometrics, security keys, or multi-factor authentication.
    

**3. Firewall**

- Monitors and controls incoming and outgoing network traffic.
    
- Applies security rules to allow or block traffic.
    
- Helps prevent unauthorized network access.
    

**4. Intrusion Detection System (IDS)**

- Monitors network or system activity.
    
- Detects suspicious behaviour and possible attacks.
    
- Generates alerts for security administrators.
    

**5. Intrusion Prevention System (IPS)**

- Detects suspicious activity and can automatically block or prevent malicious traffic.
    

**IDS vs IPS**

|IDS|IPS|
|---|---|
|Detects suspicious activity|Detects and blocks suspicious activity|
|Generates alerts|Can take preventive action|
|Usually monitors traffic passively|Commonly operates inline|

---

### 2.5 Cryptography

[[Cryptography]] is the technique of securing information by converting readable data into an unreadable form so that only authorized parties can access it.

**Important Terms:**

- **Plaintext:** Original readable message.
    
- **Ciphertext:** Encrypted unreadable message.
    
- **Encryption:** Converting plaintext into ciphertext.
    
- **Decryption:** Converting ciphertext back into plaintext.
    
- **Key:** A value used by a cryptographic algorithm to encrypt or decrypt information.
    

There are two major types of encryption:

#### 1. Symmetric Key Encryption

Symmetric encryption uses the same secret key for encryption and decryption.

**Working:**

```
Plaintext
    |
    v
Encryption + Secret Key
    |
    v
Ciphertext
    |
    v
Decryption + Same Secret Key
    |
    v
Plaintext
```

**Features:**

- Uses one shared secret key.
    
- Fast and efficient.
    
- Suitable for large amounts of data.
    
- Requires secure key distribution.
    

**Examples:**

- AES (Advanced Encryption Standard).
    
- ChaCha20.
    

#### 2. Asymmetric Key Encryption

Asymmetric encryption uses a pair of mathematically related keys:

- Public Key – Can be shared with others.
    
- Private Key – Must remain secret.
    

Data encrypted using a public key can generally be decrypted using the corresponding private key, for suitable encryption schemes.

**Working:**

```
Plaintext
    |
    v
Encryption + Public Key
    |
    v
Ciphertext
    |
    v
Decryption + Private Key
    |
    v
Plaintext
```

**Features:**

- Uses a public-private key pair.
    
- Supports secure key establishment and digital signatures.
    
- Generally slower than symmetric encryption.
    
- Helps solve the shared-secret distribution problem.
    

**Examples:**

- RSA.
    
- Elliptic Curve Cryptography (ECC).
    

#### Symmetric vs Asymmetric Encryption

|Feature|Symmetric|Asymmetric|
|---|---|---|
|Keys|One shared secret key|Public and private key pair|
|Speed|Generally faster|Generally slower|
|Key distribution|Secret key must be shared securely|Public key can be distributed openly|
|Main use|Bulk data encryption|Key establishment and digital signatures|
|Examples|AES, ChaCha20|RSA, ECC|

#### Why Are Both Used Together?

Modern secure communication combines symmetric and asymmetric cryptography.

**Example: HTTPS**

1. The client and server perform a TLS handshake.
    
2. The server proves its identity using a digital certificate.
    
3. The parties use public-key cryptography and related key-establishment mechanisms to authenticate and establish shared secrets.
    
4. They derive symmetric session keys.
    
5. Symmetric encryption protects the actual data transfer.
    

**Reason:** Asymmetric cryptography supports authentication and key establishment, while symmetric cryptography provides efficient encryption for large amounts of data.

**Important:** Modern TLS generally uses ephemeral Diffie-Hellman key exchange, such as ECDHE, to establish shared secrets. It does not simply encrypt all communication with the server's public key.

---

### 2.6 Hashing and Digital Signatures

#### Hashing

[[Hashing]] is the process of converting data of any size into a fixed-length value called a hash or message digest.

**Features:**

- Produces a fixed-length output.
    
- A small change in input produces a significantly different hash.
    
- One-way operation: it is computationally infeasible to recover the original message from a secure hash alone.
    
- Used for integrity checking and digital signatures.
    

**Examples:**

- SHA-256.
    
- SHA-3.
    

**Example:**

```
Original Message
       |
       v
   SHA-256
       |
       v
Fixed-Length Hash
```

**Important:** Hashing is not encryption. It does not use a decryption key to recover the original message.

#### Digital Signatures

A [[Digital Signature]] is a cryptographic mechanism used to verify the authenticity and integrity of digital data.

It uses a private key for signing and the corresponding public key for verification.

**Working of Digital Signature:**

**1. Signing Process**

1. The sender creates a hash of the original message.
    
2. The sender signs the hash using their private key.
    
3. The message and digital signature are sent to the receiver.
    

**2. Verification Process**

1. The receiver calculates a new hash of the received message.
    
2. The receiver verifies the signature using the sender's public key.
    
3. The verification process checks whether the signature corresponds to the message digest.
    
4. If verification succeeds, the message is authenticated and its integrity is supported.
    

**Diagram:**

```
          SENDER
             |
       Original Message
             |
             v
          Hashing
             |
             v
        Message Hash
             |
             v
    Sign Using Private Key
             |
             v
      Digital Signature
             |
             v
   Message + Signature
             |
             v
          RECEIVER
             |
       Received Message
             |
       ----------------
       |              |
       v              v
     Hashing     Verify Signature
       |          Using Public Key
       v              |
   New Hash           v
       |          Valid / Invalid
       ----------------
             |
             v
       Compare Results
```

**Security Benefits:**

1. **Authentication:** Helps verify the identity of the signer, provided the public key is reliably associated with that identity.
    
2. **Integrity:** Detects unauthorized changes to signed data.
    
3. **Non-repudiation:** Provides evidence that a particular private key signed the data, subject to key security and legal or operational requirements.
    

**Important:** A digital signature does not encrypt the message. It verifies authenticity and integrity.

---

## 3. Modern Networking Trends and Practical Tools

### 3.1 Wireless and Mobile Networking

Wireless networking allows devices to communicate without physical cables by using radio waves and other wireless technologies.

#### 1. Wi-Fi (IEEE 802.11)

[[Wi-Fi]] is a wireless networking technology based on the IEEE 802.11 family of standards.

**Features:**

- Provides wireless LAN connectivity.
    
- Uses radio waves.
    
- Commonly operates in 2.4 GHz, 5 GHz, and 6 GHz bands, depending on the Wi-Fi standard and device.
    
- Connects devices through wireless access points.
    

**Applications:**

- Homes.
    
- Offices.
    
- Colleges.
    
- Public hotspots.
    

#### 2. Cellular Networks (4G LTE and 5G)

Cellular networks provide wireless communication over large geographical areas using cells and base stations.

**4G LTE:**

- Fourth-generation mobile network technology.
    
- Provides high-speed mobile internet.
    
- Supports voice and data services.
    

**5G:**

- Fifth-generation mobile network technology.
    
- Offers higher potential data rates.
    
- Supports lower latency in suitable deployments.
    
- Provides improved capacity and connectivity for large numbers of devices.
    

**Applications:**

- Mobile broadband.
    
- Smart cities.
    
- Industrial automation.
    
- Connected vehicles.
    
- IoT devices.
    

#### 3. Bluetooth

[[Bluetooth]] is a short-range wireless communication technology used to exchange data between nearby devices.

**Features:**

- Operates mainly in the 2.4 GHz ISM band.
    
- Uses low power for many applications.
    
- Supports device pairing.
    
- Bluetooth Low Energy (BLE) is designed for low-power applications.
    

**Applications:**

- Wireless headphones.
    
- Keyboards and mice.
    
- Smartwatches.
    
- Fitness trackers.
    
- IoT sensors.
    

#### Wi-Fi vs Bluetooth vs Cellular

|Feature|Wi-Fi|Bluetooth|Cellular|
|---|---|---|---|
|Coverage|Local area|Short range|Wide area|
|Main purpose|Wireless LAN|Device-to-device connectivity|Mobile communication|
|Power|Moderate|Generally low|Varies|
|Infrastructure|Access point/router|Often direct pairing|Cellular base stations|
|Example|Home internet|Wireless earbuds|5G mobile internet|

### 3.2 Roaming and Handoff

**Roaming:**

[[Roaming]] occurs when a mobile device uses a network other than its home network while maintaining connectivity.

Example: A mobile user travels to another region or country and connects through a partner cellular network.

**Handoff (Handover):**

[[Handoff]] is the process of transferring an active connection from one cell or access point to another.

**Types of Handoff:**

1. **Hard Handoff**
    
    - The old connection is disconnected before the new connection is established.
        
    - Also called break-before-make.
        
2. **Soft Handoff**
    
    - The device maintains connections with more than one base station during the transition.
        
    - Also called make-before-break.
        
    - Used in certain cellular technologies.
        

**Difference:**

|Roaming|Handoff|
|---|---|
|Uses another network, often outside the home network|Transfers an active connection between cells or access points|
|Often related to mobility across network/operator boundaries|Related to maintaining connectivity during movement|
|May involve additional charges depending on the service plan|Usually happens automatically during mobility|

---

### 3.3 Emerging Networking Technologies

#### 1. Cloud Computing and Data Centres

[[Cloud Computing]] provides computing resources such as servers, storage, databases, and networking over the internet.

**Features:**

- On-demand resources.
    
- Scalability.
    
- Remote accessibility.
    
- Pay-as-you-go pricing in many services.
    
- Reduced need to maintain physical infrastructure.
    

**Cloud Service Models:**

|Model|Full Form|Purpose|
|---|---|---|
|IaaS|Infrastructure as a Service|Virtual machines, storage, and networking|
|PaaS|Platform as a Service|Environment for application development|
|SaaS|Software as a Service|Ready-to-use software over the internet|

**Data Centre:**

A [[Data Centre]] is a facility containing servers, storage systems, networking equipment, cooling, and power infrastructure used to store and process data.

**Applications:**

- Cloud hosting.
    
- Banking systems.
    
- Social media platforms.
    
- Online services.
    
- Enterprise applications.
    

#### 2. Internet of Things (IoT)

[[Internet of Things]] refers to a network of physical devices connected to the internet that collect, exchange, and process data.

**Examples:**

- Smart home devices.
    
- Smart watches.
    
- Connected vehicles.
    
- Industrial sensors.
    
- Smart agriculture systems.
    

**Features:**

- Sensor-based data collection.
    
- Network connectivity.
    
- Remote monitoring.
    
- Automation.
    
- Real-time data processing.
    

**Challenges:**

- Security and privacy.
    
- Limited battery power.
    
- Network reliability.
    
- Device compatibility.
    
- Large-scale device management.
    

#### 3. 5G and 6G Networks

**5G:**

[[5G]] is the fifth generation of mobile network technology.

**Key features:**

- Higher potential data rates.
    
- Lower latency in suitable conditions.
    
- Improved network capacity.
    
- Support for massive IoT deployments.
    
- Network slicing.
    

**6G:**

[[6G]] refers to the proposed sixth generation of mobile communication technology, which is still under research and standardisation.

**Potential features:**

- Higher data rates.
    
- More intelligent network management.
    
- Advanced sensing and communication.
    
- AI-native network capabilities.
    
- Improved integration of terrestrial and non-terrestrial networks.
    

**Important:** 6G is an emerging research and standardisation direction, not a widely deployed commercial mobile-network generation as of 2026.

#### 4. Software-Defined Networking (SDN)

[[Software-Defined Networking]] is a networking architecture that separates the control plane from the data plane.

**Control Plane:**

- Makes decisions about where network traffic should go.
    
- Manages routing and network policies.
    

**Data Plane:**

- Forwards packets according to rules installed by the control plane.
    

**Features:**

- Centralised network management.
    
- Programmability.
    
- Flexible traffic control.
    
- Easier automation.
    
- Improved network resource management.
    

**Basic Architecture:**

```
       SDN Applications
              |
              v
       SDN Controller
        (Control Plane)
              |
              v
       Network Devices
         (Data Plane)
              |
              v
       Packet Forwarding
```

#### 5. Network Virtualisation

[[Network Virtualisation]] is the process of creating virtual network resources independent of the underlying physical hardware.

**Examples:**

- Virtual switches.
    
- Virtual routers.
    
- Virtual networks.
    
- Virtual LANs (VLANs).
    
- Network Functions Virtualisation (NFV).
    

**Advantages:**

- Better resource utilisation.
    
- Flexible network configuration.
    
- Reduced hardware dependency.
    
- Easier network management.
    
- Improved scalability.
    

#### 6. Edge Computing

[[Edge Computing]] processes data closer to the devices or users that generate it instead of sending everything to a distant cloud data centre.

**Features:**

- Reduces communication latency.
    
- Reduces bandwidth usage.
    
- Supports real-time processing.
    
- Can improve service reliability.
    

**Applications:**

- Autonomous vehicles.
    
- Industrial IoT.
    
- Smart cameras.
    
- Healthcare monitoring.
    
- Smart cities.
    

**Cloud vs Edge Computing**

|Cloud Computing|Edge Computing|
|---|---|
|Processes data in centralised data centres|Processes data near the source|
|May involve higher network latency|Can reduce latency|
|Suitable for large-scale processing and storage|Suitable for time-sensitive processing|
|Often requires data to travel over the network|Can reduce data transmission|

#### 7. AI-Driven Networking

[[AI-Driven Networking]] uses artificial intelligence and machine learning to monitor, manage, and optimise computer networks.

**Applications:**

- Predicting network failures.
    
- Detecting abnormal traffic.
    
- Identifying security threats.
    
- Optimising bandwidth allocation.
    
- Automated network configuration.
    
- Predictive maintenance.
    

**Advantages:**

- Faster fault detection.
    
- Improved network performance.
    
- Reduced manual configuration.
    
- Better security monitoring.
    

---

## 4. Practical Networking Tools

Several tools are used to study, simulate, monitor, and troubleshoot computer networks.

### 4.1 Wireshark

[[Wireshark]] is an open-source network protocol analyser used to capture and inspect network packets.

**Features:**

- Captures live network traffic.
    
- Displays packet details.
    
- Analyses protocols such as TCP, UDP, DNS, and HTTP.
    
- Helps identify network problems.
    
- Supports filtering and packet inspection.
    

**Common Display Filters:**

|Filter|Purpose|
|---|---|
|`dns`|Displays DNS packets|
|`tcp`|Displays TCP packets|
|`udp`|Displays UDP packets|
|`http`|Displays HTTP packets|
|`icmp`|Displays ICMP packets|
|`ip.addr == 192.168.1.1`|Displays packets involving a specific IP|
|`tcp.port == 443`|Displays TCP packets using port 443|

**Uses:**

- Network troubleshooting.
    
- Protocol analysis.
    
- Security monitoring.
    
- Understanding packet transmission.
    

### 4.2 Cisco Packet Tracer

[[Cisco Packet Tracer]] is a network simulation tool developed by Cisco.

**Features:**

- Creates virtual network topologies.
    
- Simulates routers and switches.
    
- Supports basic network configuration.
    
- Allows users to practise IP addressing and routing.
    
- Provides simulation mode to observe packet movement.
    

**Uses:**

- Learning networking fundamentals.
    
- Practising router and switch configuration.
    
- Understanding network topologies.
    
- Testing basic network communication.
    

### 4.3 GNS3

[[GNS3]] stands for Graphical Network Simulator-3.

It is a network emulation platform used to build and test complex virtual network environments.

**Features:**

- Emulates network devices using supported images.
    
- Supports virtual routers and switches.
    
- Integrates with virtual machines.
    
- Allows realistic network configuration and testing.
    

**Uses:**

- Advanced routing practice.
    
- Network design.
    
- Testing enterprise network configurations.
    
- Preparing for networking certifications.
    

### 4.4 ns-3

[[ns-3]] is an open-source discrete-event network simulator primarily used for research and education.

**Features:**

- Simulates network protocols and communication.
    
- Supports wired and wireless networks.
    
- Allows performance evaluation.
    
- Supports custom network experiments.
    
- Provides detailed simulation results.
    

**Uses:**

- Research in computer networks.
    
- Testing routing protocols.
    
- Studying wireless communication.
    
- Evaluating network performance.
    

### 4.5 Comparison of Practical Tools

|Tool|Main Purpose|Typical Use|
|---|---|---|
|Wireshark|Packet analysis|Capturing and inspecting packets|
|Cisco Packet Tracer|Network simulation|Learning network configuration|
|GNS3|Network emulation|Testing realistic network environments|
|ns-3|Network simulation|Research and protocol performance evaluation|

---

## 5. Important Protocol and Port Number Table

|Protocol|Port|Transport|
|---|---|---|
|FTP Control|21|TCP|
|FTP Data (Active Mode)|20|TCP|
|SSH / SFTP|22|TCP|
|SMTP|25|TCP|
|DNS|53|UDP/TCP|
|HTTP|80|TCP|
|POP3|110|TCP|
|IMAP|143|TCP|
|HTTPS|443|TCP|
|SMTP Submission|587|TCP|
|POP3 over TLS|995|TCP|
|IMAP over TLS|993|TCP|

**Note:** HTTP/3 uses QUIC over UDP, normally on port 443. DNS over HTTPS and DNS over TLS also provide alternative DNS transport mechanisms.

---

## 6. Important Exam Questions

### Short Answer Questions

1. Define the Application Layer.
    
2. What is DNS?
    
3. Explain the role of a recursive DNS resolver.
    
4. What is DNS caching?
    
5. Define TTL in DNS.
    
6. Differentiate between A and AAAA records.
    
7. What is the purpose of an MX record?
    
8. Define HTTP and HTTPS.
    
9. What is the difference between GET and POST?
    
10. What is an HTTP status code?
    
11. Why is HTTP called a stateless protocol?
    
12. What are cookies and tokens?
    
13. What is FTP?
    
14. Differentiate between active and passive FTP.
    
15. What is the difference between FTPS and SFTP?
    
16. Explain the roles of SMTP, POP3, and IMAP.
    
17. What is the CIA Triad?
    
18. Define eavesdropping and MITM attacks.
    
19. Differentiate between symmetric and asymmetric encryption.
    
20. What is a digital signature?
    
21. What is the difference between hashing and encryption?
    
22. Define Wi-Fi and Bluetooth.
    
23. What is roaming?
    
24. Define handoff.
    
25. What is Software-Defined Networking?
    
26. What is edge computing?
    
27. What is IoT?
    
28. State the purpose of Wireshark.
    

### Long Answer Questions

1. Explain the hierarchical structure and working of DNS with a diagram.
    
2. Describe DNS resolution, caching, TTL, and different DNS record types.
    
3. Explain HTTP request and response structures with examples.
    
4. Compare HTTP and HTTPS.
    
5. Explain FTP architecture, commands, and active and passive modes.
    
6. Differentiate between SMTP, POP3, and IMAP.
    
7. Explain the complete process of loading a website from entering a URL to browser rendering.
    
8. Explain the CIA Triad and common network security threats.
    
9. Compare symmetric and asymmetric encryption with suitable examples.
    
10. Explain the working of digital signatures with a diagram.
    
11. Explain Wi-Fi, cellular networks, Bluetooth, roaming, and handoff.
    
12. Discuss modern networking trends such as IoT, 5G, SDN, edge computing, and AI-driven networking.
    
13. Explain the purpose and features of Wireshark, Cisco Packet Tracer, GNS3, and ns-3.
    

---

## 7. Quick Revision Notes

|Topic|Key Point|
|---|---|
|Application Layer|Provides services to user applications|
|DNS|Converts domain names into IP addresses|
|Recursive Resolver|Finds DNS records on behalf of clients|
|Root Server|Directs queries to TLD servers|
|TLD Server|Directs queries to authoritative servers|
|Authoritative Server|Stores domain DNS records|
|TTL|Controls DNS cache lifetime|
|A Record|IPv4 address|
|AAAA Record|IPv6 address|
|CNAME|Domain alias|
|MX|Mail server|
|NS|Name server|
|HTTP|Web communication protocol|
|HTTPS|HTTP secured using TLS|
|HTTP Port|80|
|HTTPS Port|443|
|FTP|File transfer protocol|
|FTP Control Port|21|
|FTP Active Data Port|20|
|SFTP|Secure file transfer over SSH|
|SMTP|Sends email|
|POP3|Retrieves and often downloads email|
|IMAP|Synchronises and manages email|
|CIA Triad|Confidentiality, Integrity, Availability|
|Symmetric Encryption|Same key for encryption and decryption|
|Asymmetric Encryption|Public and private key pair|
|Hashing|Produces a fixed-length digest|
|Digital Signature|Verifies authenticity and integrity|
|Wi-Fi|Wireless LAN technology|
|Bluetooth|Short-range wireless communication|
|Roaming|Using another network outside the home network|
|Handoff|Transfers an active connection|
|IoT|Connected physical devices|
|SDN|Separates control and data planes|
|Edge Computing|Processes data near its source|
|Wireshark|Network packet analyser|
|Packet Tracer|Network simulation tool|
|GNS3|Network emulation platform|
|ns-3|Discrete-event network simulator|

---

## 8. Reference Textbooks and Learning Resources

### Recommended Textbooks

1. **Data Communications and Networking – Behrouz A. Forouzan**
    
    - Useful for understanding Application Layer protocols, network security, and networking fundamentals.
        
2. **Computer Networks – Andrew S. Tanenbaum and David J. Wetherall**
    
    - Covers network architecture, protocols, wireless networking, and modern networking concepts.
        
3. **Computer Networking: A Top-Down Approach – James F. Kurose and Keith W. Ross**
    
    - Particularly useful for Application Layer protocols, DNS, HTTP, email, and network security.
        

### Practical Tools

- [[Wireshark]] – Packet capturing and protocol analysis.
    
- [[Cisco Packet Tracer]] – Network simulation and configuration.
    
- [[GNS3]] – Advanced network emulation.
    
- [[ns-3]] – Network research and simulation.
    

---

## 9. Recommended Study Order

1. Learn [[DNS]] hierarchy, resolution, caching, and record types.
    
2. Understand [[HTTP]] request-response structure and [[HTTPS]] security.
    
3. Study [[FTP]] connections, commands, and transfer modes.
    
4. Memorise the roles of [[SMTP]], [[POP3]], and [[IMAP]].
    
5. Practise the complete end-to-end web flow diagram.
    
6. Understand the [[CIA Triad]] and common security threats.
    
7. Compare symmetric and asymmetric encryption.
    
8. Practise the digital signature diagram.
    
9. Study Wi-Fi, Bluetooth, cellular networks, and handoff.
    
10. Revise IoT, SDN, cloud computing, edge computing, and AI-driven networking.
    
11. Memorise important port numbers and practical tools.
    

**High-priority examination topics:** DNS resolution diagram, HTTP vs HTTPS, FTP active vs passive mode, SMTP vs POP3 vs IMAP, end-to-end web flow, CIA Triad, symmetric vs asymmetric encryption, digital signatures, and SDN.