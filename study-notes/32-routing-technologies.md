# Network+ N10-009 Study Notes: Routing Technologies

## Video Topic

Routing Technologies

## Summary

Routing tables contain detailed information that routers use to forward traffic.

A router evaluates the destination IP address, compares it against routing-table entries, and chooses the best route.

When multiple routes match, the router evaluates:

- Longest prefix match
- Administrative distance
- Routing metric

This lesson also introduces:

- Routing-table codes
- Route age
- Next hop
- Outgoing interface
- First Hop Redundancy Protocol
- Virtual IP addresses
- Router failover
- Subinterfaces
- Router-on-a-stick
- VLAN trunking

---

## Routing Table Purpose

A routing table helps a device determine where traffic should go.

Routing tables are used by:

- Routers
- Workstations
- Servers
- Firewalls
- Cloud gateways

### Key Takeaway

```text
Routing table = Map used to forward packets
```

---

## Routing Table Entry Example

A routing-table entry may look like:

```text
R 10.10.30.0/24 [120/1] via 10.10.50.2, 00:00:14, Serial0/3/1
```

### Breakdown

| Field | Meaning |
| ----- | ------- |
| `R` | Route code for RIP |
| `10.10.30.0/24` | Destination subnet and prefix length |
| `120` | Administrative distance |
| `1` | Routing metric |
| `10.10.50.2` | Next-hop IP address |
| `00:00:14` | Route age |
| `Serial0/3/1` | Outgoing interface |

---

## Route Codes

Routing-table codes identify how a route was learned.

| Route Code | Meaning |
| ---------- | ------- |
| `C` | Directly connected |
| `S` | Static route |
| `R` | RIP |
| `D` | EIGRP |
| `O` | OSPF |
| `B` | BGP |

### Key Takeaway

```text
Route code = Source of routing information
```

---

## Longest Prefix Match

If multiple routes match a destination IP address, the router chooses the route with the longest prefix length.

### Example Destination

```text
192.168.1.6
```

### Matching Routes

| Route | Match Quality |
| ----- | ------------- |
| `192.168.0.0/16` | Broad match |
| `192.168.1.0/24` | More specific |
| `192.168.1.6/32` | Most specific |

### Best Route

```text
192.168.1.6/32
```

### Key Takeaway

```text
Longest prefix match = Most specific route wins
```

---

## Administrative Distance

Administrative distance helps a router choose between routes learned from different sources.

Lower administrative distance is preferred.

| Route Source | Administrative Distance |
| ------------ | ----------------------- |
| Directly connected | `0` |
| Static route | `1` |
| EIGRP | `90` |
| OSPF | `110` |
| RIP | `120` |

### Example

```text
Static route AD: 1
OSPF route AD:   110

Preferred route:
Static route
```

### Key Takeaway

```text
Lower administrative distance = More trusted route source
```

---

## Routing Metric

A routing metric is used by a routing protocol to compare multiple routes learned by that same protocol.

### Important Rule

```text
Administrative distance compares different route sources.

Routing metric compares routes within the same routing protocol.
```

### Examples

| Protocol | Example Metric |
| -------- | -------------- |
| RIP | Hop count |
| OSPF | Cost |
| EIGRP | Composite metric |
| BGP | Policy-based attributes |

### Key Takeaway

```text
Routing metrics are protocol-specific.
```

---

## RIP Metric Example

RIP uses:

```text
Hop count
```

### Example

```text
R 10.10.30.0/24 [120/1] via 10.10.50.2
```

This means:

```text
Administrative distance: 120
Metric:                  1 hop
```

---

## EIGRP Metric Example

EIGRP uses a different metric calculation than RIP.

### Example

```text
D 10.10.30.0/24 [90/metric-value] via 10.10.50.2
```

The administrative distance is:

```text
90
```

The routing metric is calculated differently than RIP.

### Key Takeaway

```text
Do not compare RIP and EIGRP metrics directly.
```

---

## Route-Selection Workflow

```text
1. Match destination IP address.
2. Select longest prefix match.
3. If route sources differ, compare administrative distance.
4. If same routing protocol has multiple routes, compare metric.
5. Forward traffic to next hop using outgoing interface.
```

---

## FHRP

FHRP stands for:

```text
First Hop Redundancy Protocol
```

FHRP provides default-gateway redundancy.

### Problem

A workstation usually has one default gateway.

If that router fails, connectivity may be lost.

### Solution

Use a virtual IP address shared by redundant routers.

---

## Virtual IP Address

A virtual IP address is commonly abbreviated as:

```text
VIP
```

The VIP acts as the default gateway for end-user devices.

### Example

```text
Client default gateway
→ VIP
→ Active router
```

If the active router fails:

```text
Standby router detects failure
→ Standby becomes active
→ Standby takes ownership of VIP
→ Client keeps using same default gateway
```

### Key Takeaway

```text
FHRP + VIP = Default-gateway redundancy
```

---

## Active and Standby Routers

| Router Role | Purpose |
| ----------- | ------- |
| Active router | Currently handles traffic |
| Standby router | Waits to take over if active router fails |

### Failover Flow

```text
Active router fails
→ Standby router detects failure
→ Standby router takes control of VIP
→ Traffic continues through standby router
```

---

## Subinterfaces

A subinterface is a logical interface created under one physical router interface.

### Example Physical Interface

```text
GigabitEthernet0/0
```

### Example Subinterfaces

```text
GigabitEthernet0/0.10
GigabitEthernet0/0.20
GigabitEthernet0/0.100
```

Each subinterface can use:

- Separate VLAN
- Separate IP address
- Separate subnet mask
- Separate routing configuration

### Key Takeaway

```text
Subinterface = Virtual interface under one physical interface
```

---

## Router-on-a-Stick

Router-on-a-stick uses one physical router interface with multiple subinterfaces to route between VLANs.

### Example

```text
Switch
→ Trunk link
→ Router physical interface
→ Multiple router subinterfaces
```

### VLAN Example

| VLAN | Router Subinterface |
| ---- | ------------------- |
| VLAN 10 | `g0/0.10` |
| VLAN 20 | `g0/0.20` |
| VLAN 100 | `g0/0.100` |

### Key Takeaway

```text
Router-on-a-stick = One router interface, multiple VLAN subinterfaces
```

---

## Cloud Engineering Connection

Cloud engineers apply routing-technology concepts when working with:

- Virtual route tables
- Cloud routers
- Transit gateways
- VPN gateways
- Virtual IP failover
- Load balancers
- High-availability architectures
- Virtual interfaces
- VLAN-aware appliances
- Firewall appliances
- Hybrid-cloud routing
- Network troubleshooting

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Most specific route | Longest prefix match |
| Lower route-source preference value | Administrative distance |
| Compare routes within same protocol | Routing metric |
| Directly connected route code | `C` |
| RIP route code | `R` |
| EIGRP route code | `D` |
| OSPF route code | `O` |
| BGP route code | `B` |
| Default-gateway redundancy | FHRP |
| Shared default-gateway address | VIP |
| Logical interface under physical interface | Subinterface |
| One physical router link serving multiple VLANs | Router-on-a-stick |

---

## Memory Trick

```text
Longest prefix = Most specific route wins
Lower AD       = More trusted route source
Metric         = Tie-breaker inside same protocol

FHRP + VIP     = Default-gateway redundancy

Subinterface   = Virtual interface on physical port
```

---

## Practice Questions

### 1. What is the purpose of a routing table?

Answer: To help a device determine where packets should be forwarded.

### 2. Which route wins when multiple prefixes match?

Answer: The route with the longest prefix length.

### 3. Which is more specific: `/16`, `/24`, or `/32`?

Answer:

```text
/32
```

### 4. What does administrative distance compare?

Answer: The trustworthiness of routes learned from different route sources.

### 5. Which is preferred: administrative distance `1` or `110`?

Answer:

```text
1
```

### 6. What does a routing metric compare?

Answer: Routes learned by the same routing protocol.

### 7. What does FHRP stand for?

Answer:

```text
First Hop Redundancy Protocol
```

### 8. What is a VIP?

Answer: A virtual IP address used as a shared default gateway.

### 9. What is a subinterface?

Answer: A logical interface created under one physical router interface.

### 10. What is router-on-a-stick?

Answer: A design that uses one router interface with multiple subinterfaces to route between VLANs.
