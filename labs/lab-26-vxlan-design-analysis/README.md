# Lab 26: VXLAN Design Analysis

## Objective

Identify the major components of a VXLAN design and explain how a Layer 2 overlay can operate across a Layer 3 network.

## Scenario

A company runs workloads in two data centers.

The company wants virtual machines in each data center to communicate as though they are part of the same logical network.

The data centers use different IP-addressing schemes and are connected through a routed IP network.

---

## Traditional VLAN Limitation

| Feature | Traditional VLAN |
| ------- | ---------------- |
| OSI layer | Layer 2 |
| Approximate scale | Around `4,000` VLANs |
| Identifier | VLAN ID |
| Main limitation | Limited scale for very large data-center environments |

---

## VXLAN Solution

| Feature | VXLAN |
| ------- | ----- |
| Full name | Virtual Extensible LAN |
| Main purpose | Extend Layer 2 logical networks over Layer 3 transport |
| Identifier | VNI |
| Approximate scale | Around `16 million` logical networks |
| Tunnel endpoints | VTEPs |
| Transport | UDP/IP |
| Common environment | Data centers and cloud infrastructure |

---

## Multi-Data-Center Scenario

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

---

## Logical VXLAN Segments

| Logical Workload Group | VNI |
| ---------------------- | --- |
| VM A1 ↔ VM A2 | `2000` |
| VM B1 ↔ VM B2 | `3000` |
| VM C1 ↔ VM C2 | `4000` |

---

## Encapsulation Flow

```text
Original Ethernet frame
→ Source VTEP encapsulates frame
→ VXLAN header added
→ UDP/IP transport carries traffic across Layer 3 underlay
→ Destination VTEP receives traffic
→ Destination VTEP decapsulates frame
→ Original Ethernet frame delivered to destination network
```

---

## Overlay vs. Underlay

| Network Type | Description |
| ------------ | ----------- |
| Underlay | Routed Layer 3 IP transport network |
| Overlay | Logical VXLAN network carried across the underlay |

---

## Scenario Analysis

### Scenario 1: Workload Mobility

An application moves from one data center to another.

**Recommended technology:**

```text
VXLAN
```

**Reason:**

VXLAN allows the workload to remain connected to the expected logical network even when the underlying location changes.

---

### Scenario 2: Multi-Tenant Cloud Environment

A service provider needs more than `4,000` isolated logical networks.

**Recommended technology:**

```text
VXLAN
```

**Reason:**

VXLAN supports approximately `16 million` logical networks through the use of a 24-bit VNI.

---

### Scenario 3: Encapsulated Traffic

A Layer 2 Ethernet frame must cross a Layer 3 routed network.

**Recommended approach:**

```text
Encapsulate the original Ethernet frame using VXLAN over UDP/IP.
```

---

## What I Observed

VXLAN extends Layer 2 logical networks across Layer 3 transport networks.

The VNI identifies the logical VXLAN segment.

The VTEP encapsulates and decapsulates VXLAN traffic.

The underlay network provides routed IP transport.

The overlay network provides the logical VXLAN segment.

---

## Important Limitation

VXLAN introduces additional encapsulation and design complexity.

A network engineer should evaluate:

- MTU requirements
- VTEP configuration
- Underlay routing
- Overlay design
- Network segmentation
- Security requirements
- Troubleshooting procedures
- Data-center architecture
- Multi-tenant requirements

---

## Cloud Engineering Connection

Cloud engineers use VXLAN concepts when supporting:

- Multi-cloud networking
- Data-center interconnection
- Workload mobility
- Software-defined networking
- Overlay networks
- Kubernetes networking
- Service-provider environments
- Multi-tenant systems
- Virtualized infrastructure
- Cloud migrations

---

## Skills Practiced

- Comparing VLAN and VXLAN
- Identifying VNI purpose
- Identifying VTEP purpose
- Distinguishing overlay and underlay networks
- Explaining VXLAN encapsulation
- Connecting VXLAN to multi-data-center networking
- Applying VXLAN concepts to cloud infrastructure
