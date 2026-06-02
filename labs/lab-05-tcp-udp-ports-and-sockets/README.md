# Lab 05: TCP, UDP, Ports, and Sockets

## Objective

Inspect real network connections on a Mac to identify TCP connections, IP addresses, and port numbers.

## Scenario

A computer may communicate with several remote services at the same time.

Each connection uses an IP address, a transport protocol, and port numbers to deliver traffic to the correct application.

This lab uses a Terminal command to inspect active TCP connections.

---

## Command Used

```bash
lsof -nP -iTCP -sTCP:ESTABLISHED
```

### Command Breakdown

| Command Part        | Meaning                                                           |
| ------------------- | ----------------------------------------------------------------- |
| `lsof`              | Lists open files and network connections                          |
| `-n`                | Prevents hostname lookups so IP addresses display directly        |
| `-P`                | Displays port numbers instead of converting them to service names |
| `-iTCP`             | Filters for TCP network connections                               |
| `-sTCP:ESTABLISHED` | Shows established TCP connections                                 |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Opened a web browser and visited a website using HTTPS.
3. Ran the following command:

```bash
lsof -nP -iTCP -sTCP:ESTABLISHED
```

4. Reviewed the output for an active browser connection.
5. Identified the local IP address, temporary client-side port, remote IP address, and server-side port.

---

## Command Output

One representative browser connection was selected from the Terminal output:

```text
Google 1269 kenya 29u IPv4 0x9262b066b68ed799 0t0 TCP 10.0.0.235:49708->34.238.107.67:443 (ESTABLISHED)
```

---

## Connection Analysis

| Connection Detail      | Value                                |
| ---------------------- | ------------------------------------ |
| Application or process | Google Chrome, displayed as `Google` |
| Transport protocol     | TCP                                  |
| Local IP address       | `10.0.0.235`                         |
| Local temporary port   | `49708`                              |
| Remote IP address      | `34.238.107.67`                      |
| Remote server port     | `443`                                |
| Connection status      | `ESTABLISHED`                        |

---

## What I Observed

The active network connection included a local IP address and a temporary client-side port.

The local device used the IP address `10.0.0.235` and the temporary client-side port `49708`.

The remote destination used the IP address `34.238.107.67` and the server-side port `443`.

For an HTTPS connection, the remote server commonly uses:

```text
TCP port 443
```

The connection status was:

```text
ESTABLISHED
```

This means the TCP session was active when the Terminal command was run.

---

## Socket Explanation

A socket identifies one endpoint of a network conversation.

A socket can be represented as:

```text
IP address + protocol + port number
```

For this connection, the client socket was:

```text
10.0.0.235 + TCP + port 49708
```

The server socket was:

```text
34.238.107.67 + TCP + port 443
```

Together, the client socket and server socket identify the active TCP conversation between the browser and the remote HTTPS server.

---

## TCP Connection Takeaway

TCP is a connection-oriented protocol.

The established TCP connection shown in the Terminal output represents an active communication session between the client and the remote server.

The client used a temporary local port, while the remote HTTPS server used the standard TCP port `443`.

TCP supports:

* Acknowledgments
* Reliable delivery
* Error recovery
* Packet sequencing
* Flow control

---

## UDP Comparison

The command used in this lab filters the output to show established TCP connections only.

UDP is connectionless and does not establish a formal session in the same way TCP does.

An optional command to inspect UDP traffic is:

```bash
lsof -nP -iUDP
```

---

## Cloud Engineering Connection

Cloud engineers use IP addresses, ports, protocols, sockets, and firewall rules when configuring:

* Virtual machines
* Cloud web servers
* Security groups
* Network security groups
* Load balancers
* VPN connections
* Application gateways
* Hybrid cloud environments

Understanding sockets and port numbers helps engineers troubleshoot whether a service is reachable and whether traffic is reaching the correct application.

---

## Skills Practiced

* Running `lsof` to inspect active TCP connections
* Identifying an established TCP session
* Identifying a local private IP address
* Identifying a temporary client-side port
* Identifying a remote server IP address
* Recognizing TCP port `443` as an HTTPS service port
* Understanding sockets
* Comparing TCP and UDP behavior
* Documenting a technical lab in GitHub
