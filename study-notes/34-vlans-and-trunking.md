# Network+ N10-009 Study Notes: VLANs and Trunking

## Video Topic

VLANs and Trunking

## Summary

A Virtual Local Area Network, or VLAN, allows a switch to separate devices into different broadcast domains while still using the same physical switch.

Instead of buying and managing separate switches for every network segment, administrators can assign switch ports to different VLANs.

This lesson also covers:

- Broadcast domains
- VLAN segmentation
- 802.1Q trunking
- VLAN tagging
- VLAN IDs
- Native VLANs
- Default VLANs
- Inter-Switch Link
- Layer 3 switching
- Switched Virtual Interfaces
- Voice VLANs
- Data VLANs
- Voice-over-IP traffic separation

---

## LAN and Broadcast Domains

A Local Area Network is commonly abbreviated as:

```text
LAN
```

A LAN is broadly described as a group of devices in the same broadcast domain.

### Key Takeaway

```text
Broadcast domain = Group of devices that receive the same broadcast traffic
```

---

## Why VLANs Are Useful

Without VLANs, separate broadcast domains may require separate physical switches.

### Traditional Design

```text
Red network
→ Separate switch

Blue network
→ Separate switch
```

### VLAN Design

```text
One physical switch
→ Red VLAN
→ Blue VLAN
```

### Benefits

- Lower hardware cost
- Less rack space
- Fewer power requirements
- Easier management
- Logical segmentation
- Better network organization

---

## VLAN

VLAN stands for:

```text
Virtual Local Area Network
```

A VLAN creates logical segmentation on a switch.

Devices assigned to the same VLAN can communicate within the same broadcast domain.

Devices in different VLANs require routing to communicate.

### Example

```text
VLAN 100
→ Finance devices

VLAN 200
→ Voice devices

VLAN 300
→ Engineering devices
```

### Key Takeaway

```text
VLAN = Logical broadcast domain on a switch
```

---

## VLAN IDs

VLANs are identified by number.

### Examples

```text
VLAN 1
VLAN 2
VLAN 3
VLAN 100
VLAN 200
```

### VLAN Tag Size

```text
12 bits
```

### Usable VLAN Count

```text
4,094 usable VLANs
```

Some VLAN numbers are reserved.

---

## Access Ports

An access port normally carries traffic for one VLAN.

### Example

```text
Switch port 1
→ VLAN 100

Switch port 2
→ VLAN 200
```

### Key Takeaway

```text
Access port = Usually assigned to one VLAN
```

---

## Trunk Ports

A trunk port carries traffic for multiple VLANs over one physical connection.

### Example

```text
Switch A
→ One trunk cable
→ Switch B

Traffic carried:
VLAN 100
VLAN 200
VLAN 300
```

### Key Takeaway

```text
Trunk = One link carrying multiple VLANs
```

---

## 802.1Q Trunking

802.1Q is the standard method for VLAN trunking.

It may also be written as:

```text
802.1Q
```

or:

```text
.1Q
```

### Key Takeaway

```text
802.1Q = Standard VLAN trunking method
```

---

## VLAN Tagging

802.1Q trunking inserts a VLAN tag into the Ethernet frame.

### Ethernet Frame Before Tagging

```text
Preamble
Start Frame Delimiter
Destination MAC
Source MAC
Type
Payload
Frame Check Sequence
```

### Ethernet Frame After Tagging

```text
Preamble
Start Frame Delimiter
Destination MAC
Source MAC
VLAN Tag
Type
Payload
Frame Check Sequence
```

### Key Takeaway

```text
VLAN tag = Identifies which VLAN the frame belongs to
```

---

## VLAN Trunking Example

A device in VLAN 200 sends traffic to another switch.

```text
Device in VLAN 200
→ Frame enters trunk port
→ Switch adds VLAN 200 tag
→ Frame crosses trunk
→ Receiving switch reads VLAN tag
→ Receiving switch removes tag
→ Frame delivered to VLAN 200 device
```

---

## ISL

Before 802.1Q became the standard, some environments used:

```text
ISL
```

ISL stands for:

```text
Inter-Switch Link
```

ISL was proprietary and is now considered outdated.

### Key Takeaway

```text
ISL = Legacy proprietary trunking method
802.1Q = Modern trunking standard
```

---

## Default VLAN

A switch has a default VLAN.

Many switches use:

```text
VLAN 1
```

as the default VLAN.

### Key Takeaway

```text
Default VLAN = VLAN assigned to ports before additional configuration
```

---

## Native VLAN

A native VLAN traverses an 802.1Q trunk without a VLAN tag.

### Use Cases

- Management traffic
- Switch-to-switch communication
- Legacy compatibility

### Important Rule

The native VLAN must match on both sides of the trunk.

### Key Takeaway

```text
Native VLAN = Untagged traffic on a trunk
```

---

## Layer 2 Switch vs. Layer 3 Switch

| Feature | Layer 2 Switch | Layer 3 Switch |
| ------- | -------------- | -------------- |
| Main forwarding basis | MAC address | MAC address and IP address |
| Primary OSI layer | Layer 2 | Layer 2 and Layer 3 |
| VLAN support | Yes | Yes |
| Inter-VLAN routing | No | Yes |
| Routing functionality | No | Yes |

### Key Takeaway

```text
Layer 2 switch = Switches frames
Layer 3 switch = Switches frames and routes packets
```

---

## SVI

SVI stands for:

```text
Switched Virtual Interface
```

An SVI is a logical Layer 3 interface associated with a VLAN.

### Example

```text
VLAN 100
→ SVI for VLAN 100
→ IP address assigned
→ Routing enabled
```

### Key Takeaway

```text
SVI = Logical Layer 3 interface for a VLAN
```

---

## Inter-VLAN Routing

Devices in different VLANs cannot communicate directly without routing.

A Layer 3 switch can route between VLANs using SVIs.

### Example

```text
VLAN 100
→ SVI 100
→ Layer 3 routing
→ SVI 200
→ VLAN 200
```

---

## Voice VLAN and Data VLAN

Enterprise networks often use the same Ethernet cable for both:

- Phone traffic
- Computer traffic

Voice and data can be separated into different VLANs.

### Example

```text
Phone
→ VLAN 200

Computer
→ VLAN 100
```

### Benefits

- Better traffic separation
- Easier Quality of Service configuration
- Reduced congestion impact
- Better voice quality
- More efficient cabling

---

## Voice and Data Over One Cable

### Example Design

```text
Switch
→ Ethernet cable
→ IP phone
→ Ethernet pass-through
→ Computer
```

The switch recognizes both voice and data traffic and places each type into the correct VLAN.

### Key Takeaway

```text
Voice VLAN + Data VLAN
→ One physical connection
→ Separate logical networks
```

---

## Cloud Engineering Connection

Cloud engineers use VLAN concepts when working with:

- Hybrid cloud networks
- Data-center segmentation
- Virtual switches
- Hypervisors
- Private cloud environments
- Network virtualization
- Firewall zones
- Layer 3 switching
- Voice and data separation
- SDN platforms
- VXLAN overlays
- Kubernetes networking
- Multi-tenant infrastructure

### Example

```text
Shared physical infrastructure
→ Separate logical networks
→ Apply segmentation policies
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Separate broadcast domains on one switch | VLAN |
| Standard VLAN trunking | 802.1Q |
| One cable carrying multiple VLANs | Trunk |
| Frame marking for VLAN identity | VLAN tag |
| Legacy proprietary trunking | ISL |
| Untagged VLAN on trunk | Native VLAN |
| Default VLAN on many switches | VLAN 1 |
| Routing between VLANs on a switch | Layer 3 switch |
| Logical Layer 3 interface for VLAN | SVI |
| Voice and data on same cable | Voice VLAN and data VLAN |

---

## Memory Trick

```text
VLAN  = Logical broadcast domain
Trunk = One link carrying many VLANs
802.1Q = VLAN-tagging standard
Native VLAN = Untagged VLAN on trunk
SVI = Layer 3 interface for VLAN
```

---

## Practice Questions

### 1. What does VLAN stand for?

Answer:

```text
Virtual Local Area Network
```

### 2. What problem does a VLAN solve?

Answer: It creates separate broadcast domains on the same physical switch.

### 3. What is a trunk port?

Answer: A switch port that carries traffic for multiple VLANs.

### 4. What standard is used for VLAN trunking?

Answer:

```text
802.1Q
```

### 5. What is a VLAN tag?

Answer: A field inserted into an Ethernet frame that identifies the VLAN.

### 6. How many usable VLANs are available with the 12-bit VLAN ID?

Answer:

```text
4,094
```

### 7. What is the native VLAN?

Answer: The VLAN whose traffic traverses a trunk without a VLAN tag.

### 8. What is ISL?

Answer:

```text
Inter-Switch Link
```

A legacy proprietary trunking method.

### 9. What is an SVI?

Answer:

```text
Switched Virtual Interface
```

A logical Layer 3 interface assigned to a VLAN.

### 10. Why use separate voice and data VLANs?

Answer: To improve traffic separation, reduce contention, and protect voice quality.
