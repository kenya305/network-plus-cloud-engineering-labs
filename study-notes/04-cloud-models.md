# Network+ N10-009 Study Notes: Cloud Models

## Video Topic

Cloud Models

## Summary

Cloud-based applications can be deployed in different ways depending on who needs access to the application, where the application should run, and how much responsibility the customer wants to manage.

This lesson covers:

* Public cloud
* Private cloud
* Hybrid cloud
* Software as a Service (SaaS)
* Infrastructure as a Service (IaaS)
* Hardware as a Service (HaaS)
* Platform as a Service (PaaS)
* On-premises infrastructure
* Shared responsibility models

---

## Cloud Deployment Models

Cloud deployment models describe where cloud resources are hosted and who can access them.

### Public Cloud

A public cloud is designed to provide resources or applications that may be accessible over the internet.

### Example

A company builds a website or application that customers need to access from anywhere.

### Key Characteristics

* Hosted by a cloud provider
* Commonly accessed through the internet
* Designed for scalability
* Can support external users

### Cloud Engineering Connection

Cloud engineers use public cloud platforms to deploy websites, APIs, storage, virtual machines, and other services.

Examples include:

* Amazon Web Services (AWS)
* Microsoft Azure
* Google Cloud Platform (GCP)

---

### Private Cloud

A private cloud is designed for internal use by one organization.

It may run inside the organization's own virtualized local data center.

### Example

A company deploys an internal application that only employees should access.

### Key Characteristics

* Used by one organization
* Commonly designed for internal access
* Greater control over the environment
* May run in a local data center

### Cloud Engineering Connection

Private clouds may be used when organizations require more control over security, access, compliance, or internal systems.

---

### Hybrid Cloud

A hybrid cloud combines public cloud and private cloud environments.

Organizations often use hybrid cloud configurations because some applications need public access while other applications should remain private.

### Example

A company hosts a public customer-facing website in the public cloud but keeps sensitive internal systems in a private environment.

### Key Characteristics

* Combines public and private cloud resources
* Supports flexible application deployment
* Helps organizations balance accessibility and control
* Common in enterprise environments

### Cloud Engineering Connection

Cloud engineers frequently work with hybrid environments that connect:

* Public cloud services
* Private cloud resources
* On-premises infrastructure
* VPNs
* Internal applications
* External applications

---

## Cloud Service Models

Cloud service models describe how much responsibility the cloud provider manages and how much responsibility the customer manages.

The primary cloud service models are:

| Model       | Full Name                       | Customer Responsibility Level |
| ----------- | ------------------------------- | ----------------------------- |
| SaaS        | Software as a Service           | Lower                         |
| PaaS        | Platform as a Service           | Medium                        |
| IaaS        | Infrastructure as a Service     | Higher                        |
| On-premises | Customer-managed infrastructure | Highest                       |

---

## SaaS: Software as a Service

SaaS stands for Software as a Service.

SaaS provides a complete application that users can access on demand.

The user typically logs in through a browser and uses the application without installing or maintaining the software locally.

### Key Characteristics

* Complete application offering
* Accessed through a login screen or browser
* No local software installation required
* Provider manages the application
* Provider manages software upgrades
* Data is stored within the third-party cloud platform

### Examples

* Gmail
* Microsoft 365

### Simple Example

```text
Log in → Use the application → Log out
```

### Cloud Engineering Connection

SaaS is useful when an organization needs access to an application without managing the software infrastructure.

### Exam Tip

If the question describes a complete cloud application that users log in to and use without installing or maintaining software, think SaaS.

---

## IaaS: Infrastructure as a Service

IaaS stands for Infrastructure as a Service.

IaaS provides the computing resources needed to build and run applications.

The cloud provider supplies the underlying infrastructure, while the customer installs software, manages the application, maintains the data, and performs software upgrades.

IaaS may also be called Hardware as a Service (HaaS).

### Key Characteristics

* Cloud provider supplies computing infrastructure
* Customer manages the software
* Customer manages application data
* Customer performs software upgrades
* Customer has more control than with SaaS

### Examples

* Cloud-hosted virtual machines
* Cloud-hosted web servers
* Computing resources rented from a cloud provider

### Simple Example

```text
Cloud provider supplies server resources → Customer installs and manages software
```

### Cloud Engineering Connection

Cloud engineers commonly use IaaS to deploy:

* Virtual machines
* Web servers
* Storage
* Networks
* Firewalls
* Custom applications

### Exam Tip

If the question says the customer needs cloud-hosted computing resources but wants to install and manage their own software, think IaaS.

---

## HaaS: Hardware as a Service

HaaS stands for Hardware as a Service.

HaaS is another name that may be used for IaaS because the customer is effectively using hardware resources in the cloud.

### Key Takeaway

```text
HaaS is commonly associated with IaaS.
```

---

## PaaS: Platform as a Service

PaaS stands for Platform as a Service.

PaaS is a middle ground between SaaS and IaaS.

The cloud provider supplies the tools and underlying platform needed to build an application.

The customer develops and maintains the application, while the provider manages the underlying engine or platform.

### Key Characteristics

* Provider supplies development tools
* Provider manages the underlying platform
* Customer builds and customizes the application
* Customer maintains the application they created

### Example

* Salesforce platform tools used to create customized applications

### Simple Example

```text
Cloud provider supplies building blocks → Customer builds the application
```

### Cloud Engineering Connection

PaaS can help development and engineering teams build applications without managing the full underlying infrastructure.

### Exam Tip

If the question says the cloud provider gives the customer tools or building blocks to create a customized application, think PaaS.

---

## On-Premises Infrastructure

On-premises infrastructure is managed entirely by the customer.

The customer is responsible for everything from the physical data center to the applications and data.

### Key Characteristics

* Customer manages the data center
* Customer manages physical servers
* Customer manages networking
* Customer manages operating systems
* Customer manages applications
* Customer manages data

### Simple Example

```text
Customer manages everything
```

---

## Cloud Responsibility Matrix

The amount of customer responsibility changes depending on the cloud model.

| Model       | Provider Manages                                           | Customer Manages                                                |
| ----------- | ---------------------------------------------------------- | --------------------------------------------------------------- |
| SaaS        | Most application infrastructure and application management | User access, accounts, devices, and data usage responsibilities |
| PaaS        | Underlying platform and application engine                 | Custom application development, accounts, devices, and data     |
| IaaS        | Physical data center, physical network, and physical host  | Operating systems, software, applications, accounts, and data   |
| On-premises | Nothing                                                    | Everything                                                      |

### Memory Trick

```text
SaaS = Use the software
PaaS = Build on the platform
IaaS = Manage software on rented infrastructure
On-premises = Manage everything
```

---

## Quick Comparison Table

| Model         | Best Description                                    | Example Clue                                   |
| ------------- | --------------------------------------------------- | ---------------------------------------------- |
| Public cloud  | Cloud resources available for broad external access | Customer-facing website                        |
| Private cloud | Cloud resources for one organization's internal use | Internal company application                   |
| Hybrid cloud  | Combination of public and private cloud resources   | Public website plus internal systems           |
| SaaS          | Complete cloud application                          | Log in and use the software                    |
| PaaS          | Cloud platform for application development          | Use building blocks to create an app           |
| IaaS          | Cloud-hosted computing infrastructure               | Rent servers and manage your own software      |
| On-premises   | Customer manages everything                         | Organization owns and maintains infrastructure |

---

## Exam Clue Table

| If the exam mentions...                                 | Think...      |
| ------------------------------------------------------- | ------------- |
| Application available for broad internet access         | Public cloud  |
| Internal virtualized company data center                | Private cloud |
| Combination of public and private cloud resources       | Hybrid cloud  |
| Log in through a browser and use a complete application | SaaS          |
| No local application installation or upgrades required  | SaaS          |
| Build a customized application using provider tools     | PaaS          |
| Provider manages the underlying application engine      | PaaS          |
| Rent server resources and manage your own software      | IaaS          |
| Hardware as a Service                                   | IaaS / HaaS   |
| Customer manages the entire data center                 | On-premises   |

---

## Practice Questions

### 1. A company wants to deploy a website that customers can access over the internet. Which deployment model is appropriate?

Answer: Public cloud

### 2. A company uses a local virtualized data center for an internal application. Which deployment model is this?

Answer: Private cloud

### 3. A company uses public cloud resources for external applications and private cloud resources for internal applications. Which deployment model is this?

Answer: Hybrid cloud

### 4. A user logs in to Gmail through a browser without installing software. Which service model is this?

Answer: SaaS

### 5. A developer wants cloud-based tools to build a customized application without managing the underlying platform. Which service model is appropriate?

Answer: PaaS

### 6. A company rents cloud-hosted servers but installs and upgrades its own software. Which service model is this?

Answer: IaaS

### 7. Which model gives the customer the greatest responsibility?

Answer: On-premises

### 8. Which cloud service model generally gives the customer the least infrastructure-management responsibility?

Answer: SaaS
