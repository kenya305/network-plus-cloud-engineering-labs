# Lab 16: Network Topology Selection

## Objective

Compare common network topologies and select the appropriate design for realistic enterprise, WAN, and data-center requirements.

## Scenario

A cloud engineer or network administrator may need to evaluate topology options when designing or troubleshooting network infrastructure.

The correct topology depends on:

- Number of devices
- Number of sites
- Redundancy requirements
- Available network paths
- Data-center architecture
- Cabling requirements
- Cost
- Scalability
- Performance

---

## Network Topology Comparison

| Topology | Description | Common Use |
| -------- | ----------- | ---------- |
| Star | Devices connect to one central network device | Switched Ethernet LAN |
| Hub-and-spoke | Locations connect through one central hub | Centralized WAN or LAN |
| Mesh | Devices or sites have multiple network paths | WAN redundancy |
| Hybrid | Multiple topology types are combined | Enterprise network |
| Spine-and-leaf | Leaf switches connect to spine switches | Data center |
| Top-of-rack | Leaf switch installed inside each rack | Data-center rack connectivity |
| Point-to-point | One location connects directly to one other location | WAN or campus link |

---

## Scenario Analysis

### Scenario 1: Office Ethernet Network

A company needs to connect employee workstations, printers, and servers to one central Ethernet switch.

**Recommended topology:**

```text
Star topology
```

**Reason:**

A star topology connects devices to one central network component.

---

### Scenario 2: Redundant WAN Connections

A company needs multiple network paths between remote offices.

If one link fails, traffic should use another available path.

**Recommended topology:**

```text
Mesh topology
```

**Reason:**

A mesh topology provides alternate network paths and supports redundancy.

---

### Scenario 3: Enterprise Network With Multiple Designs

A company uses:

- Star topology for office LAN connections
- Mesh topology for WAN redundancy
- Point-to-point connections between two buildings

**Recommended topology description:**

```text
Hybrid topology
```

**Reason:**

A hybrid topology combines multiple topology types.

---

### Scenario 4: Data-Center Network

A company needs a scalable data-center topology.

Each rack has a leaf switch.

Each leaf switch connects to every spine switch.

**Recommended topology:**

```text
Spine-and-leaf topology
```

**Reason:**

Spine-and-leaf architecture supports scalable data-center networking with predictable traffic paths and redundancy.

---

### Scenario 5: Top-of-Rack Switching

A data-center rack contains multiple servers.

The company wants the cabling to remain organized inside the rack.

**Recommended design:**

```text
Top-of-rack switching
```

**Reason:**

A leaf switch installed near the top of the rack allows local server connections to remain inside the same rack.

---

### Scenario 6: Building-to-Building Link

A company needs one dedicated network connection between two campus buildings.

**Recommended topology:**

```text
Point-to-point topology
```

**Reason:**

Point-to-point topology directly connects one location to one other location.

---

## Spine-and-Leaf Diagram

```text
        Spine 1 -------- Spine 2
          /  \            /  \
         /    \          /    \
      Leaf 1  Leaf 2  Leaf 3  Leaf 4
        |       |       |       |
      Rack 1  Rack 2  Rack 3  Rack 4
```

### Typical Inter-Rack Traffic Path

```text
Server in Rack 1
→ Leaf 1
→ Spine switch
→ Leaf 3
→ Server in Rack 3
```

---

## What I Observed

Different topologies are appropriate for different network requirements.

Star topology is common for switched Ethernet networks.

Mesh topology supports redundancy and alternate paths.

Hybrid topology combines multiple topology types inside one enterprise environment.

Spine-and-leaf topology supports scalable data-center architecture.

Top-of-rack switching keeps rack cabling organized.

Point-to-point topology directly connects two locations.

---

## Important Limitation

The correct network topology depends on:

- Business requirements
- Cost
- Number of sites
- Number of devices
- Cabling requirements
- Redundancy requirements
- Performance requirements
- Network complexity
- Troubleshooting requirements
- Scalability

A network engineer should evaluate the complete infrastructure before selecting a topology.

---

## Cloud Engineering Connection

Cloud engineers need to understand topology design when supporting:

- Data centers
- Virtual networks
- Hybrid cloud environments
- WAN connections
- Branch offices
- Disaster recovery
- High availability
- Redundant paths
- Network troubleshooting
- Cloud-to-on-premises connectivity

Understanding network topology helps engineers identify how devices are connected and how traffic should move across the infrastructure.

---

## Skills Practiced

- Comparing network topologies
- Identifying star topology use cases
- Identifying mesh topology use cases
- Identifying hybrid topology designs
- Understanding spine-and-leaf architecture
- Understanding top-of-rack switching
- Identifying point-to-point connections
- Applying topology-selection concepts to realistic scenarios
- Documenting networking concepts in GitHub
````
