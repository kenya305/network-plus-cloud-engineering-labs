# Network+ N10-009 Study Notes: Magic Number Subnetting

## Video Topic

Magic Number Subnetting

## Summary

The magic-number method is a shortcut for calculating IPv4 subnet details without converting every value between decimal and binary.

Use it to calculate:

- Subnet ID
- Broadcast address
- First usable host
- Last usable host
- Interesting octet
- Magic number

---

## Core Formula

```text
Magic number = 256 - Interesting-octet subnet-mask value
```

The interesting octet is the subnet-mask octet that is neither `0` nor `255`.

Example:

```text
Subnet mask: 255.255.240.0
Interesting octet: 240
Magic number: 256 - 240 = 16
```

---

## Four Values to Calculate

| Value | Meaning |
| ----- | ------- |
| Subnet ID | First address in the subnet |
| Broadcast address | Last address in the subnet |
| First usable host | Subnet ID + 1 |
| Last usable host | Broadcast address - 1 |

---

## Common Magic Numbers

| Interesting-Octet Mask | Magic Number |
| ---------------------- | ------------ |
| `128` | `128` |
| `192` | `64` |
| `224` | `32` |
| `240` | `16` |
| `248` | `8` |
| `252` | `4` |
| `254` | `2` |
| `255` | `1` |

### Memory Pattern

```text
128, 64, 32, 16, 8, 4, 2, 1
```

---

## CIDR and Interesting-Octet Ranges

| CIDR Range | Interesting Octet |
| ---------- | ----------------- |
| `/9` through `/16` | Octet 2 |
| `/17` through `/24` | Octet 3 |
| `/25` through `/30` | Octet 4 |

---

## Magic-Number Workflow

```text
1. Convert CIDR to dotted-decimal mask if needed.
2. Identify the interesting octet.
3. Calculate magic number = 256 - interesting-octet mask.
4. Find the range containing the IP value in the interesting octet.
5. Subnet ID = First value in that range.
6. Broadcast interesting-octet value = Subnet-ID value + magic number - 1.
7. First usable host = Subnet ID + 1.
8. Last usable host = Broadcast address - 1.
```

---

## Example 1: Choose a Subnet Mask for 40 Devices

### Starting Network

```text
192.168.1.0/24
```

### Requirement

```text
More than one subnet
At least 40 usable host addresses per subnet
```

| CIDR Prefix | Subnet Mask | Possible Subnets | Usable Hosts per Subnet |
| ----------- | ----------- | ---------------- | ----------------------- |
| `/24` | `255.255.255.0` | `1` | `254` |
| `/25` | `255.255.255.128` | `2` | `126` |
| `/26` | `255.255.255.192` | `4` | `62` |
| `/27` | `255.255.255.224` | `8` | `30` |

### Best Choice

```text
/26
```

A `/26` provides:

```text
62 usable hosts per subnet
```

A `/27` is too small because it provides only:

```text
30 usable hosts per subnet
```

---

## Example 2: 165.245.77.14 with Mask 255.255.240.0

### Given

```text
IP address:  165.245.77.14
Subnet mask: 255.255.240.0
```

### Calculation

```text
Interesting octet: Third octet
Magic number:      256 - 240 = 16
Matching range:    64–79
Subnet ID:         165.245.64.0
Broadcast:         165.245.79.255
First usable host: 165.245.64.1
Last usable host:  165.245.79.254
```

---

## Example 3: 10.180.122.244 with Mask 255.248.0.0

### Given

```text
IP address:  10.180.122.244
Subnet mask: 255.248.0.0
```

### Calculation

```text
Interesting octet: Second octet
Magic number:      256 - 248 = 8
Matching range:    176–183
Subnet ID:         10.176.0.0
Broadcast:         10.183.255.255
First usable host: 10.176.0.1
Last usable host:  10.183.255.254
```

---

## Example 4: 172.16.242.133/27

### Convert CIDR to Mask

```text
/27 = 255.255.255.224
```

### Calculation

```text
Interesting octet: Fourth octet
Magic number:      256 - 224 = 32
Matching range:    128–159
Subnet ID:         172.16.242.128
Broadcast:         172.16.242.159
First usable host: 172.16.242.129
Last usable host:  172.16.242.158
```

---

## Important Special Cases

Traditional usable-host calculations typically use:

```text
2^h - 2
```

However:

```text
/31 = Special point-to-point use case
/32 = Single host route
```

---

## Cloud Engineering Connection

Cloud engineers use subnet calculations when designing:

- Virtual private clouds
- Virtual networks
- Public subnets
- Private subnets
- Database subnets
- Route tables
- NAT gateways
- Security groups
- VPN connections
- Kubernetes networks
- IP-address allocation plans

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Faster subnetting shortcut | Magic-number method |
| Mask octet not equal to `0` or `255` | Interesting octet |
| Calculate magic number | `256 - interesting-octet mask` |
| First address in subnet | Subnet ID |
| Last address in subnet | Broadcast address |
| First usable host | Subnet ID + 1 |
| Last usable host | Broadcast - 1 |
| Need at least `40` devices per subnet | `/26` |

---

## Memory Trick

```text
Interesting octet = Mask octet not equal to 0 or 255
Magic number      = 256 - Interesting octet
Subnet ID         = Start of range
Broadcast         = Start + Magic - 1
First host        = Subnet + 1
Last host         = Broadcast - 1
```

---

## Practice Questions

### 1. What is the magic-number formula?

Answer:

```text
256 - Interesting-octet subnet-mask value
```

### 2. What is the interesting octet?

Answer: The subnet-mask octet that is neither `0` nor `255`.

### 3. What is the magic number for `255.255.240.0`?

Answer:

```text
16
```

### 4. What subnet contains `165.245.77.14` with mask `255.255.240.0`?

Answer:

```text
165.245.64.0/20
```

### 5. What is the broadcast address for `10.180.122.244` with mask `255.248.0.0`?

Answer:

```text
10.183.255.255
```

### 6. What subnet contains `172.16.242.133/27`?

Answer:

```text
172.16.242.128/27
```

### 7. Which prefix supports at least `40` usable hosts while creating more than one subnet from a `/24`?

Answer:

```text
/26
```
