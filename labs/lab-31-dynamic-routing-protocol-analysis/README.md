# Lab 31: Dynamic Routing Protocol Analysis

## Objective

Compare dynamic-routing protocols and document how routers automatically learn and update routes.

## Scenario

A company has three routers connecting multiple IPv4 subnets.

Router 1 is directly connected to three networks but needs to learn two remote networks automatically.

The company wants to avoid manual static-route configuration.

---

## Network Topology

### Router 1 Directly Connected Networks

```text
10.10.10.0/24
10.10.40.0/24
10.10.50.0/24
```

### Remote Networks

```text
10.10.20.0/24
10.10.30.0/24
```

---

## Part 1: Dynamic Route Updates

Router 2 sends a routing update to Router 1.

```text
Destination network: 10.10.20.0/24
Next hop:            10.10.40.2
```

Router 3 sends a routing update to Router 1.

```text
Destination network: 10.10.30.0/24
Next hop:            10.10.50.2
```

---

## Part 2: Updated Router 1 Routing Table

| Destination Network | Route Type | Next Hop |
| ------------------- | ---------- | -------- |
| `10.10.10.0/24` | Directly connected | Local interface |
| `10.10.40.0/24` | Directly connected | Local interface |
| `10.10.50.0/24` | Directly connected | Local interface |
| `10.10.20.0/24` | Dynamically learned | `10.10.40.2` |
| `10.10.30.0/24` | Dynamically learned | `10.10.50.2` |

---

## Part 3: Dynamic-Routing Workflow

```text
1. Router discovers nearby routing-protocol neighbors.
2. Router receives route updates.
3. Router evaluates possible paths.
4. Router updates routing table.
5. Router shares learned routes with nearby routers.
6. Router reacts to topology changes.
7. Network converges.
```

---

## Part 4: Protocol Comparison

| Protocol | Full Name | Scope | Main Characteristics | Best-Fit Scenario |
| -------- | --------- | ----- | -------------------- | ----------------- |
| EIGRP | Enhanced Interior Gateway Routing Protocol | Internal | Cisco-centric, efficient updates, fast convergence, loop prevention | Cisco-heavy enterprise network |
| OSPF | Open Shortest Path First | Internal | Open standard, multi-vendor, link-state, lowest-cost path | Multi-vendor enterprise network |
| BGP | Border Gateway Protocol | External | Internet-scale, inter-AS routing, policy-based routing | Internet connectivity or routing between organizations |

---

## Part 5: Routing-Metric Analysis

| Metric | Meaning |
| ------ | ------- |
| Hop count | Number of routers crossed |
| Cost | Relative path preference |
| Bandwidth | Available throughput |
| Delay | Time required to cross link |
| Link availability | Whether link is up or down |
| Policy | Administrative routing preference |

---

## Part 6: Convergence Scenario

### Scenario

Router 2 is removed from the network.

### Dynamic-Routing Response

```text
Router 2 becomes unavailable
→ Neighbor routers detect change
→ Routing update sent
→ Route to 10.10.20.0/24 removed or replaced
→ Routing tables update
→ Network converges
```

---

## Part 7: Cloud Scenario Analysis

### Scenario A: Hybrid Cloud VPN

A company connects its on-premises network to a cloud environment using a VPN.

**Recommended routing approach:**

```text
Dynamic route exchange using BGP
```

**Reason:**

BGP can exchange routes between separate administrative domains and automatically update routing information.

---

### Scenario B: Multi-Vendor Enterprise Network

A company uses routers from multiple vendors inside one enterprise WAN.

**Recommended routing protocol:**

```text
OSPF
```

**Reason:**

OSPF is an open standard supported by many vendors.

---

### Scenario C: Cisco-Centric Enterprise Network

A company primarily uses Cisco routers and wants fast convergence with efficient updates.

**Recommended routing protocol:**

```text
EIGRP
```

**Reason:**

EIGRP is commonly used in Cisco-centric environments and converges quickly.

---

## What I Observed

Dynamic routing allows routers to:

```text
Discover routes
Exchange updates
Select best paths
Remove unavailable routes
Adapt to network changes
Converge automatically
```

EIGRP, OSPF, and BGP support different routing scenarios.

```text
EIGRP = Cisco-centric internal routing
OSPF  = Open-standard internal routing
BGP   = External routing between autonomous systems
```

---

## Important Limitation

Dynamic routing adds complexity and overhead.

A network engineer should evaluate:

- CPU usage
- Memory usage
- Routing-update traffic
- Convergence behavior
- Protocol compatibility
- Vendor support
- Security
- Monitoring
- Network size
- Failure scenarios

---

## Cloud Engineering Connection

Cloud engineers use dynamic-routing concepts when supporting:

- Hybrid cloud connectivity
- Site-to-site VPNs
- Cloud routers
- Transit gateways
- BGP peering
- Direct-connect services
- ExpressRoute
- Multi-region routing
- Route propagation
- Network failover
- SD-WAN
- On-premises-to-cloud routing

---

## Skills Practiced

- Explaining dynamic routing
- Identifying routing updates
- Explaining convergence
- Comparing EIGRP, OSPF, and BGP
- Distinguishing internal and external routing protocols
- Applying dynamic routing to cloud-network scenarios
- Documenting routing analysis in GitHub
