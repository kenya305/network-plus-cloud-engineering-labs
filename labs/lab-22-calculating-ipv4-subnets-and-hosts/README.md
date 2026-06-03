# Lab 22: Calculating IPv4 Subnets and Hosts

## Objective

Practice calculating borrowed subnet bits, remaining host bits, possible subnet counts, usable hosts per subnet, and actual subnet boundaries.

## Scenario

A cloud engineer or network administrator may need to divide a larger IPv4 address space into smaller networks.

Variable-Length Subnet Masks, or VLSM, help create efficient subnet sizes for different workloads.

This lab performs manual calculations and verifies the results using Python.

---

## Core Formulas

```text
Subnet bits = New prefix - Historical default prefix
Host bits   = 32 - New prefix
Subnets     = 2^subnet bits
Usable hosts per subnet = 2^host bits - 2
```

---

## Historical Starting Prefixes

| Historical Class | First-Octet Range | Default Prefix |
| ---------------- | ----------------- | -------------- |
| Class A | `1` through `126` | `/8` |
| Class B | `128` through `191` | `/16` |
| Class C | `192` through `223` | `/24` |

---

## Exercise 1: Calculate 10.1.1.0/24

| Detail | Result |
| ------ | ------ |
| Historical starting prefix | `/8` |
| Borrowed subnet bits | `24 - 8 = 16` |
| Remaining host bits | `32 - 24 = 8` |
| Possible subnets | `2^16 = 65,536` |
| Usable hosts per subnet | `2^8 - 2 = 254` |

---

## Exercise 2: Calculate 192.168.11.0/26

| Detail | Result |
| ------ | ------ |
| Historical starting prefix | `/24` |
| Borrowed subnet bits | `26 - 24 = 2` |
| Remaining host bits | `32 - 26 = 6` |
| Possible subnets | `2^2 = 4` |
| Usable hosts per subnet | `2^6 - 2 = 62` |

---

## Exercise 3: Calculate 172.16.55.0/21

| Detail | Result |
| ------ | ------ |
| Historical starting prefix | `/16` |
| Borrowed subnet bits | `21 - 16 = 5` |
| Remaining host bits | `32 - 21 = 11` |
| Possible subnets | `2^5 = 32` |
| Usable hosts per subnet | `2^11 - 2 = 2,046` |
| Actual network address | `172.16.48.0/21` |

### Network-Boundary Explanation

A `/21` subnet uses blocks of:

```text
8
```

in the third octet.

The value:

```text
55
```

falls inside:

```text
48–55
```

Therefore, the actual network address is:

```text
172.16.48.0/21
```

---

## Terminal Verification Command

Run:

```bash
python3 - <<'PY'
import ipaddress

examples = [
    ("10.1.1.0/24", 8),
    ("192.168.11.0/26", 24),
    ("172.16.55.0/21", 16),
]

for cidr, historical_prefix in examples:
    network = ipaddress.IPv4Network(cidr, strict=False)
    new_prefix = network.prefixlen
    subnet_bits = new_prefix - historical_prefix
    host_bits = 32 - new_prefix
    subnets = 2 ** subnet_bits
    usable_hosts = (2 ** host_bits) - 2

    print(f"Input: {cidr}")
    print(f"Network: {network.network_address}/{network.prefixlen}")
    print(f"Netmask: {network.netmask}")
    print(f"Broadcast: {network.broadcast_address}")
    print(f"Subnet bits: {subnet_bits}")
    print(f"Host bits: {host_bits}")
    print(f"Possible subnets: {subnets}")
    print(f"Usable hosts per subnet: {usable_hosts}")
    print("-" * 40)
PY
```

---

## Terminal Output

```text
Input: 10.1.1.0/24
Network: 10.1.1.0/24
Netmask: 255.255.255.0
Broadcast: 10.1.1.255
Subnet bits: 16
Host bits: 8
Possible subnets: 65536
Usable hosts per subnet: 254
----------------------------------------
Input: 192.168.11.0/26
Network: 192.168.11.0/26
Netmask: 255.255.255.192
Broadcast: 192.168.11.63
Subnet bits: 2
Host bits: 6
Possible subnets: 4
Usable hosts per subnet: 62
----------------------------------------
Input: 172.16.55.0/21
Network: 172.16.48.0/21
Netmask: 255.255.248.0
Broadcast: 172.16.55.255
Subnet bits: 5
Host bits: 11
Possible subnets: 32
Usable hosts per subnet: 2046
----------------------------------------
```

---

## Verification Analysis

| Input | Actual Network | Netmask | Broadcast Address | Subnet Bits | Host Bits | Possible Subnets | Usable Hosts | Status |
| ----- | -------------- | ------- | ----------------- | ----------- | --------- | ---------------- | ------------ | ------ |
| `10.1.1.0/24` | `10.1.1.0/24` | `255.255.255.0` | `10.1.1.255` | `16` | `8` | `65,536` | `254` | Verified |
| `192.168.11.0/26` | `192.168.11.0/26` | `255.255.255.192` | `192.168.11.63` | `2` | `6` | `4` | `62` | Verified |
| `172.16.55.0/21` | `172.16.48.0/21` | `255.255.248.0` | `172.16.55.255` | `5` | `11` | `32` | `2,046` | Verified |

---

## What I Observed

The Python verification confirmed the manual VLSM calculations.

The number of borrowed subnet bits determines the number of possible subnets.

The number of remaining host bits determines the number of usable hosts within each traditional IPv4 subnet.

The lab also confirmed that:

```text
172.16.55.0/21
```

belongs to:

```text
172.16.48.0/21
```

The `/21` subnet uses a netmask of:

```text
255.255.248.0
```

and a broadcast address of:

```text
172.16.55.255
```

---

## Important Limitation

The traditional formula:

```text
2^h - 2
```

is commonly used for standard IPv4 subnetting questions.

Special-purpose cases such as `/31` point-to-point links and `/32` host routes should be evaluated separately.

---

## Cloud Engineering Connection

Cloud engineers use VLSM when configuring:

- Virtual private clouds
- Virtual networks
- Public subnets
- Private subnets
- Database subnets
- Application subnets
- Route tables
- NAT gateways
- Security groups
- VPN connections
- Hybrid cloud networks
- Kubernetes networks
- IP-address allocation plans

---

## Skills Practiced

- Calculating borrowed subnet bits
- Calculating remaining host bits
- Calculating possible subnets
- Calculating usable host addresses
- Identifying actual subnet boundaries
- Applying VLSM concepts
- Using Python to verify subnet calculations
- Connecting subnet calculations to cloud-network planning
- Documenting networking calculations in GitHub
