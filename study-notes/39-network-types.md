# Network+ N10-009 Study Notes: Network Types

## Video Topic

Network Types

## Summary

Wireless networks can be designed in several ways depending on the number of devices, distance, coverage needs, and security requirements.

This lesson covers:

- Wireless mesh networks
- Self-healing wireless networks
- Ad hoc wireless connections
- IBSS
- Point-to-point wireless links
- Infrastructure mode
- Client isolation
- IoT onboarding
- Building-to-building wireless connectivity

---

## Wireless Mesh Network

A wireless mesh network uses multiple wireless devices or access points that communicate with each other.

### Example

```text
Access Point 1
↔ Access Point 2
↔ Access Point 3
```

Client devices connect to the closest access point.

The access points communicate across the mesh to reach the rest of the network.

### Common Use Cases

- Home mesh Wi-Fi systems
- Large residences
- Branch offices
- Campuses
- Outdoor wireless coverage
- Environments where cabling is difficult

### Key Takeaway

```text
Mesh network = Multiple wireless nodes communicate with each other
```

---

## Self-Healing Mesh

A mesh network can adapt if one node leaves or fails.

### Example

```text
Access Point 2 fails
→ Remaining nodes detect failure
→ Traffic uses another available path
→ Connectivity continues
```

### Key Takeaway

```text
Self-healing mesh = Network automatically adapts when a node is unavailable
```

---

## Ad Hoc Wireless Networking

An ad hoc wireless network connects devices directly without using an access point.

### Example

```text
Laptop
↔ Printer
```

or:

```text
Phone
↔ IoT device
```

### Common Use Cases

- Temporary device setup
- IoT onboarding
- Direct file transfer
- Device-to-device communication
- Small two-device networks

### Key Takeaway

```text
Ad hoc = Direct wireless device-to-device connection
```

---

## IBSS

IBSS stands for:

```text
Independent Basic Service Set
```

IBSS is another name for an ad hoc wireless network.

### Key Takeaway

```text
IBSS = Ad hoc wireless networking without an access point
```

---

## IoT Onboarding Example

An IoT device may temporarily create an ad hoc network during initial setup.

### Workflow

```text
Phone
→ Connects directly to IoT device
→ Sends SSID and wireless-security settings
→ Ad hoc connection closes
→ IoT device joins normal wireless network
```

### Key Takeaway

```text
Ad hoc connections can be temporary setup tools for IoT devices.
```

---

## Point-to-Point Wireless

Point-to-point wireless connects two locations directly.

### Example

```text
Building A
→ Wireless bridge
→ Building B
```

Each side typically uses:

- Compatible access point or bridge hardware
- Directional antenna
- Appropriate power output
- Supported frequency
- Clear line of sight when possible

### Common Use Cases

- Building-to-building links
- Long-distance wireless bridges
- Connecting separate homes
- Campus links
- Remote-site connectivity

### Key Takeaway

```text
Point-to-point = Direct wireless bridge between two locations
```

---

## Point-to-Point Considerations

Not every access point supports point-to-point mode.

Validate:

- Access-point software support
- Hardware capability
- Antenna type
- Distance
- Frequency range
- Transmit power
- Line of sight
- Environmental interference
- Regulatory limits

---

## Infrastructure Mode

Infrastructure mode is the most common wireless-network design.

Wireless devices connect through a central access point.

### Example

```text
Laptop
Phone
Tablet
Printer
→ Access Point
→ Wired network
→ Internet
```

### Key Takeaway

```text
Infrastructure mode = Devices connect through a central access point
```

---

## Client Isolation

Some access points allow wireless clients to communicate directly with each other.

Other access points isolate wireless clients so they can only communicate with:

- Access point
- Wired network
- Internet
- Approved resources

### Example

```text
Guest laptop
→ Access point
→ Internet

Guest laptop
✕ Cannot communicate directly with another guest device
```

### Key Takeaway

```text
Client isolation = Prevent wireless clients from communicating directly with each other
```

---

## Why Client Isolation Matters

Client isolation is useful in:

- Guest Wi-Fi
- Hotels
- Coffee shops
- Airports
- Shared workspaces
- Public wireless networks

### Benefit

```text
Client isolation
→ Reduces risk between untrusted wireless devices
```

---

## Network-Type Comparison

| Wireless Network Type | Design | Best-Fit Use |
| --------------------- | ------ | ------------ |
| Mesh | Multiple nodes communicate with each other | Large coverage areas and resilient home or office Wi-Fi |
| Ad hoc / IBSS | Devices connect directly without AP | Temporary setup or simple device-to-device links |
| Point-to-point | Two locations connected directly | Building-to-building wireless bridge |
| Infrastructure mode | Devices connect through central AP | Home and office wireless networks |

---

## Wireless Design Decision Guide

| Requirement | Recommended Design |
| ----------- | ------------------ |
| Extend wireless coverage across large home | Mesh |
| Connect IoT device during setup | Ad hoc / IBSS |
| Connect two buildings without cable | Point-to-point |
| Standard home or office Wi-Fi | Infrastructure mode |
| Prevent guests from reaching each other | Client isolation |

---

## Cloud Engineering Connection

Cloud engineers encounter wireless-network types when supporting:

- Branch-office connectivity
- Hybrid cloud environments
- IoT onboarding
- Remote workforces
- Cloud-managed access points
- Guest networks
- Zero-trust access
- SASE
- Wireless bridges
- Campus networks
- Edge computing

### Example

```text
Remote building
→ Point-to-point wireless bridge
→ Main office network
→ Cloud applications
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Multiple APs communicate with each other | Mesh |
| Network adapts after one node fails | Self-healing mesh |
| Direct device-to-device Wi-Fi | Ad hoc |
| Independent Basic Service Set | IBSS |
| Two buildings linked wirelessly | Point-to-point |
| Devices connect through central AP | Infrastructure mode |
| Guests cannot communicate with each other | Client isolation |
| IoT device setup network | Ad hoc / IBSS |

---

## Memory Trick

```text
Mesh           = Many APs work together
Ad hoc / IBSS  = Device to device
Point-to-point = Building to building
Infrastructure = Device to AP
Isolation      = Clients cannot talk directly
```

---

## Practice Questions

### 1. What is a wireless mesh network?

Answer: A network in which multiple wireless devices or access points communicate with each other.

### 2. What does self-healing mean in a mesh network?

Answer: The network automatically finds an alternative path when a node becomes unavailable.

### 3. What is an ad hoc wireless connection?

Answer: A direct device-to-device wireless connection without an access point.

### 4. What does IBSS stand for?

Answer:

```text
Independent Basic Service Set
```

### 5. What is a common IoT use case for ad hoc networking?

Answer: Temporarily connecting to the IoT device to provide SSID and security settings.

### 6. What is a point-to-point wireless connection?

Answer: A direct wireless bridge between two locations.

### 7. What is infrastructure mode?

Answer: A wireless design in which devices connect through a central access point.

### 8. What is client isolation?

Answer: A feature that prevents wireless clients from communicating directly with each other.

### 9. Which design is common in home and office Wi-Fi?

Answer:

```text
Infrastructure mode
```

### 10. Which design is appropriate for a building-to-building wireless bridge?

Answer:

```text
Point-to-point
```
