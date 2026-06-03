# Network+ N10-009 Study Notes: Software-Defined Networking

## Video Topic

Software-Defined Networking

## Summary

Software-defined networking, or SDN, separates networking functions that were traditionally combined inside physical devices.

A router, switch, or firewall commonly includes three functional planes:

- Data plane
- Control plane
- Management plane

SDN makes it possible to represent these functions in software and manage them more flexibly in virtualized and cloud-based environments.

This lesson also introduces SD-WAN, which applies software-defined networking concepts to wide-area networks.

---

## Three Networking Planes

| Plane | Main Purpose |
| ----- | ------------ |
| Data plane | Forwards traffic between interfaces |
| Control plane | Determines how traffic should be handled |
| Management plane | Allows administrators to configure and monitor the device |

---

## Data Plane

The data plane may also be called the:

```text
Infrastructure layer
```

The data plane performs the heavy lifting.

It forwards traffic from one interface to another.

### Data-Plane Functions

- Forwarding traffic
- Transferring information between interfaces
- Trunking
- Encrypting traffic
- Network Address Translation
- Applying forwarding decisions

### Key Takeaway

```text
Data plane = Moves the traffic
```

---

## Control Plane

The control plane determines how the device should behave.

It contains tables and logic used to make forwarding decisions.

### Control-Plane Examples

- Routing tables
- Switching tables
- NAT tables
- Policy decisions
- Forwarding logic

### Key Takeaway

```text
Control plane = Decides how traffic should move
```

---

## Management Plane

The management plane allows an administrator to manage the device.

### Management-Plane Examples

- SSH access
- Console access
- Web-based management interface
- Centralized configuration tools
- Administrative dashboards

### Key Takeaway

```text
Management plane = Configures and monitors the device
```

---

## Physical Firewall Example

A physical firewall includes all three planes.

| Firewall Function | Plane |
| ----------------- | ----- |
| Interfaces forwarding traffic | Data plane |
| Tables controlling allowed and blocked traffic | Control plane |
| Console or web interface used by administrator | Management plane |

---

## Software-Defined Networking

Software-defined networking virtualizes networking functions that were historically performed inside dedicated physical devices.

### Benefits

- Greater flexibility
- Centralized management
- Easier automation
- Virtualized deployments
- Cloud-friendly architecture
- Faster updates
- More consistent policy enforcement

### Key Takeaway

```text
SDN separates network functions so they can be managed and deployed more flexibly.
```

---

## SD-WAN

SD-WAN stands for:

```text
Software-Defined Wide Area Network
```

SD-WAN was designed to manage wide-area networking in cloud-based environments.

Traditional WAN designs often connected branch offices back to one centralized data center.

Modern organizations may use:

- Cloud-hosted email
- Cloud databases
- Cloud applications
- Multiple cloud providers
- Distributed services
- Remote sites

SD-WAN helps optimize access to these distributed resources.

---

## Traditional WAN vs. SD-WAN

| Traditional WAN | SD-WAN |
| --------------- | ------ |
| Branch office connects back to centralized data center | Branch office may connect directly to cloud services |
| Centralized application access | Distributed cloud application access |
| Static routing design | Application-aware routing |
| Per-device configuration | Central policy management |
| Manual updates | Zero-touch provisioning |

---

## Application Awareness

SD-WAN can identify the type of application traffic moving through the network.

### Examples

- Email traffic
- Database traffic
- Web application traffic
- Cloud-service traffic

Once SD-WAN identifies the application, it can forward the traffic toward the most appropriate service location.

### Key Takeaway

```text
Application-aware routing = SD-WAN can optimize traffic based on the application being used
```

---

## Zero-Touch Provisioning

Zero-touch provisioning allows remote networking devices to update automatically without manual intervention.

### Example

```text
Cloud application location changes
→ SD-WAN policy updates centrally
→ Remote routers update automatically
```

### Benefits

- Reduces manual configuration
- Speeds up deployments
- Improves consistency
- Helps remote sites adapt to changes
- Supports distributed cloud services

### Key Takeaway

```text
Zero-touch provisioning = Automatic device configuration and updates
```

---

## Transport Agnostic

SD-WAN is designed to work across different transport types.

### Examples

- Fiber
- 5G
- DSL
- Broadband
- MPLS
- Cellular
- Internet connections

### Key Takeaway

```text
Transport agnostic = SD-WAN can use different connection types
```

---

## Central Policy Management

Instead of configuring each router individually, SD-WAN policies can be managed from a central console.

### Example

```text
Administrator updates policy once
→ Policy is pushed to SD-WAN routers
→ Remote sites receive the update
```

### Key Takeaway

```text
Central policy management = Configure once, distribute automatically
```

---

## Cloud Engineering Connection

Cloud engineers work with SDN and SD-WAN when supporting:

- Virtual networks
- Cloud routers
- Cloud firewalls
- Hybrid cloud connectivity
- Multi-cloud networking
- Branch-office connectivity
- Remote-site routing
- Application-aware traffic steering
- Centralized network policies
- Zero-touch provisioning
- Network automation
- Cloud migrations

### Example

```text
Remote branch needs cloud email access
→ SD-WAN identifies email traffic
→ Traffic is sent directly to the appropriate cloud service
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Forwards traffic between interfaces | Data plane |
| Routing tables or switching tables | Control plane |
| SSH, console, or web management | Management plane |
| Virtualized networking functions | SDN |
| Software-defined wide-area networking | SD-WAN |
| Route traffic based on application type | Application awareness |
| Automatic router updates without manual intervention | Zero-touch provisioning |
| Fiber, 5G, DSL, or broadband support | Transport agnostic |
| Configure policies once from one console | Central policy management |
| Remote site goes directly to cloud service | SD-WAN optimization |

---

## Memory Trick

```text
Data plane       = Moves traffic
Control plane    = Makes decisions
Management plane = Lets administrators manage

SDN              = Software-defined networking
SD-WAN           = Software-defined WAN
ZTP              = Zero-touch provisioning
```

---

## Practice Questions

### 1. What does the data plane do?

Answer: It forwards traffic between interfaces.

### 2. What does the control plane do?

Answer: It determines how traffic should be handled using routing, switching, NAT, and other tables.

### 3. What does the management plane do?

Answer: It allows administrators to configure and monitor devices.

### 4. What does SDN stand for?

Answer:

```text
Software-Defined Networking
```

### 5. What does SD-WAN stand for?

Answer:

```text
Software-Defined Wide Area Network
```

### 6. What does application-aware routing mean?

Answer: The SD-WAN can identify application traffic and direct it toward the appropriate service.

### 7. What is zero-touch provisioning?

Answer: Automatic configuration and updating of network devices without manual intervention.

### 8. What does transport agnostic mean?

Answer: The SD-WAN can operate across different connection types such as fiber, 5G, DSL, or broadband.

### 9. What is central policy management?

Answer: Policies are configured from one central console and pushed automatically to remote SD-WAN devices.
