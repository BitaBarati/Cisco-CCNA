# TCP/IP and OSI Models

## 1. OSI vs. TCP/IP

Both models describe how network communication works. OSI provides a 7-layer reference model, while TCP/IP represents the protocol architecture used in real-world networks.

| OSI Layer | TCP/IP Layer | Main Function |
|---|---|---|
| 7. Application | Application | Network services and application protocols |
| 6. Presentation | Application | Data representation and encryption |
| 5. Session | Application | Session management |
| 4. Transport | Transport | End-to-end communication and port numbers |
| 3. Network | Internet | Logical addressing and routing |
| 2. Data Link | Network Access | Ethernet frames and MAC addressing |
| 1. Physical | Network Access | Physical transmission of bits |

## 2. TCP/IP Protocol Stack

The TCP/IP model consists of four layers.

### 2.1. Application Layer

Provides network services to applications.

**Common protocols:**

- HTTP / HTTPS
- DNS
- DHCP
- SSH
- FTP

### 2.2. Transport Layer

Provides communication between application processes using port numbers.

- **TCP:** Connection-oriented, reliable data delivery.
- **UDP:** Connectionless transport with lower protocol overhead.

**Common ports:**

- HTTP: TCP 80
- HTTPS: TCP 443 (TCP-based HTTPS)
- SSH: TCP 22
- DNS: UDP/TCP 53

### 2.3. Internet Layer

Handles logical addressing and packet delivery between networks.

**Common protocols:**

- IPv4 / IPv6
- ICMP
- IPsec

### 2.4. Network Access Layer

Handles communication over the local network and physical transmission.

**Common technologies and protocols:**

- Ethernet
- Wi-Fi
- ARP (IPv4 address resolution)

## 3. Encapsulation and PDU

As data moves down the TCP/IP stack, each layer adds its own protocol information.

| Layer | PDU |
|---|---|
| Application | Data |
| Transport | Segment (TCP) / Datagram (UDP) |
| Internet | Packet |
| Network Access | Frame |

**Encapsulation Process:**

```text
Application Data
       |
       v
TCP Segment / UDP Datagram
       |
       v
IP Packet
       |
       v
Ethernet Frame
       |
       v
Bits
```

At the receiving device, the process is reversed. This is called **Decapsulation**.

## 4. Addressing at Different Layers

| Address Type | Layer | Purpose |
|---|---|---|
| Port Number | Transport | Identifies an application process |
| IP Address | Internet | Identifies a network interface logically |
| MAC Address | Network Access | Identifies an interface on the local Ethernet link |

## 5. Practical Example: PC to Server

Consider a PC accessing a web server on another network.

1. The application generates an HTTP/HTTPS request.
2. The Transport layer uses TCP or UDP, depending on the application protocol.
3. The Internet layer adds source and destination IP addresses.
4. The Network Access layer creates an Ethernet frame.
5. The frame is sent to the local gateway when the destination is outside the local subnet.
6. Routers forward the IP packet toward the destination network.
7. The destination server decapsulates the received data.

**Important:** At each routed Ethernet hop, the Layer 2 frame is replaced with a new frame. The source and destination IP addresses normally remain unchanged unless a mechanism such as NAT modifies them.

## 6. Verification Commands

### 6.1. Windows

**Check IP configuration:**

```cmd
ipconfig /all
```

**Test network connectivity:**

```cmd
ping 192.168.1.1
```

**Display the routing table:**

```cmd
route print
```

**Display the ARP cache:**

```cmd
arp -a
```

### 6.2. Cisco IOS

**Check interface status and IP addresses:**

```cisco
show ip interface brief
```

**Display the routing table:**

```cisco
show ip route
```

**Display the ARP table:**

```cisco
show ip arp
```

**Test connectivity:**

```cisco
ping 192.168.1.1
```

## 7. Troubleshooting Workflow

When network communication fails, check the following:

1. Verify the physical connection and interface status.
2. Check the IP address and subnet mask.
3. Verify the default gateway.
4. Test local connectivity using `ping`.
5. Check ARP resolution.
6. Inspect the routing table.
7. Verify the destination service and port.
