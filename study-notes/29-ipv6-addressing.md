# Network+ N10-009 Study Notes: IPv6 Addressing

## Video Topic

IPv6 Addressing

## Summary

IPv6 is the next generation of Internet Protocol addressing.

IPv4 uses a 32-bit address space, while IPv6 uses a 128-bit address space.

IPv6 provides a much larger number of available addresses and helps reduce the long-term dependency on IPv4 workarounds such as Network Address Translation.

This lesson covers:

- IPv4 address limitations
- IPv6 address structure
- Hexadecimal notation
- Hextets
- IPv6 address compression
- Leading-zero removal
- Double-colon compression
- IPv4 and IPv6 coexistence
- Tunneling
- Dual-stack routing
- NAT64
- DNS64

---

## IPv4 Address Limitation

IPv4 uses:

```text
32-bit addresses
```

This provides approximately:

```text
4.29 billion addresses
```

The rapid growth of internet-connected devices created pressure on the available IPv4 address space.

### Common IPv4 Workaround

```text
Network Address Translation
```

NAT allows multiple private IPv4 devices to communicate externally using a smaller number of public IPv4 addresses.

### Key Takeaway

```text
IPv4 address space is limited.
IPv6 provides a much larger address space.
```

---

## IPv6 Address Size

IPv6 uses:

```text
128-bit addresses
```

An IPv6 address contains:

```text
16 bytes
```

or:

```text
16 octets
```

### Comparison

| Protocol | Address Size | Typical Notation |
| -------- | ------------ | ---------------- |
| IPv4 | `32 bits` | Decimal values separated by periods |
| IPv6 | `128 bits` | Hexadecimal values separated by colons |

---

## IPv6 Hextets

An IPv6 address is divided into eight groups.

Each group contains:

```text
16 bits
```

Each group may also be called a:

```text
Hextet
```

### Structure

```text
8 hextets
× 16 bits per hextet
= 128 bits
```

### Example

```text
2601:04C3:4002:BE00:0000:0000:0000:0066
```

---

## Hexadecimal Notation

IPv6 uses hexadecimal values.

Hexadecimal uses:

```text
0 through 9
A through F
```

### Key Takeaway

```text
IPv6 = Hexadecimal values separated by colons
```

---

## IPv6 Address Compression

IPv6 addresses may be shortened to make them easier to read.

Two common compression rules are:

```text
1. Remove leading zeros from each hextet.
2. Replace one consecutive series of all-zero hextets with a double colon.
```

---

## Rule 1: Remove Leading Zeros

### Full Address

```text
2601:04C3:4002:BE00:0000:0000:0000:0066
```

### Remove Leading Zeros

```text
2601:4C3:4002:BE00:0:0:0:66
```

### Key Takeaway

```text
Leading zeros may be removed from each hextet.
```

---

## Rule 2: Use Double-Colon Compression

A consecutive series of all-zero hextets may be replaced with:

```text
::
```

### Example

```text
2601:4C3:4002:BE00:0:0:0:66
```

becomes:

```text
2601:4C3:4002:BE00::66
```

### Important Rule

Double-colon compression may be used:

```text
Only once in a single IPv6 address
```

Using `::` more than once would make it ambiguous how many zero groups were removed.

---

## IPv6 Compression Example 1

### Full Address

```text
2600:DDDD:1111:0001:0000:0000:0000:0001
```

### Remove Leading Zeros

```text
2600:DDDD:1111:1:0:0:0:1
```

### Replace Consecutive Zero Hextets

```text
2600:DDDD:1111:1::1
```

---

## IPv6 Compression Example 2

### Full Address

```text
2601:04C3:4002:BE00:0000:0000:0000:0066
```

### Remove Leading Zeros

```text
2601:4C3:4002:BE00:0:0:0:66
```

### Replace Consecutive Zero Hextets

```text
2601:4C3:4002:BE00::66
```

---

## IPv4 and IPv6 Communication

IPv4 and IPv6 do not directly communicate with each other.

Organizations use transition technologies to support communication between the two protocols.

### Common Transition Methods

- Tunneling
- Dual-stack routing
- NAT64
- DNS64

---

## Tunneling

Tunneling carries one protocol inside another protocol.

### Examples

```text
IPv6 over IPv4
IPv4 over IPv6
```

### Why Tunneling Was Used

Early IPv6 adoption required compatibility with networks that still used IPv4 infrastructure.

### Key Takeaway

```text
Tunneling = Carry one IP protocol inside another
```

---

## 6to4 Tunneling

6to4 is a tunneling method that carries IPv6 traffic across an IPv4 network.

### Characteristics

- IPv6 traffic crosses IPv4 infrastructure
- Relay routers are required
- NAT support is limited
- Less common in modern enterprise environments

### Key Takeaway

```text
6to4 = IPv6 traffic tunneled over IPv4
```

---

## IPv4-in-IPv6 Tunneling

IPv4 traffic may also be tunneled across an IPv6 network.

### Key Takeaway

```text
IPv4-in-IPv6 = IPv4 traffic carried over IPv6 transport
```

---

## Dual-Stack Routing

Dual-stack routing allows a device to use IPv4 and IPv6 at the same time.

### Example

A network interface may have:

```text
IPv4 address
IPv6 address
```

Applications can use whichever protocol is supported.

### Benefits

- Supports gradual migration
- Allows IPv4 and IPv6 coexistence
- Reduces immediate replacement requirements
- Common in modern networks

### Key Takeaway

```text
Dual stack = IPv4 and IPv6 enabled together
```

---

## NAT64

NAT64 translates between IPv6 and IPv4.

It allows an IPv6-only client to communicate with an IPv4-only service.

### Simplified Flow

```text
IPv6 client
→ NAT64 router
→ IPv4 service
```

### Key Takeaway

```text
NAT64 = IPv6-to-IPv4 address translation
```

---

## DNS64

DNS64 supports NAT64 by synthesizing IPv6 responses for IPv4-only destinations.

### Simplified Flow

```text
IPv6 client requests DNS record
→ DNS64 receives IPv4 answer
→ DNS64 creates synthesized IPv6 response
→ IPv6 client connects through NAT64 router
→ NAT64 translates traffic to IPv4 destination
```

### Key Takeaway

```text
DNS64 helps IPv6 clients reach IPv4-only services through NAT64.
```

---

## NAT64 and DNS64 Example

### Scenario

```text
IPv6-only client
→ Wants to reach IPv4-only website
```

### Process

```text
1. IPv6 client sends DNS request.
2. DNS64 obtains IPv4 record.
3. DNS64 creates synthesized IPv6 response.
4. Client sends traffic to synthesized IPv6 address.
5. NAT64 router translates traffic to IPv4.
6. IPv4 server receives request.
7. Return traffic is translated back to IPv6.
```

---

## IPv4 vs. IPv6 Comparison

| Feature | IPv4 | IPv6 |
| ------- | ---- | ---- |
| Address size | `32 bits` | `128 bits` |
| Typical notation | Decimal and periods | Hexadecimal and colons |
| Address availability | Limited | Extremely large |
| Common transition method | NAT | Dual stack, tunneling, NAT64 |
| Compression rules | Not applicable | Leading-zero removal and `::` |

---

## Cloud Engineering Connection

Cloud engineers work with IPv6 when supporting:

- Cloud virtual networks
- Public cloud workloads
- Hybrid cloud connectivity
- Dual-stack applications
- IPv6-only services
- NAT64 gateways
- DNS64 services
- Kubernetes clusters
- Container networking
- Load balancers
- Public endpoints
- Network migrations
- Security groups
- Firewall rules

### Example

```text
IPv6-only cloud workload
→ Needs access to IPv4-only service
→ Use DNS64 and NAT64
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Next-generation IP addressing | IPv6 |
| IPv6 address length | `128 bits` |
| IPv4 address length | `32 bits` |
| IPv6 groups separated by colons | Hextets |
| Remove zeros at beginning of group | Leading-zero removal |
| Compress consecutive zero groups | `::` |
| Use `::` more than once | Not allowed |
| IPv4 and IPv6 enabled together | Dual stack |
| IPv6 over IPv4 | 6to4 tunneling |
| IPv4 traffic inside IPv6 network | IPv4-in-IPv6 tunneling |
| Translate IPv6 client traffic to IPv4 | NAT64 |
| Synthesized IPv6 DNS record | DNS64 |

---

## Memory Trick

```text
IPv4   = 32 bits
IPv6   = 128 bits
Hextet = 16-bit IPv6 group

::     = Compress one consecutive zero sequence
Dual stack = IPv4 + IPv6 together
NAT64      = Translate IPv6 to IPv4
DNS64      = Create IPv6-style DNS answer for IPv4 service
```

---

## Practice Questions

### 1. How many bits are in an IPv6 address?

Answer:

```text
128 bits
```

### 2. How many bits are in one IPv6 hextet?

Answer:

```text
16 bits
```

### 3. How many hextets are in an IPv6 address?

Answer:

```text
8
```

### 4. Which notation is used by IPv6?

Answer: Hexadecimal values separated by colons.

### 5. Can leading zeros be removed from an IPv6 hextet?

Answer: Yes.

### 6. How many times can `::` appear in one IPv6 address?

Answer:

```text
Once
```

### 7. What is dual-stack routing?

Answer: Using IPv4 and IPv6 on the same device or network interface.

### 8. What does NAT64 do?

Answer: It translates traffic between IPv6 and IPv4.

### 9. What does DNS64 do?

Answer: It synthesizes IPv6 DNS responses so IPv6 clients can reach IPv4-only services through NAT64.

### 10. What is 6to4 tunneling?

Answer: A tunneling method that carries IPv6 traffic over an IPv4 network.
