````markdown
# Lab 11: Optical Fiber Comparison

## Objective

Compare multimode and single-mode fiber-optic cabling to determine which option is appropriate for different networking requirements.

## Scenario

A cloud engineer or network administrator may need to select fiber-optic cabling for different infrastructure environments.

This lab compares multimode and single-mode fiber and applies each type to realistic networking scenarios.

---

## Fiber-Optic Cable Components

| Component | Purpose |
| --------- | ------- |
| Light source | Sends light through the fiber |
| Core | Central path where light travels |
| Cladding | Surrounds the core and helps reflect light back into the core |
| Buffer coating | Protects the fiber cable |
| Receiver | Receives the light signal |
| Ferrule | Protects and aligns the fiber at the connector end |

---

## Multimode Fiber

### Characteristics

| Feature | Multimode Fiber |
| ------- | --------------- |
| Number of light paths | Multiple |
| Core size | Larger |
| Common distance | Shorter-distance fiber connections |
| Example maximum distance from video | Approximately `2 km` |
| Common light source | LED |
| Typical use | Building-level or campus-level links |

### Summary

```text
Multimode fiber
→ Multiple light paths
→ Larger core
→ Shorter-distance connection
→ Commonly uses LED
```

---

## Single-Mode Fiber

### Characteristics

| Feature | Single-Mode Fiber |
| ------- | ----------------- |
| Number of light paths | One |
| Core size | Smaller |
| Common distance | Longer-distance fiber connections |
| Example maximum distance from video | Some standards support up to approximately `100 km` |
| Common light source | Laser or high-intensity light source |
| Typical use | Long-distance network links |

### Summary

```text
Single-mode fiber
→ One light path
→ Smaller core
→ Longer-distance connection
→ Commonly uses laser
```

---

## Multimode vs. Single-Mode Comparison

| Feature | Multimode Fiber | Single-Mode Fiber |
| ------- | --------------- | ----------------- |
| Number of light paths | Multiple | One |
| Core size | Larger | Smaller |
| Typical distance | Shorter | Longer |
| Example distance from video | Approximately `2 km` | Some standards up to approximately `100 km` |
| Common light source | LED | Laser or high-intensity light source |
| Typical environment | Building or campus | Long-distance infrastructure |

---

## Scenario Analysis

### Scenario 1: Office Building Connection

A company needs a fiber-optic connection between network closets inside the same building.

**Recommended fiber type:**

```text
Multimode fiber
```

**Reason:**

Multimode fiber is appropriate for shorter-distance connections and commonly uses an LED light source.

---

### Scenario 2: Long-Distance Connection Between Facilities

A company needs to connect two facilities across a long distance.

**Recommended fiber type:**

```text
Single-mode fiber
```

**Reason:**

Single-mode fiber supports longer-distance network links using a smaller core and a focused light path.

---

### Scenario 3: High-Interference Environment

A company needs network connectivity near industrial equipment that creates radio-frequency interference.

**Recommended media type:**

```text
Fiber optic
```

**Reason:**

Fiber-optic cabling uses light and is not affected by radio-frequency interference.

---

### Scenario 4: Secure Network Link

A company needs a more secure physical network connection that is difficult to tap without detection.

**Recommended media type:**

```text
Fiber optic
```

**Reason:**

Fiber-optic connections are more difficult to tap without creating a detectable disruption.

---

## What I Observed

Fiber-optic cabling can support longer distances and avoid radio-frequency interference.

Multimode fiber uses multiple light paths through a larger core and is commonly used for shorter-distance connections.

Single-mode fiber uses one light path through a smaller core and is commonly used for longer-distance connections.

---

## Important Limitation

The correct fiber-optic cable depends on the specific networking standard, distance requirement, connector type, transceiver, and device compatibility.

A network engineer should verify the equipment documentation before selecting fiber cabling.

---

## Cloud Engineering Connection

Cloud engineers need to understand fiber optics when working with:

- Data centers
- Hybrid cloud infrastructure
- Server racks
- Network switches
- Campus networks
- Long-distance connections
- High-speed uplinks
- Secure network environments
- High-interference locations
- Backup network paths

Understanding the differences between multimode and single-mode fiber helps engineers select compatible cabling and troubleshoot connectivity issues.

---

## Skills Practiced

- Identifying fiber-optic cable components
- Comparing multimode and single-mode fiber
- Identifying appropriate fiber use cases
- Recognizing the role of LEDs and lasers
- Understanding radio-frequency interference
- Applying fiber-optic concepts to realistic infrastructure scenarios
- Documenting networking concepts in GitHub
````
