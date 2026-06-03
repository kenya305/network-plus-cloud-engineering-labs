# Network+ N10-009 Study Notes: Virtual Extensible LAN (VXLAN)

## Video Topic

Virtual Extensible LAN

## Summary

Virtual Extensible LAN, or VXLAN, is designed for large-scale data centers, service providers, and cloud environments.

VXLAN allows Layer 2 network segments to extend across a Layer 3 IP network.

This makes it possible for workloads in different data centers to communicate as though they are connected to the same logical network.

VXLAN helps solve several scaling and mobility challenges:

- Applications may move between data centers
- Cloud workloads may run in different locations
- Data centers may use different IP-addressing schemes
- Underlying transport networks may use different connectivity types
- Traditional VLANs do not scale far enough for very large environments

---

## Data Center Interconnection

Data Center Interconnection is commonly abbreviated as:

```text
DCI
```

DCI allows separate data centers to connect and exchange traffic.

### Why DCI Matters

Organizations may distribute:

- Applications
- Servers
- Virtual machines
- Databases
- Cloud resources
- Customer workloads

across multiple data centers.

### Key Takeaway

```text
DCI = Connectivity between separate data centers
```

---

## Traditional VLANs

VLAN stands for:

```text
Virtual Local Area Network
```

A VLAN creates logical Layer 2 segmentation across switches.

### VLAN Characteristics

| Feature | VLAN |
| ------- | ---- |
| OSI layer | Layer 2 |
| Main purpose | Logical segmentation |
| Identifier size | 12 bits |
| Approximate maximum VLAN count | Around `4,000` |
| Routed across Layer 3 networks directly | No |

### Key Limitation

Traditional VLANs are useful, but they do not scale well enough for very large multi-data-center or cloud environments.

---

## VXLAN

VXLAN stands for:

```text
Virtual Extensible LAN
```

VXLAN extends Layer 2 network segments across a Layer 3 IP network.

### Key Characteristics

| Feature | VXLAN |
| ------- | ----- |
| Main purpose | Extend Layer 2 networks over Layer 3 transport |
| Transport network | IP network |
| Maximum logical networks | Approximately `16 million` |
| Identifier | VNI |
| Encapsulation | Original Ethernet frame encapsulated inside VXLAN over UDP/IP |
| Common use | Data centers, cloud environments, service providers |

### Key Takeaway

```text
VXLAN = Layer 2 overlay carried across a Layer 3 network
```

---

## VLAN vs. VXLAN

| Feature | VLAN | VXLAN |
| ------- | ---- | ----- |
| Full name | Virtual Local Area Network | Virtual Extensible LAN |
| Scope | Layer 2 network segmentation | Layer 2 overlay across Layer 3 network |
| Scale | Around `4,000` networks | Approximately `16 million` networks |
| Identifier | VLAN ID | VNI |
| Multi-data-center support | Limited | Designed for large-scale environments |
| Routed transport | Not directly | Uses Layer 3 IP transport |

### Key Takeaway

```text
VLAN  = Smaller Layer 2 segmentation model
VXLAN = Larger overlay model for modern data centers
```

---

## VNI: VXLAN Network Identifier

VNI stands for:

```text
VXLAN Network Identifier
```

A VNI identifies a VXLAN logical network.

VXLAN uses a:

```text
24-bit VNI
```

This supports:

```text
2^24 = 16,777,216
```

possible VXLAN network identifiers.

### Example VNIs

```text
VNI 2000
VNI 3000
VNI 4000
```

### Key Takeaway

```text
VNI = Logical VXLAN segment identifier
```

---

## VTEP: VXLAN Tunnel Endpoint

VTEP stands for:

```text
VXLAN Tunnel Endpoint
```

A VTEP encapsulates and decapsulates VXLAN traffic.

### VTEP Responsibilities

- Receives original Layer 2 Ethernet frame
- Adds VXLAN encapsulation
- Sends encapsulated traffic across Layer 3 IP network
- Receives encapsulated traffic at destination
- Removes VXLAN encapsulation
- Delivers original Ethernet frame to destination network

### Example

```text
Data Center A VTEP: 1.1.1.1
Data Center B VTEP: 2.2.2.2
```

### Key Takeaway

```text
VTEP = Entry and exit point for VXLAN tunnel traffic
```

---

## VXLAN Tunnel

A VXLAN tunnel carries traffic between VTEPs over an IP network.

### Simplified Flow

```text
Original Ethernet frame
→ VXLAN encapsulation
→ UDP/IP transport
→ Layer 3 network
→ Destination VTEP
→ Decapsulation
→ Original Ethernet frame delivered
```

### Key Takeaway

```text
VXLAN tunnel = Encapsulated Layer 2 traffic carried over Layer 3
```

---

## VXLAN Encapsulation

The original Ethernet frame is placed inside additional headers.

### Simplified Encapsulation Stack

```text
Outer Ethernet header
Outer IP header
UDP header
VXLAN header
Original Ethernet frame
```

### Original Ethernet Frame May Contain

```text
Original Ethernet header
Original IP header
Payload
```

### Why Encapsulation Matters

Encapsulation allows the original Layer 2 frame to move across a routed Layer 3 network.

---

## Example Multi-Data-Center Design

### Data Center A

```text
Virtualization server
├── Virtual switch
├── VM A1
├── VM B1
└── VM C1

Top-of-rack switch
└── VTEP 1.1.1.1
```

### Data Center B

```text
Virtualization server
├── Virtual switch
├── VM A2
├── VM B2
└── VM C2

Top-of-rack switch
└── VTEP 2.2.2.2
```

### Logical VXLAN Segments

```text
VM A1 ↔ VM A2 → VNI 2000
VM B1 ↔ VM B2 → VNI 3000
VM C1 ↔ VM C2 → VNI 4000
```

### Key Takeaway

```text
Workloads in different data centers can communicate as though they share the same logical network.
```

---

## Underlay and Overlay Networks

VXLAN is easier to understand when separating the physical transport from the logical network.

### Underlay Network

The underlay is the Layer 3 IP network that transports VXLAN traffic.

```text
Underlay = Physical or routed IP transport
```

### Overlay Network

The overlay is the logical VXLAN network built on top of the underlay.

```text
Overlay = Logical VXLAN segment carried over underlay
```

### Key Takeaway

```text
Underlay carries the traffic.
Overlay defines the logical network.
```

---

## Why VXLAN Is Useful

VXLAN supports:

- Large-scale multi-tenant environments
- Cloud workload mobility
- Multi-data-center connectivity
- Application portability
- Logical network consistency
- Layer 2 extension over routed networks
- Data-center scaling
- Service-provider environments

### Example

```text
Application moves from Data Center A to Data Center B
→ Logical VXLAN segment remains available
→ Application can retain expected network behavior
```

---

## Cloud Engineering Connection

Cloud engineers use VXLAN concepts when supporting:

- Multi-cloud networking
- Data-center fabrics
- Virtualized workloads
- Kubernetes networking
- Overlay networks
- Service-provider environments
- Software-defined networking
- Cloud migrations
- Workload mobility
- Multi-tenant infrastructure
- Data Center Interconnection

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Virtual Extensible LAN | VXLAN |
| Connect Layer 2 segments across Layer 3 | VXLAN |
| Around `16 million` logical networks | VXLAN |
| VXLAN logical segment ID | VNI |
| VXLAN tunnel entry and exit point | VTEP |
| Original Ethernet frame carried over UDP/IP | VXLAN encapsulation |
| Separate data centers connected together | DCI |
| Around `4,000` logical networks | VLAN |
| Logical network carried over physical transport | Overlay |
| Physical routed IP transport | Underlay |

---

## Memory Trick

```text
VXLAN = VLAN scaling for modern data centers

VNI   = VXLAN Network Identifier
VTEP  = VXLAN Tunnel Endpoint
DCI   = Data Center Interconnection

Overlay = Logical VXLAN network
Underlay = Routed IP transport
```

---

## Practice Questions

### 1. What does VXLAN stand for?

Answer:

```text
Virtual Extensible LAN
```

### 2. What problem does VXLAN solve?

Answer: It allows Layer 2 network segments to extend across Layer 3 networks and scale to very large numbers of logical networks.

### 3. Approximately how many logical networks can traditional VLANs support?

Answer:

```text
Around 4,000
```

### 4. Approximately how many logical networks can VXLAN support?

Answer:

```text
Around 16 million
```

### 5. What does VNI stand for?

Answer:

```text
VXLAN Network Identifier
```

### 6. What does VTEP stand for?

Answer:

```text
VXLAN Tunnel Endpoint
```

### 7. What does a VTEP do?

Answer: It encapsulates and decapsulates VXLAN traffic.

### 8. What transport protocol is used by VXLAN encapsulation?

Answer:

```text
UDP
```

### 9. What is the underlay network?

Answer: The Layer 3 IP transport network.

### 10. What is the overlay network?

Answer: The logical VXLAN network built on top of the underlay.
