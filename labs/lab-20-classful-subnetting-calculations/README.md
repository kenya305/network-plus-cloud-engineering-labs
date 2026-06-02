# Lab 20: Classful Subnetting Calculations

## Objective

Practice identifying historical IPv4 address classes and calculating the network address, first usable host address, last usable host address, and broadcast address.

## Scenario

A cloud engineer or network administrator needs to understand subnet boundaries when planning IP-address ranges and troubleshooting network communication.

Although modern networks use CIDR notation, historical classful boundaries provide a useful foundation for learning subnet calculations.

---

## Important Modern Networking Note

Class-based subnetting is a historical learning framework.

Modern networks use:

```text
CIDR
```

CIDR stands for:

```text
Classless Inter-Domain Routing
```

The subnet-calculation logic learned in this lab also applies to CIDR-based networking.

---

## IPv4 Address Classes Reference

| Address Class | First-Octet Range | Default Subnet Mask | CIDR Equivalent | Main Use |
| ------------- | ----------------- | ------------------- | --------------- | -------- |
| Class A | `1` through `126` | `255.0.0.0` | `/8` | Large host networks |
| Class B | `128` through `191` | `255.255.0.0` | `/16` | Medium host networks |
| Class C | `192` through `223` | `255.255.255.0` | `/24` | Smaller host networks |
| Class D | `224` through `239` | Not applicable | Not applicable | Multicast |
| Class E | `240` through `255` | Not applicable | Not applicable | Reserved |

### Important Exceptions

```text
0.x.x.x   = Reserved
127.x.x.x = Loopback
```

---

## Subnet Calculation Pattern

Use this pattern:

```text
Network address      = Host bits set to 0
First usable host    = Network address + 1
Broadcast address    = Host bits set to 1
Last usable host     = Broadcast address - 1
```

---

## Exercise 1: Identify Historical Address Classes

| IPv4 Address | First Octet | Historical Address Class |
| ------------ | ----------- | ------------------------ |
| `17.22.90.7` | `17` | Class A |
| `220.10.77.40` | `220` | Class C |
| `165.245.0.1` | `165` | Class B |
| `128.90.10.2` | `128` | Class B |
| `191.77.24.250` | `191` | Class B |
| `192.1.12.5` | `192` | Class C |

---

## Exercise 2: Calculate Class A Subnet Values

### Given IPv4 Address

```text
10.74.222.11
```

### Historical Address Class

```text
Class A
```

### Default Subnet Mask

```text
255.0.0.0
```

### CIDR Equivalent

```text
/8
```

### Network and Host Boundary

```text
Network | Host | Host | Host
10      | 74   | 222  | 11
```

### Calculation

```text
Network address      = 10.0.0.0
First usable host    = 10.0.0.1
Last usable host     = 10.255.255.254
Broadcast address    = 10.255.255.255
```

### Result Table

| Subnet Detail | Result |
| ------------- | ------ |
| Network address | `10.0.0.0` |
| First usable host | `10.0.0.1` |
| Last usable host | `10.255.255.254` |
| Broadcast address | `10.255.255.255` |

---

## Exercise 3: Calculate Class B Subnet Values

### Given IPv4 Address

```text
172.16.88.200
```

### Historical Address Class

```text
Class B
```

### Default Subnet Mask

```text
255.255.0.0
```

### CIDR Equivalent

```text
/16
```

### Network and Host Boundary

```text
Network | Network | Host | Host
172     | 16      | 88   | 200
```

### Calculation

```text
Network address      = 172.16.0.0
First usable host    = 172.16.0.1
Last usable host     = 172.16.255.254
Broadcast address    = 172.16.255.255
```

### Result Table

| Subnet Detail | Result |
| ------------- | ------ |
| Network address | `172.16.0.0` |
| First usable host | `172.16.0.1` |
| Last usable host | `172.16.255.254` |
| Broadcast address | `172.16.255.255` |

---

## Exercise 4: Calculate Class C Subnet Values

### Given IPv4 Address

```text
192.168.4.77
```

### Historical Address Class

```text
Class C
```

### Default Subnet Mask

```text
255.255.255.0
```

### CIDR Equivalent

```text
/24
```

### Network and Host Boundary

```text
Network | Network | Network | Host
192     | 168     | 4       | 77
```

### Calculation

```text
Network address      = 192.168.4.0
First usable host    = 192.168.4.1
Last usable host     = 192.168.4.254
Broadcast address    = 192.168.4.255
```

### Result Table

| Subnet Detail | Result |
| ------------- | ------ |
| Network address | `192.168.4.0` |
| First usable host | `192.168.4.1` |
| Last usable host | `192.168.4.254` |
| Broadcast address | `192.168.4.255` |

---

## Subnet Comparison Table

| IPv4 Address | Historical Class | Default Mask | CIDR | Network Address | First Usable Host | Last Usable Host | Broadcast Address |
| ------------ | ---------------- | ------------ | ---- | --------------- | ----------------- | ---------------- | ----------------- |
| `10.74.222.11` | Class A | `255.0.0.0` | `/8` | `10.0.0.0` | `10.0.0.1` | `10.255.255.254` | `10.255.255.255` |
| `172.16.88.200` | Class B | `255.255.0.0` | `/16` | `172.16.0.0` | `172.16.0.1` | `172.16.255.254` | `172.16.255.255` |
| `192.168.4.77` | Class C | `255.255.255.0` | `/24` | `192.168.4.0` | `192.168.4.1` | `192.168.4.254` | `192.168.4.255` |

---

## What I Observed

The historical address class determines the default subnet mask.

The default subnet mask identifies the boundary between:

```text
Network bits
Host bits
```

The network address is calculated by setting all host bits to:

```text
0
```

The broadcast address is calculated by setting all host bits to:

```text
1
```

The first usable host is:

```text
Network address + 1
```

The last usable host is:

```text
Broadcast address - 1
```

---

## Important Limitation

Modern networks use CIDR notation rather than class-based subnetting.

Classful boundaries remain useful for learning, but real-world cloud and enterprise environments may use prefix lengths such as:

```text
/12
/20
/27
```

The same calculation process applies when working with modern CIDR subnets.

---

## Cloud Engineering Connection

Cloud engineers use subnet calculations when configuring:

- Virtual networks
- Cloud subnets
- CIDR blocks
- Private address spaces
- Public address spaces
- Route tables
- Security groups
- Network access controls
- NAT gateways
- VPN connections
- Hybrid cloud networks
- Network segmentation
- IP-address planning

Understanding subnet boundaries helps engineers allocate IP addresses correctly and avoid overlapping network ranges.

---

## Skills Practiced

- Identifying historical IPv4 address classes
- Recognizing default subnet masks
- Connecting classful masks to CIDR notation
- Identifying network and host boundaries
- Calculating network addresses
- Calculating first usable host addresses
- Calculating last usable host addresses
- Calculating broadcast addresses
- Connecting classful subnetting to modern CIDR concepts
- Documenting subnetting calculations in GitHub
