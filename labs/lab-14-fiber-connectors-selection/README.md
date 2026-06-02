# Lab 14: Fiber Connectors Selection

## Objective

Compare SC, LC, ST, and MPO fiber connectors to identify the appropriate connector type for different network-infrastructure requirements.

## Scenario

A cloud engineer or network administrator may need to identify or select a fiber connector when installing, documenting, or troubleshooting network equipment.

The correct connector depends on:

- Device interface
- Connector size
- Locking mechanism
- Number of fibers
- Rack-space requirements
- Equipment compatibility

---

## Fiber Connector Comparison

| Connector | Full Name | Alternate Name | Locking Mechanism | Main Characteristic |
| --------- | --------- | -------------- | ----------------- | ------------------- |
| SC | Subscriber Connector | Square Connector, Standard Connector | Push-and-lock | Common square fiber connector |
| LC | Local Connector | Lucent Connector, Little Connector | Clip-lock | Smaller compact connector |
| ST | Straight Tip | None | Bayonet twist-lock | Round connector that locks with a twist |
| MPO | Multi-Fiber Push On | MTP may refer to branded version | Push-and-lock | Multiple fibers inside one compact connector |

---

## Scenario Analysis

### Scenario 1: Common Square Fiber Connector

A technician needs a common square-shaped fiber connector that pushes into place and locks.

**Recommended connector:**

```text
SC
```

**Reason:**

SC is commonly known as the Subscriber Connector or Square Connector.

It uses a push-and-lock mechanism.

---

### Scenario 2: Compact Connector for Limited Space

A technician needs a smaller fiber connector with a clip-lock mechanism.

**Recommended connector:**

```text
LC
```

**Reason:**

LC is smaller than SC and uses a clip on top to lock into the interface.

---

### Scenario 3: Twist-Lock Fiber Connector

A technician needs a round fiber connector that locks into place with a slight twist.

**Recommended connector:**

```text
ST
```

**Reason:**

ST stands for Straight Tip and uses a bayonet twist-lock mechanism.

---

### Scenario 4: High-Density Fiber Connection

A data-center rack needs a compact connector that carries multiple fibers.

**Recommended connector:**

```text
MPO
```

**Reason:**

MPO stands for Multi-Fiber Push On.

It can combine multiple fibers into one compact connector.

The lesson shows an MPO connector with:

```text
12 fibers
```

---

## Connector Locking Mechanisms

| Connector | Locking Mechanism |
| --------- | ----------------- |
| SC | Push-and-lock |
| LC | Clip-lock |
| ST | Bayonet twist-lock |
| MPO | Push-and-lock |

---

## Paired Fiber Connections

SC and LC connectors may be combined into pairs.

One connector is commonly used for:

```text
Transmit
```

The other connector is commonly used for:

```text
Receive
```

---

## What I Observed

Fiber connectors are designed for different equipment, density, and locking requirements.

SC is a square connector with a push-and-lock mechanism.

LC is a smaller connector with a clip-lock mechanism.

ST is a round connector with a bayonet twist-lock mechanism.

MPO supports multiple fibers inside one compact connector and is useful for high-density environments.

---

## Important Limitation

A fiber connector should not be selected based only on its appearance.

Before installing fiber cabling, verify:

- Device interface
- Connector type
- Fiber type
- Number of fibers
- Transmit and receive requirements
- Transceiver compatibility
- Cable specification
- Equipment documentation

---

## Cloud Engineering Connection

Cloud engineers need to understand fiber connectors when supporting:

- Data centers
- Fiber-optic uplinks
- Server racks
- Network switches
- Storage networks
- High-density connections
- Hybrid cloud infrastructure
- Transceivers
- Physical-layer troubleshooting
- Network installations

Understanding fiber connectors helps engineers identify compatibility requirements and troubleshoot physical network connections.

---

## Skills Practiced

- Comparing SC, LC, ST, and MPO connectors
- Recognizing connector shapes
- Identifying locking mechanisms
- Understanding paired transmit and receive connections
- Identifying high-density MPO use cases
- Connecting fiber connectors to data-center infrastructure
- Applying connector-selection concepts to realistic scenarios
- Documenting networking concepts in GitHub
