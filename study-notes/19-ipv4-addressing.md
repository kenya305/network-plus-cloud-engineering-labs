# Network+ N10-009 Study Notes: IPv4 Addressing

## Video Topic

IPv4 Addressing

## Summary

IPv4 is a widely used network-layer protocol.

An IPv4 address identifies a network interface so that it can communicate using Internet Protocol.

IPv4 configuration commonly includes:

- IPv4 address
- Subnet mask
- Default gateway
- DHCP configuration
- Loopback address
- Link-local address
- Private IP address
- Public IP address
- Virtual IP address
- Network Address Translation
- CIDR notation

---

## IPv4 and the OSI Model

IPv4 operates at:

```text
OSI Layer 3: Network Layer
```

Layer 3 is responsible for logical addressing and routing traffic between networks.

### Key Takeaway

```text
IPv4 address = Layer 3 logical address
```

---

## IPv4 Address Structure

An IPv4 address contains:

```text
32 bits
```

The address is divided into:

```text
4 octets
```

Each octet contains:

```text
8 bits
```

### Example

```text
192.168.1.165
```

### Structure

| IPv4 Component | Value |
| -------------- | ----- |
| Total number of bits | `32` |
| Number of octets | `4` |
| Bits per octet | `8` |
| Decimal range per octet | `0` through `255` |

### Key Takeaway

```text
IPv4 address
= 32 bits
= 4 bytes
= 4 octets
```

---

## IPv4 Address Example

Consider the following IPv4 address:

```text
192.168.1.131
```

Each decimal octet represents an 8-bit binary value.

| Decimal Octet | Binary Value |
| ------------- | ------------ |
| `192` | `11000000` |
| `168` | `10101000` |
| `1` | `00000001` |
| `131` | `10000011` |

### Full Binary Representation

```text
192.168.1.131
=
11000000.10101000.00000001.10000011
```

---

## Unique IPv4 Address Requirement

A device interface needs an IPv4 address to communicate using IPv4.

Within the relevant network, each active interface should use a unique IPv4 address.

### Important Note

If two devices on the same network use the same IPv4 address, an address conflict may occur.

### Key Takeaway

```text
Each active interface needs a unique IPv4 address within its network context.
```

---

## Subnet Mask

A subnet mask is used with an IPv4 address to determine the local IP subnet.

### Example

```text
IPv4 address: 192.168.1.165
Subnet mask:  255.255.255.0
```

The subnet mask helps a local device determine whether a destination is:

```text
Local
```

or:

```text
Remote
```

### Important Note

The subnet mask is used locally by the device to make routing decisions.

### Key Takeaway

```text
Subnet mask = Identifies the local network portion of an IPv4 address
```

---

## Default Gateway

A default gateway is the local router address used to send traffic outside the local subnet.

### Example

```text
IPv4 address:     192.168.1.165
Subnet mask:      255.255.255.0
Default gateway:  192.168.1.1
```

The default gateway must be reachable from the local subnet.

### Traffic Example

```text
Local device needs to reach external network
→ Sends traffic to default gateway
→ Router forwards traffic toward destination
```

### Key Takeaway

```text
Default gateway = Local router used to reach remote networks
```

---

## Local vs. Remote Communication

A device uses its IPv4 address and subnet mask to decide whether the destination is local or remote.

### Local Destination

```text
Destination is inside local subnet
→ Device communicates locally
```

### Remote Destination

```text
Destination is outside local subnet
→ Device sends traffic to default gateway
```

---

## Loopback Address

The IPv4 loopback block is:

```text
127.0.0.0/8
```

The most common loopback address is:

```text
127.0.0.1
```

The loopback address refers to the local device.

It is commonly used to test whether the local TCP/IP stack is operating correctly.

### Example Command

```bash
ping 127.0.0.1
```

### Key Takeaway

```text
127.0.0.1 = Common IPv4 loopback address
```

### Exam Tip

If the question mentions testing the local TCP/IP stack, think:

```text
Loopback address
```

---

## Reserved IPv4 Address Block

The IPv4 address block:

```text
240.0.0.0/4
```

is reserved.

This range should not be assigned as ordinary host addresses.

### Historical Terminology

This reserved range has historically been associated with:

```text
Class E
```

### Important Note

Class-based addressing terminology is historical.

Modern networks use CIDR notation.

---

## Virtual IP Address

A virtual IP address may also be called:

```text
VIP
```

A VIP is not limited to one physical network adapter.

A VIP may be used as a logical address for:

- Virtual machines
- Routers
- Load balancers
- High-availability services
- Clustered systems
- Failover configurations

### Example

```text
Users connect to one VIP
→ Load balancer distributes requests
→ Backend servers process traffic
```

### Key Takeaway

```text
VIP = Logical IP address used by a virtual or shared service
```

---

## Manual IPv4 Configuration

Historically, administrators manually configured:

- IPv4 address
- Subnet mask
- Default gateway
- DNS server settings

This required changes on each individual device.

### Limitation

Manual configuration can become time-consuming and difficult to manage across large networks.

---

## DHCP: Dynamic Host Configuration Protocol

DHCP stands for:

```text
Dynamic Host Configuration Protocol
```

DHCP automatically provides IPv4 configuration to connected devices.

### DHCP May Assign

- IPv4 address
- Subnet mask
- Default gateway
- DNS server
- Lease time

### Example

```text
Device connects to wired or wireless network
→ DHCP server provides IPv4 configuration
→ Device communicates on network
```

### Key Takeaway

```text
DHCP = Automatic IPv4 configuration
```

---

## APIPA and IPv4 Link-Local Addressing

APIPA stands for:

```text
Automatic Private IP Addressing
```

APIPA assigns an IPv4 link-local address when a device cannot obtain normal IPv4 configuration from a DHCP server.

The IPv4 link-local block is:

```text
169.254.0.0/16
```

The usable automatic-selection range is:

```text
169.254.1.0 through 169.254.254.255
```

The first and last `/24` blocks are reserved.

### Key Limitation

An APIPA address is only useful for local-link communication.

It is not routable across the public internet.

### Example

```text
DHCP server unavailable
→ Device assigns IPv4 link-local address
→ Device may communicate only on local link
```

### ARP Check

Before selecting a link-local address, the device uses ARP to check whether another device is already using that address.

### Key Takeaway

```text
169.254.x.x address
→ Possible DHCP problem
→ Link-local communication only
```

### Exam Tip

If a device receives an address beginning with:

```text
169.254
```

think:

```text
APIPA
DHCP server may be unavailable
```

---

## Public IPv4 Address

A public IPv4 address is routable on the public internet.

Public IPv4 addresses are used for communication across external networks.

### Key Takeaway

```text
Public IPv4 address = Routable on public internet
```

---

## Private IPv4 Address

A private IPv4 address is designed for use inside a private network.

Private IPv4 addresses are not publicly routable on the global internet.

RFC 1918 defines three private IPv4 address ranges.

---

## RFC 1918 Private IPv4 Address Ranges

| Private Address Range | CIDR Notation | Decimal Subnet Mask | Approximate Number of Addresses |
| --------------------- | ------------- | ------------------- | ------------------------------- |
| `10.0.0.0` through `10.255.255.255` | `10.0.0.0/8` | `255.0.0.0` | More than `16 million` |
| `172.16.0.0` through `172.31.255.255` | `172.16.0.0/12` | `255.240.0.0` | More than `1 million` |
| `192.168.0.0` through `192.168.255.255` | `192.168.0.0/16` | `255.255.0.0` | More than `65,000` |

### Memory Trick

```text
10.x.x.x

172.16.x.x
through
172.31.x.x

192.168.x.x
```

### Important Note

Not every address beginning with:

```text
172
```

is private.

Only the following range is private:

```text
172.16.0.0 through 172.31.255.255
```

---

## Private IPv4 Address Range 1

### CIDR Block

```text
10.0.0.0/8
```

### Address Range

```text
10.0.0.0
through
10.255.255.255
```

### Decimal Subnet Mask

```text
255.0.0.0
```

### Host Portion Size

```text
24 bits
```

### Historical Classful Reference

```text
Class A private block
```

---

## Private IPv4 Address Range 2

### CIDR Block

```text
172.16.0.0/12
```

### Address Range

```text
172.16.0.0
through
172.31.255.255
```

### Decimal Subnet Mask

```text
255.240.0.0
```

### Host Portion Size

```text
20 bits
```

### Historical Classful Reference

```text
16 contiguous Class B ranges
```

---

## Private IPv4 Address Range 3

### CIDR Block

```text
192.168.0.0/16
```

### Address Range

```text
192.168.0.0
through
192.168.255.255
```

### Decimal Subnet Mask

```text
255.255.0.0
```

### Host Portion Size

```text
16 bits
```

### Historical Classful Reference

```text
256 contiguous Class C ranges
```

---

## CIDR Notation

CIDR stands for:

```text
Classless Inter-Domain Routing
```

CIDR notation identifies the number of network bits in an address range.

### Examples

| CIDR Notation | Decimal Subnet Mask |
| ------------- | ------------------- |
| `/8` | `255.0.0.0` |
| `/12` | `255.240.0.0` |
| `/16` | `255.255.0.0` |
| `/24` | `255.255.255.0` |

### Key Takeaway

```text
CIDR notation identifies the network-prefix length.
```

---

## Classful Addressing Note

Older networking documentation may refer to:

- Class A
- Class B
- Class C
- Class D
- Class E

Modern networking primarily uses:

```text
CIDR notation
```

### Key Takeaway

```text
Classful terms are useful historical references.
CIDR is the modern addressing method.
```

---

## NAT: Network Address Translation

NAT stands for:

```text
Network Address Translation
```

NAT allows private IPv4 addresses to communicate with public networks by translating address information.

### Example

```text
Private device address
→ NAT router or firewall
→ Public IPv4 address
→ Internet
```

### Why NAT Matters

Private IPv4 addresses are not routed across the public internet.

NAT helps organizations use private addresses internally while still allowing internet communication.

### Key Takeaway

```text
NAT translates private-address communication for public-network access.
```

---

## IPv4 Address-Type Comparison

| Address Type | Example | Main Purpose |
| ------------ | ------- | ------------ |
| Local host address | `192.168.1.165` | Identifies interface inside local network |
| Subnet mask | `255.255.255.0` | Identifies local subnet |
| Default gateway | `192.168.1.1` | Routes traffic outside local subnet |
| Loopback | `127.0.0.1` | Tests local TCP/IP stack |
| IPv4 link-local / APIPA | `169.254.x.x` | Local-link communication when normal configuration is unavailable |
| Private IPv4 address | `10.x.x.x`, `172.16-31.x.x`, `192.168.x.x` | Internal network communication |
| Public IPv4 address | Publicly assigned address | Public-internet communication |
| VIP | Logical service address | Shared, virtual, clustered, or failover service |
| Reserved block | `240.0.0.0/4` | Reserved address space |

---

## Cloud Engineering Connection

Cloud engineers use IPv4 addressing when configuring:

- Virtual networks
- Cloud subnets
- Virtual machines
- Route tables
- Default routes
- Network interfaces
- Load balancers
- VIPs
- NAT gateways
- Firewalls
- Security groups
- VPN connections
- Hybrid cloud environments
- Private endpoints
- Public endpoints

### Cloud Scenario Examples

```text
Virtual machine receives private IPv4 address
→ Internal cloud-network communication

Private subnet needs outbound internet access
→ NAT gateway

Public web application receives inbound internet traffic
→ Public endpoint or load balancer

Load-balanced application uses logical service address
→ VIP
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Layer used by IPv4 | OSI Layer 3 |
| Total bits in IPv4 address | `32` |
| Number of IPv4 octets | `4` |
| Maximum decimal value in one octet | `255` |
| Determines whether destination is local or remote | Subnet mask |
| Routes traffic outside local subnet | Default gateway |
| Common local TCP/IP test address | `127.0.0.1` |
| Entire loopback block | `127.0.0.0/8` |
| Automatic configuration from network server | DHCP |
| Address begins with `169.254` | APIPA / IPv4 link-local |
| DHCP may be unavailable | APIPA / IPv4 link-local |
| Logical shared service address | VIP |
| Private-to-public address translation | NAT |
| Private `10` range | `10.0.0.0/8` |
| Private `172` range | `172.16.0.0/12` |
| Private `192.168` range | `192.168.0.0/16` |
| Modern prefix notation | CIDR |
| Historical reserved Class E range | `240.0.0.0/4` |

---

## Memory Trick

```text
IPv4 address     = 32 bits = 4 octets
Subnet mask      = Local or remote decision
Default gateway  = Exit to remote network
127.0.0.1        = Loopback
169.254.x.x      = APIPA / possible DHCP issue
10.x.x.x         = Private
172.16-31.x.x    = Private
192.168.x.x      = Private
NAT              = Private-to-public translation
VIP              = Logical service address
```

---

## Practice Questions

### 1. At which OSI layer does IPv4 operate?

Answer: Layer 3, the Network layer

### 2. How many bits are in an IPv4 address?

Answer: `32`

### 3. How many octets are in an IPv4 address?

Answer: `4`

### 4. How many bits are in one IPv4 octet?

Answer: `8`

### 5. What is the maximum decimal value of one IPv4 octet?

Answer: `255`

### 6. What does a subnet mask help a device determine?

Answer: Whether an IP address is local or outside the local subnet.

### 7. What is a default gateway?

Answer: A local router address used to communicate outside the local subnet.

### 8. What is the common IPv4 loopback address?

Answer: `127.0.0.1`

### 9. What is the purpose of the loopback address?

Answer: To test whether the local TCP/IP stack is working properly.

### 10. What does DHCP stand for?

Answer: Dynamic Host Configuration Protocol

### 11. What does APIPA stand for?

Answer: Automatic Private IP Addressing

### 12. Which IPv4 prefix is associated with link-local addressing?

Answer: `169.254.0.0/16`

### 13. What might an address beginning with `169.254` indicate?

Answer: The device may not have received normal configuration from a DHCP server.

### 14. Can an APIPA address normally reach the public internet?

Answer: No. IPv4 link-local addresses are for local-link communication.

### 15. What does VIP stand for?

Answer: Virtual IP address

### 16. What does NAT stand for?

Answer: Network Address Translation

### 17. What are the three RFC 1918 private IPv4 ranges?

Answer:

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

### 18. Is every IPv4 address beginning with `172` private?

Answer: No. Only `172.16.0.0` through `172.31.255.255` are part of the RFC 1918 private range.

### 19. What does CIDR stand for?

Answer: Classless Inter-Domain Routing

### 20. Which notation is primarily used in modern network planning: classful addressing or CIDR?

Answer: CIDR
