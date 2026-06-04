# Network+ N10-009 Study Notes: Spanning Tree Protocol

## Video Topic

Spanning Tree Protocol

## Summary

Spanning Tree Protocol, or STP, prevents Layer 2 switching loops.

A switching loop can occur when redundant Ethernet links create more than one active path between switches. Ethernet frames do not include a Layer 2 hop counter, so looping traffic can multiply until switches become overwhelmed.

This lesson covers:

- Switching loops
- Broadcast storms
- IEEE 802.1D
- STP port states
- Root bridge
- Root ports
- Designated ports
- Blocked ports
- Topology changes
- Convergence
- Rapid Spanning Tree Protocol
- IEEE 802.1w

---

## Why Switching Loops Are Dangerous

```text
Switch A
→ Cable 1
→ Switch B

Switch A
→ Cable 2
→ Switch B
```

If both links forward traffic normally:

```text
Frame loops
→ More traffic appears
→ Switch resources are overwhelmed
→ Users lose connectivity
```

### Key Takeaway

```text
Layer 2 loops can take down a network within seconds.
```

---

## Broadcast Storm

A broadcast storm occurs when broadcast or flooded Ethernet traffic circulates repeatedly and consumes network capacity.

### Symptoms

- Network slows dramatically
- Switch CPU utilization increases
- Interfaces become saturated
- Users lose connectivity

```text
Switching loop
→ Broadcast storm
→ Network outage
```

---

## STP

STP stands for:

```text
Spanning Tree Protocol
```

The classic STP standard is:

```text
IEEE 802.1D
```

STP prevents loops by placing selected switch ports into a non-forwarding state.

```text
STP = Prevents Layer 2 switching loops
```

---

## How STP Prevents Loops

```text
1. Switches exchange STP information.
2. STP identifies the network topology.
3. STP selects one root bridge.
4. STP determines best forwarding paths.
5. Redundant ports are blocked.
6. If an active path fails, STP recalculates.
7. A blocked path may become active.
```

```text
STP keeps redundancy while preventing duplicate forwarding paths.
```

---

## Classic STP Port States

| Port State | Purpose |
| ---------- | ------- |
| Blocking | Does not forward user traffic; prevents loops |
| Listening | Processes STP information and prepares for topology changes |
| Learning | Learns MAC addresses but does not yet forward user traffic |
| Forwarding | Sends and receives normal network traffic |
| Disabled | Administratively unavailable |

```text
Blocking
→ Listening
→ Learning
→ Forwarding
```

---

## STP Bridge and Port Roles

| Role | Purpose |
| ---- | ------- |
| Root bridge | Central reference point for STP topology |
| Root port | Best path from a non-root switch toward root bridge |
| Designated port | Forwarding port selected for a network segment |
| Blocked port | Redundant port prevented from forwarding traffic |

---

## Failover Example

### Normal Operation

```text
Primary forwarding path
→ Active

Redundant path
→ Blocked
```

### Link Failure

```text
Primary path fails
→ STP detects topology change
→ STP relearns topology
→ Previously blocked path becomes active
→ Connectivity resumes
```

---

## Convergence

Convergence is the process of recalculating and applying a stable topology after a network change.

```text
Link failure
→ Topology recalculated
→ Ports transition to correct states
→ Stable forwarding resumes
```

---

## RSTP

RSTP stands for:

```text
Rapid Spanning Tree Protocol
```

The commonly referenced RSTP standard is:

```text
IEEE 802.1w
```

RSTP improves recovery speed.

| Protocol | Approximate Convergence Time |
| -------- | ---------------------------- |
| Classic STP | `30–50 seconds` |
| RSTP | Around `6 seconds` |

```text
RSTP = Faster recovery from topology changes
```

---

## RSTP Compatibility

RSTP is designed to remain compatible with classic STP environments.

```text
Older STP switch
+
Newer RSTP switch
→ Can participate in same network
```

---

## Accuracy Note

Classic STP uses:

```text
Blocking
Listening
Learning
Forwarding
Disabled
```

RSTP simplifies operational states to:

```text
Discarding
Learning
Forwarding
```

For the exam, recognize both classic STP and RSTP terminology.

---

## Cloud Engineering Connection

Cloud engineers use STP concepts when supporting:

- Data-center switching
- Hybrid cloud links
- Colocation environments
- Redundant network paths
- Top-of-rack switches
- Layer 2 extensions
- Private cloud infrastructure
- High-availability designs
- Broadcast-storm troubleshooting

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Prevent Layer 2 loops | STP |
| IEEE 802.1D | Classic STP |
| IEEE 802.1w | RSTP |
| Faster spanning-tree convergence | RSTP |
| Central reference switch | Root bridge |
| Best path toward root bridge | Root port |
| Redundant path not forwarding | Blocked port |
| Active forwarding port for segment | Designated port |
| Traffic multiplies until network fails | Broadcast storm |
| Topology recalculated after failure | Convergence |

---

## Memory Trick

```text
STP  = Stop loops
RSTP = Recover faster

Root bridge     = Central reference
Root port       = Best path toward root
Designated port = Active forwarding port
Blocked port    = Standby path
```

---

## Practice Questions

### 1. What problem does STP solve?

Answer: STP prevents Layer 2 switching loops.

### 2. Why can an Ethernet frame loop indefinitely?

Answer: Ethernet frames do not contain a Layer 2 hop-count field.

### 3. What does STP stand for?

Answer: Spanning Tree Protocol

### 4. What classic IEEE standard is associated with STP?

Answer: IEEE 802.1D

### 5. What does RSTP stand for?

Answer: Rapid Spanning Tree Protocol

### 6. What IEEE standard is associated with RSTP?

Answer: IEEE 802.1w

### 7. What is the root bridge?

Answer: The central reference switch used for STP calculations.

### 8. What is a root port?

Answer: The best path from a non-root switch toward the root bridge.

### 9. What is a blocked port?

Answer: A redundant port prevented from forwarding normal traffic so a loop does not form.

### 10. What happens after an active path fails?

Answer: STP or RSTP recalculates the topology and may activate a previously blocked path.
