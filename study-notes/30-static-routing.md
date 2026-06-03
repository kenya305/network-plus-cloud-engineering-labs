# Network+ N10-009 Study Notes: Static Routing

## Video Topic

Static Routing

## Summary

Routers forward traffic between IP subnets.

A router examines the destination IP address inside a packet and checks its routing table to decide where the packet should go next.

If the destination network is directly connected, the router forwards the packet to that local network.

If the destination network is remote, the router uses a routing-table entry to select a next hop.

If no matching route exists, the router discards the packet.

This lesson covers:

- Routing tables
- Destination networks
- Directly connected routes
- Remote networks
- Next-hop IP addresses
- Static routes
- Stub networks
- Static-routing advantages
- Static-routing limitations
- Routing loops
- Manual route configuration

---

## Router Forwarding Process

A router performs a sequence of steps when it receives a packet.

```text
1. Read destination IP address.
2. Check routing table.
3. Determine whether destination network is directly connected.
4. If not directly connected, identify next hop.
5. Forward traffic through the correct interface.
6. If no route exists, discard the packet.
```

### Key Takeaway

```text
Router = Device that forwards packets between IP subnets
```

---

## Routing Table

A routing table contains information about networks the router knows how to reach.

### Routing-Table Information

| Routing Detail | Meaning |
| -------------- | ------- |
| Destination network | Network the router is trying to reach |
| Prefix length | Network size, such as `/24` |
| Next hop | Next router in the path |
| Interface | Local interface used to send the packet |
| Directly connected route | Network physically attached to the router |
| Static route | Manually configured route |

### Key Takeaway

```text
Routing table = Map used by router to forward packets
```

---

## Directly Connected Routes

A directly connected route is a network attached directly to one of the router's interfaces.

### Example Router 1 Networks

```text
10.10.10.0/24
10.10.40.0/24
10.10.50.0/24
```

These networks are directly connected to Router 1.

### Key Takeaway

```text
Directly connected route = Local network attached to router
```

---

## Remote Networks

A remote network is not directly attached to the router.

The router must use a next-hop router to reach it.

### Example Remote Networks for Router 1

```text
10.10.20.0/24
10.10.30.0/24
```

Router 1 needs additional routing-table entries to reach these networks.

---

## Next Hop

The next hop is the IP address of the next router along the path.

### Example

```text
Destination network: 10.10.20.0/24
Next hop:            10.10.40.2
```

This means:

```text
Traffic for 10.10.20.0/24
→ Send to router at 10.10.40.2
```

### Key Takeaway

```text
Next hop = Next router that receives the packet
```

---

## Missing Route Behavior

If the router does not know how to reach a destination network, it discards the packet.

### Example

```text
Destination: 10.10.20.2
Routing table: No route for 10.10.20.0/24
Result: Packet discarded
```

### Key Takeaway

```text
No matching route
→ Packet discarded
```

---

## Static Routing

Static routing is the manual creation of routing-table entries.

An administrator configures each route directly on the router.

### Example Static Route Logic

```text
If destination is 10.10.20.0/24
→ Send traffic to next hop 10.10.40.2
```

```text
If destination is 10.10.30.0/24
→ Send traffic to next hop 10.10.50.2
```

### Key Takeaway

```text
Static route = Manually configured path to a network
```

---

## Example Static Route Table for Router 1

| Destination Network | Route Type | Next Hop |
| ------------------- | ---------- | -------- |
| `10.10.10.0/24` | Directly connected | Local interface |
| `10.10.40.0/24` | Directly connected | Local interface |
| `10.10.50.0/24` | Directly connected | Local interface |
| `10.10.20.0/24` | Static route | `10.10.40.2` |
| `10.10.30.0/24` | Static route | `10.10.50.2` |

---

## Stub Network

A stub network has a limited number of paths, commonly one primary path in or out.

### Example

```text
Remote office
→ One WAN link
→ Central network
```

Static routing is often appropriate for stub networks because the route rarely changes.

### Key Takeaway

```text
Stub network = Network with limited routing paths
```

---

## Advantages of Static Routing

| Advantage | Explanation |
| --------- | ----------- |
| Simple for small networks | Easy to configure when only a few routes exist |
| Low overhead | No dynamic-routing protocol processing |
| Predictable | Routes do not change automatically |
| Secure | No routing updates are exchanged automatically |
| Useful for stub networks | Works well when only one path exists |

### Key Takeaway

```text
Static routing = Simple, predictable, and low overhead
```

---

## Limitations of Static Routing

| Limitation | Explanation |
| ---------- | ----------- |
| Manual configuration | Every route must be entered by an administrator |
| Poor scalability | Difficult to manage across hundreds or thousands of routers |
| No automatic rerouting | Routes do not automatically adapt to failures |
| Human error risk | Incorrect routes can cause outages or routing loops |
| Ongoing maintenance | Changes must be applied manually |

### Key Takeaway

```text
Static routing does not automatically adapt to network changes.
```

---

## Routing Loop

A routing loop occurs when routers repeatedly forward traffic between each other without reaching the destination.

### Example

```text
Router A sends packet to Router B
→ Router B sends packet back to Router A
→ Process repeats
```

### Common Cause

```text
Incorrect static route configuration
```

### Key Takeaway

```text
Routing loop = Packet forwarded repeatedly between routers
```

---

## Static vs. Dynamic Routing

| Feature | Static Routing | Dynamic Routing |
| ------- | -------------- | --------------- |
| Configuration | Manual | Learned and updated automatically |
| CPU and memory usage | Low | Higher |
| Scaling | Better for small networks | Better for larger networks |
| Automatic rerouting | No | Yes, depending on protocol |
| Common use | Stub networks, simple routes | Enterprise networks with changing paths |

---

## Cloud Engineering Connection

Cloud engineers use static-routing concepts when working with:

- Cloud route tables
- Virtual private clouds
- Virtual networks
- Subnets
- VPN gateways
- Transit gateways
- NAT gateways
- Hybrid cloud connectivity
- Private endpoints
- Peering connections
- On-premises-to-cloud routing
- Firewall appliances
- Network troubleshooting

### Example

```text
Private subnet needs access to another network
→ Add route-table entry
→ Point route to correct next hop
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Device forwarding packets between subnets | Router |
| Table used to select route | Routing table |
| Network physically attached to router | Directly connected route |
| Next router in packet path | Next hop |
| Manually configured route | Static route |
| No matching route | Packet discarded |
| Remote office with one WAN path | Stub network |
| No dynamic-routing overhead | Static route |
| Packet repeatedly forwarded between routers | Routing loop |
| Route does not change automatically | Static routing |

---

## Memory Trick

```text
Destination
→ Check routing table
→ Directly connected?
→ If no, use next hop
→ If no route, discard packet
```

---

## Practice Questions

### 1. What does a router examine first when forwarding a packet?

Answer: The destination IP address.

### 2. What is a routing table?

Answer: A table containing known networks and forwarding information.

### 3. What is a directly connected route?

Answer: A network attached directly to one of the router's interfaces.

### 4. What is a next hop?

Answer: The IP address of the next router along the packet path.

### 5. What happens if no matching route exists?

Answer: The router discards the packet.

### 6. What is static routing?

Answer: Manual configuration of routing-table entries.

### 7. Why are static routes useful for stub networks?

Answer: Stub networks commonly have only one path, so routes rarely change.

### 8. What is one major limitation of static routing?

Answer: It does not automatically adapt to network changes or failures.

### 9. What can happen if static routes are configured incorrectly?

Answer: Connectivity failures or routing loops.

### 10. What next hop should Router 1 use for `10.10.20.0/24`?

Answer:

```text
10.10.40.2
```

### 11. What next hop should Router 1 use for `10.10.30.0/24`?

Answer:

```text
10.10.50.2
```
