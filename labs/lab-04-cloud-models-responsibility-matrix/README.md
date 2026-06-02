# Lab 04: Cloud Models Responsibility Matrix

## Objective

Compare cloud deployment models and cloud service models to determine which option is appropriate for different business requirements.

## Scenario

A company is reviewing different cloud options for four technology needs:

1. A customer-facing website that anyone can access online
2. An internal employee application
3. An email platform that employees can log in to and use
4. A custom web application that the company wants to build and manage

The goal is to identify the correct cloud deployment model and service model for each use case.

---

## Cloud Deployment Models Comparison

| Deployment Model | Description                                                           | Example Business Use Case                    |
| ---------------- | --------------------------------------------------------------------- | -------------------------------------------- |
| Public Cloud     | Cloud resources designed for broad access, commonly over the internet | Customer-facing website                      |
| Private Cloud    | Cloud environment used internally by one organization                 | Internal employee application                |
| Hybrid Cloud     | Combination of public and private cloud environments                  | Public website plus private internal systems |

---

## Cloud Service Models Comparison

| Service Model | Provider Responsibility                                                         | Customer Responsibility                                               | Example                          |
| ------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------- | -------------------------------- |
| SaaS          | Provider manages the complete application and underlying infrastructure         | Customer manages user access, accounts, devices, and data usage       | Gmail or Microsoft 365           |
| PaaS          | Provider manages the platform and underlying engine                             | Customer builds and maintains the custom application and manages data | Application development platform |
| IaaS          | Provider manages the physical data center, physical network, and physical hosts | Customer manages operating systems, software, applications, and data  | Cloud-hosted virtual machine     |
| On-premises   | Provider does not manage the infrastructure                                     | Customer manages everything                                           | Company-owned local data center  |

---

## Use Case Analysis

### Use Case 1: Customer-Facing Website

**Requirement:** Customers need to access a website over the internet.

**Recommended deployment model:** Public cloud

**Reason:** A public cloud is appropriate for an application that needs to be accessible broadly over the internet.

---

### Use Case 2: Internal Employee Application

**Requirement:** Only employees should access the application.

**Recommended deployment model:** Private cloud

**Reason:** A private cloud provides an internal environment for organization-specific applications.

---

### Use Case 3: Email Platform

**Requirement:** Employees need an email service that they can log in to and use without installing or upgrading software.

**Recommended service model:** SaaS

**Reason:** SaaS provides a complete application that users can access through a browser or login screen.

---

### Use Case 4: Custom Web Application

**Requirement:** The company wants to install and manage its own software on cloud-hosted server resources.

**Recommended service model:** IaaS

**Reason:** IaaS provides computing infrastructure while allowing the customer to manage the application, software, and data.

---

### Optional Alternative for Use Case 4

If the company wants to build a custom application using provider-managed development tools and does not want to manage the underlying engine, PaaS may be more appropriate.

---

## Shared Responsibility Takeaway

As the service model changes, the amount of customer responsibility changes.

```text
SaaS → Lower customer management responsibility
PaaS → Moderate customer management responsibility
IaaS → Higher customer management responsibility
On-premises → Customer manages everything
```

---

## Cloud Engineering Connection

Cloud engineers need to understand cloud models so they can recommend the correct architecture based on business requirements, security needs, application access, and operational responsibilities.

These decisions affect:

* Application architecture
* Infrastructure management
* Security responsibilities
* Data management
* User access
* Scalability
* Cost planning
* Hybrid cloud connectivity

---

## Skills Practiced

* Comparing public, private, and hybrid cloud deployments
* Comparing SaaS, PaaS, IaaS, and on-premises environments
* Applying cloud models to business requirements
* Understanding shared responsibility concepts
* Documenting a cloud engineering decision matrix
