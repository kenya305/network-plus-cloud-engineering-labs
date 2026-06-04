# Lab 32: Routing Table Selection, FHRP, and Subinterfaces

## Objective

Analyze routing-table decisions, compare administrative distance and routing metrics, and document FHRP and subinterface use cases.

## Scenario

A company is troubleshooting routing behavior and designing redundant default-gateway connectivity.

The network team must:

- Select the best route
- Compare route sources
- Explain routing metrics
- Design gateway failover
- Support multiple VLANs over one router interface

---

## Part 1: Routing Table Entry Breakdown

### Example Entry

```text
R 10.10.30.0/24 [120/1] via 10.10.50.2, 00:00:14, Serial0/3/1
```

### Analysis

| Field | Value | Meaning |
| ----- | ----- | ------- |
| Route code | `R` | Route learned through RIP |
| Destination subnet | `10.10.30.0/24` | Target network |
| Administrative distance | `120` | Trust level of RIP source |
| Routing metric | `1` | RIP hop count |
| Next hop | `10.10.50.2` | Next router |
| Route age | `00:00:14` | Route active for 14 seconds |
| Outgoing interface | `Serial0/3/1` | Interface used to send traffic |

---

## Part 2: Longest Prefix Match

### Destination

```text
192.168.1.6
```

### Matching Routes

| Route | Match? | Specificity |
| ----- | ------ | ----------- |
| `192.168.0.0/16` | Yes | Broad |
| `192.168.1.0/24` | Yes | More specific |
| `192.168.1.6/32` | Yes | Most specific |

### Selected Route

```text
192.168.1.6/32
```

### Reason

```text
The longest prefix match is the most specific route.
```

---

## Part 3: Administrative Distance Comparison

| Route Source | Administrative Distance | Preference |
| ------------ | ----------------------- | ---------- |
| Directly connected | `0` | Highest |
| Static route | `1` | Very high |
| EIGRP | `90` | Higher than OSPF |
| OSPF | `110` | Higher than RIP |
| RIP | `120` | Lower than OSPF |

### Scenario

The router learns the same destination from:

```text
Static route: AD 1
OSPF route:   AD 110
```

### Selected Route

```text
Static route
```

### Reason

```text
Lower administrative distance is preferred.
```

---

## Part 4: Routing Metric Comparison

### Scenario

OSPF learns two routes to the same destination.

| Path | OSPF Cost |
| ---- | --------- |
| Path A | `10` |
| Path B | `20` |

### Selected Route

```text
Path A
```

### Reason

```text
Lower routing metric is preferred within the same protocol.
```

---

## Part 5: FHRP Design

### Problem

A workstation has one default gateway.

If the router fails, the workstation loses external connectivity.

### FHRP Solution

```text
Client devices
→ Use VIP as default gateway
→ Active router owns VIP
→ Standby router monitors active router
→ Standby router takes VIP if active router fails
```

### Roles

| Component | Purpose |
| --------- | ------- |
| VIP | Shared virtual default-gateway address |
| Active router | Handles normal traffic |
| Standby router | Takes over during failure |
| FHRP | Coordinates failover |

---

## Part 6: Subinterface Design

### Physical Interface

```text
GigabitEthernet0/0
```

### Logical Subinterfaces

| VLAN | Subinterface | Purpose |
| ---- | ------------ | ------- |
| VLAN 10 | `g0/0.10` | Routes VLAN 10 traffic |
| VLAN 20 | `g0/0.20` | Routes VLAN 20 traffic |
| VLAN 100 | `g0/0.100` | Routes VLAN 100 traffic |

### Traffic Flow

```text
Switch
→ Trunk link
→ Router physical interface
→ Matching VLAN subinterface
→ Routed destination
```

---

## Part 7: Router-on-a-Stick

### Definition

```text
Router-on-a-stick
= One physical router interface
+ Multiple subinterfaces
+ VLAN trunk
```

### Use Case

A small environment needs inter-VLAN routing without dedicating one physical router port to every VLAN.

---

## What I Observed

Routing tables contain more than destination networks.

They may include:

```text
Route code
Prefix length
Administrative distance
Routing metric
Next hop
Route age
Outgoing interface
```

Route selection follows this workflow:

```text
1. Longest prefix match
2. Administrative distance
3. Routing metric
```

FHRP provides default-gateway redundancy.

Subinterfaces allow multiple VLANs to use one physical router interface.

---

## Important Limitation

Routing behavior may vary by:

- Router vendor
- Routing protocol
- Platform defaults
- Administrative configuration
- Network topology
- High-availability design

A network engineer should verify platform-specific documentation before applying changes.

---

## Cloud Engineering Connection

Cloud engineers use these concepts when supporting:

- Cloud route tables
- Transit gateways
- VPN gateways
- Virtual IP failover
- High availability
- Virtual interfaces
- Firewall appliances
- VLAN-aware workloads
- Hybrid cloud routing
- Network troubleshooting

---

## Skills Practiced

- Reading a routing-table entry
- Applying longest prefix match
- Comparing administrative distance
- Comparing routing metrics
- Explaining FHRP
- Explaining VIP failover
- Explaining subinterfaces
- Explaining router-on-a-stick
- Connecting routing technologies to cloud engineering
