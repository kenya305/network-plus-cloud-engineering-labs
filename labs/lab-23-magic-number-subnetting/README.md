# Lab 23: Magic Number Subnetting

## Objective

Practice using the magic-number method to calculate subnet IDs, broadcast addresses, and usable-host ranges.

## Scenario

A cloud engineer or network administrator may need to calculate subnet boundaries quickly while designing or troubleshooting IPv4 networks.

This lab applies the magic-number shortcut to realistic examples and verifies the results using Python.

---

## Magic-Number Formula

```text
Magic number = 256 - Interesting-octet subnet-mask value
```

---

## Common Magic Numbers

| Interesting-Octet Mask | Magic Number |
| ---------------------- | ------------ |
| `128` | `128` |
| `192` | `64` |
| `224` | `32` |
| `240` | `16` |
| `248` | `8` |
| `252` | `4` |
| `254` | `2` |
| `255` | `1` |

---

## Exercise 1: 165.245.77.14 with Mask 255.255.240.0

```text
Interesting octet: Third octet
Magic number:      256 - 240 = 16
Matching range:    64–79
Subnet ID:         165.245.64.0
Broadcast:         165.245.79.255
First usable host: 165.245.64.1
Last usable host:  165.245.79.254
```

---

## Exercise 2: 10.180.122.244 with Mask 255.248.0.0

```text
Interesting octet: Second octet
Magic number:      256 - 248 = 8
Matching range:    176–183
Subnet ID:         10.176.0.0
Broadcast:         10.183.255.255
First usable host: 10.176.0.1
Last usable host:  10.183.255.254
```

---

## Exercise 3: 172.16.242.133/27

```text
/27 mask:           255.255.255.224
Interesting octet: Fourth octet
Magic number:      256 - 224 = 32
Matching range:    128–159
Subnet ID:         172.16.242.128
Broadcast:         172.16.242.159
First usable host: 172.16.242.129
Last usable host:  172.16.242.158
```

---

## Exercise 4: Select a Prefix for 40 Hosts

| CIDR Prefix | Subnet Mask | Subnets | Usable Hosts per Subnet |
| ----------- | ----------- | ------- | ----------------------- |
| `/25` | `255.255.255.128` | `2` | `126` |
| `/26` | `255.255.255.192` | `4` | `62` |
| `/27` | `255.255.255.224` | `8` | `30` |

Best choice:

```text
/26
```

because it provides:

```text
62 usable hosts per subnet
```

---

## Terminal Verification Command

Run:

```bash
python3 - <<'PY'
import ipaddress

examples = [
    "165.245.77.14/20",
    "10.180.122.244/13",
    "172.16.242.133/27",
]

for cidr in examples:
    interface = ipaddress.IPv4Interface(cidr)
    network = interface.network

    print(f"Input: {cidr}")
    print(f"Netmask: {network.netmask}")
    print(f"Network: {network.network_address}/{network.prefixlen}")
    print(f"Broadcast: {network.broadcast_address}")
    print(f"First usable host: {network.network_address + 1}")
    print(f"Last usable host: {network.broadcast_address - 1}")
    print("-" * 40)

print("Host-capacity comparison:")
for prefix in [25, 26, 27]:
    host_bits = 32 - prefix
    usable_hosts = (2 ** host_bits) - 2
    print(f"/{prefix}: {usable_hosts} usable hosts")
PY
```

---

## Terminal Output

```text
Input: 165.245.77.14/20
Netmask: 255.255.240.0
Network: 165.245.64.0/20
Broadcast: 165.245.79.255
First usable host: 165.245.64.1
Last usable host: 165.245.79.254
----------------------------------------
Input: 10.180.122.244/13
Netmask: 255.248.0.0
Network: 10.176.0.0/13
Broadcast: 10.183.255.255
First usable host: 10.176.0.1
Last usable host: 10.183.255.254
----------------------------------------
Input: 172.16.242.133/27
Netmask: 255.255.255.224
Network: 172.16.242.128/27
Broadcast: 172.16.242.159
First usable host: 172.16.242.129
Last usable host: 172.16.242.158
----------------------------------------
Host-capacity comparison:
/25: 126 usable hosts
/26: 62 usable hosts
/27: 30 usable hosts
```

---

## Verification Analysis

| Input | Actual Network | Netmask | Broadcast Address | First Usable Host | Last Usable Host | Status |
| ----- | -------------- | ------- | ----------------- | ----------------- | ---------------- | ------ |
| `165.245.77.14/20` | `165.245.64.0/20` | `255.255.240.0` | `165.245.79.255` | `165.245.64.1` | `165.245.79.254` | Verified |
| `10.180.122.244/13` | `10.176.0.0/13` | `255.248.0.0` | `10.183.255.255` | `10.176.0.1` | `10.183.255.254` | Verified |
| `172.16.242.133/27` | `172.16.242.128/27` | `255.255.255.224` | `172.16.242.159` | `172.16.242.129` | `172.16.242.158` | Verified |

---

## Host-Capacity Analysis

| CIDR Prefix | Usable Hosts | Supports at Least 40 Hosts? |
| ----------- | ------------ | --------------------------- |
| `/25` | `126` | Yes |
| `/26` | `62` | Yes |
| `/27` | `30` | No |

The most efficient choice that supports at least `40` usable hosts is:

```text
/26
```

---

## What I Observed

The Python verification confirmed the magic-number calculations.

The magic-number method quickly identified each subnet boundary without requiring full binary conversion.

The key formula is:

```text
Magic number = 256 - Interesting-octet subnet-mask value
```

The subnet ID is the first address in the matching range.

The broadcast address is:

```text
Subnet-ID interesting-octet value + magic number - 1
```

The first usable host is:

```text
Subnet ID + 1
```

The last usable host is:

```text
Broadcast address - 1
```

For a network requiring at least `40` usable host addresses, `/26` is the most efficient choice because it provides:

```text
62 usable hosts
```

---

## Important Limitation

The magic-number method is a shortcut.

Understanding CIDR notation, subnet masks, binary math, and subnet boundaries remains important.

Special-purpose cases such as `/31` point-to-point links and `/32` host routes should be evaluated separately.

---

## Cloud Engineering Connection

Cloud engineers use subnet calculations when planning:

- Virtual private clouds
- Virtual networks
- Public subnets
- Private subnets
- Database subnets
- Application subnets
- Route tables
- NAT gateways
- Security groups
- VPN connections
- Hybrid cloud networks
- Kubernetes networks
- IP-address allocation plans

---

## Skills Practiced

- Identifying the interesting octet
- Calculating the magic number
- Identifying subnet ranges
- Calculating subnet IDs
- Calculating broadcast addresses
- Calculating usable-host ranges
- Selecting CIDR prefixes based on host requirements
- Using Python to verify subnet boundaries
- Connecting subnetting shortcuts to cloud-network planning
