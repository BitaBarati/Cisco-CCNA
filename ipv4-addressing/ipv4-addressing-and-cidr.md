# IPv4 Addressing and CIDR

## 1. IPv4 Address Overview

**IPv4** is a 32-bit logical address used to identify devices on an IP network.

- Written in dotted-decimal notation.
- Consists of 4 octets.
- Each octet ranges from 0 to 255.
- Example: `192.168.1.10`

## 2. IPv4 Address Classes

In traditional **Classful Addressing**, IPv4 addresses are divided into five classes.

| Class | First Octet Range | Default Subnet Mask | Purpose |
|---|---:|---|---|
| A | 1–126 | 255.0.0.0 (/8) | Large networks |
| B | 128–191 | 255.255.0.0 (/16) | Medium networks |
| C | 192–223 | 255.255.255.0 (/24) | Small networks |
| D | 224–239 | N/A | Multicast |
| E | 240–255 | N/A | Experimental / Reserved |

**Important Notes:**

- `127.0.0.0/8` is reserved for loopback.
- Class D is used for multicast, not normal host addressing.
- Class E is reserved for experimental purposes.
- Classful addressing is historical. Modern networks use CIDR.

## 3. Private and Public IPv4 Addresses

IPv4 addresses are commonly categorized as private or public.

### Private IPv4 Ranges

Private addresses are used inside local networks and are not directly routable over the public Internet.

| Class | Private IP Range | CIDR |
|---|---|---|
| A | 10.0.0.0 – 10.255.255.255 | 10.0.0.0/8 |
| B | 172.16.0.0 – 172.31.255.255 | 172.16.0.0/12 |
| C | 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 |

### Public IPv4 Addresses

- Public IP addresses are globally routable.
- They are assigned by ISPs or allocated through the appropriate Internet address registries.
- They are used for communication across the Internet.

**Important:** Private IP addresses commonly access the Internet through NAT (Network Address Translation).

## 4. Special IPv4 Addresses

| Address / Range | Purpose |
|---|---|
| 127.0.0.0/8 | Loopback |
| 169.254.0.0/16 | Link-Local (APIPA) |
| 0.0.0.0 | Unspecified address |
| 0.0.0.0/0 | Default route |
| 255.255.255.255 | Limited broadcast |

## 5. Subnet Mask

A **subnet mask** separates the network portion from the host portion of an IPv4 address.

**Example:**

```text
IP Address:  192.168.1.10
Subnet Mask: 255.255.255.0
Network:     192.168.1.0
```

The subnet mask determines which bits identify the network and which bits identify the host.

## 6. CIDR (Classless Inter-Domain Routing)

**CIDR** allows flexible network allocation without relying on traditional IP address classes.

It uses a prefix length to identify the network portion of an IP address.

**Example:**

```text
192.168.1.0/24
```

`/24` means that the first 24 bits represent the network portion.

### Common CIDR Prefixes

| CIDR | Subnet Mask | Total Addresses | Usable Hosts* |
|---|---|---:|---:|
| /8 | 255.0.0.0 | 16,777,216 | 16,777,214 |
| /16 | 255.255.0.0 | 65,536 | 65,534 |
| /24 | 255.255.255.0 | 256 | 254 |
| /25 | 255.255.255.128 | 128 | 126 |
| /26 | 255.255.255.192 | 64 | 62 |
| /27 | 255.255.255.224 | 32 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /29 | 255.255.255.248 | 8 | 6 |
| /30 | 255.255.255.252 | 4 | 2 |

*Usable host counts assume traditional IPv4 subnets where network and broadcast addresses are reserved.*

## 7. Basic Subnetting Calculations

### Key Formulas

For a conventional IPv4 subnet:

- **Host bits:** 32 - Prefix Length
- **Total addresses:** 2^Host Bits
- **Usable hosts:** 2^Host Bits - 2

### Example: 192.168.1.0/26

**Given:**

```text
Network:     192.168.1.0/26
Subnet Mask: 255.255.255.192
```

**Results:**

| Item | Value |
|---|---|
| Network Address | 192.168.1.0 |
| First Usable Host | 192.168.1.1 |
| Last Usable Host | 192.168.1.62 |
| Broadcast Address | 192.168.1.63 |
| Total Addresses | 64 |
| Usable Hosts | 62 |

### Block Size

Block size can be calculated using:

```text
Block Size = 256 - Interesting Octet
```

**For /26:**

```text
Subnet Mask: 255.255.255.192
Block Size:  256 - 192 = 64
```

The subnet ranges in the last octet are:

```text
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

## 8. Verification Commands

### Windows

```powershell
ipconfig /all
```

### Cisco IOS

```cisco
show ip interface brief
show running-config
show ip route
```

These commands help verify IP configuration, interface status, and routing information.

## 9. Important Notes

- Classful addressing uses fixed default masks.
- CIDR supports flexible prefix lengths.
- Private IP addresses are not directly routable on the public Internet.
- NAT is commonly used to allow private networks to access the Internet.
- Network and broadcast addresses are generally not assigned to hosts in conventional IPv4 subnets.
- `/31` can be used on point-to-point links, and `/32` identifies a single IPv4 address.
