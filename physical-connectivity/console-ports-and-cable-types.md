# Cisco Console Ports and Cable Types

## 1. Identify the Console Port

| Port Type | Physical Appearance | Connection |
|---|---|---|
| RJ45 Console | RJ45-shaped port labeled CONSOLE | RJ45 Console Cable |
| USB Mini-B | Small USB Mini-B port labeled CONSOLE | USB Mini-B Cable |
| USB Type-B | Square USB Type-B port labeled CONSOLE | USB Type-B Cable |
| USB Type-C | USB-C port labeled CONSOLE | USB Type-C Cable |

**Important:** A USB port is not necessarily a Console port. Check the port label and device documentation.

## 2. Console Cable Types

| Cable Type | Connection |
|---|---|
| RJ45-to-DB9 | Device RJ45 Console → Computer Serial Port |
| USB-to-RJ45 | Device RJ45 Console → Computer USB |
| USB Mini-B | Device USB Console → Computer USB |
| USB Type-B | Device USB Console → Computer USB |
| USB Type-C | Device USB Console → Computer USB |

## 3. Connect Using an RJ45 Console Cable

1. Connect the RJ45 end to the device's **CONSOLE** port.
2. Connect the other end to the computer.
3. If the computer has no serial port, use a USB-to-Serial adapter.
4. Open **Device Manager**.
5. Expand **Ports (COM & LPT)**.
6. Identify the assigned COM port.

## 4. Connect Using a USB Console Port

1. Connect the USB cable to the device's USB Console port.
2. Connect the other end to the computer.
3. Install the required USB console driver if necessary.
4. Open **Device Manager**.
5. Check **Ports (COM & LPT)** for the assigned COM port.

## 5. Configure PuTTY

1. Open **PuTTY**.
2. Select **Serial**.
3. Enter the assigned COM port.
4. Configure the serial settings:

| Setting | Value |
|---|---|
| Speed | 9600 |
| Data Bits | 8 |
| Stop Bits | 1 |
| Parity | None |
| Flow Control | None |

5. Click **Open**.
6. Press **Enter** to display the CLI prompt.

**Note:** 9600 baud is a common default. Use the device documentation if its required speed is different.

## 6. Identify Common Cisco Devices

Examples of Cisco device families include:

- Catalyst 2960 / 9200 / 9300 Switches
- ISR 4000 Series Routers
- Catalyst 8000 Series Edge Platforms

Console connectivity can differ between models and hardware revisions. Before selecting a cable:

1. Check the exact model number.
2. Locate the port labeled **CONSOLE**.
3. Check the device hardware installation guide.
4. Confirm whether the connection requires RJ45, USB, or another supported interface.

## 7. Verify the Connection

After opening the serial session, press **Enter**.

**Common prompts:**

```text
Switch>
Router>
```

Run:

```cisco
enable
show version
show line
```

## 8. Troubleshooting

| Problem | Check |
|---|---|
| No COM port appears | Cable, USB adapter, and driver |
| PuTTY cannot open the port | Correct COM number and other applications using it |
| Blank terminal | Press Enter and check cable connection |
| Unreadable characters | Verify baud rate and serial settings |
| USB connection not detected | Check driver and device compatibility |

## 9. Practical Lab

**Objective:** Connect to a Cisco switch through its Console port.

1. Identify the Console port on the switch.
2. Select the compatible console cable.
3. Connect the switch to the computer.
4. Find the COM port in Device Manager.
5. Open PuTTY and configure the serial connection.
6. Access the switch CLI.
7. Run:

```cisco
enable
show version
show running-config
```

**Expected Result:** The switch CLI is accessible through the Console connection.
