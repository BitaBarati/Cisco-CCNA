# Ethernet Fundamentals

## 1. Ethernet Overview

**Ethernet** is a widely used technology for wired Local Area Networks (LANs).

It defines how devices communicate over an Ethernet link using **frames** and **MAC addresses**.

## 2. Ethernet Frame

An Ethernet frame contains the information required for local network communication.

| Field | Purpose |
|---|---|
| Destination MAC | Identifies the receiving interface |
| Source MAC | Identifies the sending interface |
| EtherType | Identifies the encapsulated protocol, such as IPv4 or IPv6 |
| Payload | Carries the encapsulated data |
| FCS | Detects transmission errors using CRC |

**Important:**

- Standard Ethernet frame size is **64–1518 bytes**, including the FCS, without VLAN tagging.
- A VLAN-tagged Ethernet frame can be larger.
- The **FCS** is used for error detection, not error correction.

## 3. MAC Address

A **MAC address** is a Layer 2 address used for communication on a local network.

**Example:**

    00:1A:2B:3C:4D:5E

**Check the MAC address on Windows:**

    ipconfig /all

**Display the MAC address table on a Cisco switch:**

    show mac address-table

## 4. Ethernet Communication

When a device sends an Ethernet frame:

1. The source device identifies the destination MAC address.
2. The frame is transmitted through the Ethernet link.
3. The receiving switch examines the destination MAC address.
4. The switch forwards the frame based on its MAC address table.
5. The destination device receives the frame.

**Unknown Destination MAC:**

If the destination MAC address is unknown, a switch typically floods the frame out other eligible ports in the same VLAN.

## 5. Cisco Switch Verification

### Check Interface Status

    show interfaces status

Displays port status, VLAN assignment, duplex, and speed.

### Check MAC Address Table

    show mac address-table

Displays learned MAC addresses and their associated switch ports.

### Inspect an Interface

    show interfaces gigabitEthernet 0/1

Displays detailed interface information, including speed, duplex, traffic counters, and errors.

### Check Interface Configuration

    show running-config interface gigabitEthernet 0/1

Displays the configured settings of a specific interface.

## 6. Basic Interface Configuration

**Enter global configuration mode:**

    configure terminal

**Select an interface:**

    interface gigabitEthernet 0/1

**Enable the interface:**

    no shutdown

**Set the interface description:**

    description Connected-to-PC01

**Exit configuration mode:**

    end

**Verify the interface:**

    show interfaces status

## 7. Common Ethernet Issues

| Problem | Verification |
|---|---|
| Interface is down | `show interfaces status` |
| Interface is administratively down | Check for `shutdown` in interface configuration |
| No MAC address learned | Check link status and generate network traffic |
| Interface errors | `show interfaces` |
| Incorrect speed or duplex | Inspect interface configuration and status |

## 8. Practical Verification Workflow

When an Ethernet connection is not working:

1. Check the cable and physical connection.
2. Verify that both interfaces are operational.
3. Check speed and duplex settings.
4. Inspect interface error counters.
5. Verify MAC address learning.
6. Test connectivity between connected devices.
