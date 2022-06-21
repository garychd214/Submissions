# Network Models
Network models describe layers of communication. From a security perspective, it is important to understand what happens at each layer, the dependencies, and the weaknesses.

- OSI Model (Open Systems Interconnections)

    <img src = "Pics/CISSP OSI.jpg" width = "400">
- TCP/IP Model

    <img src = "Pics/CISSP TCPIP.jpg" width = "400">

- OSI vs TCP/IP 

    <img src = "Pics/CISSP OSI vs TCPIP.jpg" width = "600">

<br>
<br>


## Decision engines
Decision engines can be purely rule based or incorporate behavior, pattern matching, anomoly detection, predictive analysis or even AI.

- Pattern-matching decisions are based on established known signatures
    - Signatures must be up-to-date

- Behavior-based anomaly decisions rely on predicted nroms and deviations
    - Can be learned over time and/or start with a set of assumption and adapt to local conditions.

### Four possible decision States
    1. True Positive - Actually Normal
    2. True Nagative - Actually Abnormal
    3. False Postive - It shows Abnormal but it's acutally Normal
    4. False Nagative - It shows Normal but it's actually Abnormal

<br>
<br>

## Non-IP Networking Protocols
1. MPLS (Multiprotocol Label Switching)
    - Scalable (Can be grow)
    - Protocol-independent (regardless of protocols)
    - Transport architecture
    - Data packets are assigned labels (tags)
        - MPLS LER(Label Edge Routers) make packet-forwarding decisions based on the label
        - End-to-end circuits use any transport medium and any protocols
        - The LER at the outbound point in MPLS cloud removes the label and formwards the packet using regular IP routing information
    - Operates between Layers 2 and 3

2. DNP3 (Distributed Network Protocol 3)
    - Layer 2 open standards-based communication protocol
    - Used between compenents in process automation systems
    - Primarily in the electric, water, waster water, transportation, oil, and gas industries
    - DNP3 was developed to meet the need for standard porotocol that would allow SCADA system components developed by differing vendors to talk
    - DNP3 ensures the reliability of communications within the environments of utilities (Error Checking)
    - DNP3 does not embed security components

3. FCoE (Fibre Channel over Ethernet)
    - Layer 2 standards-based protocol
    - Allows Fibre Channel frames to be carried over Ethernet links
    - FCoE, network(IP), and storage (iSCSI, Internet Small Computer Systems Interface) data traffic can be consolidated using a single network.
    - FCoE is NOT Routable at the IP Layer

<br>
<br>

## VoIP (Voice over IP)
VoIP is not only the transmission of voice traic over IP (instead of analog circuits) but also the foundation for more <b><u>advanced communications technologies such as web adn video conferencing </b></u> 
<img src = "Pics/CISSP VoIP Terms.jpg" width = "800">

### Protocols
- H.323: First widely adopted protocol
- SIP (Session Initiation Protocol): Leading Multimedia Open Protocol
    <br> CAUTION: availability requires power and network connectivity
    - Protocols
        - Integrity: MD5
        - Encryption: SIP over TLS
        - Privacy: CallerID Suppression
        - Guaranteed Transport: RTP (Real-Time Transport Protocol)
        - Packet Loss: PLC (Packet Loss Concealment)
    - Architecture
        - Proxy Server: NAme mapping and packet relay
        - Registrar Server: Maintains record of user locations
        - Redirect Server: Allow SIP Devices to retain their identity regradless of location (if switch from one device to the other device, maintain the identity)
        - Distributed Member Nodes: Maintain records in a peer-to-peer environment

<br>
<br>

## Wireless Modes
- Ad Hoc mode is a Peer-to-Peer Wireless relationship
- Infrastructure mode topology includes wireless devices, access points, and wired routers connected to the internet
    - WPAN
        - Wireless Personal Area Network
        - 802.15 standard (Wireless Keyboards, Wireless Mouses, etc)
    - WLAN
        - Wireless Local Area Network
        - 802.11 standard
    - WMAN
        - Wireless Metropolitan Area Network 
        - 802.16 standard
    - WWAN
        - Wireless Wide Area Network
        - Point-to-Point microwave linkes

### 802.11 IEEE 

<pre>
Spec        Data Rate   Frequency   Distance    Notes
802.11      2 Mbps      2.4 GHz     100m
802.11b     11 Mbps     2.4 GHz     100m
802.11a     54 Mbps     5  GHz      120m
802.11g     54 Mbps     2.4 GHz     140m
802.11n     150 Mbps    2.4/5 GHz   250m
802.11i                                         Security for 802.11 techonologies
802.11e                                         QoS for priority and time sensitive
</pre>

### 802.11 Security
<img src= "Pics/CISSP 802.11 Security.jpg">

### Wireless Vector Attacks
- Discovery
    - War driving
    - War chalking
- RF Spectrum
    - Sniffing
    - Packet Capture
    - Interference
- Access Point
    - Rogue Access Point / Evil Twin
    - MAC impersonation
- Denial of Service
    - Signal Jamming
    - Packet injection

<br>
<br>

## Network Attack Impact
- Network attacks can result in unauthorized access to or theft of data which is a violation of confidentiality
- Network attacks can result in modification of data, which is a violation of integrity
- Network attacks can result in inaccessibility of data or disruption of service, which is a violation of availability.

### Sniffing
Sniffing is Capturing Packets and it can be done on every layers in the OSI Model
<pre>
Application     -   User ID/PW Sniffing
Presentation    -   SSL/TLS Session Sniffing
Session         -   Telnet and FTP Sniffing
Transport       -   TCP Session Sniffing, UDP Sniffing
Network         -   IP, Port Sniffing
Datalink        -   MAC / ARP Sniffing
Physical        -   Surveillance Sniffing
</pre>

### Poisoning
Poisoning is Manipulating trusted data
- ARP Cache
- Routing table
- DNS Pharming
- Website (XSS)

### Session Hijacking
Session Hijacking attack intercepts communication between two systems via Session
- MITM (Man in the middle) Attack
- Replay Attack

### Spoofing
Spoofing attack is when an attacker impersonates an address, system, or person
- MAC address
- IP address
- Domain
- Hyperlink
- Email Sender
- Trusted source

