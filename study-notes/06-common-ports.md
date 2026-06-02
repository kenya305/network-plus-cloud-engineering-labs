# Network+ N10-009 Study Notes: Common Ports

## Video Topic

Common Ports

## Summary

Network professionals frequently configure and troubleshoot port numbers associated with applications and services.

A port number helps identify the application or service that should receive network traffic.

The transport protocol also matters.

For example:

```text
TCP port 80 is different from UDP port 80.
```

This lesson covers common ports that should be recognized for the CompTIA Network+ exam.

---

## Common Ports Reference Table

| Protocol | Full Name | Port Number | Transport Protocol | Purpose |
| -------- | --------- | ----------- | ------------------ | ------- |
| FTP Data | File Transfer Protocol Data | 20 | TCP | Transfers file data |
| FTP Control | File Transfer Protocol Control | 21 | TCP | Sends FTP commands and control information |
| SSH | Secure Shell | 22 | TCP | Encrypted remote terminal access |
| SFTP | Secure File Transfer Protocol | 22 | TCP | Encrypted file transfer using SSH |
| Telnet | Telecommunication Network | 23 | TCP | Unencrypted remote terminal access |
| SMTP | Simple Mail Transfer Protocol | 25 | TCP | Server-to-server email transfer |
| SMTP with TLS | Simple Mail Transfer Protocol with Transport Layer Security | 587 | TCP | Encrypted email submission |
| DNS Query | Domain Name System | 53 | UDP | Resolves domain names to IP addresses |
| DNS Transfer | Domain Name System | 53 | TCP | Supports larger DNS transfers |
| DHCP Server | Dynamic Host Configuration Protocol | 67 | UDP | Assigns IP configuration from the server |
| DHCP Client | Dynamic Host Configuration Protocol | 68 | UDP | Receives IP configuration on the client |
| TFTP | Trivial File Transfer Protocol | 69 | UDP | Transfers small files without authentication |
| HTTP | Hypertext Transfer Protocol | 80 | TCP | Unencrypted web traffic |
| HTTPS | Hypertext Transfer Protocol Secure | 443 | TCP | Encrypted web traffic using TLS |
| NTP | Network Time Protocol | 123 | UDP | Synchronizes system clocks |
| SNMP Query | Simple Network Management Protocol | 161 | UDP | Queries and monitors network devices |
| SNMP Trap | Simple Network Management Protocol Trap | 162 | UDP | Sends proactive device alerts |
| LDAP | Lightweight Directory Access Protocol | 389 | TCP | Queries directory services |
| LDAPS | Lightweight Directory Access Protocol Secure | 636 | TCP | Secure directory queries |
| SMB | Server Message Block | 445 | TCP | Shares files, printers, and authentication resources |
| Syslog | System Logging Protocol | 514 | UDP | Sends log data to a centralized location |
| MS-SQL | Microsoft Structured Query Language Server | 1433 | TCP | Connects to Microsoft SQL Server |
| RDP | Remote Desktop Protocol | 3389 | TCP | Provides remote desktop access |
| SIP | Session Initiation Protocol | 5060 | TCP | Initiates and manages voice-over-IP sessions |
| SIP | Session Initiation Protocol | 5061 | TCP | Common SIP communication port |

---

## FTP: File Transfer Protocol

FTP stands for File Transfer Protocol.

FTP is used to transfer files between devices across different operating systems.

FTP uses two TCP ports:

| Port | Purpose |
| ---- | ------- |
| TCP port `20` | File transfer data |
| TCP port `21` | Control commands |

FTP supports:

- Username and password authentication
- Directory listings
- File uploads
- File downloads
- File deletion
- File renaming

### Exam Tip

If the question mentions standard file transfer with separate data and control channels, think FTP.

---

## SSH: Secure Shell

SSH stands for Secure Shell.

SSH uses:

```text
TCP port 22
```

SSH provides encrypted remote terminal access.

It allows administrators to securely manage remote systems from a command-line interface.

### Exam Tip

If the question mentions secure remote terminal access, think SSH.

---

## SFTP: Secure File Transfer Protocol

SFTP stands for Secure File Transfer Protocol.

SFTP also uses:

```text
TCP port 22
```

SFTP uses SSH as its underlying protocol.

This provides encrypted file transfer and file management.

### Key Takeaway

```text
SSH and SFTP both use TCP port 22.
```

---

## Telnet

Telnet uses:

```text
TCP port 23
```

Telnet provides remote terminal access, but it does not encrypt the communication.

Information is transmitted in clear text.

This may expose:

- Login credentials
- Commands
- Session data

### Exam Tip

If the question mentions unencrypted remote terminal access, think Telnet.

---

## SMTP: Simple Mail Transfer Protocol

SMTP stands for Simple Mail Transfer Protocol.

SMTP is used to send email messages and transfer messages between email servers.

| Port | Purpose |
| ---- | ------- |
| TCP port `25` | Server-to-server email transfer |
| TCP port `587` | Email submission using TLS encryption |

### Exam Tip

If the question mentions sending email, think SMTP.

---

## DNS: Domain Name System

DNS stands for Domain Name System.

DNS translates a fully qualified domain name, or FQDN, into an IP address.

Example:

```text
www.professormesser.com → IP address
```

DNS commonly uses:

| Port | Purpose |
| ---- | ------- |
| UDP port `53` | Small DNS queries |
| TCP port `53` | Larger DNS transfers |

### Exam Tip

If the question mentions resolving a website name to an IP address, think DNS.

---

## DHCP: Dynamic Host Configuration Protocol

DHCP stands for Dynamic Host Configuration Protocol.

DHCP automatically assigns network configuration to devices.

DHCP uses:

| Port | Device |
| ---- | ------ |
| UDP port `67` | DHCP server |
| UDP port `68` | DHCP client |

DHCP may assign:

- IP address
- Subnet mask
- Default gateway
- DNS server
- Lease time

### DHCP Lease

A DHCP lease allows a device to use an assigned IP address for a specific period.

The device may renew the lease when needed.

### DHCP Reservation

A DHCP reservation assigns the same IP address to a device based on its MAC address.

### Exam Tip

If the question mentions automatic IP addressing, think DHCP.

---

## TFTP: Trivial File Transfer Protocol

TFTP stands for Trivial File Transfer Protocol.

TFTP uses:

```text
UDP port 69
```

TFTP is used for simple file transfers with minimal overhead.

TFTP commonly does not require authentication.

### Example

A voice-over-IP phone may:

1. Connect to the network
2. Receive an IP address using DHCP
3. Download a configuration file using TFTP

### Exam Tip

If the question mentions a quick configuration-file transfer without authentication, think TFTP.

---

## HTTP and HTTPS

HTTP stands for Hypertext Transfer Protocol.

HTTPS stands for Hypertext Transfer Protocol Secure.

| Protocol | Port | Encryption |
| -------- | ---- | ---------- |
| HTTP | TCP port `80` | No encryption |
| HTTPS | TCP port `443` | TLS encryption |

### Exam Tip

If browser traffic is encrypted, think HTTPS and TCP port `443`.

---

## NTP: Network Time Protocol

NTP stands for Network Time Protocol.

NTP uses:

```text
UDP port 123
```

NTP synchronizes clocks across devices.

This is important for:

- Routers
- Switches
- Firewalls
- Servers
- Operating systems
- Security logs

### Why Accurate Time Matters

Accurate timestamps help administrators compare logs across multiple devices during troubleshooting or incident investigations.

---

## SNMP: Simple Network Management Protocol

SNMP stands for Simple Network Management Protocol.

SNMP is used to monitor and manage network devices.

| Port | Purpose |
| ---- | ------- |
| UDP port `161` | Queries devices |
| UDP port `162` | Receives proactive alerts called traps |

### SNMP Versions

| Version | Features |
| ------- | -------- |
| SNMPv1 | Basic queries and responses without encryption |
| SNMPv2 | Supports bulk transfers but does not provide encryption |
| SNMPv3 | Supports message integrity, authentication, and encryption |

### SNMP Trap

An SNMP trap allows a device to proactively send an alert to a management station.

### Exam Tip

If the question mentions proactive SNMP alerts, think UDP port `162`.

---

## LDAP and LDAPS

LDAP stands for Lightweight Directory Access Protocol.

LDAP is used to query directory databases.

| Protocol | Port | Encryption |
| -------- | ---- | ---------- |
| LDAP | TCP port `389` | Standard directory query |
| LDAPS | TCP port `636` | Secure directory query |

LDAP uses a hierarchical structure.

Examples include:

- Organization
- Organizational unit
- Common name

### Exam Tip

If the question mentions a directory service, think LDAP.

---

## SMB: Server Message Block

SMB stands for Server Message Block.

SMB may also be associated with CIFS, or Common Internet File System.

SMB uses:

```text
TCP port 445
```

SMB supports:

- File sharing
- Printer sharing
- Authentication
- Permissions
- File locking

### Exam Tip

If the question mentions Windows file shares, think SMB.

---

## Syslog

Syslog uses:

```text
UDP port 514
```

Syslog sends log data from devices to a centralized location.

Syslog is commonly used with a SIEM.

SIEM stands for:

```text
Security Information and Event Management
```

### Cloud Engineering Connection

Centralized logging helps cloud and security teams troubleshoot issues and detect suspicious activity.

---

## MS-SQL

MS-SQL stands for Microsoft Structured Query Language Server.

MS-SQL uses:

```text
TCP port 1433
```

### Exam Tip

If the question mentions Microsoft SQL Server, think TCP port `1433`.

---

## RDP: Remote Desktop Protocol

RDP stands for Remote Desktop Protocol.

RDP uses:

```text
TCP port 3389
```

RDP allows a user to view and control a remote desktop.

RDP is commonly associated with Windows systems, but clients are also available for macOS, Linux, iPhone, and Android.

### Exam Tip

If the question mentions remote desktop access, think RDP.

---

## SIP: Session Initiation Protocol

SIP stands for Session Initiation Protocol.

SIP commonly uses:

```text
TCP port 5060
TCP port 5061
```

SIP manages communication sessions for voice-over-IP services.

SIP may support:

- Phone call setup
- Phone call termination
- Video conferencing
- Instant messaging
- File transfer

### Exam Tip

If the question mentions voice-over-IP call setup, think SIP.

---

## Cloud Engineering Connection

Cloud engineers frequently configure firewall rules, security groups, network security groups, and load balancers using port numbers.

Examples:

| Cloud Scenario | Relevant Port |
| -------------- | ------------- |
| Secure website | TCP `443` |
| Remote Linux server administration | TCP `22` |
| Remote Windows desktop | TCP `3389` |
| DNS resolution | UDP `53` |
| Database connection to Microsoft SQL Server | TCP `1433` |
| Centralized logging | UDP `514` |
| Windows file share | TCP `445` |

Understanding common ports helps cloud engineers:

- Configure access rules
- Troubleshoot blocked traffic
- Reduce security risk
- Identify exposed services
- Understand application dependencies

---

## Memory Grouping Strategy

### File Transfer

| Protocol | Port |
| -------- | ---- |
| FTP Data | TCP `20` |
| FTP Control | TCP `21` |
| SFTP | TCP `22` |
| TFTP | UDP `69` |

### Remote Access

| Protocol | Port |
| -------- | ---- |
| SSH | TCP `22` |
| Telnet | TCP `23` |
| RDP | TCP `3389` |

### Email

| Protocol | Port |
| -------- | ---- |
| SMTP | TCP `25` |
| SMTP with TLS | TCP `587` |

### Web Traffic

| Protocol | Port |
| -------- | ---- |
| HTTP | TCP `80` |
| HTTPS | TCP `443` |

### Network Services

| Protocol | Port |
| -------- | ---- |
| DNS | UDP/TCP `53` |
| DHCP Server | UDP `67` |
| DHCP Client | UDP `68` |
| NTP | UDP `123` |
| SNMP Query | UDP `161` |
| SNMP Trap | UDP `162` |

### Directory, File Sharing, Logging, and Databases

| Protocol | Port |
| -------- | ---- |
| LDAP | TCP `389` |
| LDAPS | TCP `636` |
| SMB | TCP `445` |
| Syslog | UDP `514` |
| MS-SQL | TCP `1433` |

### Voice-over-IP

| Protocol | Port |
| -------- | ---- |
| SIP | TCP `5060` |
| SIP | TCP `5061` |

---

## Practice Questions

### 1. Which TCP ports are associated with FTP?

Answer: TCP ports `20` and `21`

### 2. Which protocol uses TCP port `22` for encrypted remote terminal access?

Answer: SSH

### 3. Which protocol uses TCP port `22` for encrypted file transfer?

Answer: SFTP

### 4. Which protocol uses TCP port `23`?

Answer: Telnet

### 5. Which TCP port is commonly used for server-to-server email transfer?

Answer: TCP port `25`

### 6. Which port is used for SMTP with TLS encryption?

Answer: TCP port `587`

### 7. Which port is commonly used for DNS queries?

Answer: UDP port `53`

### 8. Which ports are used by DHCP?

Answer: UDP ports `67` and `68`

### 9. Which protocol uses UDP port `69`?

Answer: TFTP

### 10. Which ports are used for HTTP and HTTPS?

Answer: TCP port `80` for HTTP and TCP port `443` for HTTPS

### 11. Which protocol uses UDP port `123`?

Answer: NTP

### 12. Which ports are used for SNMP queries and SNMP traps?

Answer: UDP port `161` for queries and UDP port `162` for traps

### 13. Which ports are used for LDAP and LDAPS?

Answer: TCP port `389` for LDAP and TCP port `636` for LDAPS

### 14. Which protocol uses TCP port `445`?

Answer: SMB

### 15. Which protocol uses UDP port `514`?

Answer: Syslog

### 16. Which protocol uses TCP port `1433`?

Answer: MS-SQL

### 17. Which protocol uses TCP port `3389`?

Answer: RDP

### 18. Which ports are commonly associated with SIP?

Answer: TCP ports `5060` and `5061`
