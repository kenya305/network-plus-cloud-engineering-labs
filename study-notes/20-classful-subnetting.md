# Network+ N10-009 Study Notes: Classful Subnetting

## Video Topic

Classful Subnetting

## Summary

IPv4 was designed to support networks of different sizes.

Historically, IPv4 addresses were organized into classes.

The class of an IPv4 address helped determine the default subnet mask and the boundary between:

- Network bits
- Host bits

Modern networks use CIDR notation instead of class-based subnetting.

However, classful boundaries remain useful as a starting point for learning subnetting.

This lesson covers:

- Class A addresses
- Class B addresses
- Class C addresses
- Class D multicast addresses
- Class E reserved addresses
- Default subnet masks
- Network bits
- Host bits
- Network address
- First usable host address
- Last usable host address
- Broadcast address
- Historical classful addressing
- Modern CIDR notation

---

## Important Modern Networking Note

Class-based subnetting has not been the modern addressing standard since:

```text
1993
```

Modern networking uses:

```text
CIDR
```

CIDR stands for:

```text
Classless Inter-Domain Routing
```

Classful terminology may still appear in:

- Network+ exam questions
- Older documentation
- Casual technical conversations
- Foundational subnetting lessons

### Key Takeaway

```text
Classful addressing = Historical learning framework
CIDR notation       = Modern networking method
```

---

## IPv4 Address Classes

The historical IPv4 class is identified by the first octet.

| Address Class | First-Octet Range | Default Subnet Mask | CIDR Equivalent | Network Bits | Host Bits | Main Use |
| ------------- | ----------------- | ------------------- | --------------- | ------------ | --------- | -------- |
| Class A | `1` through `126` | `255.0.0.0` | `/8` | `8` | `24` | Large host networks |
| Class B | `128` through `191` | `255.255.0.0` | `/16` | `16` | `16` | Medium host networks |
| Class C | `192` through `223` | `255.255.255.0` | `/24` | `24` | `8` | Smaller host networks |
| Class D | `224` through `239` | Not applicable | Not applicable | Not applicable | Not applicable | Multicast |
| Class E | `240` through `255` | Not applicable | Not applicable | Not applicable | Not applicable | Reserved |

### Important Exceptions

The complete historical Class A numerical pattern includes first-octet values beginning at `0` and extending through `127`.

However:

```text
0.x.x.x   = Reserved
127.x.x.x = Loopback
```

For ordinary host-address planning, Class A examples commonly use:

```text
1 through 126
```

---

## Binary Prefix Patterns

Address classes can also be identified by the beginning binary bits of the first octet.

| Address Class | Beginning Binary Pattern |
| ------------- | ------------------------ |
| Class A | `0` |
| Class B | `10` |
| Class C | `110` |
| Class D | `1110` |
| Class E | `1111` |

### Memory Trick

```text
Class A = 0
Class B = 10
Class C = 110
Class D = 1110
Class E = 1111
```

---

## Class A Addresses

A Class A address uses:

```text
8 network bits
24 host bits
```

### Default Subnet Mask

```text
255.0.0.0
```

### CIDR Equivalent

```text
/8
```

### Boundary

```text
Network | Host | Host | Host
```

### Example

```text
10.74.222.11
```

The first octet is:

```text
10
```

This falls within the Class A range.

### Key Takeaway

```text
Class A = First octet identifies network
```

---

## Class B Addresses

A Class B address uses:

```text
16 network bits
16 host bits
```

### Default Subnet Mask

```text
255.255.0.0
```

### CIDR Equivalent

```text
/16
```

### Boundary

```text
Network | Network | Host | Host
```

### Example

```text
172.16.88.200
```

The first octet is:

```text
172
```

This falls within the Class B range.

### Key Takeaway

```text
Class B = First two octets identify network
```

---

## Class C Addresses

A Class C address uses:

```text
24 network bits
8 host bits
```

### Default Subnet Mask

```text
255.255.255.0
```

### CIDR Equivalent

```text
/24
```

### Boundary

```text
Network | Network | Network | Host
```

### Example

```text
192.168.4.77
```

The first octet is:

```text
192
```

This falls within the Class C range.

### Key Takeaway

```text
Class C = First three octets identify network
```

---

## Class D Addresses

Class D addresses are used for:

```text
Multicast
```

### First-Octet Range

```text
224 through 239
```

Class D addresses are not assigned as ordinary individual host addresses.

### Key Takeaway

```text
Class D = Multicast
```

---

## Class E Addresses

Class E addresses are:

```text
Reserved
```

### First-Octet Range

```text
240 through 255
```

These addresses are not assigned as ordinary host addresses.

### Key Takeaway

```text
Class E = Reserved
```

---

## Class Identification Examples

| IPv4 Address | First Octet | Historical Address Class |
| ------------ | ----------- | ------------------------ |
| `17.22.90.7` | `17` | Class A |
| `220.10.77.40` | `220` | Class C |
| `165.245.0.1` | `165` | Class B |
| `128.90.10.2` | `128` | Class B |
| `191.77.24.250` | `191` | Class B |
| `192.1.12.5` | `192` | Class C |

---

## Four Important IPv4 Subnet Values

When calculating an IPv4 subnet, identify four important values:

```text
1. Network address
2. First usable host address
3. Last usable host address
4. Broadcast address
```

---

## Network Address

The network address identifies the subnet.

To calculate the network address:

```text
Set all host bits to 0
```

### Key Takeaway

```text
Network address = Host bits set to 0
```

---

## First Usable Host Address

The first usable host address is:

```text
Network address + 1
```

### Key Takeaway

```text
First usable host = One address after network address
```

---

## Broadcast Address

The broadcast address is the final address in the subnet.

To calculate the broadcast address:

```text
Set all host bits to 1
```

### Key Takeaway

```text
Broadcast address = Host bits set to 1
```

---

## Last Usable Host Address

The last usable host address is:

```text
Broadcast address - 1
```

### Key Takeaway

```text
Last usable host = One address before broadcast address
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

## Example 1: Class A Subnet Calculation

### Given IPv4 Address

```text
10.74.222.11
```

### Identify the Class

The first octet is:

```text
10
```

This is a historical:

```text
Class A address
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

### Calculate the Network Address

Set all host bits to `0`:

```text
10.0.0.0
```

### Calculate the First Usable Host

Add `1` to the network address:

```text
10.0.0.1
```

### Calculate the Broadcast Address

Set all host bits to `1`:

```text
10.255.255.255
```

### Calculate the Last Usable Host

Subtract `1` from the broadcast address:

```text
10.255.255.254
```

### Final Answer

| Subnet Detail | Result |
| ------------- | ------ |
| IPv4 address | `10.74.222.11` |
| Historical class | Class A |
| Default subnet mask | `255.0.0.0` |
| CIDR equivalent | `/8` |
| Network address | `10.0.0.0` |
| First usable host | `10.0.0.1` |
| Last usable host | `10.255.255.254` |
| Broadcast address | `10.255.255.255` |

---

## Example 2: Class B Subnet Calculation

### Given IPv4 Address

```text
172.16.88.200
```

### Identify the Class

The first octet is:

```text
172
```

This is a historical:

```text
Class B address
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

### Calculate the Network Address

Set all host bits to `0`:

```text
172.16.0.0
```

### Calculate the First Usable Host

Add `1` to the network address:

```text
172.16.0.1
```

### Calculate the Broadcast Address

Set all host bits to `1`:

```text
172.16.255.255
```

### Calculate the Last Usable Host

Subtract `1` from the broadcast address:

```text
172.16.255.254
```

### Final Answer

| Subnet Detail | Result |
| ------------- | ------ |
| IPv4 address | `172.16.88.200` |
| Historical class | Class B |
| Default subnet mask | `255.255.0.0` |
| CIDR equivalent | `/16` |
| Network address | `172.16.0.0` |
| First usable host | `172.16.0.1` |
| Last usable host | `172.16.255.254` |
| Broadcast address | `172.16.255.255` |

---

## Example 3: Class C Subnet Calculation

### Given IPv4 Address

```text
192.168.4.77
```

### Identify the Class

The first octet is:

```text
192
```

This is a historical:

```text
Class C address
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

### Calculate the Network Address

Set all host bits to `0`:

```text
192.168.4.0
```

### Calculate the First Usable Host

Add `1` to the network address:

```text
192.168.4.1
```

### Calculate the Broadcast Address

Set all host bits to `1`:

```text
192.168.4.255
```

### Calculate the Last Usable Host

Subtract `1` from the broadcast address:

```text
192.168.4.254
```

### Final Answer

| Subnet Detail | Result |
| ------------- | ------ |
| IPv4 address | `192.168.4.77` |
| Historical class | Class C |
| Default subnet mask | `255.255.255.0` |
| CIDR equivalent | `/24` |
| Network address | `192.168.4.0` |
| First usable host | `192.168.4.1` |
| Last usable host | `192.168.4.254` |
| Broadcast address | `192.168.4.255` |

---

## Classful Subnetting Comparison

| Detail | Class A | Class B | Class C |
| ------ | ------- | ------- | ------- |
| First-octet range | `1–126` | `128–191` | `192–223` |
| Default subnet mask | `255.0.0.0` | `255.255.0.0` | `255.255.255.0` |
| CIDR equivalent | `/8` | `/16` | `/24` |
| Network bits | `8` | `16` | `24` |
| Host bits | `24` | `16` | `8` |
| Network octets | First octet | First two octets | First three octets |
| Host octets | Last three octets | Last two octets | Last octet |

---

## Modern CIDR Connection

Modern networks do not rely only on class boundaries.

CIDR allows more flexible subnet masks.

### Examples

```text
/8
/12
/16
/20
/24
/27
```

The same subnet-calculation process still applies:

```text
Network address      = Host bits set to 0
First usable host    = Network address + 1
Broadcast address    = Host bits set to 1
Last usable host     = Broadcast address - 1
```

### Key Takeaway

```text
The classful method is the starting point.
The same logic applies to CIDR subnetting.
```

---

## Cloud Engineering Connection

Cloud engineers use subnetting when configuring:

- Virtual networks
- Cloud subnets
- CIDR blocks
- Route tables
- Private IP ranges
- Public IP ranges
- Security groups
- Network access controls
- NAT gateways
- Load balancers
- VPN connections
- Hybrid cloud environments
- IP-address allocation
- Network segmentation

### Example Cloud Scenario

```text
Cloud virtual network
→ Divide address space into smaller subnets
→ Assign workloads to correct subnet
→ Apply routing and security rules
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Historical large-network class | Class A |
| Historical medium-network class | Class B |
| Historical smaller-network class | Class C |
| Multicast addresses | Class D |
| Reserved addresses | Class E |
| Class A default mask | `255.0.0.0` |
| Class B default mask | `255.255.0.0` |
| Class C default mask | `255.255.255.0` |
| Class A CIDR equivalent | `/8` |
| Class B CIDR equivalent | `/16` |
| Class C CIDR equivalent | `/24` |
| Host bits set to `0` | Network address |
| Host bits set to `1` | Broadcast address |
| One address after network address | First usable host |
| One address before broadcast address | Last usable host |
| Modern subnetting method | CIDR |
| Classful addressing replaced in 1993 | CIDR |

---

## Memory Trick

```text
Class A = /8  = 255.0.0.0
Class B = /16 = 255.255.0.0
Class C = /24 = 255.255.255.0

Network   = Host bits set to 0
First     = Network + 1
Broadcast = Host bits set to 1
Last      = Broadcast - 1
```

---

## Practice Questions

### 1. What is the default subnet mask for a historical Class A address?

Answer: `255.0.0.0`

### 2. What is the CIDR equivalent of a historical Class A address?

Answer: `/8`

### 3. What is the default subnet mask for a historical Class B address?

Answer: `255.255.0.0`

### 4. What is the CIDR equivalent of a historical Class B address?

Answer: `/16`

### 5. What is the default subnet mask for a historical Class C address?

Answer: `255.255.255.0`

### 6. What is the CIDR equivalent of a historical Class C address?

Answer: `/24`

### 7. Which historical class is used for multicast?

Answer: Class D

### 8. Which historical class is reserved?

Answer: Class E

### 9. How do you calculate the network address?

Answer: Set all host bits to `0`.

### 10. How do you calculate the first usable host address?

Answer: Add `1` to the network address.

### 11. How do you calculate the broadcast address?

Answer: Set all host bits to `1`.

### 12. How do you calculate the last usable host address?

Answer: Subtract `1` from the broadcast address.

### 13. What is the network address for `10.74.222.11/8`?

Answer: `10.0.0.0`

### 14. What is the broadcast address for `10.74.222.11/8`?

Answer: `10.255.255.255`

### 15. What is the network address for `172.16.88.200/16`?

Answer: `172.16.0.0`

### 16. What is the broadcast address for `172.16.88.200/16`?

Answer: `172.16.255.255`

### 17. What is the network address for `192.168.4.77/24`?

Answer: `192.168.4.0`

### 18. What is the broadcast address for `192.168.4.77/24`?

Answer: `192.168.4.255`

### 19. What modern method replaced classful addressing?

Answer: CIDR

### 20. Why is classful addressing still useful to learn?

Answer: It provides a foundation for understanding subnet boundaries and subnet calculations.
