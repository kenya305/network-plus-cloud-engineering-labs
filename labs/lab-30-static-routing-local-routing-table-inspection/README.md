# Lab 30: Static Routing and Local Routing Table Inspection

## Objective

Inspect the local IPv4 routing table on a Mac and document how routers use destination networks, interfaces, gateways, and next hops.

## Scenario

A cloud engineer or network administrator may need to review routing information while troubleshooting connectivity.

This lab uses macOS Terminal commands to inspect the local IPv4 routing table and identify the default route.

---

## Commands Used

```bash
netstat -rn -f inet
route -n get default
```

### Command Breakdown

| Command | Meaning |
| ------- | ------- |
| `netstat -rn -f inet` | Displays the IPv4 routing table using numeric output |
| `route -n get default` | Displays the default IPv4 route using numeric output |
| `-r` | Shows the routing table |
| `-n` | Prevents hostname resolution |
| `-f inet` | Filters for IPv4 routes |
| `default` | Route used when no more-specific route matches |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran:

```bash
netstat -rn -f inet
```

3. Reviewed the IPv4 routing table.
4. Identified:
   - Default route
   - Local subnet route
   - Gateway
   - Interface
5. Ran:

```bash
route -n get default
```

6. Reviewed the default-route details.
7. Redacted private network details and MAC addresses before publishing.

---

## Routing Table Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % netstat -rn -f inet
Routing tables

Internet:
Destination        Gateway                    Flags               Netif Expire
default            [REDACTED PRIVATE GATEWAY] UGScg                 en0
10/24              link#6                     UCS                   en0      !
10.0.0.1/32        link#6                     UCS                   en0      !
10.0.0.1           [REDACTED MAC ADDRESS]     UHLWIir               en0   1200
10.0.0.11/32       link#6                     UCS                   en0      !
10.0.0.21          [REDACTED MAC ADDRESS]     UHLWI                 en0   1152
10.0.0.62          [REDACTED MAC ADDRESS]     UHLWI                 en0   1115
127                127.0.0.1                  UCS                   lo0
127.0.0.1          127.0.0.1                  UH                    lo0
169.254            link#6                     UCS                   en0      !
169.254.169.254    link#6                     UHRLSW                en0     19
224.0.0/4          link#6                     UmCS                  en0      !
224.0.0.251        [REDACTED MAC ADDRESS]     UHmLWI                en0
239.255.255.250    [REDACTED MAC ADDRESS]     UHmLWI                en0
255.255.255.255/32 link#6                     UCS                   en0      !
```

---

## Default Route Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % route -n get default
   route to: default
destination: default
       mask: default
    gateway: [REDACTED PRIVATE GATEWAY]
  interface: en0
      flags: <UP,GATEWAY,DONE,STATIC,PRCLONING,GLOBAL>
 recvpipe  sendpipe  ssthresh  rtt,msec    rttvar  hopcount      mtu     expire
       0         0         0         0         0         0      1500         0
```

---

## Routing Table Analysis

| Routing Detail | Result |
| -------------- | ------ |
| Default route | `default` |
| Default gateway | `[REDACTED PRIVATE GATEWAY]` |
| Local IPv4 subnet | `10.0.0.0/24` |
| Network interface | `en0` |
| Default-route type | Static default route |
| Default-route status | Up and active |
| MTU | `1500` |
| Loopback interface | `lo0` |

---

## What the Default Route Means

The default route is used when no more-specific route matches the destination.

```text
Destination does not match a more-specific route
→ Send packet to default gateway
→ Use interface en0
```

The router or operating system uses the default gateway as the next hop for traffic leaving the local subnet.

---

## Local Route Interpretation

The routing table showed a local subnet route represented by macOS as:

```text
10/24
```

For this local environment, that corresponds to:

```text
10.0.0.0/24
```

This means addresses inside the local subnet can be reached directly through:

```text
en0
```

without sending the traffic to another router first.

---

## Loopback Route Interpretation

The routing table also included:

```text
127
127.0.0.1
```

These routes use:

```text
lo0
```

The `lo0` interface is the loopback interface used for local host communication.

---

## Link-Local Route Interpretation

The routing table included:

```text
169.254
```

This represents the IPv4 link-local range:

```text
169.254.0.0/16
```

Link-local addressing may be used when normal DHCP-based configuration is unavailable.

---

## Multicast Route Interpretation

The routing table included multicast-related ranges:

```text
224.0.0.0/4
224.0.0.251
239.255.255.250
```

These entries support local multicast communication.

---

## Static Route Scenario Analysis

Router 1 knows these directly connected networks:

```text
10.10.10.0/24
10.10.40.0/24
10.10.50.0/24
```

Router 1 also needs routes to these remote networks:

```text
10.10.20.0/24
10.10.30.0/24
```

### Required Static Routes

| Destination Network | Next Hop |
| ------------------- | -------- |
| `10.10.20.0/24` | `10.10.40.2` |
| `10.10.30.0/24` | `10.10.50.2` |

### Traffic Flow Example

```text
Destination: 10.10.20.2
→ Router 1 checks routing table
→ Matches route for 10.10.20.0/24
→ Sends traffic to next hop 10.10.40.2
→ Router 2 forwards traffic to local destination network
```

---

## What I Observed

The macOS routing table included a default route, local subnet routes, loopback routes, link-local routes, and multicast-related routes.

The default route used:

```text
interface: en0
```

The default-route flags included:

```text
UP
GATEWAY
STATIC
GLOBAL
```

This indicates that the default route is active and uses a configured gateway.

The routing table helps the operating system determine whether traffic should be delivered locally or forwarded toward another network.

If no more-specific route matches a destination, the system uses the default route.

---

## Privacy Note

Sensitive local-network details were redacted before publishing this lab.

The following values were removed or generalized:

- Full private gateway address
- MAC addresses
- Hardware-specific identifiers
- Device-specific neighbor entries

The redacted output still demonstrates the routing concepts without exposing unnecessary local-network details.

---

## Important Limitation

This lab inspects the Mac routing table.

It does not modify routes.

Static-route syntax varies across operating systems, cloud platforms, and router vendors.

---

## Cloud Engineering Connection

Cloud engineers use route tables when supporting:

- Virtual private clouds
- Virtual networks
- Subnets
- NAT gateways
- Internet gateways
- Transit gateways
- VPN connections
- Peering connections
- Private endpoints
- Hybrid cloud connectivity
- Firewall appliances
- Cloud troubleshooting

---

## Skills Practiced

- Inspecting an IPv4 routing table
- Identifying a default route
- Identifying a gateway
- Identifying a network interface
- Interpreting route flags
- Identifying loopback routes
- Identifying link-local routes
- Identifying multicast routes
- Explaining next-hop routing
- Distinguishing directly connected and static routes
- Applying static-routing concepts to cloud networking
- Redacting sensitive network details before publishing
