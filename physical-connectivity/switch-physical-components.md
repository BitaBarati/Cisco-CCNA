# Cisco Switch Physical Components

## 1. Physical View in Cisco Packet Tracer

Cisco Packet Tracer provides a **Physical View** for inspecting the hardware components of network devices.

### 1.1 Accessing Physical View

1. Open Cisco Packet Tracer.
2. Add a Multilayer Switch to the workspace.
3. Open the device window.
4. Select the **Physical** tab.
5. Inspect the available hardware components and module slots.

### 1.2 Main Physical Components

- Power Supply Modules
- Fan Modules
- SFP Transceiver Slots
- Network Interfaces
- Module Bays
- Cover Plates

## 2. Power Supply Modules

**Power Supply Units (PSUs)** provide electrical power to network devices.

### 2.1 AC Power Supply

- Receives electrical power from an AC source.
- Converts input power into the DC power required by internal components.
- Must be compatible with the switch model.

### 2.2 Power Supply Slots

Physical bays designed to accommodate power supply modules.

Some enterprise switches support multiple power supplies for redundancy.

### 2.3 Power Supply Cover Plate

A cover plate protects an unused power supply bay.

**Important:**

- Power supply configurations vary between switch models.
- Redundant power supplies improve power availability.
- Hot-swapping support depends on the hardware platform.

## 3. Fan Modules

Fan modules provide airflow to maintain the operating temperature of internal components.

**Important Considerations:**

- Maintain the required airflow direction.
- Check fan status during hardware troubleshooting.
- Use compatible replacement fan modules.
- Fan failure may cause overheating or reduced system availability.

## 4. SFP Transceiver Modules

**Small Form-Factor Pluggable (SFP)** modules provide flexible connectivity options for network devices.

They allow switches to connect through different transmission media, including:

- Fiber-optic cables
- Copper Ethernet cables

SFP modules are inserted into compatible SFP slots.

### 4.1 GLC-LH-SMD

**Standard:** 1000BASE-LX/LH

| Property | Specification |
|---|---|
| Media | Fiber Optic |
| Connector | Dual LC |
| Wavelength | 1310 nm |
| Fiber Type | Single-Mode / Multimode |
| Maximum Distance | 10 km (SMF) |
| Multimode Distance | Up to 550 m |
| DOM Support | Yes |
| Temperature Range | Extended (-5°C to 85°C) |

**Important:**

- GLC-LH-SMD is an optical SFP transceiver.
- For legacy multimode fiber installations, a mode-conditioning patch cord may be required.
- DOM (Digital Optical Monitoring) provides diagnostic information such as optical power and temperature.

### 4.2 GLC-T

**Standard:** 1000BASE-T

| Property | Specification |
|---|---|
| Media | Copper Ethernet |
| Connector | RJ-45 |
| Speed | 10/100/1000 Mbps |
| Maximum Distance | 100 m |
| Cable | Category 5 or better |
| Temperature Range | Commercial (0°C to 70°C) |

**Important:**

- GLC-T uses twisted-pair copper cabling.
- It supports 10/100/1000 Mbps auto-negotiation.
- It supports Auto MDI/MDIX.

### 4.3 GLC-TE

**Standard:** 1000BASE-T

| Property | Specification |
|---|---|
| Media | Copper Ethernet |
| Connector | RJ-45 |
| Speed | 10/100/1000 Mbps |
| Maximum Distance | 100 m |
| Cable | Category 5 or better |
| Temperature Range | Extended (-5°C to 85°C) |

**Important:**

GLC-TE provides extended operating temperature support compared to GLC-T.

### 4.4 SFP Comparison

| Module | Media | Connector | Speed | DOM |
|---|---|---|---|---|
| GLC-LH-SMD | Fiber | Dual LC | 1 Gbps | Yes |
| GLC-T | Copper | RJ-45 | 10/100/1000 Mbps | No |
| GLC-TE | Copper | RJ-45 | 10/100/1000 Mbps | No |

## 5. Fixed Ports vs. Modular Ports

Cisco switches may provide different types of physical interfaces.

### 5.1 Fixed Ports

- Built directly into the switch.
- Their number and type are determined by the hardware model.
- Commonly used for endpoint and network connections.

### 5.2 Modular Ports

- Designed to accept compatible expansion modules or transceivers.
- Allow different connectivity options.
- May support copper or fiber connections, depending on the platform.

**Important:** Not every switch supports modular expansion. Always check the hardware specifications before selecting a module.

## 6. Hardware Verification Using Cisco IOS

Cisco IOS provides commands to inspect hardware information and interface status.

### 6.1 Display Device Information

**Command Mode:** Privileged EXEC

```cisco
Switch> enable
Switch# show version
```

Displays:

- Cisco IOS software version
- Device model
- System uptime
- Hardware information
- System image information

### 6.2 Display Hardware Inventory

**Command Mode:** Privileged EXEC

```cisco
Switch# show inventory
```

Displays hardware inventory information, including product identifiers and available components on supported platforms.

### 6.3 Display Interface Status

**Command Mode:** Privileged EXEC

```cisco
Switch# show interfaces status
```

Displays:

- Interface status
- VLAN assignment
- Duplex mode
- Speed
- Interface type

### 6.4 Display Transceiver Information

**Command Mode:** Privileged EXEC

```cisco
Switch# show interfaces transceiver detail
```

Displays detailed transceiver diagnostic information when supported by the switch and installed transceiver.

**Note:** Command availability and output depend on the hardware platform and Cisco IOS version.

## 7. Practical Lab – Packet Tracer

### Objective

Identify the physical components of a Cisco Multilayer Switch.

### Procedure

1. Open Cisco Packet Tracer.
2. Add a Multilayer Switch to the workspace.
3. Open the device window.
4. Select the **Physical** tab.
5. Identify the power supply modules.
6. Locate the fan modules.
7. Identify available SFP transceiver slots.
8. Inspect the available modules, including GLC-LH-SMD, GLC-T, and GLC-TE where supported.
9. Open the **CLI** tab.
10. Execute the following commands:

```cisco
Switch> enable
Switch# show version
Switch# show inventory
Switch# show interfaces status
```

### Expected Results

After completing this lab, you should be able to:

- Identify the main physical components of a switch.
- Understand the purpose of power supply and fan modules.
- Differentiate between copper and fiber SFP transceivers.
- Recognize common Cisco SFP module models.
- Inspect basic hardware and interface information using Cisco IOS.

## 8. Important Notes

- Always verify SFP compatibility with the switch model.
- Match the transceiver type with the appropriate cable and connector.
- Check transmission distance and fiber specifications before deployment.
- Do not assume all Cisco switches support the same hardware modules.
- Physical View capabilities in Packet Tracer are simulation-dependent.
- Real hardware specifications must be verified using official Cisco documentation.

## 9. Official Cisco References

- Cisco SFP Modules for Gigabit Ethernet Applications – Data Sheet
- Cisco Catalyst Switch Command References
