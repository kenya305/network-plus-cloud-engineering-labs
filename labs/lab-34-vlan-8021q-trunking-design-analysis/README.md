# Lab 34: VLAN and 802.1Q Trunking Design Analysis

## Objective

Analyze VLAN segmentation, 802.1Q trunking, native VLAN behavior, inter-VLAN routing, and voice/data separation.

## Scenario

A company wants to reduce hardware costs and simplify its switch infrastructure.

Instead of using separate physical switches for each department, the company will use VLANs on shared switches.

The company also needs to connect VLANs across switches and support both phone and computer traffic over one cable.

---

## Part 1: VLAN Segmentation

### Physical Design

```text
One physical switch
→ VLAN 100
→ VLAN 200
→ VLAN 300
```

### Department Mapping

| VLAN | Department or Function |
| ---- | ---------------------- |
| `100` | Finance |
| `200` | Voice |
| `300` | Engineering |

### Key Takeaway

```text
Each VLAN is a separate broadcast domain.
```

---

## Part 2: Access-Port Assignment

| Switch Port | Connected Device | VLAN |
| ----------- | ---------------- | ---- |
| Port 1 | Finance workstation | `100` |
| Port 2 | Finance workstation | `100` |
| Port 3 | IP phone | `200` |
| Port 4 | Engineering workstation | `300` |

### Key Takeaway

```text
Access port = Port assigned to one VLAN
```

---

## Part 3: 802.1Q Trunk Design

Two switches must carry multiple VLANs across one physical cable.

### Recommended Design

```text
Switch A
→ 802.1Q trunk
→ Switch B
```

### VLANs Carried

```text
VLAN 100
VLAN 200
VLAN 300
```

### Benefit

```text
One trunk link
→ Carries multiple VLANs
→ Reduces cabling requirements
```

---

## Part 4: VLAN Tagging Flow

```text
Device in VLAN 200
→ Frame enters Switch A
→ Switch A adds VLAN 200 tag
→ Tagged frame crosses trunk
→ Switch B reads VLAN tag
→ Switch B removes tag
→ Frame delivered to VLAN 200 device
```

---

## Part 5: Native VLAN Analysis

### Definition

```text
Native VLAN = Untagged VLAN traffic on an 802.1Q trunk
```

### Important Rule

```text
Native VLAN must match on both sides of the trunk.
```

### Risk

A native VLAN mismatch may create:

- Switch log errors
- Connectivity issues
- Security concerns
- Troubleshooting confusion

---

## Part 6: Layer 3 Switching and SVIs

### Requirement

Devices in VLAN 100 need to communicate with devices in VLAN 300.

### Recommended Design

```text
Layer 3 switch
→ SVI for VLAN 100
→ SVI for VLAN 300
→ Inter-VLAN routing
```

### SVI Mapping

| VLAN | SVI Purpose |
| ---- | ----------- |
| `100` | Layer 3 gateway for Finance VLAN |
| `200` | Layer 3 gateway for Voice VLAN |
| `300` | Layer 3 gateway for Engineering VLAN |

---

## Part 7: Voice and Data VLAN Design

### Requirement

A single Ethernet cable connects an IP phone and a computer.

### Recommended Design

```text
Switch
→ Ethernet cable
→ IP phone
→ Pass-through cable
→ Computer
```

### VLAN Assignment

| Traffic Type | VLAN |
| ------------ | ---- |
| Voice traffic | `200` |
| Data traffic | `100` |

### Benefits

- Improved voice quality
- Easier Quality of Service
- Better traffic separation
- Reduced cable requirements
- Simplified desk connectivity

---

## Part 8: VLAN Technology Comparison

| Technology | Purpose |
| ---------- | ------- |
| VLAN | Creates logical broadcast domains |
| Access port | Carries one VLAN |
| Trunk port | Carries multiple VLANs |
| 802.1Q | Standard trunking protocol |
| VLAN tag | Identifies VLAN membership |
| Native VLAN | Untagged VLAN on trunk |
| SVI | Layer 3 virtual interface for VLAN |
| ISL | Legacy proprietary trunking method |

---

## What I Observed

VLANs allow one physical switch to support multiple logical broadcast domains.

802.1Q trunks carry multiple VLANs over one physical connection.

VLAN tags identify the logical network associated with each frame.

Layer 3 switches can route between VLANs using SVIs.

Voice and data traffic can share one physical cable while remaining logically separated.

---

## Important Limitation

VLANs improve segmentation but do not automatically provide complete security.

A network engineer should still evaluate:

- Access-control policies
- Firewall rules
- Trunk configuration
- Native VLAN consistency
- VLAN hopping risks
- Layer 3 routing
- Quality of Service
- Monitoring
- Documentation
- Change control

---

## Cloud Engineering Connection

Cloud engineers use VLAN and trunking concepts when supporting:

- Data-center networking
- Virtual switches
- Private cloud infrastructure
- Hypervisors
- SDN
- VXLAN
- Firewall segmentation
- Hybrid cloud environments
- Multi-tenant networking
- Voice and data separation

---

## Skills Practiced

- Identifying VLAN broadcast domains
- Assigning VLAN IDs
- Explaining access ports
- Explaining trunk ports
- Explaining 802.1Q tagging
- Identifying native VLAN behavior
- Explaining SVIs
- Applying inter-VLAN routing concepts
- Separating voice and data traffic
- Connecting VLAN concepts to cloud engineering
