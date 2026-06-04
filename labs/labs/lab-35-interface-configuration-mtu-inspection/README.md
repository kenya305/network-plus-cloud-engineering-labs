# Lab 35: Interface Configuration and MTU Inspection

## Objective

Inspect a Mac network interface and document interface status, MTU, IPv4 configuration, and IPv6 behavior.

## Scenario

A cloud engineer or network administrator may need to validate interface settings during troubleshooting.

This lab uses macOS Terminal commands to inspect the active Wi-Fi interface without changing any network settings.

---

## Commands Used

```bash
networksetup -getinfo Wi-Fi
ifconfig en0
networksetup -getMTU Wi-Fi
```

### Command Breakdown

| Command | Meaning |
| ------- | ------- |
| `networksetup -getinfo Wi-Fi` | Displays Wi-Fi IP configuration |
| `ifconfig en0` | Displays detailed interface information for `en0` |
| `networksetup -getMTU Wi-Fi` | Displays the active Wi-Fi MTU setting |
| `en0` | Active network interface used in this lab |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran:

```bash
networksetup -getinfo Wi-Fi
```

3. Reviewed:
   - IPv4 address
   - Subnet mask
   - Default gateway
   - IPv6 configuration mode
4. Ran:

```bash
ifconfig en0
```

5. Reviewed:
   - Interface status
   - MTU
   - IPv4 configuration
   - IPv6 addresses
   - Media setting
6. Ran:

```bash
networksetup -getMTU Wi-Fi
```

7. Confirmed the MTU value.
8. Redacted sensitive details before publishing.

---

## Wi-Fi Configuration Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % networksetup -getinfo Wi-Fi
DHCP Configuration
IP address: [REDACTED PRIVATE IP]
Subnet mask: 255.255.255.0
Router: [REDACTED PRIVATE GATEWAY]
Client ID:
IPv6: Automatic
IPv6 IP address: none
IPv6 Router: none
Wi-Fi ID: [REDACTED WI-FI HARDWARE ID]
```

---

## Interface Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % ifconfig en0
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
    options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
    ether [REDACTED MAC ADDRESS]
    inet6 [REDACTED LINK-LOCAL IPV6 ADDRESS] prefixlen 64 secured
    inet6 [REDACTED GLOBAL IPV6 ADDRESS] prefixlen 64 autoconf secured
    inet6 [REDACTED TEMPORARY IPV6 ADDRESS] prefixlen 64 autoconf temporary
    inet6 [REDACTED DYNAMIC IPV6 ADDRESS] prefixlen 64 dynamic
    inet [REDACTED PRIVATE IP] netmask 0xffffff00 broadcast [REDACTED BROADCAST ADDRESS]
    nd6 options=201<PERFORMNUD,DAD>
    media: autoselect
    status: active
```

---

## MTU Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % networksetup -getMTU Wi-Fi
Active MTU: 1500 (Current Setting: 1500)
```

---

## Interface Analysis

| Interface Detail | Result |
| ---------------- | ------ |
| Active interface | `en0` |
| Interface status | `active` |
| Interface flags | `UP`, `RUNNING`, `BROADCAST`, `MULTICAST` |
| MTU | `1500 bytes` |
| IPv4 address | `[REDACTED PRIVATE IP]` |
| Subnet mask | `255.255.255.0` |
| Default gateway | `[REDACTED PRIVATE GATEWAY]` |
| IPv4 assignment method | DHCP |
| IPv6 configuration mode | Automatic |
| IPv6 status | IPv6 addresses present on `en0` |
| Media setting | `autoselect` |

---

## IPv6 Observation

The `networksetup -getinfo Wi-Fi` output displayed:

```text
IPv6: Automatic
IPv6 IP address: none
IPv6 Router: none
```

The more detailed `ifconfig en0` output displayed several IPv6 addresses.

This demonstrates that different macOS commands may summarize interface information differently.

For detailed interface validation, review:

```text
ifconfig en0
```

alongside:

```text
networksetup -getinfo Wi-Fi
```

---

## MTU Observation

The interface MTU was:

```text
1500 bytes
```

This matches the standard Ethernet MTU discussed in the lesson.

```text
Standard Ethernet MTU
→ 1500 bytes
```

---

## Speed and Duplex Note

This lab used the active Wi-Fi interface.

The Wi-Fi output confirmed:

```text
media: autoselect
status: active
```

Ethernet speed and duplex troubleshooting remains important for wired links.

```text
Speed mismatch
→ Link may fail

Duplex mismatch
→ Link may remain active but perform poorly
```

---

## Part 2: Link Aggregation Analysis

### Scenario

Two switches need more bandwidth and redundancy.

Each switch has four available 1 Gbps interfaces.

### Recommended Design

```text
Four 1 Gbps links
→ Configure as LAG
→ Negotiate with LACP
→ Treat as one logical connection
```

### Expected Aggregate Throughput

```text
Up to 4 Gbps
```

### Key Takeaway

```text
LACP helps form and manage a link aggregation group.
```

---

## Part 3: Jumbo-Frame Analysis

### Standard Ethernet MTU

```text
1500 bytes
```

### Jumbo-Frame Example

```text
9000 bytes
```

Some platforms support jumbo-frame MTU values up to:

```text
9216 bytes
```

### Requirement

```text
Source
Destination
Switches
Routers
Firewalls
Virtual switches
→ Must all support the configured MTU
```

### Risk

```text
MTU mismatch
→ Dropped frames
→ Connectivity issues
→ Performance problems
```

---

## What I Observed

The active interface was:

```text
en0
```

The interface status was:

```text
active
```

The active MTU was:

```text
1500 bytes
```

The interface used DHCP for IPv4 addressing and automatic IPv6 configuration.

The detailed interface output showed that IPv6 addresses were present even though the higher-level Wi-Fi summary did not list a specific IPv6 address.

Link aggregation can combine multiple physical links into one logical link.

LACP helps negotiate and manage that link aggregation automatically.

Jumbo frames can improve bulk-transfer efficiency, but every device in the path must support the larger MTU.

---

## Privacy Note

Sensitive local-network details were redacted before publishing this lab.

The following values were removed or generalized:

- Full private IPv4 address
- Full private gateway address
- MAC address
- Wi-Fi hardware identifier
- IPv6 addresses
- Broadcast address

The redacted output still demonstrates the interface configuration concepts without exposing unnecessary local-network details.

---

## Important Limitation

This lab inspects network-interface configuration.

It does not modify:

- Speed
- Duplex
- MTU
- IP configuration
- DNS configuration
- Link aggregation

Interface syntax varies across operating systems and network vendors.

---

## Cloud Engineering Connection

Cloud engineers use interface-configuration concepts when supporting:

- Virtual network interfaces
- Cloud instances
- Kubernetes nodes
- Container networking
- VPN tunnels
- Storage networks
- Data-center uplinks
- Hybrid cloud links
- Load balancers
- SDN platforms
- Network troubleshooting

---

## Skills Practiced

- Inspecting a network interface
- Reviewing DHCP-based IPv4 configuration
- Reviewing IPv6 configuration
- Reviewing MTU settings
- Identifying interface status
- Explaining speed and duplex mismatches
- Explaining LAG
- Explaining LACP
- Explaining jumbo frames
- Connecting interface configuration to cloud engineering
- Redacting sensitive network details before publishing
