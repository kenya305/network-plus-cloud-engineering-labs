# Lab 42: Power, UPS, and PDU Infrastructure Analysis

## Objective

Analyze electrical-power fundamentals and select appropriate UPS and PDU solutions for network infrastructure.

## Scenario

A company is improving power resilience for a small data center and several network closets.

The environment includes:

- Core router
- Core switch
- Access switches
- Firewalls
- Servers
- Wireless LAN controller
- Rack-mounted equipment
- Remote branch offices

The network team must calculate power requirements and select appropriate power-protection solutions.

---

## Safety Notice

Do not open electrical equipment or touch energized components.

Electrical servicing should be performed only by trained and authorized personnel.

Remember that some devices may retain a charge after being disconnected.

---

## Part 1: Electrical Fundamentals

| Measurement | Meaning | Abbreviation |
| ----------- | ------- | ------------ |
| Ampere | Electrical-current flow | `A` |
| Volt | Electrical pressure | `V` |
| Watt | Electrical power usage | `W` |

### Formula

```text
Watts = Volts × Amps
```

or:

```text
W = V × A
```

---

## Part 2: Power Calculation

### Scenario

A network device uses:

```text
120 V
0.5 A
```

### Calculation

```text
W = V × A
W = 120 × 0.5
W = 60
```

### Result

```text
60 W
```

---

## Part 3: Additional Power Calculations

| Device | Voltage | Current | Calculation | Power Usage |
| ------ | ------- | ------- | ----------- | ----------- |
| Router | `120 V` | `0.5 A` | `120 × 0.5` | `60 W` |
| Switch | `120 V` | `1.0 A` | `120 × 1.0` | `120 W` |
| Firewall | `120 V` | `0.75 A` | `120 × 0.75` | `90 W` |
| Wireless controller | `120 V` | `0.4 A` | `120 × 0.4` | `48 W` |

### Total

```text
60 W + 120 W + 90 W + 48 W = 318 W
```

### Key Takeaway

```text
UPS capacity must support connected equipment and desired runtime.
```

---

## Part 4: AC vs. DC

| Power Type | Meaning | Common Use |
| ---------- | ------- | ---------- |
| AC | Alternating Current | Wall outlets and building power |
| DC | Direct Current | Internal electronics |

### Conversion Flow

```text
Wall outlet AC
→ Device power supply
→ DC
→ Network equipment
```

---

## Part 5: Power-Problem Analysis

| Power Problem | Description | Possible Impact |
| ------------- | ----------- | --------------- |
| Outage | Complete power loss | Devices shut down |
| Brownout | Voltage drops below normal | Instability or equipment restart |
| Surge | Voltage rises above normal | Equipment-damage risk |
| Spike | Brief voltage increase | Equipment-damage risk |

---

## Part 6: UPS Comparison

| UPS Type | Also Called | Main Characteristic | Best-Fit Use |
| -------- | ----------- | ------------------- | ------------ |
| Standby | Offline | Switches to battery after failure | Less-sensitive equipment |
| Line-interactive | Line-interactive | Adjusts voltage during brownouts | Network closets and small offices |
| Online | Double-conversion | Continuously protected power with no transfer delay | Data centers and critical infrastructure |

---

## Part 7: UPS Selection Scenarios

### Scenario A: Home Office Router

```text
Requirement:
Protect home router and modem during brief outage

Recommended UPS:
Standby UPS
```

### Scenario B: Network Closet

```text
Requirement:
Protect access switch from brownouts and brief outages

Recommended UPS:
Line-interactive UPS
```

### Scenario C: Data-Center Core Infrastructure

```text
Requirement:
Protect core router, firewall, and switches with no transfer delay

Recommended UPS:
Online or double-conversion UPS
```

---

## Part 8: PDU Analysis

### PDU Definition

```text
Power Distribution Unit
```

### Purpose

```text
UPS or building power
→ PDU
→ Rack-mounted equipment
```

### Common Rack Connections

- Routers
- Switches
- Firewalls
- Servers
- Storage devices
- Wireless controllers

---

## Part 9: Intelligent PDU Scenario

### Requirement

A remote branch router becomes unresponsive.

No technician is on site.

### Solution

```text
Administrator
→ Connects to managed PDU
→ Selects router outlet
→ Powers outlet off
→ Powers outlet on
→ Router restarts
```

### Benefits

- Remote recovery
- Reduced travel
- Faster incident response
- Outlet-level control
- Monitoring
- Reporting

---

## Part 10: UPS and PDU Design

### Recommended Rack Flow

```text
Building power
→ UPS
→ Intelligent PDU
→ Rack-mounted network equipment
```

### Why This Design Works

```text
UPS
→ Battery backup and power conditioning

PDU
→ Distributes protected power

Intelligent PDU
→ Adds remote monitoring and control
```

---

## Part 11: Design Checklist

Before selecting a UPS or PDU, verify:

- Total wattage
- Battery runtime
- Number of outlets
- Rack-mount requirements
- Surge handling
- Brownout protection
- Automatic shutdown support
- Remote monitoring
- Outlet-level control
- Replacement-battery plan
- Redundancy
- Power-circuit limits
- Documentation

---

## What I Observed

Reliable network infrastructure depends on stable power.

The electrical relationship is:

```text
W = V × A
```

A UPS provides:

```text
Battery-backed power
Power conditioning
Outage protection
Brownout protection
Surge protection
```

A PDU provides:

```text
Rack-level power distribution
```

An intelligent PDU can also provide:

```text
Remote monitoring
Outlet-level control
Remote device restart
```

---

## Important Limitation

This lab is a planning and documentation exercise.

Do not perform electrical work unless properly trained and authorized.

A production design should also evaluate:

- Licensed electrical support
- Building codes
- Fire codes
- Circuit capacity
- Redundant power feeds
- Generator support
- UPS runtime
- Battery replacement
- Environmental monitoring
- Maintenance procedures
- Change control
- Vendor requirements

---

## Cloud Engineering Connection

Cloud engineers use power-infrastructure knowledge when supporting:

- Data centers
- Colocation facilities
- Private cloud
- Edge computing
- Hybrid cloud
- Branch offices
- Disaster recovery
- Remote infrastructure
- Network closets
- Business continuity
- High availability

---

## Skills Practiced

- Explaining amps, volts, and watts
- Calculating power consumption
- Comparing AC and DC
- Identifying outages, brownouts, and surges
- Comparing UPS types
- Selecting UPS solutions for different environments
- Explaining PDUs
- Explaining intelligent PDUs
- Designing UPS-to-PDU rack power flow
- Connecting power planning to cloud engineering
