# Network+ N10-009 Study Notes: Seven Second Subnetting

## Video Topic

Seven Second Subnetting

## Summary

Seven-second subnetting is a shortcut for calculating IPv4 subnet information quickly with minimal math.

The method uses a predefined chart so that a network administrator can quickly identify:

- Subnet mask
- Number of networks
- Number of addresses per subnet
- Subnet ID
- Broadcast address
- First usable host
- Last usable host

The goal is to reduce the amount of binary conversion and arithmetic required during an exam or troubleshooting workflow.

---

## Why Use Seven-Second Subnetting?

Traditional subnetting may require:

- Binary conversion
- Decimal conversion
- Powers-of-two calculations
- Repeated arithmetic

Seven-second subnetting reduces this work by using a reference chart.

### Key Takeaway

```text
Seven-second subnetting
= Prebuilt chart
= Faster subnet calculations
= Minimal math
```

---

## Core Four-Step Process

```text
1. Convert CIDR notation to dotted-decimal subnet mask.
2. Determine the subnet ID.
3. Determine the broadcast address.
4. Calculate the first and last usable host addresses.
```

### Host-Address Rules

```text
First usable host = Subnet ID + 1
Last usable host  = Broadcast address - 1
```

---

## Core Reference Chart

| CIDR Prefix | Interesting-Octet Mask | Number of Networks | Addresses per Subnet |
| ----------- | ---------------------- | ------------------ | -------------------- |
| `/25` | `128` | `2` | `128` |
| `/26` | `192` | `4` | `64` |
| `/27` | `224` | `8` | `32` |
| `/28` | `240` | `16` | `16` |
| `/29` | `248` | `32` | `8` |
| `/30` | `252` | `64` | `4` |

### Pattern

```text
Networks:
2, 4, 8, 16, 32, 64

Addresses per subnet:
128, 64, 32, 16, 8, 4
```

---

## Decimal Subnet-Mask Reference

| CIDR Prefix | Dotted-Decimal Mask |
| ----------- | ------------------- |
| `/8` | `255.0.0.0` |
| `/9` | `255.128.0.0` |
| `/10` | `255.192.0.0` |
| `/11` | `255.224.0.0` |
| `/12` | `255.240.0.0` |
| `/13` | `255.248.0.0` |
| `/14` | `255.252.0.0` |
| `/15` | `255.254.0.0` |
| `/16` | `255.255.0.0` |
| `/17` | `255.255.128.0` |
| `/18` | `255.255.192.0` |
| `/19` | `255.255.224.0` |
| `/20` | `255.255.240.0` |
| `/21` | `255.255.248.0` |
| `/22` | `255.255.252.0` |
| `/23` | `255.255.254.0` |
| `/24` | `255.255.255.0` |
| `/25` | `255.255.255.128` |
| `/26` | `255.255.255.192` |
| `/27` | `255.255.255.224` |
| `/28` | `255.255.255.240` |
| `/29` | `255.255.255.248` |
| `/30` | `255.255.255.252` |

---

## Subnet-Boundary Reference

| Addresses per Subnet | Common Boundaries |
| -------------------- | ----------------- |
| `128` | `0`, `128` |
| `64` | `0`, `64`, `128`, `192` |
| `32` | `0`, `32`, `64`, `96`, `128`, `160`, `192`, `224` |
| `16` | `0`, `16`, `32`, `48`, `64`, `80`, `96`, `112`, `128`, `144`, `160`, `176`, `192`, `208`, `224`, `240` |
| `8` | Multiples of `8` |
| `4` | Multiples of `4` |

---

## Example 1: 165.245.12.88/24

### Convert CIDR to Mask

```text
/24 = 255.255.255.0
```

### Determine Subnet ID

```text
165.245.12.0
```

### Determine Broadcast Address

```text
165.245.12.255
```

### Determine Usable Hosts

```text
First usable host: 165.245.12.1
Last usable host:  165.245.12.254
```

---

## Example 2: 165.245.12.88/26

### Convert CIDR to Mask

```text
/26 = 255.255.255.192
```

### Addresses per Subnet

```text
64
```

### Matching Range

The fourth-octet value is:

```text
88
```

The matching range is:

```text
64–127
```

### Results

```text
Subnet ID:         165.245.12.64
Broadcast:         165.245.12.127
First usable host: 165.245.12.65
Last usable host:  165.245.12.126
```

---

## Example 3: 165.245.12.88/20

### Convert CIDR to Mask

```text
/20 = 255.255.240.0
```

### Addresses per Subnet in Interesting Octet

```text
16
```

### Matching Range

The third-octet value is:

```text
12
```

The matching range is:

```text
0–15
```

### Results

```text
Subnet ID:         165.245.0.0
Broadcast:         165.245.15.255
First usable host: 165.245.0.1
Last usable host:  165.245.15.254
```

---

## Example 4: 18.172.200.77/11

### Convert CIDR to Mask

```text
/11 = 255.224.0.0
```

### Addresses per Subnet in Interesting Octet

```text
32
```

### Matching Range

The second-octet value is:

```text
172
```

The matching range is:

```text
160–191
```

### Results

```text
Subnet ID:         18.160.0.0
Broadcast:         18.191.255.255
First usable host: 18.160.0.1
Last usable host:  18.191.255.254
```

---

## Example 5: 18.172.200.77/17

### Convert CIDR to Mask

```text
/17 = 255.255.128.0
```

### Addresses per Subnet in Interesting Octet

```text
128
```

### Matching Range

The third-octet value is:

```text
200
```

The matching range is:

```text
128–255
```

### Results

```text
Subnet ID:         18.172.128.0
Broadcast:         18.172.255.255
First usable host: 18.172.128.1
Last usable host:  18.172.255.254
```

---

## Accuracy Notes

The transcript includes a few spoken or transcription slips.

Use these corrected values:

```text
/27 mask = 255.255.255.224
```

not:

```text
255.255.255.244
```

For the `/26` example, the last usable host is:

```text
165.245.12.126
```

For the `/20` example, the IP address is documented consistently as:

```text
165.245.12.88/20
```

---

## Cloud Engineering Connection

Cloud engineers use subnetting shortcuts when working with:

- Virtual private clouds
- Virtual networks
- Public subnets
- Private subnets
- Route tables
- NAT gateways
- Security groups
- VPN connections
- Hybrid cloud networks
- Kubernetes networking
- IP-address planning

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Fast subnetting shortcut | Seven-second subnetting |
| CIDR-to-mask conversion | Reference chart |
| Network boundary lookup | Subnet-boundary chart |
| First usable host | Subnet ID + 1 |
| Last usable host | Broadcast - 1 |
| `/26` | `255.255.255.192` |
| `/27` | `255.255.255.224` |
| `/20` | `255.255.240.0` |
| `/11` | `255.224.0.0` |
| `/17` | `255.255.128.0` |

---

## Memory Trick

```text
Convert CIDR
Find subnet range
Subnet ID = First address
Broadcast = Last address
First host = Subnet + 1
Last host = Broadcast - 1
```

---

## Practice Questions

### 1. What is the purpose of seven-second subnetting?

Answer: To calculate subnet information quickly using predefined charts and minimal arithmetic.

### 2. What is the dotted-decimal mask for `/26`?

Answer:

```text
255.255.255.192
```

### 3. What subnet contains `165.245.12.88/26`?

Answer:

```text
165.245.12.64/26
```

### 4. What is the broadcast address for `165.245.12.88/26`?

Answer:

```text
165.245.12.127
```

### 5. What subnet contains `18.172.200.77/11`?

Answer:

```text
18.160.0.0/11
```

### 6. What subnet contains `18.172.200.77/17`?

Answer:

```text
18.172.128.0/17
```
