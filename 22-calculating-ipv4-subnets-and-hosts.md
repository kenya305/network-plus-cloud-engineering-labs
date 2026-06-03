# Network+ N10-009 Study Notes: Calculating IPv4 Subnets and Hosts

## Video Topic

Calculating IPv4 Subnets and Hosts

## Summary

Variable-Length Subnet Masks, or VLSM, allow a network administrator to divide a larger IPv4 network into smaller subnets.

Unlike historical classful subnetting, VLSM allows different CIDR prefix lengths based on the number of required subnets and hosts.

This lesson covers:

- VLSM
- Borrowed subnet bits
- Remaining host bits
- Powers of two
- Number of possible subnets
- Number of usable hosts per subnet
- Actual subnet boundaries
- Cloud-network planning

---

## Why Subnet Networks?

It would be impractical for one device to know the location of every other device in the world.

Instead, networks are divided into smaller subnets.

Routers move traffic between those networks.

```text
Large network
→ Divide into smaller subnets
→ Routers move traffic between subnets
```

---

## VLSM: Variable-Length Subnet Masks

VLSM stands for:

```text
Variable-Length Subnet Masks
```

VLSM allows different subnet-mask lengths to be used for different requirements.

Example:

```text
10.0.0.0/8
→ Can be divided into smaller networks such as:
10.1.1.0/24
10.1.1.0/26
```

### Key Takeaway

```text
VLSM creates efficient subnet sizes based on actual requirements.
```

---

## Historical Starting Prefixes

Modern networks use CIDR, but the historical default prefixes are useful learning baselines.

| Historical Class | First-Octet Range | Default Mask | Default Prefix |
| ---------------- | ----------------- | ------------ | -------------- |
| Class A | `1` through `126` | `255.0.0.0` | `/8` |
| Class B | `128` through `191` | `255.255.0.0` | `/16` |
| Class C | `192` through `223` | `255.255.255.0` | `/24` |

```text
Classful addressing = Historical learning baseline
CIDR and VLSM       = Modern networking methods
```

---

## Network Bits, Subnet Bits, and Host Bits

An IPv4 address contains:

```text
32 bits
```

| Bit Type | Purpose |
| -------- | ------- |
| Network bits | Identify the historical starting network portion |
| Subnet bits | Borrowed bits used to create smaller subnets |
| Host bits | Remaining bits used for host addresses inside each subnet |

### Formulas

```text
Subnet bits = New CIDR prefix - Historical default prefix
Host bits   = 32 - New CIDR prefix
```

---

## Powers of Two Reference

| Exponent | Result |
| -------- | ------ |
| `2^1` | `2` |
| `2^2` | `4` |
| `2^3` | `8` |
| `2^4` | `16` |
| `2^5` | `32` |
| `2^6` | `64` |
| `2^7` | `128` |
| `2^8` | `256` |
| `2^9` | `512` |
| `2^10` | `1,024` |
| `2^11` | `2,048` |
| `2^12` | `4,096` |
| `2^16` | `65,536` |

---

## Calculate the Number of Subnets

```text
Number of subnets = 2^s
```

Where:

```text
s = Number of borrowed subnet bits
```

Example:

```text
2 borrowed bits
→ 2^2
→ 4 subnets
```

---

## Calculate the Number of Usable Hosts

For traditional IPv4 subnetting questions:

```text
Usable hosts per subnet = 2^h - 2
```

Where:

```text
h = Number of remaining host bits
```

Subtract `2` because each traditional subnet reserves:

```text
1 network address
1 broadcast address
```

### Important Exception

Special-purpose cases such as `/31` point-to-point links and `/32` host routes should be evaluated separately.

---

## Example 1: 10.1.1.0/24

### Historical Starting Prefix

```text
10.x.x.x
→ Historical Class A baseline
→ /8
```

### Borrowed Subnet Bits

```text
24 - 8 = 16
```

### Remaining Host Bits

```text
32 - 24 = 8
```

### Possible Subnets

```text
2^16 = 65,536
```

### Usable Hosts per Subnet

```text
2^8 - 2
= 256 - 2
= 254
```

| Detail | Result |
| ------ | ------ |
| Network | `10.1.1.0/24` |
| Historical prefix | `/8` |
| Borrowed subnet bits | `16` |
| Remaining host bits | `8` |
| Possible subnets | `65,536` |
| Usable hosts per subnet | `254` |

---

## Example 2: 192.168.11.0/26

### Historical Starting Prefix

```text
192.x.x.x
→ Historical Class C baseline
→ /24
```

### Borrowed Subnet Bits

```text
26 - 24 = 2
```

### Remaining Host Bits

```text
32 - 26 = 6
```

### Possible Subnets

```text
2^2 = 4
```

### Usable Hosts per Subnet

```text
2^6 - 2
= 64 - 2
= 62
```

| Detail | Result |
| ------ | ------ |
| Network | `192.168.11.0/26` |
| Historical prefix | `/24` |
| Borrowed subnet bits | `2` |
| Remaining host bits | `6` |
| Possible subnets | `4` |
| Usable hosts per subnet | `62` |

---

## Example 3: 172.16.55.0/21

### Historical Starting Prefix

```text
172.x.x.x
→ Historical Class B baseline
→ /16
```

### Borrowed Subnet Bits

```text
21 - 16 = 5
```

### Remaining Host Bits

```text
32 - 21 = 11
```

### Possible Subnets

```text
2^5 = 32
```

### Usable Hosts per Subnet

```text
2^11 - 2
= 2,048 - 2
= 2,046
```

### Network-Boundary Clarification

The given address:

```text
172.16.55.0/21
```

belongs to this actual subnet:

```text
172.16.48.0/21
```

A `/21` network uses blocks of:

```text
8
```

in the third octet.

Since `55` falls inside the range `48–55`, the network address is:

```text
172.16.48.0
```

| Detail | Result |
| ------ | ------ |
| Given address | `172.16.55.0/21` |
| Actual network address | `172.16.48.0/21` |
| Historical prefix | `/16` |
| Borrowed subnet bits | `5` |
| Remaining host bits | `11` |
| Possible subnets | `32` |
| Usable hosts per subnet | `2,046` |

---

## Quick Calculation Workflow

```text
1. Identify the historical starting prefix.
2. Identify the new CIDR prefix.
3. Calculate borrowed subnet bits.
4. Calculate remaining host bits.
5. Calculate subnets using 2^s.
6. Calculate usable hosts using 2^h - 2.
7. Verify the actual network boundary.
```

---

## Cloud Engineering Connection

Cloud engineers use VLSM when planning:

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

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Variable-Length Subnet Masks | VLSM |
| Divide a larger network into smaller networks | Subnetting |
| Borrowed subnet bits | New prefix minus starting prefix |
| Remaining host bits | `32 - CIDR prefix` |
| Number of subnets | `2^s` |
| Usable hosts | `2^h - 2` |
| Network and broadcast addresses | Excluded from traditional usable-host count |
| Actual subnet boundary | Calculate the block size |

---

## Memory Trick

```text
Subnet bits = New prefix - Starting prefix
Host bits   = 32 - New prefix
Subnets     = 2^s
Hosts       = 2^h - 2
```

---

## Practice Questions

### 1. What does VLSM stand for?

Answer: Variable-Length Subnet Masks

### 2. Why is VLSM useful?

Answer: It allows administrators to create efficient subnet sizes based on the required number of networks and hosts.

### 3. How do you calculate borrowed subnet bits?

Answer:

```text
New CIDR prefix - Historical default prefix
```

### 4. How do you calculate remaining host bits?

Answer:

```text
32 - New CIDR prefix
```

### 5. How do you calculate possible subnets?

Answer:

```text
2^s
```

### 6. How do you calculate usable hosts for a traditional IPv4 subnet?

Answer:

```text
2^h - 2
```

### 7. How many usable hosts are available in `192.168.11.0/26`?

Answer: `62`

### 8. How many possible subnets are created when two bits are borrowed?

Answer: `4`

### 9. How many usable hosts are available in a `/21` subnet?

Answer: `2,046`

### 10. What subnet contains `172.16.55.0/21`?

Answer:

```text
172.16.48.0/21
```
