# Cisco Packet Tracer — Installation and Setup

## 1. Overview

Cisco Packet Tracer is a network simulation tool used to build network topologies, configure Cisco devices, test connectivity, and practice networking scenarios in a virtual environment.

## 2. Installation

### 2.1. Download

1. Visit the official Cisco Networking Academy.
2. Sign in to your Cisco Networking Academy account or create an account if required.
3. Find Cisco Packet Tracer in the available learning resources.
4. Download the installer compatible with your operating system.

**Note:** Download Packet Tracer only from official Cisco sources.

### 2.2. Install on Windows

1. Locate the downloaded installer.
2. Double-click the installer file.
3. Accept the license agreement.
4. Select the installation directory.
5. Complete the installation.
6. Launch Cisco Packet Tracer from the Start menu or desktop shortcut.

## 3. Initial Setup

1. Open Cisco Packet Tracer.
2. Complete the sign-in process if prompted.
3. Select the appropriate account or access option available in your version.
4. Wait for the main workspace to load.

The workspace is where network devices are placed, connected, and configured.

## 4. Workspace Overview

| Area | Purpose |
|---|---|
| Logical Workspace | Build and organize network topologies |
| Device Selection Panel | Select routers, switches, PCs, servers, and other devices |
| Connections | Select cables and connect network devices |
| Realtime Mode | Observe network behavior during normal operation |
| Simulation Mode | Inspect supported network events and packet flow |
| Device Configuration | Configure device settings through available interfaces |

## 5. Create and Save a Lab

1. Open Packet Tracer.
2. Start a new project using **File > New**, if necessary.
3. Add the required devices to the workspace.
4. Connect the devices using appropriate connections.
5. Configure device settings as required by the lab.
6. Save the project using **File > Save As**.
7. Enter a descriptive filename and save the project as a `.pkt` file.

**Example filename:**

`first-network-lab.pkt`

## 6. Open an Existing Lab

1. Launch Packet Tracer.
2. Select **File > Open**.
3. Browse to the location of the saved `.pkt` file.
4. Open the file and continue working on the topology.

## 7. Simulation Modes

### 7.1. Realtime Mode

Use Realtime mode to observe the network under normal operating conditions and test connectivity.

### 7.2. Simulation Mode

Use Simulation mode to inspect supported protocol events and follow packet movement through the simulated network.

1. Switch to **Simulation** mode.
2. Configure the event filters if necessary.
3. Generate network traffic, such as a ping.
4. Use **Capture/Forward** to inspect events step by step.
5. Use **Auto Capture/Play** to observe events automatically.

**Note:** Available events and simulation behavior depend on the devices and protocols used.

## 8. Lab Organization

Use descriptive filenames and organize lab files by topic.

**Example directory structure:**

```text
Cisco-CCNA/
└── labs/
    ├── packet-tracer/
    │   ├── first-network-lab.pkt
    │   └── basic-connectivity.pkt
    ├── switching/
    └── routing/
```

Keep lab files separate from Markdown documentation. Store each lab in the directory that best matches its subject.

## 9. Common Issues

| Issue | Recommended Check |
|---|---|
| Packet Tracer does not launch | Check system compatibility and installation status |
| Sign-in is unsuccessful | Verify account credentials and internet connectivity |
| Devices cannot communicate | Check cabling, interfaces, IP addressing, and device configuration |
| Simulation events are not visible | Review event filters and generate traffic |
| Lab changes are missing after reopening | Save the project before closing Packet Tracer |

## 10. Practical Workflow

Use the following workflow for each lab:

1. Define the objective.
2. Build the topology.
3. Connect the devices.
4. Configure the required settings.
5. Test connectivity.
6. Verify the results.
7. Troubleshoot any failures.
8. Save the `.pkt` file.
9. Document the configuration and observations.
