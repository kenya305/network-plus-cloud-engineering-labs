# Network+ N10-009 Study Notes: Infrastructure as Code

## Video Topic

Infrastructure as Code

## Summary

Infrastructure as Code, or IaC, describes infrastructure using configuration files instead of relying only on manual setup.

IaC can define:

- Servers
- Routers
- Switches
- Firewalls
- Applications
- CPU requirements
- Network configuration
- IP addressing
- Installed software
- Security controls
- Cloud resources

IaC allows cloud environments to be deployed consistently, duplicated across locations, updated through code changes, and tracked through source control.

This lesson also introduces:

- Playbooks
- SOAR platforms
- Configuration drift
- Compliance
- Test-to-production consistency
- Source control
- Version control
- Git
- Branches
- Merging
- Merge conflicts

---

## Infrastructure as Code

Infrastructure as Code is commonly abbreviated as:

```text
IaC
```

IaC uses code or configuration files to describe the desired state of infrastructure.

### Key Takeaway

```text
IaC = Describe infrastructure in code
```

---

## Why IaC Matters

Traditional infrastructure deployment may require administrators to:

- Manually install systems
- Configure network devices
- Apply software settings
- Assign IP addresses
- Install applications
- Repeat the same steps across environments

IaC allows these tasks to be defined once and deployed repeatedly.

### Example

```text
Write infrastructure definition
→ Deploy definition
→ Cloud platform builds environment
```

---

## Infrastructure Components That Can Be Defined

| Infrastructure Component | Example Details |
| ------------------------ | --------------- |
| Servers | Hostnames, CPU, memory, applications |
| Routers | Interfaces, routes, IP addresses |
| Switches | VLANs, trunks, management settings |
| Firewalls | Rules, network zones, security policies |
| Applications | Installed packages, dependencies |
| Databases | Hostnames, configurations, connectivity |
| Cloud resources | Instances, networks, storage, security groups |

---

## Repeatable Deployment

IaC allows an environment to be duplicated.

### Example

```text
Production environment in Data Center A
→ Reuse same IaC definitions
→ Deploy matching environment in Data Center B
```

### Benefits

- Consistency
- Faster deployment
- Reduced manual error
- Disaster recovery support
- Multi-region deployment
- Easier testing

---

## Versioned Infrastructure

IaC configurations can be updated over time.

### Example

```text
Version 1
→ Deploy environment

Version 2
→ Modify configuration
→ Redeploy environment
→ Apply updated settings
```

### Key Takeaway

```text
Infrastructure can be versioned like software.
```

---

## Playbooks

A playbook is a defined series of steps used to respond to a specific event or issue.

### Example Use Cases

- Data breach investigation
- Malware response
- Ransomware recovery
- Device isolation
- System reimaging
- Application redeployment
- Security incident response

### Malware-Response Example

```text
Malware detected
→ Isolate device from network
→ Delete compromised storage
→ Reimage system
→ Redeploy system
→ Return device to service
```

### Key Takeaway

```text
Playbook = Repeatable response workflow
```

---

## SOAR Platforms

SOAR stands for:

```text
Security Orchestration, Automation, and Response
```

SOAR platforms help centralize and automate security-response workflows.

### SOAR Functions

- Run playbooks
- Coordinate security tools
- Automate repetitive response tasks
- Monitor incident activity
- Standardize response procedures
- Reduce manual effort

### Key Takeaway

```text
SOAR = Centralized security automation and response
```

---

## Configuration Drift

Configuration drift occurs when systems that were originally identical gradually become different.

### Example

```text
Server A
→ Updated manually

Server B
→ Not updated

Result
→ Different configurations
→ Configuration drift
```

### How IaC Helps

```text
Use one approved IaC definition
→ Deploy consistently
→ Reduce configuration drift
```

---

## Compliance

IaC can help enforce consistent standards across environments.

### Example

```text
Approved security baseline
→ Stored in IaC definitions
→ Applied to all systems
→ Consistent compliance posture
```

### Key Takeaway

```text
IaC supports repeatability and compliance.
```

---

## Test and Production Consistency

IaC can help make testing environments match production environments.

### Example

```text
Deploy test environment from IaC
→ Validate changes
→ Deploy same approved definitions to production
```

### Benefit

This reduces unexpected differences between test and production systems.

---

## Source Control

Source control tracks changes to code and configuration files.

It may also be called:

```text
Version control
```

### Benefits

- Tracks changes
- Stores revision history
- Supports collaboration
- Prevents uncontrolled edits
- Allows testing before deployment
- Supports rollback
- Provides audit trail

### Key Takeaway

```text
Source control = Manage and track changes
```

---

## Git

Git is a widely used version-control system.

Git helps teams:

- Store code
- Track revisions
- Create branches
- Merge changes
- Resolve conflicts
- Collaborate across locations
- Maintain production definitions

### Key Takeaway

```text
Git = Version-control system
```

---

## Branching

A branch is a separate version of code used for changes or testing.

### Example

```text
Production branch
→ Create test branch
→ Make changes
→ Validate changes
→ Merge approved updates
```

### Benefits

- Safe testing
- Parallel development
- Controlled changes
- Reduced production risk

---

## Merging

Merging combines changes from one branch into another.

### Example

```text
Feature branch
→ Approved changes
→ Merge into production branch
```

---

## Merge Conflicts

A merge conflict occurs when two changes affect the same line or section of code.

### Example

```text
Administrator A changes line 20
Administrator B changes line 20
→ Merge conflict
→ Manual review may be required
```

### Key Takeaway

```text
Merge conflict = Competing changes that require resolution
```

---

## IaC Workflow

```text
1. Define infrastructure requirements.
2. Write configuration files.
3. Store files in source control.
4. Create branch for changes.
5. Test the updated configuration.
6. Review and approve changes.
7. Merge changes.
8. Deploy updated infrastructure.
9. Monitor for issues.
```

---

## Cloud Engineering Connection

Cloud engineers use IaC when working with:

- Virtual machines
- Virtual networks
- Cloud firewalls
- Security groups
- Load balancers
- Databases
- Storage
- Multi-region deployments
- Disaster recovery
- DevOps workflows
- CI/CD pipelines
- Compliance
- Source control
- Automation
- Environment consistency

### Example

```text
Need matching test and production environments
→ Define infrastructure as code
→ Store in Git
→ Deploy from same approved definitions
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Describe infrastructure using configuration files | IaC |
| Duplicate identical environment in another data center | IaC |
| Repeatable security-response steps | Playbook |
| Security Orchestration, Automation, and Response | SOAR |
| Systems slowly become inconsistent | Configuration drift |
| Track changes to definition files | Source control |
| Another term for source control | Version control |
| Popular version-control platform | Git |
| Separate copy of code for testing | Branch |
| Combine approved changes | Merge |
| Two users edit same line differently | Merge conflict |

---

## Memory Trick

```text
IaC      = Infrastructure described as code
Playbook = Repeatable response steps
SOAR     = Security automation platform
Drift    = Systems slowly become inconsistent
Git      = Version control
Branch   = Safe place to test changes
Merge    = Combine approved changes
Conflict = Competing edits
```

---

## Practice Questions

### 1. What does IaC stand for?

Answer:

```text
Infrastructure as Code
```

### 2. What is the purpose of IaC?

Answer: To define infrastructure using code or configuration files so environments can be deployed consistently and repeatedly.

### 3. What is a playbook?

Answer: A defined series of repeatable steps used to respond to an issue or event.

### 4. What does SOAR stand for?

Answer:

```text
Security Orchestration, Automation, and Response
```

### 5. What is configuration drift?

Answer: The gradual difference that develops between systems that were originally configured the same way.

### 6. How can IaC help with compliance?

Answer: IaC applies approved configuration standards consistently across systems.

### 7. What is source control?

Answer: A system for tracking and managing changes to code and configuration files.

### 8. What is Git?

Answer: A version-control system used to track changes, create branches, merge updates, and support collaboration.

### 9. What is a branch?

Answer: A separate version of code used for testing or development changes.

### 10. What is a merge conflict?

Answer: A conflict that occurs when multiple changes affect the same line or section of code.
