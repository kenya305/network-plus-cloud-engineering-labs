# Lab 39: Wireless Network Type Design Analysis

## Objective

Compare mesh, ad hoc, point-to-point, and infrastructure wireless-network designs and select the best option for realistic scenarios.

## Scenario

A company is planning wireless connectivity for:

- A large office
- A guest Wi-Fi network
- Two nearby buildings
- IoT devices
- Remote users
- Cloud applications

The network team must select the appropriate wireless-network design for each requirement.

---

## Part 1: Wireless Mesh Design

### Requirement

A large office needs Wi-Fi coverage across multiple rooms.

### Recommended Design

```text
Wireless mesh
```

### Topology

```text
Access Point 1
↔ Access Point 2
↔ Access Point 3
```

### Benefit

```text
One node fails
→ Remaining nodes detect failure
→ Traffic uses another path
→ Connectivity continues
```

### Key Takeaway

```text
Mesh networks improve coverage and resilience.
```

---

## Part 2: Ad Hoc / IBSS Design

### Requirement

A smartphone needs to configure an IoT door lock before the lock joins the main wireless network.

### Recommended Design

```text
Ad hoc / IBSS
```

### Workflow

```text
Phone
→ Connects directly to IoT lock
→ Sends SSID and wireless-security settings
→ Temporary ad hoc connection ends
→ IoT lock joins main wireless network
```

### Key Takeaway

```text
IBSS supports temporary direct device-to-device communication.
```

---

## Part 3: Point-to-Point Wireless Design

### Requirement

Building A and Building B are nearby but do not have a physical cable between them.

### Recommended Design

```text
Point-to-point wireless bridge
```

### Topology

```text
Building A
→ Directional antenna
→ Wireless bridge
→ Directional antenna
→ Building B
```

### Design Considerations

- Access-point support
- Directional antennas
- Distance
- Line of sight
- Frequency
- Transmit power
- Weather
- Interference
- Regulatory requirements

### Key Takeaway

```text
Point-to-point wireless connects two locations directly.
```

---

## Part 4: Infrastructure Mode Design

### Requirement

Employees need standard office Wi-Fi access.

### Recommended Design

```text
Infrastructure mode
```

### Topology

```text
Laptop
Phone
Tablet
Printer
→ Central access point
→ Wired network
→ Cloud applications
```

### Key Takeaway

```text
Infrastructure mode is the most common wireless design.
```

---

## Part 5: Client Isolation Design

### Requirement

Guests need internet access but should not communicate directly with other guest devices.

### Recommended Design

```text
Guest Wi-Fi
+
Client isolation
```

### Traffic Flow

```text
Guest laptop
→ Access point
→ Internet
```

Blocked traffic:

```text
Guest laptop
✕ Other guest laptop
```

### Key Takeaway

```text
Client isolation reduces risk between untrusted wireless devices.
```

---

## Part 6: Network-Type Comparison

| Wireless Network Type | Main Characteristic | Recommended Use |
| --------------------- | ------------------- | --------------- |
| Mesh | Multiple nodes communicate and self-heal | Large coverage area |
| Ad hoc / IBSS | Direct device-to-device Wi-Fi | Temporary setup or IoT onboarding |
| Point-to-point | Direct bridge between two locations | Building-to-building link |
| Infrastructure mode | Clients connect through central AP | Standard home or office Wi-Fi |
| Client isolation | Prevents client-to-client communication | Guest network security |

---

## Part 7: Scenario Selection

| Scenario | Best Wireless Design |
| -------- | -------------------- |
| Large home needs broader coverage | Mesh |
| IoT light bulb needs initial configuration | Ad hoc / IBSS |
| Two buildings need wireless connectivity | Point-to-point |
| Employees need office Wi-Fi | Infrastructure mode |
| Hotel guests should not reach each other | Client isolation |

---

## What I Observed

Wireless-network design depends on the use case.

```text
Mesh
→ Multiple nodes and self-healing paths

Ad hoc / IBSS
→ Direct device-to-device connection

Point-to-point
→ Direct wireless bridge between locations

Infrastructure mode
→ Devices connect through access point

Client isolation
→ Wireless clients cannot communicate directly
```

---

## Important Limitation

Wireless design should also consider:

- Security requirements
- Bandwidth
- Distance
- Interference
- Line of sight
- AP placement
- Device compatibility
- Client density
- Regulatory limits
- Weather
- Monitoring
- Authentication
- Segmentation

---

## Cloud Engineering Connection

Cloud engineers use these concepts when supporting:

- Branch-office networking
- Hybrid cloud connectivity
- Guest Wi-Fi
- IoT onboarding
- Remote-site links
- Cloud-managed Wi-Fi
- SASE
- Zero-trust access
- Edge computing
- Campus networking

---

## Skills Practiced

- Comparing wireless-network types
- Explaining wireless mesh
- Explaining self-healing networks
- Explaining ad hoc and IBSS
- Designing point-to-point wireless links
- Explaining infrastructure mode
- Applying client isolation
- Connecting wireless design to cloud engineering
