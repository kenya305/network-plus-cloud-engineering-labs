# Network+ N10-009 Study Notes: Network Architectures

## Video Topic

Network Architectures

## Summary

Network architectures describe how network resources, switches, users, and traffic flows are organized.

Many enterprise networks follow established design patterns to improve:

- Performance
- Scalability
- Redundancy
- Troubleshooting
- Network management
- Security planning
- Resource access

This lesson covers:

- Three-tier architecture
- Core layer
- Distribution layer
- Access layer
- Collapsed core architecture
- Two-tier architecture
- East-west traffic
- North-south traffic
- Data-center traffic flow

---

## Three-Tier Architecture

A three-tier architecture is a common enterprise-network design.

It separates the network into three layers:

```text
Core layer
Distribution layer
Access layer
```

### Three-Tier Diagram

```text
                 Core Layer
          Central resources and routing
                      |
            Distribution Layer
      Midpoint between users and core resources
                      |
                 Access Layer
       User devices connect through local switches
```

### Key Takeaway

```text
Three-tier architecture
= Core + Distribution + Access
```

---

## Core Layer

The core layer is the central part of the enterprise network.

It commonly provides access to critical resources.

### Core Resources May Include

- Servers
- Applications
- Databases
- Central routing resources
- Data-center systems
- Shared enterprise services

### Core Layer Purpose

The core layer helps move traffic efficiently between major parts of the network.

### Simple Example

```text
Users need access to database
→ Traffic travels toward core layer
→ Database resource is reached
```

### Key Takeaway

```text
Core layer = Central network resources and high-speed connectivity
```

---

## Distribution Layer

The distribution layer sits between the access layer and the core layer.

It provides a midpoint for connectivity.

The distribution layer commonly uses switches to connect users to critical resources.

### Distribution Layer Purpose

The distribution layer may support:

- Connectivity between access and core layers
- Redundancy
- Traffic aggregation
- Network segmentation
- Policy enforcement
- Efficient routing between network areas

### Simple Example

```text
Access switch
→ Distribution switch
→ Core network
```

### Key Takeaway

```text
Distribution layer = Midpoint between users and core resources
```

---

## Access Layer

The access layer is where users and endpoint devices connect to the network.

Access switches are commonly located close to users.

For example, an access switch may be installed on the same floor of an office building.

### Devices Connected at the Access Layer

- Workstations
- Laptops
- Printers
- Phones
- Wireless access points
- Other endpoint devices

### Simple Example

```text
Employee laptop
→ Access switch
→ Distribution layer
→ Core resources
```

### Key Takeaway

```text
Access layer = User and endpoint-device connectivity
```

---

## City Analogy for Three-Tier Architecture

A three-tier network can be compared to a city.

| Network Layer | City Analogy |
| ------------- | ------------ |
| Core layer | Downtown area with major resources |
| Distribution layer | Highways connecting neighborhoods to downtown |
| Access layer | Local roads connecting homes to highways |

### Visual Example

```text
Home
→ Local road
→ Highway
→ Downtown resources
```

### Network Equivalent

```text
User device
→ Access switch
→ Distribution switch
→ Core resources
```

---

## Three-Tier Redundancy

A three-tier design may include multiple links between layers.

### Example

```text
Access switch
→ Distribution switch 1
→ Core

Access switch
→ Distribution switch 2
→ Core
```

If one component or connection fails, traffic may use another path.

### Benefits

- Improved resiliency
- Better fault tolerance
- More network-path options
- Reduced risk of complete outage

### Key Takeaway

```text
Multiple links can provide redundancy between network layers.
```

---

## Campus Network Example

A campus may have multiple buildings.

Users on each floor connect to an access switch.

The access switches connect to distribution switches.

The distribution switches connect to the core network, which may be located inside a central data center.

### Campus Diagram

```text
Building A
├── Floor 1 access switch
├── Floor 2 access switch
└── Distribution switches
             |
             |
          Core network
             |
             |
Building B
├── Floor 1 access switch
├── Floor 2 access switch
└── Distribution switches
```

---

## Collapsed Core Architecture

A collapsed core architecture combines the core layer and distribution layer.

This creates a two-tier architecture.

### Collapsed Core Layers

```text
Collapsed core layer
Access layer
```

### Diagram

```text
       Collapsed Core Layer
     Core + Distribution combined
                |
          Access Layer
      Users and endpoint devices
```

### Benefits

- Simpler design
- Fewer network devices
- Lower implementation cost
- Easier troubleshooting
- Appropriate for smaller organizations

### Limitation

A collapsed core design may provide fewer redundancy options than a larger three-tier architecture.

### Key Takeaway

```text
Collapsed core
= Core layer + Distribution layer combined
```

### Exam Tip

If the question mentions a smaller organization using a two-tier design, think:

```text
Collapsed core architecture
```

---

## Three-Tier vs. Collapsed Core

| Feature | Three-Tier Architecture | Collapsed Core Architecture |
| ------- | ----------------------- | --------------------------- |
| Number of layers | Three | Two |
| Core layer | Separate | Combined with distribution |
| Distribution layer | Separate | Combined with core |
| Access layer | Separate | Separate |
| Complexity | Higher | Lower |
| Cost | Commonly higher | Commonly lower |
| Redundancy options | Commonly greater | May be more limited |
| Common use | Larger enterprise networks | Smaller organizations |

---

## Data-Center Traffic Flow

Traffic flow can be described based on where the traffic originates and where it is going.

Two common data-center traffic-flow descriptions are:

```text
East-west traffic
North-south traffic
```

---

## East-West Traffic

East-west traffic stays inside the same data center.

The source and destination are internal resources.

### Examples

- File server communicates with image server
- Application server communicates with database server
- Internal service communicates with another internal service
- Virtual machine communicates with another virtual machine inside the same data center

### Diagram

```text
File server
↔
Image server
```

### Key Characteristics

- Internal data-center communication
- Local network traffic
- Commonly faster response time
- May not leave the data-center environment

### Key Takeaway

```text
East-west traffic = Traffic inside the data center
```

### Exam Tip

If the question mentions server-to-server traffic inside the same data center, think:

```text
East-west traffic
```

---

## North-South Traffic

North-south traffic enters or leaves the data center.

The source or destination is external to the data center.

### Examples

- User on the internet connects to a web server
- Data-center server sends information to an external service
- Remote employee accesses an internal application
- Application receives inbound internet traffic

### Diagram

```text
Internet
↕
Data center
```

### Key Characteristics

- Traffic enters or exits the data center
- May come from external networks
- Commonly requires additional security controls
- May pass through firewalls or edge devices

### Security Consideration

North-south traffic commonly requires a different security posture because external traffic may come from unknown or untrusted sources.

### Key Takeaway

```text
North-south traffic = Traffic entering or leaving the data center
```

### Exam Tip

If the question mentions internet traffic moving into or out of a data center, think:

```text
North-south traffic
```

---

## East-West vs. North-South Traffic

| Traffic Flow | Direction | Description | Example |
| ------------ | --------- | ----------- | ------- |
| East-west | Internal | Traffic stays inside the same data center | Application server communicates with database server |
| North-south | Inbound or outbound | Traffic enters or leaves the data center | Internet user connects to web server |

### Memory Trick

```text
East-west
= Side-to-side
= Internal traffic

North-south
= In and out
= External traffic
```

---

## Network Architecture Comparison

| Architecture or Traffic Type | Description | Common Use |
| ---------------------------- | ----------- | ---------- |
| Three-tier architecture | Core, distribution, and access layers | Larger enterprise networks |
| Collapsed core architecture | Core and distribution combined into one layer | Smaller organizations |
| Access layer | User and endpoint-device connectivity | Local switch connections |
| Distribution layer | Midpoint between users and core resources | Traffic aggregation and redundancy |
| Core layer | Central network resources and high-speed connectivity | Enterprise backbone |
| East-west traffic | Internal data-center traffic | Server-to-server communication |
| North-south traffic | Traffic entering or leaving data center | Internet and external connectivity |

---

## Cloud Engineering Connection

Cloud engineers need to understand network architectures when supporting:

- Data centers
- Hybrid cloud environments
- Virtual networks
- Cloud subnets
- Application tiers
- Network segmentation
- Firewalls
- Security groups
- Load balancers
- Database connectivity
- Internal service communication
- Internet-facing applications
- Branch offices
- Campus networks

### Cloud Scenario Examples

```text
Application server communicates with database server inside cloud network
→ East-west traffic

Internet user connects to cloud-hosted website
→ North-south traffic

Small company combines core and distribution functionality
→ Collapsed core architecture

Large campus separates core, distribution, and access switches
→ Three-tier architecture
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Three enterprise-network layers | Core, distribution, and access |
| Central critical resources | Core layer |
| Midpoint between users and central resources | Distribution layer |
| User devices connect to nearby switches | Access layer |
| Core and distribution combined | Collapsed core |
| Two-tier architecture | Collapsed core |
| Smaller organization with simpler architecture | Collapsed core |
| Traffic between servers inside one data center | East-west traffic |
| File server communicating with image server | East-west traffic |
| Traffic entering or leaving data center | North-south traffic |
| Internet traffic reaching web server | North-south traffic |
| External traffic with different security posture | North-south traffic |

---

## Memory Trick

```text
Core         = Central resources
Distribution = Midpoint
Access       = End-user connections

Collapsed core = Core + Distribution

East-west   = Internal traffic
North-south = Inbound and outbound traffic
```

---

## Practice Questions

### 1. What are the three layers of a three-tier network architecture?

Answer: Core, distribution, and access

### 2. Which layer commonly contains central network resources?

Answer: Core layer

### 3. Which layer provides a midpoint between users and core resources?

Answer: Distribution layer

### 4. Which layer commonly connects user devices to the network?

Answer: Access layer

### 5. What is a collapsed core architecture?

Answer: A two-tier architecture that combines the core and distribution layers.

### 6. Why might a smaller organization use a collapsed core design?

Answer: It may be simpler, easier to troubleshoot, and less expensive to implement.

### 7. What is a possible limitation of a collapsed core design?

Answer: It may provide fewer redundancy options.

### 8. What is east-west traffic?

Answer: Traffic that stays inside the same data center.

### 9. What is north-south traffic?

Answer: Traffic that enters or leaves the data center.

### 10. A file server communicates with an image server inside the same data center. What type of traffic is this?

Answer: East-west traffic

### 11. An internet user connects to a data-center web server. What type of traffic is this?

Answer: North-south traffic

### 12. Why may north-south traffic require additional security controls?

Answer: It may come from or travel to external and potentially untrusted networks.
