# VLSM Practical Exercises

## 1. VLSM Overview

**VLSM (Variable Length Subnet Mask)** allows a network to be divided into subnets with different prefix lengths.

Each subnet receives an address range based on its host requirements.

**Main Advantages:**

- Efficient IP address allocation.
- Reduced IP address waste.
- Flexible subnet sizing.

## 2. VLSM Calculation Rules

Before assigning subnets, determine the number of hosts required by each network.

### Required Formulas

```text
Total Addresses = 2^Host Bits
Usable Hosts = 2^Host Bits - 2
Prefix Length = 32 - Host Bits
```

Choose the smallest subnet that provides enough usable host addresses.

### Common Subnet Sizes

| Required Hosts | Prefix | Subnet Mask | Usable Hosts |
|---:|---:|---|---:|
| 126 | /25 | 255.255.255.128 | 126 |
| 62 | /26 | 255.255.255.192 | 62 |
| 30 | /27 | 255.255.255.224 | 30 |
| 14 | /28 | 255.255.255.240 | 14 |
| 6 | /29 | 255.255.255.248 | 6 |
| 2 | /30 | 255.255.255.252 | 2 |

## 3. VLSM Allocation Process

1. Identify the required number of hosts for each subnet.
2. Sort subnet requirements from largest to smallest.
3. Select the smallest suitable subnet for each requirement.
4. Allocate address blocks sequentially.
5. Ensure each subnet starts at a valid network boundary.
6. Verify that subnet ranges do not overlap.

**Important:** Always allocate the largest subnet first.

## 4. Solved VLSM Scenario

### Scenario

A company has been assigned the following network:

```text
192.168.10.0/24
```

The network must be divided into four subnets:

| Department | Required Hosts |
|---|---:|
| Administration | 100 |
| Sales | 50 |
| IT | 25 |
| Management | 10 |

### Step 1: Sort Host Requirements

```text
Administration: 100
Sales:            50
IT:               25
Management:       10
```

### Step 2: Select Suitable Prefixes

| Department | Required Hosts | Prefix | Usable Hosts |
|---|---:|---:|---:|
| Administration | 100 | /25 | 126 |
| Sales | 50 | /26 | 62 |
| IT | 25 | /27 | 30 |
| Management | 10 | /28 | 14 |

### Step 3: Allocate Subnets

Starting from `192.168.10.0/24`:

| Department | Network Address | First Host | Last Host | Broadcast |
|---|---|---|---|---|
| Administration | 192.168.10.0/25 | 192.168.10.1 | 192.168.10.126 | 192.168.10.127 |
| Sales | 192.168.10.128/26 | 192.168.10.129 | 192.168.10.190 | 192.168.10.191 |
| IT | 192.168.10.192/27 | 192.168.10.193 | 192.168.10.222 | 192.168.10.223 |
| Management | 192.168.10.224/28 | 192.168.10.225 | 192.168.10.238 | 192.168.10.239 |

### Step 4: Remaining Addresses

The following range remains unallocated:

```text
192.168.10.240 – 192.168.10.255
```

This range contains 16 addresses and can be used for future subnetting if needed.

## 5. VLSM Verification Checklist

Before finalizing an address plan, verify:

- Each subnet supports the required number of hosts.
- Subnets do not overlap.
- Network addresses are valid subnet boundaries.
- Broadcast addresses are correct.
- Each subnet belongs to the original assigned network.
- No address block is allocated more than once.

## 6. Practical Exercises

Solve the following scenarios independently.

### Exercise 1

**Given:**

```text
Network: 192.168.20.0/24
```

**Required Subnets:**

| Department | Required Hosts |
|---|---:|
| HR | 60 |
| Finance | 30 |
| IT | 12 |
| Support | 6 |

**Tasks:**

1. Determine the appropriate prefix for each subnet.
2. Calculate the subnet mask.
3. Assign network addresses.
4. Identify the first and last usable IP addresses.
5. Calculate the broadcast address.
6. Identify the remaining unallocated range.

### Exercise 2

**Given:**

```text
Network: 10.10.0.0/23
```

**Required Subnets:**

| Department | Required Hosts |
|---|---:|
| LAN 1 | 200 |
| LAN 2 | 100 |
| LAN 3 | 50 |
| LAN 4 | 20 |
| LAN 5 | 10 |

**Tasks:**

1. Calculate the required prefix for each subnet.
2. Allocate addresses from largest to smallest.
3. Complete the subnet allocation table.
4. Verify that all subnets fit within the assigned network.

### Exercise 3

A company has received:

```text
Network: 172.16.5.0/24
```

**Required Subnets:**

- Network A: 80 hosts
- Network B: 40 hosts
- Network C: 20 hosts
- Network D: 10 hosts

**Tasks:**

1. Design a VLSM addressing plan.
2. Calculate all network and broadcast addresses.
3. Determine usable host ranges.
4. Identify unused address space.

## 7. Key Points

- VLSM uses different subnet masks within the same assigned network.
- Allocate the largest subnet first.
- Choose the smallest subnet that supports the required hosts.
- Every subnet must have a valid network boundary.
- Always check for overlapping address ranges.
- CIDR prefix length determines subnet size.
