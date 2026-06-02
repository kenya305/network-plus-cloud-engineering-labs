# Lab 07: ICMP Ping and Traceroute

## Objective

Use Terminal commands on a Mac to test network connectivity and observe the path traffic takes across a network.

## Scenario

A cloud engineer or network administrator may need to determine whether a device is reachable and identify the path traffic takes to reach a destination.

This lab uses:

- `ping` to test reachability using ICMP
- `traceroute` to observe the network path and TTL behavior

---

## Commands Used

```bash
ping -c 4 1.1.1.1
traceroute 1.1.1.1
```

### Command Breakdown

| Command Part | Meaning |
| ------------ | ------- |
| `ping` | Sends ICMP echo requests to test connectivity |
| `-c 4` | Sends four ICMP echo requests |
| `1.1.1.1` | Destination IP address used for the connectivity test |
| `traceroute` | Displays the route traffic takes toward the destination |
| `1.1.1.1` | Destination IP address used for the route trace |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran the ICMP connectivity test:

```bash
ping -c 4 1.1.1.1
```

3. Reviewed the ping replies.
4. Ran the route trace:

```bash
traceroute 1.1.1.1
```

5. Reviewed the network hops.
6. Documented the results.

---

## Ping Command Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % ping -c 4 1.1.1.1
PING 1.1.1.1 (1.1.1.1): 56 data bytes
64 bytes from 1.1.1.1: icmp_seq=0 ttl=54 time=25.293 ms
64 bytes from 1.1.1.1: icmp_seq=1 ttl=54 time=19.464 ms
64 bytes from 1.1.1.1: icmp_seq=2 ttl=54 time=22.174 ms
64 bytes from 1.1.1.1: icmp_seq=3 ttl=54 time=21.950 ms

--- 1.1.1.1 ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 19.464/22.220/25.293/2.068 ms
```

---

## Traceroute Command Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % traceroute 1.1.1.1
traceroute to 1.1.1.1 (1.1.1.1), 64 hops max, 40 byte packets
 1  10.0.0.1 (10.0.0.1)  19.163 ms  2.595 ms  3.860 ms
 2  172.30.14.50 (172.30.14.50)  15.896 ms
    172.30.14.51 (172.30.14.51)  9.924 ms  15.631 ms
 3  po-56-rur301.hillsboro.nj.panjde.comcast.net (68.85.128.105)  13.290 ms
    po-56-rur302.hillsboro.nj.panjde.comcast.net (68.85.128.205)  26.727 ms
    po-56-rur301.hillsboro.nj.panjde.comcast.net (68.85.128.105)  21.459 ms
 4  po-2-rur301.hillsboro.nj.panjde.comcast.net (96.216.139.225)  17.747 ms
    po-300-xar01.hillsboro.nj.panjde.comcast.net (96.108.9.5)  16.461 ms
    po-2-rur301.hillsboro.nj.panjde.comcast.net (96.216.139.225)  13.554 ms
 5  be-35-rar01.plainfield.nj.panjde.comcast.net (96.216.136.221)  26.022 ms  14.818 ms
    po-300-xar01.hillsboro.nj.panjde.comcast.net (96.108.9.5)  25.220 ms
 6  be-98-ar03.plainfield.nj.panjde.comcast.net (68.85.35.37)  15.014 ms
    be-35-rar01.plainfield.nj.panjde.comcast.net (96.216.136.221)  24.266 ms
    be-98-ar03.plainfield.nj.panjde.comcast.net (68.85.35.37)  17.486 ms
 7  be-98-ar03.plainfield.nj.panjde.comcast.net (68.85.35.37)  16.703 ms
    be-31123-cs02.newark.nj.ibone.comcast.net (96.110.42.37)  16.071 ms
    be-98-ar03.plainfield.nj.panjde.comcast.net (68.85.35.37)  36.482 ms
 8  be-2111-pe11.newark.nj.ibone.comcast.net (96.110.33.242)  16.603 ms
    be-31143-cs04.newark.nj.ibone.comcast.net (96.110.42.45)  39.589 ms
    be-2411-pe11.newark.nj.ibone.comcast.net (96.110.33.254)  17.482 ms
 9  be-2111-pe11.newark.nj.ibone.comcast.net (96.110.33.242)  22.181 ms *  24.065 ms
10  162.158.61.133 (162.158.61.133)  18.706 ms * *
11  one.one.one.one (1.1.1.1)  17.233 ms
    162.158.61.109 (162.158.61.109)  16.680 ms
    one.one.one.one (1.1.1.1)  16.420 ms
```

---

## Ping Analysis

| Detail                  | Result      |
| ----------------------- | ----------- |
| Destination IP address  | `1.1.1.1`   |
| Number of packets sent  | `4`         |
| Number of packets received | `4`      |
| Packet loss             | `0.0%`      |
| Minimum round-trip time | `19.464 ms` |
| Average round-trip time | `22.220 ms` |
| Maximum round-trip time | `25.293 ms` |

---

## Traceroute Analysis

| Detail                    | Result                      |
| ------------------------- | --------------------------- |
| Destination IP address    | `1.1.1.1`                   |
| Number of visible hops    | `11`                        |
| First visible hop         | `10.0.0.1`                  |
| Final visible hop         | `one.one.one.one (1.1.1.1)` |
| Timed-out hops shown as `*` | Yes                       |
| Timed-out probes observed | Hops `9` and `10`           |

---

## What I Observed

The `ping` command successfully tested connectivity to `1.1.1.1`.

All four ICMP echo requests received responses.

The test showed:

```text
4 packets transmitted
4 packets received
0.0% packet loss
```

The average round-trip time was:

```text
22.220 ms
```

This means the destination was reachable and responded successfully to the ICMP requests.

The `traceroute` command displayed the path traffic took toward `1.1.1.1`.

The first visible hop was:

```text
10.0.0.1
```

This is the local router.

The final visible hop was:

```text
one.one.one.one (1.1.1.1)
```

The traceroute reached the destination after `11` visible hops.

Some intermediate traceroute probes timed out and appeared as:

```text
*
```

This is not necessarily an error.

Some routers do not respond to traceroute probes, even when traffic continues successfully toward the destination.

The traceroute also showed multiple router responses for some hops.

This may happen when traffic follows different network paths or when load balancing is used across the network.

Each hop helps demonstrate how routers process traffic and how TTL values are used during traceroute.

---

## Cloud Engineering Connection

Cloud engineers use ICMP and traceroute when troubleshooting:

- Virtual machine connectivity
- Routing problems
- VPN connections
- Hybrid cloud networks
- Firewall rules
- Security groups
- Network path issues
- Latency problems

---

## Skills Practiced

- Running an ICMP ping test
- Interpreting packet loss
- Reviewing round-trip latency
- Running traceroute
- Reviewing network hops
- Connecting TTL behavior to ICMP time exceeded messages
- Understanding ICMP troubleshooting limitations
- Documenting a network troubleshooting lab in GitHub
