## Lab 17: Network Architecture Selection

## Objective

Compare three-tier and collapsed core architectures and identify east-west and north-south traffic flows in realistic enterprise and data-center scenarios.

## Scenario

A cloud engineer or network administrator may need to select a network architecture and classify traffic based on business requirements.

The correct design depends on:

- Organization size
- Number of users
- Number of buildings
- Critical resources
- Redundancy requirements
- Budget
- Troubleshooting requirements
- Traffic direction
- Security requirements
- Scalability

---

## Architecture Comparison

| Architecture | Description | Common Use |
| ------------ | ----------- | ---------- |
| Three-tier architecture | Separate core, distribution, and access layers | Larger enterprise or campus networks |
| Collapsed core architecture | Core and distribution layers combined | Smaller organizations |
| East-west traffic | Traffic remains inside the same data center | Server-to-server communication |
| North-south traffic | Traffic enters or leaves the data center | Internet or external-network communication |

---

## Three-Tier Architecture

### Layers

| Layer | Purpose |
| ----- | ------- |
| Core layer | Central resources and high-speed network connectivity |
| Distribution layer | Midpoint between users and core resources |
| Access layer | User and endpoint-device connectivity |

### Diagram

```text
                 Core Layer
                      |
            Distribution Layer
                      |
                 Access Layer
                      |
            Users and Endpoints
```

---

## Collapsed Core Architecture

### Layers

| Layer | Purpose |
| ----- | ------- |
| Collapsed core layer | Core and distribution functionality combined |
| Access layer | User and endpoint-device connectivity |

### Diagram

```text
          Collapsed Core Layer
        Core + Distribution combined
                    |
              Access Layer
                    |
           Users and Endpoints
```

---

## Scenario Analysis

### Scenario 1: Large Enterprise Campus

A company has multiple buildings, several floors, many users, and central data-center resources.

The organization needs redundant paths between layers.

**Recommended architecture:**

```text
Three-tier architecture
```

**Reason:**

A three-tier architecture separates core, distribution, and access layers and supports larger enterprise environments.

---

### Scenario 2: Smaller Organization

A smaller company needs a simplified and lower-cost network design.

The company does not need a large three-tier infrastructure.

**Recommended architecture:**

```text
Collapsed core architecture
```

**Reason:**

A collapsed core combines the core and distribution layers, reducing the number of required network devices.

---

### Scenario 3: Internal Application Traffic

An application server communicates with a database server inside the same data center.

**Traffic flow:**

```text
East-west traffic
```

**Reason:**

The traffic remains inside the data center.

---

### Scenario 4: Internet User Accesses Website

A user on the internet connects to a website hosted inside the data center.

**Traffic flow:**

```text
North-south traffic
```

**Reason:**

The traffic enters the data center from an external network.

---

### Scenario 5: Server Sends Data to External Provider

A server inside the data center sends information to an external cloud service.

**Traffic flow:**

```text
North-south traffic
```

**Reason:**

The traffic leaves the data center and travels to an external destination.

---

## Traffic Flow Comparison

| Scenario | Traffic Flow | Reason |
| -------- | ------------ | ------ |
| Application server communicates with database server | East-west | Traffic stays inside data center |
| File server communicates with image server | East-west | Both systems are internal |
| Internet user accesses hosted website | North-south | Traffic enters data center |
| Internal server sends data to external API | North-south | Traffic leaves data center |
| Remote user accesses internal application | North-south | Traffic enters from external network |

---

## What I Observed

Enterprise-network architecture depends on the size and complexity of the organization.

A three-tier architecture separates:

```text
Core layer
Distribution layer
Access layer
```

A collapsed core architecture combines:

```text
Core layer + Distribution layer
```

East-west traffic stays inside the data center.

North-south traffic enters or leaves the data center.

---

## Important Limitation

The correct architecture depends on:

- Business requirements
- Organization size
- Budget
- Redundancy requirements
- Scalability
- Performance
- Security controls
- Number of sites
- Number of users
- Existing infrastructure

A network engineer should evaluate the complete environment before selecting an architecture.

---

## Cloud Engineering Connection

Cloud engineers need to understand network architectures when supporting:

- Cloud virtual networks
- Hybrid cloud environments
- Data centers
- Application tiers
- Database connectivity
- Internet-facing applications
- Internal services
- Firewalls
- Security groups
- Load balancers
- Network segmentation
- Traffic-flow troubleshooting

Understanding east-west and north-south traffic helps engineers design security controls and troubleshoot application connectivity.

---

## Skills Practiced

- Comparing three-tier and collapsed core architectures
- Identifying core, distribution, and access layers
- Recognizing appropriate architecture use cases
- Identifying east-west traffic
- Identifying north-south traffic
- Applying architecture concepts to realistic scenarios
- Connecting traffic flow to cloud-security planning
- Documenting networking concepts in GitHub
