# IP Addressing

## Logical vs Physical Address

- Logical address = IP address
- Physical address = MAC address

- No IP address = no networking/Internet communication

## IP Versions

- IPv4
- IPv6

### Examples

**IPv4**
```text
192.168.1.1
```

**IPv6**
```text
1233:2312:1231:567g:bufg:ftyi:678h:bn79
```

> Note: This is just an example format. A valid IPv6 address only contains hexadecimal characters (0-9, a-f).

---

## Public vs Private IP

- Public IP address = used over the Internet
- Private IP address = used inside a LAN

### Private IPv4 Ranges

| Range | CIDR |
| ------ | ---- |
| 10.0.0.0 - 10.255.255.255 | 10.0.0.0/8 |
| 172.16.0.0 - 172.31.255.255 | 172.16.0.0/12 |
| 192.168.0.0 - 192.168.255.255 | 192.168.0.0/16 |

---

## IPv4 Basics

- 32-bit address
- 4 octets
- 8 bits per octet
- Each octet ranges from **0-255**
- Computers store/process IP addresses in binary

Example:

```text
00000000.00000000.00000000.00000000 = 0.0.0.0
```

- Approximately **4.3 billion** possible IPv4 addresses

---

## IPv4 Classes

| Class | Network Bits | Host Bits |
| ------ | ------------ | --------- |
| A | 8 | 24 |
| B | 16 | 16 |
| C | 24 | 8 |

- Class D = Multicast addresses

---

# Subnetting

## Subnet

- A smaller part of a network
- Reduces broadcast traffic
- Helps in IP address management

### Subnet Masks (CIDR Notation)

Examples:

- `/24`
- `/16`

### CIDR

- CIDR = Classless Inter-Domain Routing

---

# Basic Network Configuration

Important settings for connecting to a network:

- IPv4 address
- Default gateway
- Subnet mask

---

# Network Commands

## Windows

```cmd
ipconfig
```

## Linux

```bash
ifconfig
```

```bash
ip a
```

---

# DNS

- Google Public DNS
  - `8.8.8.8`
  - `8.8.4.4`

---

# NAT

- NAT = Network Address Translation

---

# EDR

- EDR = Endpoint Detection and Response

---
