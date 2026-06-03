# Lab 12: Copper Cabling Selection

## Objective

Compare twisted-pair copper, coaxial, twinax, and plenum-rated cabling to select the correct cable type for different networking requirements.

## Scenario

A cloud engineer or network administrator may need to recommend cabling for office networks, cable internet connections, data-center links, and building infrastructure.

This lab applies copper-cabling concepts to realistic networking scenarios.

---

## Copper Cable Types Comparison

| Cable Type | Description | Common Use |
| ---------- | ----------- | ---------- |
| Twisted-pair copper | Multiple wire pairs twisted together inside one sheath | Wired Ethernet LAN connections |
| Coaxial cable | Center conductor with insulation, shielding, and protective jacket sharing one axis | Cable internet connections |
| RG-6 | Common coaxial cable type | Cable modem connections |
| Twinax | Two-conductor short-distance cable | High-speed `10 Gbps` connections using `SFP+` |
| Plenum-rated cable | Cable with fire-safer outer jacket material | Shared air spaces |

---

## Scenario Analysis

### Scenario 1: Office Workstation Connection

A workstation needs a wired connection to an Ethernet switch.

**Recommended cable type:**

```text
Twisted-pair copper
```

**Reason:**

Twisted-pair copper is commonly used for wired Ethernet LAN connections.

---

### Scenario 2: Cable Modem Internet Connection

A company needs to connect a cable modem to an internet-service-provider connection.

**Recommended cable type:**

```text
RG-6 coaxial cable
```

**Reason:**

RG-6 coaxial cable is commonly used for cable modem and broadband internet connections.

---

### Scenario 3: Short-Distance High-Speed Server Link

A company needs a short-distance `10 Gbps` connection between devices inside a server rack.

**Recommended cable type:**

```text
Twinax
```

**Reason:**

Twinax supports short-distance, high-speed Ethernet connections and is commonly associated with `SFP+` interfaces.

---

### Scenario 4: Cable Installed Inside Shared Ceiling Air Space

A company needs to install network cabling above a drop ceiling where the open space circulates building air.

**Recommended cable type:**

```text
Plenum-rated cable
```

**Reason:**

Plenum-rated cabling uses materials designed to reduce smoke and hazardous fumes during a fire.

---

## Twisted-Pair Signal Explanation

Twisted-pair cabling commonly carries related signal pairs.

Examples include:

```text
Transmit positive
Transmit negative

Receive positive
Receive negative
```

The twists help reduce interference.

Different wire pairs may use different twist rates.

---

## Ethernet Standard Connection

The Ethernet standard defines the minimum cable category and expected throughput.

### Example

```text
1000BASE-T
→ Minimum Category 5 cabling
→ 1 Gbps Ethernet
```

### Key Takeaway

```text
The cable supports the signal.
The Ethernet standard defines the speed.
```

---

## Plenum Space Explanation

A plenum is a shared air space inside a building.

Examples may include:

- Space above a drop ceiling
- Space below a raised floor
- Open area used for air circulation

### Important Note

A ceiling space is not automatically a plenum.

If the open space carries shared air, plenum-rated cable may be required.

---

## What I Observed

Different cable types are designed for different infrastructure requirements.

Twisted-pair copper is commonly used for local Ethernet connections.

RG-6 coaxial cable is commonly used for cable modem connections.

Twinax is appropriate for short-distance, high-speed links.

Plenum-rated cable is required when cabling runs through shared air spaces.

---

## Important Limitation

The correct copper cable depends on:

- Ethernet standard
- Cable category
- Distance requirement
- Connector type
- Building code
- Fire-safety requirements
- Device compatibility
- Network throughput requirement

A network engineer should review the applicable IEEE standard and building requirements before installation.

---

## Cloud Engineering Connection

Cloud engineers need to understand copper cabling when supporting:

- Data centers
- Server racks
- Network switches
- Wireless access points
- Hybrid cloud infrastructure
- Branch offices
- Cable modem connections
- Building infrastructure
- Short-distance high-speed links

Understanding copper-cabling options helps engineers select compatible hardware and troubleshoot network performance.

---

## Skills Practiced

- Comparing copper cable types
- Identifying twisted-pair copper use cases
- Identifying RG-6 coaxial cable use cases
- Identifying twinax use cases
- Recognizing `SFP+` connections
- Understanding plenum-rated cabling
- Applying cabling concepts to realistic infrastructure scenarios
- Documenting networking concepts in GitHub
````
