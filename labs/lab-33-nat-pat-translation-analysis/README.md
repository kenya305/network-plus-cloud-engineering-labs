# Lab 33: NAT and PAT Translation Analysis

## Objective

Compare standard Network Address Translation with Port Address Translation and document how private IPv4 devices communicate with public internet services.

## Scenario

A company has internal devices using RFC 1918 private IPv4 addresses.

The devices need outbound internet access, but the company wants to minimize its use of public IPv4 addresses.

This lab analyzes standard NAT and PAT translation tables.

---

## Part 1: RFC 1918 Private Address Ranges

| Private IPv4 Range | CIDR Block | Common Use |
| ------------------ | ---------- | ---------- |
| `10.0.0.0` through `10.255.255.255` | `10.0.0.0/8` | Enterprise networks |
| `172.16.0.0` through `172.31.255.255` | `172.16.0.0/12` | Business and internal networks |
| `192.168.0.0` through `192.168.255.255` | `192.168.0.0/16` | Home and small-office networks |

---

## Part 2: Standard NAT Example

### Internal Client

```text
Private IPv4 address: 10.10.20.50
```

### Public Web Server

```text
Public IPv4 address: 104.20.19.63
```

### NAT Router Public Address

```text
Public translated IPv4 address: 94.1.1.1
```

### Outbound Translation

```text
Before NAT:
Source:      10.10.20.50
Destination: 104.20.19.63

After NAT:
Source:      94.1.1.1
Destination: 104.20.19.63
```

### Return Translation

```text
Before reverse NAT:
Source:      104.20.19.63
Destination: 94.1.1.1

After reverse NAT:
Source:      104.20.19.63
Destination: 10.10.20.50
```

### Standard NAT Mapping

| Internal Private Address | Public Translated Address |
| ------------------------ | ------------------------- |
| `10.10.20.50` | `94.1.1.1` |

---

## Part 3: PAT Example

PAT is also called:

```text
NAT overload
```

PAT translates both:

```text
IP address
+
Port number
```

### Client 1

```text
Private source socket: 10.10.20.50:3233
Public translated socket: 94.1.1.1:1055
Destination socket: 104.20.19.63:80
```

### Client 2

```text
Private source socket: 10.10.20.70:5782
Public translated socket: 94.1.1.1:1056
Destination socket: 104.20.19.63:80
```

### PAT Translation Table

| Internal Private Socket | Public Translated Socket | Destination Socket |
| ----------------------- | ------------------------ | ------------------ |
| `10.10.20.50:3233` | `94.1.1.1:1055` | `104.20.19.63:80` |
| `10.10.20.70:5782` | `94.1.1.1:1056` | `104.20.19.63:80` |

---

## Part 4: Translation Analysis

| Question | Answer |
| -------- | ------ |
| Are the internal `10.x.x.x` addresses public? | No |
| Can private IPv4 addresses route directly across the public internet? | No |
| What allows internal devices to reach public services? | NAT or PAT |
| What does standard NAT translate? | IP address |
| What does PAT translate? | IP address and port number |
| Can multiple internal devices share one public IPv4 address with PAT? | Yes |

---

## Part 5: Standard NAT vs. PAT

| Feature | Standard NAT | PAT / NAT Overload |
| ------- | ------------ | ------------------ |
| Translation model | One-to-one | Many-to-one |
| Changes IPv4 address | Yes | Yes |
| Changes source port | Not required | Yes |
| Conserves public IPv4 addresses | Somewhat | Very efficiently |
| Common home-router use | Less common | Very common |

---

## Part 6: Cloud Scenario Analysis

### Scenario

A private cloud subnet contains application servers.

The servers need to download software updates and reach public APIs.

The company does not want each server exposed directly to the internet.

### Recommended Design

```text
Private subnet
→ NAT gateway
→ Public internet
```

### Benefits

- Private workloads can initiate outbound connections
- Public IPv4 addresses are conserved
- Workloads do not require direct public exposure
- Egress traffic can be centralized
- Routing and security controls can be managed consistently

---

## What I Observed

Standard NAT commonly maps:

```text
One private IPv4 address
→ One public IPv4 address
```

PAT maps:

```text
Many private IPv4 addresses and ports
→ One shared public IPv4 address
→ Different translated port numbers
```

PAT is more efficient because many internal devices can share one public address.

---

## Important Limitation

NAT is not a complete security solution.

A cloud engineer should still evaluate:

- Firewall rules
- Security groups
- Network access controls
- Route tables
- Logging
- Monitoring
- Egress restrictions
- Public exposure
- Application requirements
- IPv6 migration strategy

---

## Cloud Engineering Connection

Cloud engineers use NAT and PAT concepts when supporting:

- Private subnets
- NAT gateways
- Internet gateways
- Outbound internet access
- Egress routing
- Container networks
- Kubernetes networking
- Firewalls
- Security architecture
- Hybrid cloud networks
- IPv4-address planning

---

## Skills Practiced

- Identifying RFC 1918 ranges
- Distinguishing private and public IPv4 addresses
- Explaining standard NAT
- Explaining PAT and NAT overload
- Interpreting NAT translation tables
- Explaining socket mappings
- Applying NAT-gateway concepts to cloud networking
- Documenting network-address translation in GitHub
