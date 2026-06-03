# Lab 21: IPv4 Subnet Mask Conversion

## Objective

Practice converting IPv4 subnet masks between CIDR notation, binary notation, and dotted-decimal notation.

## Scenario

A cloud engineer or network administrator frequently needs to interpret CIDR blocks when configuring cloud subnets, virtual networks, route tables, firewalls, and security groups.

This lab performs manual subnet-mask conversions and verifies selected results using Python.

---

## CIDR Conversion Reference

| CIDR Prefix | Decimal Subnet Mask | Network Bits | Host Bits |
| ----------- | ------------------- | ------------ | --------- |
| `/8` | `255.0.0.0` | `8` | `24` |
| `/12` | `255.240.0.0` | `12` | `20` |
| `/16` | `255.255.0.0` | `16` | `16` |
| `/19` | `255.255.224.0` | `19` | `13` |
| `/20` | `255.255.240.0` | `20` | `12` |
| `/24` | `255.255.255.0` | `24` | `8` |
| `/26` | `255.255.255.192` | `26` | `6` |

---

## Common Subnet-Mask Octet Values

| Binary Value | Decimal Value |
| ------------ | ------------- |
| `00000000` | `0` |
| `10000000` | `128` |
| `11000000` | `192` |
| `11100000` | `224` |
| `11110000` | `240` |
| `11111000` | `248` |
| `11111100` | `252` |
| `11111110` | `254` |
| `11111111` | `255` |

---

## Exercise 1: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11111111.00000000.00000000
```

### Count the Network Bits

```text
8 + 8 + 0 + 0 = 16
```

### Result

```text
CIDR notation: /16
Decimal mask:  255.255.0.0
Host bits:     16
```

---

## Exercise 2: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11111111.11111111.11000000
```

### Count the Network Bits

```text
8 + 8 + 8 + 2 = 26
```

### Result

```text
CIDR notation: /26
Decimal mask:  255.255.255.192
Host bits:     6
```

---

## Exercise 3: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11110000.00000000.00000000
```

### Count the Network Bits

```text
8 + 4 + 0 + 0 = 12
```

### Result

```text
CIDR notation: /12
Decimal mask:  255.240.0.0
Host bits:     20
```

---

## Exercise 4: Convert CIDR /19 to Decimal Mask

### CIDR Prefix

```text
/19
```

### Binary Subnet Mask

```text
11111111.11111111.11100000.00000000
```

### Result

```text
CIDR notation: /19
Decimal mask:  255.255.224.0
Host bits:     13
```

---

## Exercise 5: Convert CIDR /20 to Decimal Mask

### CIDR Prefix

```text
/20
```

### Binary Subnet Mask

```text
11111111.11111111.11110000.00000000
```

### Result

```text
CIDR notation: /20
Decimal mask:  255.255.240.0
Host bits:     12
```

---

## Exercise 6: Convert CIDR /26 to Decimal Mask

### CIDR Prefix

```text
/26
```

### Binary Subnet Mask

```text
11111111.11111111.11111111.11000000
```

### Result

```text
CIDR notation: /26
Decimal mask:  255.255.255.192
Host bits:     6
```

---

## Terminal Verification Command

Run the following command in Terminal:

```bash
python3 - <<'PY'
import ipaddress

prefixes = [8, 12, 16, 19, 20, 24, 26]

for prefix in prefixes:
    network = ipaddress.IPv4Network(f"0.0.0.0/{prefix}")
    print(f"/{prefix} = {network.netmask}")
PY
```

---

## Terminal Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % python3 - <<'PY'
import ipaddress

prefixes = [8, 12, 16, 19, 20, 24, 26]

for prefix in prefixes:
    network = ipaddress.IPv4Network(f"0.0.0.0/{prefix}")
    print(f"/{prefix} = {network.netmask}")
PY
/8 = 255.0.0.0
/12 = 255.240.0.0
/16 = 255.255.0.0
/19 = 255.255.224.0
/20 = 255.255.240.0
/24 = 255.255.255.0
/26 = 255.255.255.192
```

---

## Conversion Analysis

| CIDR Prefix | Expected Decimal Mask | Terminal Result | Status |
| ----------- | --------------------- | --------------- | ------ |
| `/8` | `255.0.0.0` | `255.0.0.0` | Verified |
| `/12` | `255.240.0.0` | `255.240.0.0` | Verified |
| `/16` | `255.255.0.0` | `255.255.0.0` | Verified |
| `/19` | `255.255.224.0` | `255.255.224.0` | Verified |
| `/20` | `255.255.240.0` | `255.255.240.0` | Verified |
| `/24` | `255.255.255.0` | `255.255.255.0` | Verified |
| `/26` | `255.255.255.192` | `255.255.255.192` | Verified |
---

## What I Observed

CIDR notation identifies the number of network bits in a subnet mask.

The binary `1` values identify the network portion.

The binary `0` values identify the host portion.

The number of host bits can be calculated using:

```text
32 - CIDR prefix length
```

For example:

```text
/26
→ 26 network bits
→ 6 host bits
→ 255.255.255.192
```

---

## Important Limitation

The Terminal command verifies the decimal subnet masks.

The CompTIA Network+ exam may still require manual conversion.

The goal is to recognize CIDR prefixes and subnet-mask octet values quickly without relying entirely on a script.

---

## Cloud Engineering Connection

Cloud engineers use CIDR notation when configuring:

- Virtual networks
- Cloud subnets
- Route tables
- Security groups
- Network access controls
- VPN tunnels
- Hybrid cloud networks
- Public endpoints
- Private endpoints
- Kubernetes networks
- Container networks
- Firewall rules
- IP-address planning

Understanding subnet-mask conversion helps engineers design address spaces correctly and avoid overlapping network ranges.

---

## Skills Practiced

- Identifying CIDR prefix lengths
- Counting network bits
- Calculating host bits
- Converting binary subnet masks to CIDR notation
- Converting CIDR notation to dotted-decimal subnet masks
- Memorizing valid subnet-mask octet values
- Using Python to verify subnet masks
- Connecting CIDR notation to cloud-network planning
- Documenting subnetting calculations in GitHub
````
