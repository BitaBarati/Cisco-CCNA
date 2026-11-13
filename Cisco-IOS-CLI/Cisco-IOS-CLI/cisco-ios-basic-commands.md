# Cisco IOS Basic Commands

## 1. Entering CLI Modes

| Command | Mode | Description |
|---|---|---|
| `enable` | User EXEC | Enter Privileged EXEC Mode |
| `disable` | Privileged EXEC | Return to User EXEC Mode |
| `configure terminal` | Privileged EXEC | Enter Global Configuration Mode |
| `exit` | Configuration Modes | Exit current mode |
| `end` | Configuration Modes | Return to Privileged EXEC Mode |

## 2. Device Configuration

### Set Hostname

**Mode:** Global Configuration

    Router(config)# hostname R1
    R1(config)#

Changes the device hostname.

### Configure Interface

**Mode:** Global Configuration → Interface Configuration

    R1(config)# interface gigabitEthernet 0/0
    R1(config-if)# ip address 192.168.1.1 255.255.255.0
    R1(config-if)# no shutdown

Configures an IP address and enables the interface.

## 3. Show Commands

Show commands are primarily executed in Privileged EXEC Mode.

| Command | Description |
|---|---|
| `show version` | Display IOS version and device information |
| `show running-config` | Display current active configuration |
| `show startup-config` | Display saved configuration |
| `show ip interface brief` | Display interface IP addresses and status |
| `show interfaces` | Display detailed interface information |
| `show ip route` | Display the routing table |
| `show clock` | Display device date and time |

### Example: Check Interface Status

    R1# show ip interface brief

Displays a summary of interfaces, IP addresses, and operational status.

## 4. Configuration Management

### Save Configuration

**Mode:** Privileged EXEC

    R1# copy running-config startup-config

Saves the current configuration to NVRAM so it can be loaded after a reboot.

### Verify Configuration

    R1# show running-config
    R1# show startup-config

Displays the active configuration and the saved configuration for comparison.

## 5. Command Help and Completion

| Command | Description |
|---|---|
| `?` | Display available commands |
| `show ?` | Display available show commands |
| `show ip ?` | Display available IP-related commands |
| `Tab` | Complete a partially entered command |
| `Ctrl + A` | Move to the beginning of the line |
| `Ctrl + E` | Move to the end of the line |

## 6. Practical Lab – Basic Router Configuration

### Topology

- 1 Router (R1)
- 1 PC (PC1)
- 1 Copper Straight-Through cable

### Configuration

**Step 1 – Set Hostname**

    Router> enable
    Router# configure terminal
    Router(config)# hostname R1

**Step 2 – Configure Interface**

    R1(config)# interface gigabitEthernet 0/0
    R1(config-if)# ip address 192.168.1.1 255.255.255.0
    R1(config-if)# no shutdown
    R1(config-if)# exit

**Step 3 – Verify Interface**

    R1# show ip interface brief

**Step 4 – Save Configuration**

    R1# copy running-config startup-config

**Step 5 – Verify Saved Configuration**

    R1# show startup-config

## 7. Important Notes

- `running-config` is stored in RAM and contains the active configuration.
- `startup-config` is stored in NVRAM and is loaded during startup.
- `no shutdown` enables an administratively disabled interface.
- Show commands are generally executed in Privileged EXEC Mode.
- A router interface must be connected and operational for its line protocol to become up.
