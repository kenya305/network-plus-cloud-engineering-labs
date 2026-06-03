# Lab 25: SDN and SD-WAN Design Analysis

## Objective

Identify the data plane, control plane, and management plane in a networking device and apply SD-WAN concepts to a realistic cloud-connectivity scenario.

## Scenario

A company has a headquarters office, two branch offices, and several cloud-hosted services.

Employees use:

- Cloud email
- Cloud databases
- Web applications
- Internal data-center systems

The company wants to improve branch-office connectivity and reduce the need to configure routers manually at every location.

---

## Part 1: Identify the Networking Planes

| Networking Function | Plane |
| ------------------- | ----- |
| Forward traffic between interfaces | Data plane |
| Perform trunking | Data plane |
| Encrypt traffic | Data plane |
| Apply NAT to traffic | Data plane |
| Store routing tables | Control plane |
| Store switching tables | Control plane |
| Store NAT tables | Control plane |
| Decide how traffic should be forwarded | Control plane |
| Provide SSH access | Management plane |
| Provide console access | Management plane |
| Provide web-based configuration | Management plane |

---

## Part 2: Physical Firewall Example

A physical firewall connects multiple networks, forwards traffic, applies policies, and provides an administrative interface.

| Firewall Component | Plane | Reason |
| ------------------ | ----- | ------ |
| Network interfaces | Data plane | Traffic moves between interfaces |
| Firewall policy table | Control plane | Determines allowed and blocked traffic |
| Routing table | Control plane | Determines where traffic should be forwarded |
| Web-based admin console | Management plane | Allows administrator configuration |
| SSH access | Management plane | Allows remote administration |

---

## Part 3: SD-WAN Scenario Analysis

### Business Requirement

The company needs branch offices to reach cloud-hosted services efficiently.

A traditional WAN design may send all traffic back to the central data center first.

SD-WAN can optimize this workflow.

### SD-WAN Design

```text
Branch office
→ SD-WAN router
→ Application-aware traffic decision
→ Direct path to cloud service when appropriate
```

### Benefits

| SD-WAN Capability | Business Benefit |
| ----------------- | ---------------- |
| Application awareness | Routes email, database, and web traffic appropriately |
| Zero-touch provisioning | Reduces manual configuration at remote sites |
| Transport agnostic design | Supports fiber, 5G, DSL, broadband, or other links |
| Central policy management | Allows policies to be configured once and pushed automatically |
| Direct cloud access | Reduces unnecessary backhaul through the data center |

---

## Part 4: Traditional WAN vs. SD-WAN

| Traditional WAN | SD-WAN |
| --------------- | ------ |
| Branch traffic often returns to centralized data center | Branch traffic may go directly to cloud services |
| Configuration may be performed device by device | Policies can be managed centrally |
| Cloud changes may require manual updates | Zero-touch provisioning supports automatic updates |
| Less application-aware | Can optimize traffic based on application type |
| May depend heavily on one transport type | Can support multiple transport types |

---

## What I Observed

Software-defined networking separates networking functions into:

```text
Data plane
Control plane
Management plane
```

The data plane moves traffic.

The control plane decides how traffic should move.

The management plane allows administrators to configure and monitor the network device.

SD-WAN extends software-defined networking concepts to wide-area networks.

It can improve cloud connectivity through:

```text
Application awareness
Zero-touch provisioning
Transport-agnostic connectivity
Central policy management
```

---

## Important Limitation

SD-WAN is not a replacement for every networking technology.

A network engineer should still evaluate:

- Security requirements
- Bandwidth
- Latency
- Redundancy
- Cloud-provider connectivity
- Existing WAN design
- Business requirements
- Cost
- Compliance requirements

---

## Cloud Engineering Connection

Cloud engineers use SDN and SD-WAN concepts when supporting:

- Hybrid cloud environments
- Multi-cloud architectures
- Virtual networks
- Cloud routers
- Cloud firewalls
- Branch-office connectivity
- Network automation
- Policy distribution
- Application-aware routing
- Zero-touch provisioning
- Cloud migrations

---

## Skills Practiced

- Identifying the data plane
- Identifying the control plane
- Identifying the management plane
- Comparing SDN and SD-WAN concepts
- Recognizing application-aware routing
- Recognizing zero-touch provisioning
- Recognizing transport-agnostic WAN design
- Applying central policy management concepts
- Connecting SD-WAN to cloud engineering
