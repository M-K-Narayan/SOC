# Computer Networks

## Network Basics

A network is two or more computers sharing data/resources.

### Two Main Aspects

- Physical
  - Wires, cables, hardware, etc.
- Logical
  - Communication between devices

For communication to happen:

- Devices must follow the same communication procedure (protocols).
- Data must not be corrupted during transmission.

---

## Types of Networks (Based on Size)

| Type | Description |
|------|-------------|
| PAN | Personal Area Network (Bluetooth, USB, etc.) |
| LAN | Small geographical network (home, office) |
| WLAN | Wireless LAN |
| CAN | Campus Area Network (group of LANs) |
| MAN | Metropolitan Area Network |
| WAN | Wide Area Network |

---

## Network Architectures

### Peer-to-Peer (P2P)

- All nodes share data.
- No central server.

### Client-Server

- Centralized server manages resources.
- Clients communicate with the server.

---

# Network Protocols

Protocols are a set of rules governing how machines exchange data.

### Physical Protocols

- Define wiring standards.
- RJ-45 pinout.
- Voltage levels on wires.
- Physical transmission characteristics.

### Logical Protocols

- Software rules controlling how and when data is sent/received.
- Work on top of physical protocols.

### Examples

| Purpose | Protocols |
|---------|-----------|
| Web Communication | HTTPS |
| Email | SMTP, POP3, IMAP |
| File Transfer | FTP, SFTP |

---

# OSI Model

- Conceptual reference model.
- Describes how data moves through a network.
- Introduced by ISO in 1984.
- Used for understanding networking.
- Not directly implemented in the real world.

### Classification

- Host Layers
- Media Layers

### Layers

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

### Data Flow

Sending:

```
7 → 6 → 5 → 4 → 3 → 2 → 1
```

Receiving:

```
1 → 2 → 3 → 4 → 5 → 6 → 7
```

---

# TCP/IP Model

Real-world implementation of networking.

1. Network Interface
2. Internet
3. Transport
4. Application

## OSI vs TCP/IP

| OSI | TCP/IP |
|------|---------|
| Physical + Data Link | Network Interface |
| Network | Internet |
| Transport | Transport |
| Session + Presentation + Application | Application |

---

# MAC Address

- OSI Layer 2
- Physical address of the NIC (Network Interface Card)

Structure:

- 48 bits (6 bytes)
- First 24 bits (3 bytes) → OUI (Organizationally Unique Identifier)
- Last 24 bits (3 bytes) → Unique device identifier

---

# IP Address

- Logical address
- OSI Layer 3
- TCP/IP Internet Layer

Types:

- IPv4
- IPv6

---

# Duplex Communication

- **Simplex** - One-way communication only.
- **Half Duplex** - Send and receive, but not simultaneously.
- **Full Duplex** - Send and receive simultaneously.

---

# Transmission Types

- Unicast
- Multicast
- Broadcast

---

# Ethernet

## Network Topologies

- Bus
- Ring
- Star
  - Connected to a central device.
- Mesh
  - Every node connects to every other node.

## Wireless Topologies

- Ad Hoc
- Infrastructure

---

# Networking Devices

## Hub

- Not very intelligent.
- Broadcasts traffic to all ports.

## Switch

- More intelligent than a hub.
- Forwards traffic based on MAC addresses.

## Wireless Access Point (WAP)

- Extends a wired network to wireless devices.

## Range Extender

- Extends Wi-Fi coverage.

## Router

- Connects two or more networks.
- Uses intelligent routing.

## Modem

- Converts analog signals to digital and vice versa.

## SOHO

- Small Office/Home Office networking devices.

## Media Converter

- Converts one media type to another (e.g., copper ↔ fiber).

## Firewall

Filters network traffic.

Types:

- Packet Filtering Firewall
- Circuit-Level Firewall
- Application-Level Firewall

## DHCP Server

- Assigns IP addresses to devices on the network.

---

# Network Cables

1. Coaxial
2. Twisted Pair
3. Fiber Optic

---

# Packet Structure

- Structure of the packet (to be covered later).

---

# Common Network Attacks

- Man-in-the-Middle (MITM)
- DNS Spoofing
- ARP Spoofing
- SYN Flood
- DHCP Starvation
- Packet Sniffing
- Port Scanning

---

# Networking Tools

- [[Wireshark]]
- [[tcpdump]]
- [[netstat]]
- [[nmap]]
- [[nslookup]]
- [[dig]]
- [[traceroute]]
- [[mtr]]

---

# Ports and Protocols

## Why Are Ports and Protocols Important?

- Devices communicate using them.
- Packet analysis.
- Distinguish legitimate vs suspicious traffic.

## Protocol

A set of rules defining how data is transmitted over a network.

Example:

- FTP
- SFTP

## Port

A logical communication endpoint used by protocols.

## Socket

Combination of:

- IP Address
- Port Number

Example:

```text
192.168.1.1:80
```

Total Ports:

```
0 - 65535
```

### Port Ranges

| Range | Purpose |
|--------|----------|
| 0–1023 | Well-Known Ports |
| 1024–49151 | Registered Ports |
| 49152–65535 | Dynamic/Ephemeral Ports |

---

# TCP vs UDP

## TCP (Transmission Control Protocol)

- Connection-oriented
- Reliable
- Packet acknowledgments
- Error checking
- Three-way handshake

### TCP Flags

- SYN
- ACK
- FIN
- RST
- URG
- PSH

TCP Header Size:

```
20 Bytes
```

### Three-Way Handshake

```
SYN
   ↓
SYN/ACK
   ↓
ACK
```

### Why TCP?

- Reliability
- Acknowledgments
- Checksum
- Ordered delivery

---

## UDP (User Datagram Protocol)

- Connectionless
- Lightweight
- Faster than TCP
- No delivery guarantee

Common Uses:

- Gaming
- Audio Streaming
- Video Streaming

UDP Header Size:

```
8 Bytes
```

---

# Important Application Layer Protocols

- DNS
- DHCP
- NTP
- SNMP
- LDAP
- LDAPS
- SMB

---

## DNS

- TCP/UDP 53
- Resolves domain names to IP addresses and vice versa.

Topics:

- DNS Hierarchy
- DNS Record Types
- Name Resolution

---

## DHCP

- UDP 67, 68
- Assigns IP addresses to devices.

---

## NTP

- UDP 123
- Synchronizes time between systems.

---

## SNMP

- UDP 161
- Monitors and manages network devices.

---

## LDAP

- TCP 389
- Accesses and queries directory services.

---

## LDAPS

- TCP 636
- Secure version of LDAP.

---

## SMB

- TCP 445
- File and printer sharing.
- Network file sharing protocol.

---

# Remote Communication Protocols

## Telnet

- TCP 23
- Insecure.
- Mostly replaced by SSH.

## SSH

- TCP 22
- Secure remote access.

## RDP

- TCP 3389
- Remote desktop access for Windows systems.

---

# File Transfer Protocols

## FTP

- TCP 20, 21
- Kind of like a Legacy protocol.
- Insecure.

## SFTP

- TCP 22
- Secure File Transfer Protocol (runs over SSH).

## TFTP

- UDP 69
- Lightweight version of FTP.

---

# Email Protocols

## SMTP

- TCP 25
- Sends email from client/server to mail server.

## POP3

- TCP 110
- Retrieves emails from the server.
- Can use encrypted or plaintext variants depending on configuration.

## IMAP

- TCP 143
- Synchronizes emails with the mail server.
- Commonly used by services like Gmail.

---

# Web Protocols

## HTTP

- TCP 80
- Transfers web content.
- Not encrypted.

## HTTPS

- TCP 443
- Secure version of HTTP.
- Uses TLS encryption.

---

# Why Learn Ports?

- Detect unusual traffic.
- Monitor open ports.
- Understand lateral movement.
- Detect data exfiltration.
- Create IDS/IPS rules.
- Analyze PCAPs using [[Wireshark]] or [[Zeek]].

---

# Useful Tools

- [[nmap]]
- [[Wireshark]]
- [[netstat]] / [[ss]]
- [[Shodan]]
- [[tcpdump]] / [[Zeek]]

---

# TODO

- [ ] Structure of packets
- [ ] Common ports used in day-to-day life
- [ ] Explore KaliGPT

---
