# Network+ N10-009 Study Notes: Designing the Cloud

## Video Topic

Designing the Cloud

## Summary

This lesson explains how cloud computing changes the way organizations deploy applications, servers, networks, and security controls.

Cloud computing allows organizations to deploy resources quickly, scale applications up or down, and access services from anywhere in the world. It also uses multitenancy, where many customers share the same cloud infrastructure while keeping their environments logically separated.

The main topics covered are:

- Cloud elasticity
- Multitenancy
- Network Function Virtualization
- Virtual Private Cloud
- Transit gateways
- VPN connectivity
- Internet gateways
- NAT gateways
- VPC endpoints
- Security groups
- Network security lists
- Virtual firewalls

---

## Cloud Computing

Cloud computing allows organizations to deploy applications, servers, storage, and networking resources without needing to physically manage all of the hardware themselves.

### Key Benefits

- Fast deployment
- Elastic scaling
- Access from anywhere
- Shared infrastructure
- Lower infrastructure overhead
- High availability options
- Virtualized servers and networks

### Elasticity

Elasticity means cloud resources can scale up or down based on demand.

Example:

If a web application has high traffic, more resources can be added.

When demand decreases, resources can be reduced.

### Multitenancy

Multitenancy means multiple customers use the same cloud provider infrastructure.

The physical infrastructure may be shared, but each customer’s environment is logically separated.

---

## Network Function Virtualization

Network Function Virtualization, or NFV, replaces physical network appliances with virtual versions.

Instead of using physical routers, switches, firewalls, and load balancers, cloud environments can use virtual appliances.

### Examples of Virtual Network Functions

- Virtual routers
- Virtual switches
- Virtual firewalls
- Virtual load balancers
- Virtual network interfaces

### Why NFV Matters

NFV gives organizations flexibility because networking resources can be deployed or changed quickly, similar to deploying virtual servers.

### Cloud Engineering Connection

Cloud engineers use NFV concepts when designing virtual networks, route tables, load balancers, firewalls, and secure connectivity between applications.

---

## Virtual Private Cloud

A Virtual Private Cloud, or VPC, is a logically isolated cloud network.

A VPC can contain:

- Virtual machines
- Public subnets
- Private subnets
- Load balancers
- Virtual routers
- Virtual switches
- Virtual firewalls
- Databases
- Application servers

A company may use separate VPCs for different applications, departments, environments, or business units.

Examples:

- Production VPC
- Development VPC
- Testing VPC
- Finance VPC
- Web application VPC

---

## Transit Gateway

A transit gateway connects multiple VPCs together.

It works like a cloud router that allows communication between separate cloud networks.

### Example

If an organization has three VPCs, a transit gateway can allow those VPCs to communicate through a central routing point.

```text
VPC A → Transit Gateway → VPC B
VPC C → Transit Gateway → VPC A
