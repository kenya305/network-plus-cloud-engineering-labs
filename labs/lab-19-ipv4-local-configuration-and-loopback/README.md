# Lab 19: IPv4 Local Configuration and Loopback

## Objective

Inspect local IPv4 configuration on a Mac and test the IPv4 loopback address.

## Scenario

A cloud engineer or network administrator may need to confirm the local IPv4 address, subnet mask, default gateway, and TCP/IP stack while troubleshooting connectivity.

This lab uses macOS Terminal commands to inspect the local configuration and validate loopback communication.

---

## Commands Used

```bash
networksetup -getinfo Wi-Fi
ping -c 4 127.0.0.1
```

### Command Breakdown

| Command | Meaning |
| ------- | ------- |
| `networksetup -getinfo Wi-Fi` | Displays IPv4 configuration details for the Wi-Fi network service |
| `ping` | Sends ICMP echo requests |
| `-c 4` | Sends four ICMP echo requests |
| `127.0.0.1` | Common IPv4 loopback address used to test the local TCP/IP stack |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran the following command to display local Wi-Fi IPv4 information:

```bash
networksetup -getinfo Wi-Fi
```

3. Reviewed the output for:
   - IPv4 address
   - Subnet mask
   - Router address
   - IPv4 configuration method
4. Ran the loopback connectivity test:

```bash
ping -c 4 127.0.0.1
```

5. Reviewed the ICMP responses.
6. Documented the results.
7. Redacted local-network details before publishing the lab.

---

## Local IPv4 Configuration Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % networksetup -getinfo Wi-Fi
DHCP Configuration
IP address: 10.0.0.x
Subnet mask: 255.255.255.0
Router: 10.0.0.x
Client ID:
IPv6: Automatic
IPv6 IP address: none
IPv6 Router: none
Wi-Fi ID: [REDACTED]
```

---

## Loopback Ping Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % ping -c 4 127.0.0.1
PING 127.0.0.1 (127.0.0.1): 56 data bytes
64 bytes from 127.0.0.1: icmp_seq=0 ttl=64 time=0.118 ms
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.134 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.135 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.138 ms

--- 127.0.0.1 ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 0.118/0.131/0.138/0.008 ms
```

---

## IPv4 Configuration Analysis

| Detail                    | Result                        |
| ------------------------- | ----------------------------- |
| IPv4 configuration method | DHCP                          |
| Local IPv4 address        | `10.0.0.x`                    |
| Subnet mask               | `255.255.255.0`               |
| Default gateway / router  | `10.0.0.x`                    |
| Local address type        | RFC 1918 private IPv4 address |
| IPv6 configuration        | Automatic                     |
| IPv6 address assigned     | None                          |

---

## Loopback Analysis

| Detail                        | Result      |
| ----------------------------- | ----------- |
| Loopback address              | `127.0.0.1` |
| Number of packets transmitted | `4`         |
| Number of packets received    | `4`         |
| Packet loss                   | `0.0%`      |
| Minimum round-trip time       | `0.118 ms`  |
| Average round-trip time       | `0.131 ms`  |
| Maximum round-trip time       | `0.138 ms`  |
| TCP/IP stack response         | Successful  |

---

## Privacy Note

Sensitive local-network details were redacted before publishing this lab.

The following details were intentionally removed or partially redacted:

* Full local private IPv4 address
* Full private default-gateway address
* Wi-Fi hardware address
* Wi-Fi network name
* MAC addresses
* Public IPv4 address
* Device identifiers

The redacted values still demonstrate the technical concepts without exposing unnecessary network details.

---

## What I Observed

The `networksetup` command showed that the Mac received its IPv4 configuration through:

```text
DHCP
```

The device used a private IPv4 address beginning with:

```text
10.0.0.x
```

The subnet mask was:

```text
255.255.255.0
```

The default gateway was located on the same private subnet:

```text
10.0.0.x
```

The local IPv4 address belongs to the RFC 1918 private range:

```text
10.0.0.0/8
```

The loopback test used:

```text
127.0.0.1
```

All four ICMP echo requests received responses:

```text
4 packets transmitted
4 packets received
0.0% packet loss
```

The average round-trip time was:

```text
0.131 ms
```

This confirms that the local TCP/IP stack responded successfully.

The loopback test checks the local device only. It does not confirm external-network or internet connectivity.

---

## APIPA Troubleshooting Note

A device may receive an IPv4 link-local address if it cannot obtain normal IPv4 configuration from a DHCP server.

The IPv4 link-local block is:

```text
169.254.0.0/16
```

A local address beginning with:

```text
169.254
```

may indicate a DHCP configuration or connectivity issue.

---

## RFC 1918 Private IPv4 Reference

| Private Address Range | CIDR Notation |
| --------------------- | ------------- |
| `10.0.0.0` through `10.255.255.255` | `10.0.0.0/8` |
| `172.16.0.0` through `172.31.255.255` | `172.16.0.0/12` |
| `192.168.0.0` through `192.168.255.255` | `192.168.0.0/16` |

---

## Cloud Engineering Connection

Cloud engineers inspect IPv4 configuration when troubleshooting:

- Virtual machines
- Cloud subnets
- Route tables
- Default gateways
- NAT gateways
- Public endpoints
- Private endpoints
- VPN connections
- Hybrid cloud networks
- Security groups
- Firewall rules
- Local connectivity

Understanding IPv4 configuration helps engineers determine whether an issue originates from the local device, local subnet, routing configuration, or external network.

---

## Skills Practiced

- Inspecting local IPv4 configuration on macOS
- Identifying an IPv4 address
- Identifying a subnet mask
- Identifying a default gateway
- Testing the IPv4 loopback address
- Interpreting ICMP ping results
- Recognizing APIPA addresses
- Reviewing RFC 1918 private IPv4 ranges
- Applying privacy controls before publishing technical output
- Documenting an IPv4 troubleshooting lab in GitHub
