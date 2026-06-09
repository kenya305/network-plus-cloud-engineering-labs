# Network+ N10-009 Study Notes: Power

## Video Topic

Power

## Summary

Reliable electrical power is essential for routers, switches, servers, firewalls, wireless controllers, and other technology infrastructure.

This lesson covers:

- Electrical safety
- Amps
- Volts
- Watts
- Alternating Current
- Direct Current
- Brownouts
- Surges
- Uninterruptible Power Supplies
- Standby UPS
- Line-interactive UPS
- Online or double-conversion UPS
- Power Distribution Units
- Remote power management

---

## Electrical Safety

Never touch energized components.

Always disconnect equipment from its power source before working near internal components.

Some devices may store a charge in capacitors even after being disconnected.

### Examples

- Older CRT monitors
- Laser printers
- Power supplies
- Other devices containing capacitors

### Key Takeaway

```text
Disconnect power before servicing equipment.
Treat electrical components with caution.
```

---

## Ampere

An ampere is commonly called an:

```text
Amp
```

The abbreviation is:

```text
A
```

Amps measure the rate of electrical-current flow.

### Water-Hose Analogy

```text
Amps
→ Amount of water flowing through the hose
```

---

## Voltage

Voltage measures electrical pressure.

The abbreviation is:

```text
V
```

### Water-Hose Analogy

```text
Volts
→ Water pressure pushing through the hose
```

### Common Examples

```text
120 V
240 V
```

---

## Watts

Watts measure electrical power usage.

The abbreviation is:

```text
W
```

### Formula

```text
Watts = Volts × Amps
```

or:

```text
W = V × A
```

### Example

```text
120 V × 0.5 A = 60 W
```

---

## Electrical Formula Reference

| Measurement | Meaning | Abbreviation |
| ----------- | ------- | ------------ |
| Ampere | Electrical-current flow | `A` |
| Volt | Electrical pressure | `V` |
| Watt | Electrical power usage | `W` |

---

## Alternating Current

Alternating Current is abbreviated as:

```text
AC
```

AC changes direction repeatedly.

It is commonly delivered through wall outlets because it can be distributed efficiently over long distances.

| Region | Typical Voltage | Typical Frequency |
| ------ | --------------- | ----------------- |
| United States and Canada | `110–120 V` | `60 Hz` |
| Europe | `220–240 V` | `50 Hz` |

### Key Takeaway

```text
AC = Wall-outlet power that repeatedly changes direction
```

---

## Direct Current

Direct Current is abbreviated as:

```text
DC
```

DC flows in one direction with a relatively constant voltage.

Many electronic devices operate internally using DC power.

### Conversion Example

```text
Wall outlet AC power
→ Power supply
→ Converts AC to DC
→ Router or switch operates
```

---

## Power Problems

| Power Problem | Meaning |
| ------------- | ------- |
| Outage | Complete loss of electrical power |
| Brownout | Voltage drops below the expected level |
| Surge | Voltage rises above the expected level |
| Spike | Brief sudden increase in voltage |

---

## UPS

UPS stands for:

```text
Uninterruptible Power Supply
```

A UPS provides temporary battery-backed power when the primary power source fails.

### UPS Benefits

- Keeps equipment running during outages
- Supports graceful shutdown
- Reduces downtime
- Helps compensate for brownouts
- Helps manage surges
- Supports business continuity

### Common Protected Devices

- Routers
- Switches
- Firewalls
- Servers
- Wireless LAN controllers
- Storage systems

---

## Standby UPS

A standby UPS is also called:

```text
Offline UPS
```

It waits until primary power fails before switching to battery power.

### Characteristics

- Lower cost
- Simple design
- Small transfer delay
- Suitable for less-sensitive equipment

### Limitation

A brief transfer delay may cause some devices to reboot.

---

## Line-Interactive UPS

A line-interactive UPS can adjust voltage when power levels fluctuate.

### Characteristics

- Better brownout handling
- Voltage regulation
- More capable than standby UPS
- Common for network closets and smaller environments

### Example

```text
Voltage drops
→ UPS compensates
→ Connected device continues operating
```

---

## Online UPS

An online UPS is also called:

```text
Double-conversion UPS
```

Connected devices continuously receive conditioned power through the UPS conversion process.

### Characteristics

- Strongest protection
- No transfer delay during outage
- Common in data centers
- Higher cost
- Suitable for critical systems

### Simplified Flow

```text
Incoming AC
→ Converted to DC
→ Battery system
→ Converted back to AC
→ Connected equipment
```

---

## UPS Comparison

| UPS Type | Also Called | Main Benefit | Main Limitation | Common Use |
| -------- | ----------- | ------------ | --------------- | ---------- |
| Standby | Offline | Lower cost | Small transfer delay | Home or less-sensitive equipment |
| Line-interactive | Line-interactive | Voltage regulation | Less protection than online UPS | Network closets and small offices |
| Online | Double-conversion | Continuous protection and no transfer delay | Higher cost | Data centers and critical infrastructure |

---

## PDU

PDU stands for:

```text
Power Distribution Unit
```

A PDU distributes power to equipment mounted inside a rack.

### Common Connected Equipment

- Routers
- Switches
- Firewalls
- Servers
- Storage appliances
- Wireless controllers

---

## Intelligent PDU

An intelligent PDU may include:

- Ethernet connection
- IP address
- Web-based management
- Remote monitoring
- Outlet-level control
- Remote power cycling
- Usage reporting
- Alerting

### Example

```text
Administrator
→ Connects to managed PDU
→ Selects outlet
→ Powers device off
→ Powers device back on
```

---

## UPS vs. PDU

| Device | Primary Purpose |
| ------ | --------------- |
| UPS | Provides battery-backed power and power conditioning |
| PDU | Distributes power to rack-mounted equipment |
| Intelligent PDU | Distributes power and provides remote outlet management |

### Key Takeaway

```text
UPS = Backup power
PDU = Power distribution
```

---

## Cloud Engineering Connection

Cloud engineers still need power-infrastructure knowledge when supporting:

- Data centers
- Colocation facilities
- Private cloud
- Edge computing
- Branch offices
- Hybrid cloud environments
- Disaster recovery
- Network closets
- High availability
- Remote power management

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Electrical-current flow | Amps |
| Electrical pressure | Volts |
| Power usage | Watts |
| `W = V × A` | Watt calculation |
| Wall-outlet current | AC |
| One-direction current used by electronics | DC |
| Reduced voltage | Brownout |
| Increased voltage | Surge |
| Battery-backed power | UPS |
| Lowest-cost UPS with transfer delay | Standby or offline UPS |
| Voltage regulation | Line-interactive UPS |
| Continuous protected power | Online or double-conversion UPS |
| Rack power distribution | PDU |
| Remotely restart device through power outlet | Intelligent PDU |

---

## Memory Trick

```text
Amps  = Flow
Volts = Pressure
Watts = Power

W = V × A

UPS = Backup power
PDU = Distribute power

Standby UPS = Waits
Line-interactive UPS = Adjusts
Online UPS = Always protects
```

---

## Practice Questions

### 1. What does an amp measure?

Answer: The rate of electrical-current flow.

### 2. What does voltage measure?

Answer: Electrical pressure.

### 3. What does a watt measure?

Answer: Electrical power usage.

### 4. What formula calculates watts?

Answer:

```text
W = V × A
```

### 5. How many watts are used by a device drawing `0.5 A` from a `120 V` source?

Answer:

```text
120 × 0.5 = 60 W
```

### 6. What does AC stand for?

Answer:

```text
Alternating Current
```

### 7. What does DC stand for?

Answer:

```text
Direct Current
```

### 8. What is a brownout?

Answer: A reduction in voltage below the expected level.

### 9. What is a surge?

Answer: An increase in voltage above the expected level.

### 10. What does UPS stand for?

Answer:

```text
Uninterruptible Power Supply
```

### 11. Which UPS type provides continuous protected power with no transfer delay?

Answer:

```text
Online or double-conversion UPS
```

### 12. What does PDU stand for?

Answer:

```text
Power Distribution Unit
```

### 13. What is the difference between a UPS and a PDU?

Answer: A UPS provides battery-backed power and power conditioning, while a PDU distributes electrical power to rack-mounted equipment.
