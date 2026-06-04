# Network+ N10-009 Study Notes: Network Address Translation

## Video Topic

Network Address Translation

## Summary

Network Address Translation, or NAT, changes IP-address information as traffic moves between networks.

One of the most common NAT use cases is translating private IPv4 addresses into public IPv4 addresses so internal devices can communicate across the public internet.

IPv4 provides approximately:

```text
4.29 billion addresses
```

The available public IPv4 address space has been exhausted.

NAT helps extend the practical use of IPv4 by allowing internal devices to use private IPv4 addresses that are not routable on the public internet.

This lesson also introduces:

- Private IPv4 address ranges
- RFC 1918
- Public IPv4 addresses
- Standard NAT
- NAT tables
- NAT overload
- Port Address Translation
- PAT
- Source ports
- Destination ports
- One-to-one translation
- Many-to-one translation

---

## Why NAT Is Needed

There are billions of internet-connected devices.

IPv4 does not provide enough public addresses for every device to receive its own public IPv4 address.

### IPv4 Address Capacity

```text
IPv4 address size: 32 bits
Approximate addresses: 4.29 billion
```

### NAT Solution

```text
Private internal IP address
→ NAT router
→ Public IP address
→ Internet
```

### Key Takeaway

```text
NAT extends the practical life of IPv4.
```

---

## NAT

NAT stands for:

```text
Network Address Translation
```

NAT modifies IP-address information in real time as packets pass through a router or firewall.

### Common Use Case

```text
Private IPv4 address
→ Translate to public IPv4 address
→ Send traffic across internet
```

### Key Takeaway

```text
NAT = Modify IP addresses as traffic crosses a network boundary
```

---

## RFC 1918 Private IPv4 Ranges

RFC 1918 defines private IPv4 address ranges.

These addresses are not routed across the public internet.

| Private IPv4 Range | CIDR Block | Common Use |
| ------------------ | ---------- | ---------- |
| `10.0.0.0` through `10.255.255.255` | `10.0.0.0/8` | Enterprise networks |
| `172.16.0.0` through `172.31.255.255` | `172.16.0.0/12` | Business and internal networks |
| `192.168.0.0` through `192.168.255.255` | `192.168.0.0/16` | Home and small-office networks |

### Key Takeaway

```text
RFC 1918 = Private IPv4 address ranges
```

---

## Private vs. Public IPv4 Addresses

| Address Type | Routable on Public Internet? | Example |
| ------------ | ---------------------------- | ------- |
| Private IPv4 address | No | `10.10.20.50` |
| Public IPv4 address | Yes | `94.1.1.1` |

### Key Takeaway

```text
Private address = Internal use
Public address  = Internet-routable
```

---

## Standard NAT

Standard NAT commonly performs a one-to-one address translation.

### Example

Internal device:

```text
10.10.20.50
```

NAT router translates the private address to:

```text
94.1.1.1
```

External web server:

```text
104.20.19.63
```

### Outbound Flow

```text
Source:      10.10.20.50
Destination: 104.20.19.63

NAT translation:

Source:      94.1.1.1
Destination: 104.20.19.63
```

### Return Flow

```text
Source:      104.20.19.63
Destination: 94.1.1.1

NAT router reverses translation:

Source:      104.20.19.63
Destination: 10.10.20.50
```

### Key Takeaway

```text
Standard NAT = One private IP translated to one public IP
```

---

## NAT Table

A NAT router maintains a translation table.

The table tracks which internal address corresponds to which translated address.

### Example

| Internal Private Address | Public Translated Address |
| ------------------------ | ------------------------- |
| `10.10.20.50` | `94.1.1.1` |

### Key Takeaway

```text
NAT table = Mapping between internal and translated addresses
```

---

## Limitation of Standard NAT

Standard one-to-one NAT still requires one public IPv4 address for each active private IPv4 translation.

### Example

```text
100 internal devices
→ May require many public IPv4 addresses
```

This is more efficient than assigning public addresses directly to every internal device, but it still consumes public addresses.

---

## NAT Overload and PAT

NAT overload allows multiple internal devices to share one public IPv4 address.

NAT overload is also called:

```text
Port Address Translation
```

or:

```text
PAT
```

PAT translates:

```text
IP address
+
Port number
```

### Key Takeaway

```text
PAT = Many private devices share one public IP by using different port numbers
```

---

## PAT Example: First Internal Device

Internal device:

```text
Private source: 10.10.20.50:3233
Destination:    104.20.19.63:80
```

PAT router translates the source to:

```text
Public source: 94.1.1.1:1055
Destination:   104.20.19.63:80
```

### Translation Table

| Internal Private Socket | Public Translated Socket |
| ----------------------- | ------------------------ |
| `10.10.20.50:3233` | `94.1.1.1:1055` |

---

## PAT Example: Second Internal Device

Another internal device:

```text
Private source: 10.10.20.70:5782
Destination:    104.20.19.63:80
```

PAT router can reuse the same public IPv4 address with a different translated port.

```text
Public source: 94.1.1.1:1056
Destination:   104.20.19.63:80
```

### Updated Translation Table

| Internal Private Socket | Public Translated Socket |
| ----------------------- | ------------------------ |
| `10.10.20.50:3233` | `94.1.1.1:1055` |
| `10.10.20.70:5782` | `94.1.1.1:1056` |

### Key Takeaway

```text
Same public IP
+ Different translated ports
= Multiple internal devices can communicate externally
```

---

## Socket Review

A socket combines:

```text
IP address
+
Port number
```

### Examples

```text
10.10.20.50:3233
94.1.1.1:1055
104.20.19.63:80
```

PAT relies on socket mappings so return traffic reaches the correct internal device.

---

## Standard NAT vs. PAT

| Feature | Standard NAT | PAT / NAT Overload |
| ------- | ------------ | ------------------ |
| Translation type | One-to-one | Many-to-one |
| Translates IP address | Yes | Yes |
| Translates port number | Not required | Yes |
| Public IPv4 efficiency | Moderate | High |
| Common home-router use | Less common | Very common |
| Multiple devices share public IP | No | Yes |

---

## NAT Traffic Flow

### Standard NAT

```text
Private IP
→ NAT router changes source IP
→ Public IP
→ Internet
```

### PAT

```text
Private IP:Port
→ PAT router changes source IP and port
→ Shared Public IP:Unique Port
→ Internet
```

---

## Home and Business Network Connection

A home or office network commonly uses PAT.

### Example

```text
Laptop
Phone
Tablet
Smart TV
Printer
Smart-home devices
→ Share one public IPv4 address
→ Router tracks each connection using ports
```

### Key Takeaway

```text
PAT allows many internal devices to share limited public IPv4 addresses.
```

---

## Cloud Engineering Connection

Cloud engineers use NAT concepts when supporting:

- Private cloud subnets
- Public cloud subnets
- NAT gateways
- Internet gateways
- Egress routing
- Private workloads
- Container networks
- Kubernetes clusters
- Firewalls
- Load balancers
- Hybrid cloud networking
- Security architecture
- Cost optimization
- IPv4-address planning

### Example

```text
Private cloud workload
→ NAT gateway
→ Public internet
```

The workload can reach external services without receiving a directly exposed public IPv4 address.

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Modify IP address in real time | NAT |
| Private IPv4 address ranges | RFC 1918 |
| Private IP translated to public IP | NAT |
| One private IP maps to one public IP | Standard NAT |
| Multiple devices share one public IP | NAT overload or PAT |
| Translate address and port | PAT |
| Port Address Translation | PAT |
| NAT overload | PAT |
| Internal mapping records | NAT table |
| Private cloud workload needs outbound internet access | NAT gateway |

---

## Memory Trick

```text
NAT = Translate IP address

PAT = Translate IP address + port
PAT = Many private devices share one public IP

RFC 1918 private ranges:
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

---

## Practice Questions

### 1. What does NAT stand for?

Answer:

```text
Network Address Translation
```

### 2. Why is NAT commonly used?

Answer: To allow private IPv4 devices to communicate externally while minimizing the number of public IPv4 addresses required.

### 3. Are RFC 1918 private addresses routable on the public internet?

Answer:

```text
No
```

### 4. What are the three RFC 1918 private ranges?

Answer:

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

### 5. What is PAT?

Answer:

```text
Port Address Translation
```

PAT translates both IP addresses and port numbers so multiple private devices can share one public IPv4 address.

### 6. What is another name for PAT?

Answer:

```text
NAT overload
```

### 7. What does a NAT table track?

Answer: Mappings between internal private addresses or sockets and translated public addresses or sockets.

### 8. What is the difference between standard NAT and PAT?

Answer: Standard NAT commonly performs one-to-one IP translation, while PAT allows many devices to share one public IP by using different port numbers.

### 9. Which technology is commonly used by home routers?

Answer:

```text
PAT
```

### 10. Why is PAT useful in cloud environments?

Answer: It allows private workloads to access external services without assigning a public IPv4 address to every workload.
