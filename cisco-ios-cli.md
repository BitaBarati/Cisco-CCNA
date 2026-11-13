# Cisco IOS Command-Line Interface (CLI)

## 1. Introduction to Cisco CLI

The Command-Line Interface (CLI) is a text-based interface used to configure, manage, and troubleshoot Cisco network devices.

Administrators use Cisco CLI to:

- Configure routers and switches.
- Manage network interfaces.
- Configure routing and switching features.
- Monitor device status.
- Troubleshoot network connectivity.
- View and modify device configurations.

## 2. Accessing Cisco CLI

Cisco CLI can be accessed through different connection methods:

- Console Connection
- SSH (Secure Shell)
- Telnet

### Accessing CLI in Cisco Packet Tracer

1. Add a Router or Switch to the workspace.
2. Open the device window.
3. Select the CLI tab.
4. Press Enter to start the CLI session.

## 3. Cisco IOS Command Modes

Cisco IOS uses different command modes. Each mode provides access to specific commands and configuration options.

### 3.1 User EXEC Mode

**Prompt:**
Router>

User EXEC mode is the initial mode after accessing the CLI.

**Features:**
- Provides limited access to device information.
- Allows basic connectivity tests.
- Does not allow configuration changes.

**Examples:**
    Router> ping 192.168.1.1
    Router> show ?

### 3.2 Privileged EXEC Mode

**Prompt:**
Router#

Privileged EXEC mode provides access to advanced monitoring, troubleshooting, and configuration commands.

**Enter this mode:**
    Router> enable
    Router#

**Return to User EXEC mode:**
    Router# disable
    Router>

**Common commands:**
    Router# show running-config
    Router# show version
    Router# show ip interface brief
    Router# show interfaces

### 3.3 Global Configuration Mode

**Prompt:**
Router(config)#

Global Configuration mode is used to modify the device's overall configuration.

**Enter this mode:**
    Router# configure terminal
    Router(config)#

**Example:**
    Router(config)# hostname R1
    R1(config)#

**Return to Privileged EXEC mode:**
    R1(config)# end
    R1#

### 3.4 Interface Configuration Mode

**Prompt:**
R1(config-if)#

Interface Configuration mode is used to configure individual network interfaces.

**Enter this mode:**
    R1(config)# interface gigabitEthernet 0/0
    R1(config-if)#

**Example:**
    R1(config-if)# ip address 192.168.1.1 255.255.255.0
    R1(config-if)# no shutdown

### 3.5 Line Configuration Mode

**Prompt:**
R1(config-line)#

Line Configuration mode is used to configure access lines, such as console and virtual terminal (VTY) lines.

**Console line example:**
    R1(config)# line console 0
    R1(config-line)#

**VTY line example:**
    R1(config)# line vty 0 4
    R1(config-line)#

### 3.6 Router Configuration Mode

**Prompt:**
R1(config-router)#

Router Configuration mode is used to configure routing protocols.

**Example:**
    R1(config)# router ospf 1
    R1(config-router)#

Available commands depend on the routing protocol and IOS platform.

## 4. Navigating Between CLI Modes

Cisco IOS provides several commands to move between command modes.

| Command | Function |
|---|---|
| enable | Enter Privileged EXEC mode |
| disable | Return to User EXEC mode |
| configure terminal | Enter Global Configuration mode |
| exit | Move one level back or exit the current session |
| end | Return directly to Privileged EXEC mode |
| Ctrl + Z | Return to Privileged EXEC mode |
| do | Execute EXEC commands from configuration modes |

### 4.1 Using Exit

The exit command moves one level back.

**Example:**
    R1(config)# interface gigabitEthernet 0/0
    R1(config-if)# exit
    R1(config)#

### 4.2 Using End

The end command returns directly to Privileged EXEC mode.

**Example:**
    R1(config-if)# end
    R1#

### 4.3 Using Do

The do command allows EXEC commands to run without leaving configuration mode.

**Example:**
    R1(config)# do show ip interface brief

This is useful when checking device status during configuration.

## 5. CLI Help and Command Completion

Cisco IOS provides built-in help features.

### 5.1 Context-Sensitive Help

Use ? to display available commands or options.

**Example:**
    R1> ?

To display available options for a specific command:

    R1# show ?

### 5.2 Command Completion

Press Tab to automatically complete a command when the entered text is unambiguous.

**Example:**
    R1# conf

Press Tab to complete:

    R1# configure

### 5.3 Command Abbreviation

Cisco IOS allows command abbreviations when they uniquely identify a command.

**Example:**
    R1# conf t

Equivalent to:

    R1# configure terminal

## 6. Basic CLI Commands

| Command | Description |
|---|---|
| show version | Display IOS and hardware information |
| show running-config | Display the active configuration |
| show startup-config | Display the saved configuration |
| show ip interface brief | Display a summary of IP interfaces |
| show interfaces | Display detailed interface information |
| show history | Display previously entered commands |

## 7. Running Configuration and Startup Configuration

Cisco IOS maintains two important configuration files.

### 7.1 Running Configuration

- Stored in RAM.
- Represents the currently active device configuration.
- Changes take effect as they are applied.
- Lost after a reboot unless saved.

**Display the running configuration:**
    R1# show running-config

### 7.2 Startup Configuration

- Stored in NVRAM on traditional Cisco platforms.
- Loaded during device startup.
- Contains the saved configuration.

**Display the startup configuration:**
    R1# show startup-config

### 7.3 Saving Configuration

To save the current configuration:

    R1# copy running-config startup-config

This saves the active configuration for use after a reboot.

## 8. Practical Lab – Cisco Packet Tracer

### Objective

Practice navigating Cisco IOS command modes and executing basic commands.

### Procedure

1. Open Cisco Packet Tracer.
2. Add a Router to the workspace.
3. Open the CLI tab.
4. Press Enter.
5. Enter Privileged EXEC mode.
6. Enter Global Configuration mode.
7. Change the router hostname.
8. Enter Interface Configuration mode.
9. Return to Privileged EXEC mode.
10. Display device information.

### Configuration Example

    Router> enable
    Router# configure terminal
    Router(config)# hostname R1
    R1(config)# interface gigabitEthernet 0/0
    R1(config-if)# exit
    R1(config)# end
    R1# show version
    R1# show ip interface brief
    R1# copy running-config startup-config

### Expected Results

After completing this lab, you should be able to:

- Access the Cisco CLI.
- Identify different IOS command modes.
- Navigate between configuration modes.
- Use built-in command help.
- Execute basic verification commands.
- Save the device configuration.

## 9. Important Notes

- Always identify the current command mode before entering a command.
- The > prompt indicates User EXEC mode.
- The # prompt indicates Privileged EXEC mode.
- The (config)# prompt indicates Global Configuration mode.
- Configuration changes should be saved when they need to persist after reboot.
- Available commands may vary depending on the hardware platform and IOS version.
