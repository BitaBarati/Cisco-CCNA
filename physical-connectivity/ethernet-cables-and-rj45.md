# Ethernet Cables and RJ45

## 1. Required Equipment

Tools and materials for Ethernet cable preparation:

- UTP Ethernet Cable
- RJ45 (8P8C) Connectors
- Crimping Tool
- Wire Stripper
- Cable Tester

## 2. RJ45 Connector

An **RJ45 connector** is commonly used to terminate Ethernet cables.

- Contains 8 contact positions.
- Uses 4 twisted pairs of wires.
- Connects Ethernet cables to network interfaces.

## 3. Ethernet Cable Types

| Cable Type | Wiring Standard | Traditional Use |
|---|---|---|
| Straight-through | Same standard on both ends | PC to Switch, Router to Switch |
| Crossover | T568A on one end, T568B on the other | Similar Ethernet interfaces, such as Switch to Switch |

**Important:** Modern network devices commonly support **Auto-MDI/MDIX**, which automatically adjusts transmit and receive pairs. Therefore, crossover cables are less frequently required.

## 4. T568A and T568B Wiring Standards

Both standards define the arrangement of the eight wires inside an Ethernet connector.

### T568A Pinout

| Pin | Wire Color |
|---:|---|
| 1 | White/Green |
| 2 | Green |
| 3 | White/Orange |
| 4 | Blue |
| 5 | White/Blue |
| 6 | Orange |
| 7 | White/Brown |
| 8 | Brown |

### T568B Pinout

| Pin | Wire Color |
|---:|---|
| 1 | White/Orange |
| 2 | Orange |
| 3 | White/Green |
| 4 | Blue |
| 5 | White/Blue |
| 6 | Green |
| 7 | White/Brown |
| 8 | Brown |

## 5. Straight-through vs Crossover

### Straight-through Cable

Both ends use the same wiring standard.

**Example:**

```text
End A: T568B
End B: T568B
```

### Crossover Cable

One end uses T568A and the other uses T568B.

**Example:**

```text
End A: T568A
End B: T568B
```

## 6. Cable Preparation and Testing

Basic cable preparation workflow:

1. Cut the Ethernet cable to the required length.
2. Remove a small section of the outer jacket.
3. Separate and arrange the wire pairs.
4. Follow the selected T568A or T568B pinout.
5. Insert all eight wires into the connector.
6. Use a crimping tool to secure the connector.
7. Test the cable using a cable tester.

**Verification:**

A correctly terminated straight-through cable should show matching pin numbers at both ends (1–1 through 8–8).

For a crossover cable, the tester should indicate the expected pair crossover.

## 7. Physical Network Connections

Common Ethernet connections:

| Device A | Device B | Typical Cable |
|---|---|---|
| PC | Switch | Straight-through |
| Router | Switch | Straight-through |
| Switch | Switch | Crossover (traditional) |
| PC | PC | Crossover (traditional) |

Modern Auto-MDI/MDIX interfaces can support either cable type for many of these connections.

### Link LED Verification

After connecting the cable:

- Check the Ethernet port LEDs.
- A link indicator usually confirms a physical link.
- Blinking activity LEDs generally indicate traffic.
- No link indicator may indicate a cable, port, or interface problem.

**Note:** LED behavior varies by device model.

## 8. Packet Tracer Lab

### Lab 1: PC to Switch

**Topology:**

```text
PC1 -------- Switch0
```

**Steps:**

1. Add one PC and one Switch to the workspace.
2. Select **Connections**.
3. Choose **Copper Straight-Through**.
4. Connect `PC1 FastEthernet0` to `Switch0 FastEthernet0/1`.
5. Wait for the link status to update.

### Lab 2: Switch to Switch

**Topology:**

```text
Switch0 -------- Switch1
```

**Steps:**

1. Add two switches.
2. Select **Connections**.
3. Choose **Copper Cross-Over** for a traditional crossover exercise.
4. Connect an Ethernet interface on each switch.
5. Check the link indicators.

**Note:** Packet Tracer simulates network connections. It does not simulate physical cable crimping or cable testing.

## 9. Cisco Verification Commands

On a Cisco switch:

```cisco
show interfaces status
show interfaces gigabitEthernet 0/1
show mac address-table
```

These commands help verify:

- Port status
- Interface errors
- Speed and duplex
- Learned MAC addresses

## 10. Troubleshooting

| Problem | What to Check |
|---|---|
| No link light | Cable connection and interface status |
| Cable tester reports incorrect pins | Wire order and connector termination |
| Interface is down | Cable, remote device, and port |
| Intermittent connection | Cable damage or loose connector |
| No MAC address learned | Link status and traffic between devices |

## 11. Key Points

- T568A and T568B are Ethernet wiring standards.
- Straight-through cables use the same standard at both ends.
- Crossover cables use different standards at each end.
- Auto-MDI/MDIX reduces the need for crossover cables.
- A cable tester checks wire continuity and pin mapping.
- Packet Tracer simulates logical connections, not physical cable construction.
