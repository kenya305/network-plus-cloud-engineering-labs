````markdown
# Network+ N10-009 Study Notes: Network Topologies

## Video Topic

Network Topologies

## Summary

A network topology describes how devices, locations, and network components are connected.

Understanding network topologies is useful when:

- Designing a network
- Planning infrastructure
- Troubleshooting connectivity
- Identifying redundant paths
- Evaluating network performance
- Documenting enterprise architecture

This lesson covers:

- Star topology
- Hub-and-spoke topology
- Mesh topology
- Hybrid topology
- Spine-and-leaf topology
- Top-of-rack switching
- Point-to-point topology

---

## Topology Overview

Networks can connect devices and locations in different ways.

The correct topology depends on:

- Number of devices
- Network size
- Cost
- Redundancy requirements
- Performance requirements
- Available cabling
- Data-center design
- Wide-area network requirements
- Troubleshooting needs

### Key Takeaway

```text
Topology = How network devices and locations are connected
```

---

## Star Topology

A star topology uses one central network device.

All other devices connect to that central device.

A star topology may also be called:

```text
Hub-and-spoke topology
```

### Star Topology Diagram

```text
           Workstation
               |
Printer ---- Switch ---- Server
               |
             Laptop
```

The switch is the central device.

The connected devices are the spokes.

### Common Example

A switched Ethernet network commonly uses a star topology.

```text
Workstations
→ Connect to Ethernet switch
→ Communicate through central switch
```

### Advantages

- Simple to design
- Easy to understand
- Common in Ethernet networks
- Easier to troubleshoot individual device connections
- Centralized connectivity

### Limitation

The central network device is important to the entire topology.

If the central switch fails, connected devices may lose communication.

### Key Takeaway

```text
Star topology = All devices connect to one central device
```

### Exam Tip

If the question mentions devices connecting to one central switch, think:

```text
Star topology
```

---

## Hub-and-Spoke Topology

Hub-and-spoke is another name commonly used for a star-style design.

The hub is the central connection point.

The spokes are the connected devices or locations.

### Diagram

```text
           Branch Office A
                 |
Branch B ---- Main Office ---- Branch C
                 |
           Branch Office D
```

### Common Use

Hub-and-spoke may be used for:

- Switched Ethernet networks
- Branch-office connections
- WAN designs
- Centralized network access

### Key Takeaway

```text
Hub-and-spoke = Central hub with connected spokes
```

---

## Mesh Topology

A mesh topology provides more than one possible network path between devices or locations.

If one path fails, traffic may use an alternate path.

### Mesh Topology Diagram

```text
Site A -------- Site B
  | \            / |
  |  \          /  |
  |   \        /   |
  |    \      /    |
Site C -------- Site D
```

### Key Characteristics

- Multiple network paths
- Redundancy
- Fault tolerance
- Possible load balancing
- Common in WAN environments

### Redundancy Example

```text
Primary link fails
→ Traffic uses alternate link
→ Connectivity continues
```

### Load-Balancing Example

```text
Traffic divided across multiple links
→ Network resources used more efficiently
```

### Advantages

- Improved availability
- Alternate paths during failures
- Supports redundancy
- May support load balancing

### Limitations

- Increased cost
- More complex design
- More cabling or WAN links
- More complex troubleshooting

### Key Takeaway

```text
Mesh topology = Multiple possible network paths
```

### Exam Tip

If the question mentions redundant links or alternate paths after a failure, think:

```text
Mesh topology
```

---

## Full Mesh vs. Partial Mesh

### Full Mesh

In a full-mesh topology, every device or site connects directly to every other device or site.

```text
Every location
→ Direct connection
→ Every other location
```

### Partial Mesh

In a partial-mesh topology, only some devices or sites have multiple connections.

```text
Selected locations
→ Multiple redundant paths
```

### Comparison

| Mesh Type | Description |
| --------- | ----------- |
| Full mesh | Every site connects directly to every other site |
| Partial mesh | Some sites have multiple connections, but not every site connects directly to every other site |

---

## Hybrid Topology

A hybrid topology combines multiple topology types inside one network.

An enterprise network may use different designs in different areas.

### Example

```text
Office LAN
→ Star topology

WAN links
→ Mesh topology

Building-to-building link
→ Point-to-point topology

Combined enterprise design
→ Hybrid topology
```

### Key Characteristics

- Uses multiple topology types
- Common in enterprise environments
- Flexible design
- Supports different business requirements

### Key Takeaway

```text
Hybrid topology = Combination of multiple topology types
```

### Exam Tip

If the question mentions multiple topology styles operating together, think:

```text
Hybrid topology
```

---

## Spine-and-Leaf Topology

Spine-and-leaf is a data-center network architecture.

It uses:

- Spine switches
- Leaf switches
- Connected servers or devices

### Spine-and-Leaf Diagram

```text
        Spine 1 -------- Spine 2
          /  \            /  \
         /    \          /    \
      Leaf 1  Leaf 2  Leaf 3  Leaf 4
        |       |       |       |
      Rack 1  Rack 2  Rack 3  Rack 4
```

### Connection Rules

Each leaf switch commonly connects to each spine switch.

```text
Leaf switch
→ Connects to every spine switch
```

Leaf switches do not commonly connect directly to other leaf switches.

```text
Leaf switch
✖ Does not directly connect to another leaf switch
```

Spine switches do not commonly connect directly to other spine switches.

```text
Spine switch
✖ Does not directly connect to another spine switch
```

### Typical Inter-Rack Traffic Path

When devices are in different racks, traffic commonly follows:

```text
Device
→ Leaf switch
→ Spine switch
→ Destination leaf switch
→ Destination device
```

### Advantages

- Predictable traffic paths
- Redundancy
- High performance
- Scalable design
- Common in data centers
- Efficient east-west traffic flow

### Key Takeaway

```text
Spine-and-leaf = Data-center design with leaf switches connected to spine switches
```

### Exam Tip

If the question mentions a scalable data-center design where every leaf connects to every spine, think:

```text
Spine-and-leaf topology
```

---

## Top-of-Rack Switching

Top-of-rack switching is commonly used with spine-and-leaf data-center designs.

A leaf switch is installed near the top of a physical server rack.

Devices inside the rack connect to the top-of-rack switch.

### Diagram

```text
Server Rack
├── Top-of-rack leaf switch
├── Server 1
├── Server 2
├── Server 3
└── Server 4
```

### Benefits

- Simplifies cabling
- Keeps many cables inside the same rack
- Supports data-center organization
- Connects racks to multiple spine switches
- Supports redundancy

### Limitation

A separate leaf switch may be needed for each rack.

As the number of racks increases, the cost also increases.

### Key Takeaway

```text
Top-of-rack switching = Leaf switch installed inside each server rack
```

---

## Point-to-Point Topology

A point-to-point topology connects one location or device directly to one other location or device.

### Diagram

```text
Building A
↔
Building B
```

### Common Examples

- Building-to-building connection
- Older WAN connection
- T1 link
- T3 link
- Dedicated connection between two sites

### Advantages

- Simple design
- Direct connection
- Easy to understand
- Useful for dedicated links

### Limitation

A single point-to-point link may not provide redundancy.

If the link fails, communication may stop unless a backup path exists.

### Key Takeaway

```text
Point-to-point = One location directly connected to one other location
```

### Exam Tip

If the question mentions a direct connection between two sites, think:

```text
Point-to-point topology
```

---

## Topology Comparison Table

| Topology | Description | Common Use | Main Benefit |
| -------- | ----------- | ---------- | ------------ |
| Star | Devices connect to one central device | Switched Ethernet LAN | Simple centralized design |
| Hub-and-spoke | Locations connect through one central hub | Branch-office WAN or LAN | Centralized connectivity |
| Mesh | Multiple paths connect devices or locations | WAN redundancy | Alternate paths and fault tolerance |
| Hybrid | Multiple topology types combined | Enterprise network | Flexible design |
| Spine-and-leaf | Leaf switches connect to spine switches | Data center | Scalable high-performance design |
| Top-of-rack | Leaf switch installed inside rack | Data-center rack | Simplified cabling |
| Point-to-point | One site connects directly to one other site | WAN or campus link | Direct dedicated connection |

---

## Cloud Engineering Connection

Cloud engineers need to understand network topologies when supporting:

- Data centers
- Hybrid cloud environments
- Virtual networks
- Branch offices
- WAN connections
- Redundant network paths
- Load balancers
- Disaster-recovery architecture
- High-availability applications
- On-premises infrastructure
- Cloud-to-cloud connectivity
- Network troubleshooting

### Example Scenarios

```text
Office devices connect to one switch
→ Star topology

Remote site has multiple WAN paths
→ Mesh topology

Enterprise uses star, mesh, and point-to-point designs
→ Hybrid topology

Data-center racks connect through leaf and spine switches
→ Spine-and-leaf topology

Two buildings have one dedicated connection
→ Point-to-point topology
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| All devices connect to one switch | Star topology |
| Central hub with connected spokes | Hub-and-spoke topology |
| Multiple paths between sites | Mesh topology |
| Redundant WAN links | Mesh topology |
| Load balancing across links | Mesh topology |
| Multiple topology types combined | Hybrid topology |
| Data-center architecture | Spine-and-leaf topology |
| Every leaf connects to every spine | Spine-and-leaf topology |
| Leaf switches do not directly connect to other leaf switches | Spine-and-leaf topology |
| Spine switches do not directly connect to other spine switches | Spine-and-leaf topology |
| Switch installed at top of each server rack | Top-of-rack switching |
| Direct connection between two sites | Point-to-point topology |
| T1 or T3 direct connection | Point-to-point topology |

---

## Memory Trick

```text
Star            = One central switch
Hub-and-spoke   = One central hub
Mesh            = Multiple paths
Hybrid          = Multiple topology types
Spine-and-leaf  = Data-center fabric
Top-of-rack     = Switch inside server rack
Point-to-point  = Direct connection between two locations
```

---

## Practice Questions

### 1. Which topology connects devices to one central network device?

Answer: Star topology

### 2. What is another name for a star topology?

Answer: Hub-and-spoke topology

### 3. Which topology provides multiple paths between devices or locations?

Answer: Mesh topology

### 4. Why might a company use a mesh topology?

Answer: To provide redundancy, alternate paths, fault tolerance, or load balancing.

### 5. What is a hybrid topology?

Answer: A combination of multiple topology types.

### 6. Which topology is commonly used inside data centers?

Answer: Spine-and-leaf topology

### 7. In a spine-and-leaf topology, what does each leaf switch commonly connect to?

Answer: Every spine switch

### 8. Do leaf switches commonly connect directly to each other in a spine-and-leaf topology?

Answer: No

### 9. Do spine switches commonly connect directly to each other in a spine-and-leaf topology?

Answer: No

### 10. What is top-of-rack switching?

Answer: A design where a leaf switch is installed near the top of each physical server rack.

### 11. What is a point-to-point topology?

Answer: A direct connection between one device or location and one other device or location.

### 12. What are examples of older point-to-point WAN connections?

Answer: T1 and T3 connections

### 13. Which topology is appropriate when traffic needs an alternate path if one link fails?

Answer: Mesh topology

### 14. Which topology might be created by combining star, mesh, and point-to-point designs?

Answer: Hybrid topology
````
