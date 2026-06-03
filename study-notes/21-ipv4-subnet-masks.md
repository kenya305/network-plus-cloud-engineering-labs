## Network+ N10-009 Study Notes: IPv4 Subnet Masks

## Video Topic

IPv4 Subnet Masks

## Summary

Modern IPv4 networking uses classless subnetting.

Classless subnetting allows network administrators to use subnet masks that do not have to match the historical Class A, Class B, or Class C boundaries.

Classless subnetting is commonly referred to as:

```text
CIDR
```

CIDR stands for:

```text
Classless Inter-Domain Routing
```

CIDR notation represents a subnet mask by counting the number of network bits set to `1`.

This lesson covers:

- Classless subnetting
- CIDR notation
- Network bits
- Host bits
- Binary subnet masks
- Dotted-decimal subnet masks
- CIDR prefix lengths
- Subnet-mask conversion
- Contiguous binary `1` values
- Remaining host-bit calculations

---

## Historical Classful vs. Modern Classless Subnetting

Class-based subnetting was historically organized around fixed boundaries.

| Historical Class | Default Subnet Mask | CIDR Equivalent |
| ---------------- | ------------------- | --------------- |
| Class A | `255.0.0.0` | `/8` |
| Class B | `255.255.0.0` | `/16` |
| Class C | `255.255.255.0` | `/24` |

Modern networks use classless subnetting.

### Key Takeaway

```text
Historical classful subnetting
→ Fixed boundaries

Modern classless subnetting
→ Flexible CIDR prefix lengths
```

---

## CIDR: Classless Inter-Domain Routing

CIDR stands for:

```text
Classless Inter-Domain Routing
```

CIDR notation identifies the number of network bits in the subnet mask.

### Example

```text
192.168.1.44/24
```

The `/24` means:

```text
24 bits are used for the network portion
8 bits remain for the host portion
```

### Equivalent Decimal Subnet Mask

```text
/24
=
255.255.255.0
```

### Key Takeaway

```text
CIDR prefix length = Number of network bits set to 1
```

---

## IPv4 Address and Subnet Mask Configuration

A device commonly uses:

- IPv4 address
- Subnet mask
- Default gateway
- DNS servers

### Example

```text
IPv4 address:    192.168.1.44
Subnet mask:     255.255.255.0
Default gateway: 192.168.1.1
DNS server:      Assigned DNS address
```

### Device Configuration Note

Different devices may request subnet masks in different formats.

| Device Type | Common Subnet-Mask Format |
| ----------- | ------------------------- |
| Desktop operating system | Dotted-decimal notation |
| Router | CIDR prefix notation |
| Switch | CIDR prefix notation or dotted-decimal notation |
| Cloud subnet configuration | CIDR prefix notation |

### Example

```text
255.255.255.0
```

may also be written as:

```text
/24
```

---

## Binary Subnet-Mask Pattern

A valid subnet mask uses a contiguous series of binary `1` values followed by binary `0` values.

### Example

```text
11111111.11111111.11111111.00000000
```

This subnet mask contains:

```text
24 binary 1 values
8 binary 0 values
```

### CIDR Equivalent

```text
/24
```

### Dotted-Decimal Equivalent

```text
255.255.255.0
```

### Key Takeaway

```text
Subnet mask
= Consecutive 1 values followed by 0 values
```

---

## Network Bits and Host Bits

The binary `1` values identify the network portion.

The binary `0` values identify the host portion.

### Example

```text
11111111.11111111.11111111.00000000
```

### Network Portion

```text
24 bits
```

### Host Portion

```text
8 bits
```

### Key Takeaway

```text
Network bits = 1 values
Host bits    = 0 values
```

---

## Common Single-Octet Subnet-Mask Values

Each subnet-mask octet can use only specific decimal values.

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

### Memory Trick

```text
0
128
192
224
240
248
252
254
255
```

### Key Takeaway

```text
Subnet-mask octets use contiguous 1 values.
```

---

## CIDR-to-Decimal Reference Table

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

## Conversion Process: Binary Subnet Mask to CIDR

To convert a binary subnet mask to CIDR notation:

1. Count the number of binary `1` values.
2. Write the total after a forward slash.
3. Determine the remaining host bits by subtracting the CIDR value from `32`.

### Formula

```text
Host bits = 32 - CIDR prefix length
```

---

## Example 1: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11111111.00000000.00000000
```

### Count the Binary 1 Values

```text
8 + 8 + 0 + 0 = 16
```

### CIDR Notation

```text
/16
```

### Network Bits

```text
16
```

### Host Bits

```text
32 - 16 = 16
```

### Dotted-Decimal Subnet Mask

```text
255.255.0.0
```

---

## Example 2: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11111111.11111111.11000000
```

### Count the Binary 1 Values

```text
8 + 8 + 8 + 2 = 26
```

### CIDR Notation

```text
/26
```

### Network Bits

```text
26
```

### Host Bits

```text
32 - 26 = 6
```

### Dotted-Decimal Subnet Mask

```text
255.255.255.192
```

---

## Example 3: Convert Binary Mask to CIDR

### Binary Subnet Mask

```text
11111111.11110000.00000000.00000000
```

### Count the Binary 1 Values

```text
8 + 4 + 0 + 0 = 12
```

### CIDR Notation

```text
/12
```

### Network Bits

```text
12
```

### Host Bits

```text
32 - 12 = 20
```

### Dotted-Decimal Subnet Mask

```text
255.240.0.0
```

---

## Conversion Process: CIDR to Decimal Subnet Mask

To convert CIDR notation to a dotted-decimal subnet mask:

1. Write the required number of binary `1` values.
2. Fill the remaining bit positions with binary `0` values.
3. Convert each octet to decimal.

---

## Example 4: Convert /26 to Decimal Subnet Mask

### CIDR Prefix

```text
/26
```

### Binary Subnet Mask

```text
11111111.11111111.11111111.11000000
```

### Convert Each Octet to Decimal

| Binary Octet | Decimal Value |
| ------------ | ------------- |
| `11111111` | `255` |
| `11111111` | `255` |
| `11111111` | `255` |
| `11000000` | `192` |

### Answer

```text
/26
=
255.255.255.192
```

### Host Bits

```text
32 - 26 = 6
```

---

## Example 5: Convert /20 to Decimal Subnet Mask

### CIDR Prefix

```text
/20
```

### Binary Subnet Mask

```text
11111111.11111111.11110000.00000000
```

### Convert Each Octet to Decimal

| Binary Octet | Decimal Value |
| ------------ | ------------- |
| `11111111` | `255` |
| `11111111` | `255` |
| `11110000` | `240` |
| `00000000` | `0` |

### Answer

```text
/20
=
255.255.240.0
```

### Host Bits

```text
32 - 20 = 12
```

---

## Example 6: Convert /19 to Decimal Subnet Mask

### CIDR Prefix

```text
/19
```

### Binary Subnet Mask

```text
11111111.11111111.11100000.00000000
```

### Convert Each Octet to Decimal

| Binary Octet | Decimal Value |
| ------------ | ------------- |
| `11111111` | `255` |
| `11111111` | `255` |
| `11100000` | `224` |
| `00000000` | `0` |

### Answer

```text
/19
=
255.255.224.0
```

### Host Bits

```text
32 - 19 = 13
```

---

## Subnet-Mask Conversion Summary

| CIDR Prefix | Binary Subnet Mask | Decimal Subnet Mask | Host Bits |
| ----------- | ------------------ | ------------------- | --------- |
| `/12` | `11111111.11110000.00000000.00000000` | `255.240.0.0` | `20` |
| `/16` | `11111111.11111111.00000000.00000000` | `255.255.0.0` | `16` |
| `/19` | `11111111.11111111.11100000.00000000` | `255.255.224.0` | `13` |
| `/20` | `11111111.11111111.11110000.00000000` | `255.255.240.0` | `12` |
| `/24` | `11111111.11111111.11111111.00000000` | `255.255.255.0` | `8` |
| `/26` | `11111111.11111111.11111111.11000000` | `255.255.255.192` | `6` |

---

## Cloud Engineering Connection

Cloud engineers use CIDR notation when configuring:

- Virtual networks
- Cloud subnets
- Route tables
- Security groups
- Network access controls
- VPN connections
- Hybrid cloud networks
- Private endpoints
- Public endpoints
- Kubernetes networking
- Container networks
- Load balancers
- Firewall rules
- IP-address planning

### Example Cloud Scenario

```text
Create cloud subnet
→ Assign CIDR block
→ Determine network and host portions
→ Apply routing and security rules
```

### Example CIDR Blocks

```text
10.0.0.0/16
10.0.1.0/24
10.0.2.0/26
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Classless subnetting | CIDR |
| CIDR full name | Classless Inter-Domain Routing |
| Number after forward slash | Number of network bits |
| Binary `1` values in subnet mask | Network bits |
| Binary `0` values in subnet mask | Host bits |
| `/8` | `255.0.0.0` |
| `/12` | `255.240.0.0` |
| `/16` | `255.255.0.0` |
| `/19` | `255.255.224.0` |
| `/20` | `255.255.240.0` |
| `/24` | `255.255.255.0` |
| `/26` | `255.255.255.192` |
| Valid subnet-mask octet values | `0, 128, 192, 224, 240, 248, 252, 254, 255` |
| Calculate remaining host bits | `32 - CIDR prefix length` |

---

## Memory Trick

```text
CIDR = Count the 1 values

Network bits = 1 values
Host bits    = 0 values

Host bits = 32 - CIDR prefix

Subnet-mask octet values:
0, 128, 192, 224, 240, 248, 252, 254, 255
```

---

## Practice Questions

### 1. What does CIDR stand for?

Answer: Classless Inter-Domain Routing

### 2. What does the number after the forward slash represent in CIDR notation?

Answer: The number of network bits in the subnet mask.

### 3. What is the dotted-decimal subnet mask for `/8`?

Answer: `255.0.0.0`

### 4. What is the dotted-decimal subnet mask for `/12`?

Answer: `255.240.0.0`

### 5. What is the dotted-decimal subnet mask for `/16`?

Answer: `255.255.0.0`

### 6. What is the dotted-decimal subnet mask for `/19`?

Answer: `255.255.224.0`

### 7. What is the dotted-decimal subnet mask for `/20`?

Answer: `255.255.240.0`

### 8. What is the dotted-decimal subnet mask for `/24`?

Answer: `255.255.255.0`

### 9. What is the dotted-decimal subnet mask for `/26`?

Answer: `255.255.255.192`

### 10. How many host bits remain in a `/26` network?

Answer: `6`

### 11. How many host bits remain in a `/20` network?

Answer: `12`

### 12. Which binary values identify the network portion of a subnet mask?

Answer: Binary `1` values

### 13. Which binary values identify the host portion of a subnet mask?

Answer: Binary `0` values

### 14. What formula calculates the number of host bits?

Answer:

```text
32 - CIDR prefix length
```

### 15. Which decimal values may appear inside a valid subnet-mask octet?

Answer:

```text
0
128
192
224
240
248
252
254
255
```
````
