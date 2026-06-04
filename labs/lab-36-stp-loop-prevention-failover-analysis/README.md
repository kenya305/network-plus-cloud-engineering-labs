# Lab 36: STP Loop Prevention and Failover Analysis

## Objective

Analyze how Spanning Tree Protocol prevents Layer 2 loops and how Rapid Spanning Tree Protocol improves recovery after a link failure.

## Scenario

A company connects two switches using redundant Ethernet links.

The company wants resiliency, but it must prevent a Layer 2 switching loop.

---

## Part 1: Loop Risk

### Unsafe Design Without STP

```text
Switch A
├── Link 1
└── Link 2

Both links connect to:

Switch B
```

### Result

```text
Ethernet frames circulate repeatedly
→ More traffic appears
→ Switch resources become overwhelmed
→ Network outage
```

```text
Redundant Layer 2 paths require loop prevention.
```

---

## Part 2: STP Solution

### Safe Design With STP

```text
Switch A
├── Link 1 → Forwarding
└── Link 2 → Blocked

Switch B
```

### Result

```text
One active forwarding path
+
One blocked standby path
=
Redundancy without switching loop
```

---

## Part 3: Classic STP Port States

| Port State | Purpose |
| ---------- | ------- |
| Blocking | Prevents forwarding loops |
| Listening | Processes STP information and prepares for transition |
| Learning | Learns MAC addresses before forwarding |
| Forwarding | Sends and receives normal traffic |
| Disabled | Does not participate |

---

## Part 4: STP Port Roles

| Role | Purpose |
| ---- | ------- |
| Root bridge | Central reference switch |
| Root port | Best path toward root bridge |
| Designated port | Active forwarding port for a segment |
| Blocked port | Redundant standby path |

---

## Part 5: Failover Scenario

### Normal Operation

```text
Primary link
→ Forwarding

Backup link
→ Blocked
```

### Failure

```text
Primary link fails
→ STP detects topology change
→ Network relearns topology
→ Backup path transitions to forwarding
→ Connectivity resumes
```

```text
STP preserves availability while avoiding loops.
```

---

## Part 6: STP vs. RSTP

| Feature | STP | RSTP |
| ------- | --- | ---- |
| Full name | Spanning Tree Protocol | Rapid Spanning Tree Protocol |
| Standard | `IEEE 802.1D` | `IEEE 802.1w` |
| Main purpose | Prevent Layer 2 loops | Prevent loops and converge faster |
| Approximate convergence | `30–50 seconds` | Around `6 seconds` |
| Backward compatibility | Baseline | Compatible with classic STP environments |

---

## Part 7: RSTP State Comparison

| Classic STP States | RSTP Equivalent |
| ------------------ | --------------- |
| Blocking | Discarding |
| Listening | Discarding |
| Learning | Learning |
| Forwarding | Forwarding |
| Disabled | Discarding |

---

## Part 8: Troubleshooting Scenario

### Symptom

```text
Users suddenly lose connectivity
Switch utilization spikes
Network slows dramatically
```

### Possible Cause

```text
Layer 2 switching loop
```

### Immediate Response

```text
Identify recently connected redundant cable
→ Remove unsafe link
→ Confirm network stability
→ Verify STP or RSTP configuration
```

---

## What I Observed

Layer 2 loops are dangerous because Ethernet frames do not have a hop counter.

STP prevents loops by blocking redundant forwarding paths.

RSTP improves recovery time by converging more quickly after a topology change.

A blocked path is not wasted.

It remains available as a backup path if the active path fails.

---

## Important Limitation

STP and RSTP reduce Layer 2 loop risk, but a network engineer should still evaluate:

- Root-bridge placement
- Redundant-link design
- Port configuration
- Trunk configuration
- VLAN topology
- Loop-protection features
- Monitoring
- Logging
- Change control
- Physical cabling

---

## Cloud Engineering Connection

Cloud engineers use STP concepts when supporting:

- Data-center switching
- Redundant network links
- Colocation environments
- Layer 2 extensions
- Private cloud infrastructure
- Hybrid-cloud connections
- Virtual-switch designs
- High availability
- Network troubleshooting

---

## Skills Practiced

- Identifying a Layer 2 switching loop
- Explaining broadcast storms
- Explaining STP
- Identifying STP port states
- Identifying root, designated, and blocked ports
- Explaining failover
- Comparing STP and RSTP
- Connecting loop prevention to cloud engineering
