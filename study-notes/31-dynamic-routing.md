# Network+ N10-009 Study Notes: Dynamic Routing

## Video Topic

Dynamic Routing

## Summary

Dynamic routing allows routers to discover routes and update routing tables automatically.

Unlike static routing, dynamic routing protocols exchange information between routers so the network can adapt when routers, links, or subnets are added or removed.

This lesson covers:

- Dynamic routing
- Routing updates
- Neighbor discovery
- Multicast updates
- Convergence
- Routing metrics
- EIGRP
- OSPF
- BGP
- Autonomous systems
- Internal and external routing protocols
- Link-state routing
- Loop prevention
- Load balancing

---

## Static Routing vs. Dynamic Routing

| Feature | Static Routing | Dynamic Routing |
| ------- | -------------- | --------------- |
| Route creation | Manually configured | Automatically learned |
| Updates after topology change | Manual | Automatic |
| CPU and memory overhead | Low | Higher |
| Scalability | Better for small networks | Better for larger networks |
| Automatic rerouting | No | Yes |
| Common use | Stub networks and simple paths | Enterprise and multi-router environments |

```text
Static routing  = Administrator configures routes manually
Dynamic routing = Routers learn and update routes automatically
```

---

## Why Use Dynamic Routing?

Dynamic routing is useful when a network contains many routers.

```text
Three or four routers
→ Static routes may be manageable

Tens or hundreds of routers
→ Dynamic routing is more efficient
```

### Benefits

- Automatic route discovery
- Automatic route updates
- Faster response to topology changes
- Reduced manual configuration
- Better scalability
- Automatic removal of unavailable routes
- Automatic learning of new routes

---

## Dynamic-Routing Overhead

Dynamic routing requires router resources.

### Resources Used

- CPU
- Memory
- Bandwidth for routing updates
- Administrative planning
- Monitoring

```text
Dynamic routing improves automation but adds overhead.
```

---

## Dynamic-Routing Process

```text
1. Discover nearby routers.
2. Receive routing updates.
3. Build or update routing table.
4. Compare possible routes.
5. Select best route.
6. Share learned routes with nearby routers.
7. React to network changes.
```

---

## Neighbor Discovery

Routers listen for routing updates from nearby routers.

These updates may be sent:

- Directly from router to router
- Using multicast traffic
- Periodically
- When a topology change occurs

```text
Neighbor discovery = Routers identify other routers participating in the same routing protocol
```

---

## Routing Updates

Router 2 tells Router 1:

```text
Destination network: 10.10.20.0/24
Next hop:            10.10.40.2
```

Router 3 tells Router 1:

```text
Destination network: 10.10.30.0/24
Next hop:            10.10.50.2
```

Router 1 then adds those routes automatically.

---

## Convergence

Convergence is the process of routers updating their routing tables after a network change.

```text
Router removed
→ Routing update sent
→ Routers remove unavailable route
→ Network converges
```

```text
Convergence = Routers agree on updated routing information after a change
```

---

## Routing Metrics

Routing protocols use different criteria to decide the best route.

### Common Metrics

- Hop count
- Link state
- Link availability
- Bandwidth
- Throughput
- Delay
- Cost
- Administrative policy

```text
Routing metric = Value used to compare possible routes
```

---

## EIGRP

EIGRP stands for:

```text
Enhanced Interior Gateway Routing Protocol
```

### Characteristics

- Commonly associated with Cisco environments
- Relatively easy to configure
- Converges quickly
- Detects and helps prevent routing loops
- Uses efficient routing updates
- Discovers nearby EIGRP routers

```text
EIGRP = Fast-converging internal routing protocol often associated with Cisco environments
```

---

## OSPF

OSPF stands for:

```text
Open Shortest Path First
```

### Characteristics

- Multi-vendor support
- Link-state protocol
- Common inside an autonomous system
- Uses cost to select routes
- May consider bandwidth, availability, and delay
- Can support equal-cost load balancing

```text
OSPF = Open, standards-based, link-state internal routing protocol
```

---

## Autonomous System

An autonomous system is a network or group of networks under one administrative control.

```text
AS
```

```text
AS = Collection of networks managed by one organization or administrative domain
```

---

## BGP

BGP stands for:

```text
Border Gateway Protocol
```

### Characteristics

- External gateway protocol
- Used for internet routing
- Common on WAN and internet connections
- Designed for large-scale route exchange
- Connects organizations and autonomous systems

```text
BGP = Routing protocol used between autonomous systems and across the internet
```

---

## Internal vs. External Routing Protocols

| Protocol Type | Purpose | Examples |
| ------------- | ------- | -------- |
| Interior Gateway Protocol | Used inside an autonomous system | EIGRP, OSPF |
| Exterior Gateway Protocol | Used between autonomous systems | BGP |

---

## Protocol Comparison

| Feature | EIGRP | OSPF | BGP |
| ------- | ----- | ---- | --- |
| Full name | Enhanced Interior Gateway Routing Protocol | Open Shortest Path First | Border Gateway Protocol |
| Main scope | Internal routing | Internal routing | External routing |
| Vendor association | Commonly Cisco-centric | Multi-vendor standard | Internet and WAN standard |
| Decision method | Protocol-specific metrics | Link-state cost | Policy-based path selection |
| Common use | Cisco enterprise networks | Enterprise multi-vendor networks | Internet and inter-AS routing |

---

## Cloud Engineering Connection

Cloud engineers use dynamic-routing concepts when working with:

- Hybrid cloud connectivity
- Site-to-site VPNs
- Cloud routers
- Transit gateways
- Direct-connect services
- ExpressRoute
- Interconnect services
- Multi-region networks
- BGP peering
- On-premises-to-cloud routing
- SD-WAN
- Route propagation
- Network failover

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Routers learn routes automatically | Dynamic routing |
| Routers agree after topology change | Convergence |
| Cisco-centric internal routing | EIGRP |
| Open, standards-based link-state routing | OSPF |
| Lowest-cost path | OSPF |
| Network under one administrative control | Autonomous system |
| Internet routing between organizations | BGP |
| External gateway protocol | BGP |
| Internal gateway protocol | OSPF or EIGRP |

---

## Memory Trick

```text
Dynamic routing = Routers teach each other routes

EIGRP = Cisco-centric and fast
OSPF  = Open standard and lowest cost
BGP   = Between autonomous systems and internet

Convergence = Network agrees after a change
```

---

## Practice Questions

### 1. What is dynamic routing?

Answer: Automatic discovery and updating of routing information between routers.

### 2. What is one advantage of dynamic routing over static routing?

Answer: Routes update automatically when the network topology changes.

### 3. What resources does dynamic routing use?

Answer: CPU, memory, and bandwidth for routing updates.

### 4. What is convergence?

Answer: The process of routers updating and agreeing on routing information after a network change.

### 5. What does EIGRP stand for?

Answer: Enhanced Interior Gateway Routing Protocol

### 6. Which environment commonly uses EIGRP?

Answer: Cisco-centric environments.

### 7. What does OSPF stand for?

Answer: Open Shortest Path First

### 8. What type of protocol is OSPF?

Answer: A link-state interior gateway protocol.

### 9. What does BGP stand for?

Answer: Border Gateway Protocol

### 10. What is BGP commonly used for?

Answer: Routing between autonomous systems and across the internet.
