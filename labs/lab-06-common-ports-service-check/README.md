# Lab 06: Common Ports Service Check

## Objective

Use Terminal commands on a Mac to check whether common web service ports are reachable.

## Scenario

A cloud engineer or network administrator may need to confirm whether a remote service is reachable on a specific port.

This lab checks whether a website is accessible over:

- HTTP using TCP port `80`
- HTTPS using TCP port `443`

---

## Commands Used

```bash
nc -vz www.professormesser.com 80
nc -vz www.professormesser.com 443
```

### Command Breakdown

| Command Part | Meaning |
| ------------ | ------- |
| `nc` | Runs Netcat, a networking utility |
| `-v` | Displays verbose output |
| `-z` | Checks whether the port is reachable without sending application data |
| `www.professormesser.com` | Remote website being tested |
| `80` | HTTP port |
| `443` | HTTPS port |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran the HTTP port check:

```bash
nc -vz www.professormesser.com 80
```

3. Ran the HTTPS port check:

```bash
nc -vz www.professormesser.com 443
```

4. Reviewed the Terminal results.
5. Documented whether each TCP port was reachable.

---

## Command Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % nc -vz www.professormesser.com 80
Connection to www.professormesser.com port 80 [tcp/http] succeeded!

kenya@Kenyas-MacBook-Pro-2 ~ % nc -vz www.professormesser.com 443
Connection to www.professormesser.com port 443 [tcp/https] succeeded!
```

---

## Port Analysis

| Service | Transport Protocol | Port  | Result    |
| ------- | ------------------ | ----- | --------- |
| HTTP    | TCP                | `80`  | Succeeded |
| HTTPS   | TCP                | `443` | Succeeded |

---

## What I Observed

The Terminal commands confirmed that the remote server accepted TCP connections on ports `80` and `443`.

The HTTP test succeeded on:

```text
TCP port 80
```

The HTTPS test succeeded on:

```text
TCP port 443
```

This means both web service ports were reachable from my local computer.

---

## Important Limitation

This lab confirms whether TCP ports `80` and `443` are reachable.

It does not confirm that every application feature on the website is working correctly.

It also does not test UDP services because UDP does not establish a formal connection in the same way TCP does.

---

## Cloud Engineering Connection

Cloud engineers use port checks when troubleshooting:

- Cloud web servers
- Firewalls
- Security groups
- Network security groups
- Load balancers
- Application gateways
- Public endpoints
- Hybrid cloud connections

A blocked or unreachable port may prevent users or applications from connecting to a service.

---

## Skills Practiced

- Running Netcat on macOS
- Testing TCP port reachability
- Recognizing HTTP port `80`
- Recognizing HTTPS port `443`
- Interpreting successful TCP connection results
- Understanding the difference between TCP and UDP testing
- Documenting a network troubleshooting lab in GitHub
