# Lab 24: Seven Second Subnetting

## Objective

Practice the seven-second subnetting shortcut by converting CIDR prefixes, identifying subnet ranges, and calculating usable-host ranges.

## Scenario

A cloud engineer or network administrator may need to calculate IPv4 subnet details quickly during troubleshooting, design work, or certification exams.

This lab verifies several seven-second subnetting examples using Python.

---

## Core Workflow

```text
1. Convert CIDR to dotted-decimal mask.
2. Identify the subnet boundary.
3. Determine subnet ID.
4. Determine broadcast address.
5. First usable host = Subnet ID + 1.
6. Last usable host = Broadcast - 1.
```

---

## Exercise 1: 165.245.12.88/24

```text
Subnet mask:       255.255.255.0
Subnet ID:         165.245.12.0
Broadcast:         165.245.12.255
First usable host: 165.245.12.1
Last usable host:  165.245.12.254
```

---

## Exercise 2: 165.245.12.88/26

```text
Subnet mask:         255.255.255.192
Addresses per block: 64
Matching range:      64–127
Subnet ID:           165.245.12.64
Broadcast:           165.245.12.127
First usable host:   165.245.12.65
Last usable host:    165.245.12.126
```

---

## Exercise 3: 165.245.12.88/20

```text
Subnet mask:                              255.255.240.0
Addresses per block in interesting octet: 16
Matching range:                           0–15
Subnet ID:                                165.245.0.0
Broadcast:                                165.245.15.255
First usable host:                        165.245.0.1
Last usable host:                         165.245.15.254
```

---

## Exercise 4: 18.172.200.77/11

```text
Subnet mask:                              255.224.0.0
Addresses per block in interesting octet: 32
Matching range:                           160–191
Subnet ID:                                18.160.0.0
Broadcast:                                18.191.255.255
First usable host:                        18.160.0.1
Last usable host:                         18.191.255.254
```

---

## Exercise 5: 18.172.200.77/17

```text
Subnet mask:                              255.255.128.0
Addresses per block in interesting octet: 128
Matching range:                           128–255
Subnet ID:                                18.172.128.0
Broadcast:                                18.172.255.255
First usable host:                        18.172.128.1
Last usable host:                         18.172.255.254
```

---

## Terminal Verification Command

Run:

```bash
python3 - <<'PY'
import ipaddress

examples = [
    "165.245.12.88/24",
    "165.245.12.88/26",
    "165.245.12.88/20",
    "18.172.200.77/11",
    "18.172.200.77/17",
]

for cidr in examples:
    interface = ipaddress.IPv4Interface(cidr)
    network = interface.network

    print(f"Input: {cidr}")
    print(f"Netmask: {network.netmask}")
    print(f"Network: {network.network_address}/{network.prefixlen}")
    print(f"Broadcast: {network.broadcast_address}")
    print(f"First usable host: {network.network_address + 1}")
    print(f"Last usable host: {network.broadcast_address - 1}")
    print("-" * 40)
PY
```

---

## Terminal Output

```text
Input: 165.245.12.88/24
Netmask: 255.255.255.0
Network: 165.245.12.0/24
Broadcast: 165.245.12.255
First usable host: 165.245.12.1
Last usable host: 165.245.12.254
----------------------------------------
Input: 165.245.12.88/26
Netmask: 255.255.255.192
Network: 165.245.12.64/26
Broadcast: 165.245.12.127
First usable host: 165.245.12.65
Last usable host: 165.245.12.126
----------------------------------------
Input: 165.245.12.88/20
Netmask: 255.255.240.0
Network: 165.245.0.0/20
Broadcast: 165.245.15.255
First usable host: 165.245.0.1
Last usable host: 165.245.15.254
----------------------------------------
Input: 18.172.200.77/11
Netmask: 255.224.0.0
Network: 18.160.0.0/11
Broadcast: 18.191.255.255
First usable host: 18.160.0.1
Last usable host: 18.191.255.254
----------------------------------------
Input: 18.172.200.77/17
Netmask: 255.255.128.0
Network: 18.172.128.0/17
Broadcast: 18.172.255.255
First usable host: 18.172.128.1
Last usable host: 18.172.255.254
----------------------------------------
```

---

## Verification Analysis

| Input | Actual Network | Netmask | Broadcast Address | First Usable Host | Last Usable Host | Status |
| ----- | -------------- | ------- | ----------------- | ----------------- | ---------------- | ------ |
| `165.245.12.88/24` | `165.245.12.0/24` | `255.255.255.0` | `165.245.12.255` | `165.245.12.1` | `165.245.12.254` | Verified |
| `165.245.12.88/26` | `165.245.12.64/26` | `255.255.255.192` | `165.245.12.127` | `165.245.12.65` | `165.245.12.126` | Verified |
| `165.245.12.88/20` | `165.245.0.0/20` | `255.255.240.0` | `165.245.15.255` | `165.245.0.1` | `165.245.15.254` | Verified |
| `18.172.200.77/11` | `18.160.0.0/11` | `255.224.0.0` | `18.191.255.255` | `18.160.0.1` | `18.191.255.254` | Verified |
| `18.172.200.77/17` | `18.172.128.0/17` | `255.255.128.0` | `18.172.255.255` | `18.172.128.1` | `18.172.255.254` | Verified |

---

## What I Observed

The Python verification confirmed each seven-second subnetting example.

The shortcut uses a predefined reference chart to reduce the amount of arithmetic required during subnet calculations.

The subnet ID is the first address in the matching range.

The broadcast address is the last address in the matching range.

The first usable host is:

```text
Subnet ID + 1
```

The last usable host is:

```text
Broadcast address - 1
```

---

## Important Limitation

Seven-second subnetting is a shortcut.

Understanding CIDR notation, subnet masks, binary math, subnet boundaries, and special-purpose subnet cases remains important.

---

## Cloud Engineering Connection

Cloud engineers use subnet calculations when planning:

- Virtual private clouds
- Virtual networks
- Public subnets
- Private subnets
- Database subnets
- Route tables
- NAT gateways
- Security groups
- VPN connections
- Hybrid cloud networks
- Kubernetes networking
- IP-address planning

---

## Skills Practiced

- Converting CIDR notation to dotted-decimal masks
- Identifying subnet boundaries
- Calculating subnet IDs
- Calculating broadcast addresses
- Calculating usable-host ranges
- Applying a fast subnetting shortcut
- Using Python to verify subnet calculations
- Connecting subnet calculations to cloud-network planning
