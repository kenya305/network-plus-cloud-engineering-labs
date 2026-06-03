# Lab 28: Infrastructure as Code and Source Control Analysis

## Objective

Apply Infrastructure as Code concepts to a cloud-infrastructure deployment scenario and document a version-control workflow.

## Scenario

A company needs matching environments for:

- Development
- Testing
- Production
- Disaster recovery

The company also wants to reduce configuration drift and track all infrastructure changes.

---

## Part 1: Infrastructure Requirements

The environment includes:

- Web server
- Database server
- Virtual network
- Firewall rules
- IP-addressing configuration
- Application deployment
- Security settings

---

## Part 2: Example IaC Definition

The following simplified YAML example represents a cloud environment.

```yaml
environment:
  name: sample-cloud-app

network:
  cidr: 10.10.0.0/16

servers:
  - hostname: web01.example.com
    role: web-server
    subnet: 10.10.1.0/24
    cpu: 2
    memory_gb: 4

  - hostname: db01.example.com
    role: database-server
    subnet: 10.10.2.0/24
    cpu: 4
    memory_gb: 8

firewall_rules:
  - name: allow-https
    protocol: tcp
    port: 443
    source: internet
    destination: web01.example.com

  - name: allow-database-from-web
    protocol: tcp
    port: 5432
    source: web01.example.com
    destination: db01.example.com
```

### Important Note

This is a documentation example, not a vendor-specific deployment file.

The goal is to demonstrate the structure and purpose of Infrastructure as Code.

---

## Part 3: Repeatable Deployment Analysis

| Requirement | IaC Benefit |
| ----------- | ----------- |
| Build matching test and production systems | Reuse same approved definitions |
| Deploy disaster-recovery environment | Duplicate infrastructure in another location |
| Apply software upgrade | Update definition and redeploy |
| Document existing systems | Store infrastructure definitions in code |
| Reduce manual setup errors | Automate repeatable deployment |

---

## Part 4: Configuration Drift Analysis

### Problem

```text
Server A receives manual update
Server B does not receive update
→ Configurations no longer match
```

### IaC Response

```text
Store approved configuration in source control
→ Redeploy approved definition
→ Restore consistent state
```

---

## Part 5: Playbook Example

### Malware-Response Playbook

```text
1. Detect malware.
2. Isolate affected device.
3. Remove device from network.
4. Delete compromised storage data.
5. Reimage system.
6. Redeploy approved configuration.
7. Verify security controls.
8. Return system to service.
```

### SOAR Connection

```text
SOAR platform
→ Runs repeatable playbook
→ Coordinates automated response
```

---

## Part 6: Git Workflow

### Recommended Workflow

```text
1. Store IaC files in Git repository.
2. Create branch for proposed change.
3. Update configuration file.
4. Review changes.
5. Test changes in non-production environment.
6. Resolve merge conflicts if needed.
7. Merge approved changes.
8. Deploy approved production version.
```

---

## Part 7: Branch and Merge Scenario

### Scenario

Two cloud engineers work on separate infrastructure updates.

```text
Engineer A
→ Creates firewall-rule branch
→ Adds HTTPS rule

Engineer B
→ Creates database-size branch
→ Increases database memory
```

### Result

```text
Review changes
→ Test changes
→ Merge approved updates
→ Deploy updated IaC configuration
```

---

## Part 8: Merge Conflict Scenario

### Scenario

Two engineers edit the same firewall rule differently.

```text
Engineer A
→ Changes source network to 10.10.1.0/24

Engineer B
→ Changes same source network to 10.10.3.0/24
```

### Required Action

```text
Resolve merge conflict
→ Review business requirement
→ Select correct value
→ Merge approved configuration
```

---

## What I Observed

Infrastructure as Code allows environments to be defined using reusable configuration files.

IaC supports:

```text
Repeatable deployment
Environment consistency
Reduced configuration drift
Compliance
Disaster recovery
Versioned changes
```

Source control supports:

```text
Change tracking
Branches
Testing
Merging
Conflict resolution
Audit history
```

---

## Important Limitation

IaC does not eliminate the need for review, testing, or security controls.

A cloud engineer should still evaluate:

- Security requirements
- Secrets management
- Access controls
- Change approvals
- Testing
- Rollback procedures
- Vendor-specific syntax
- Compliance requirements
- Monitoring
- Deployment validation

---

## Cloud Engineering Connection

Cloud engineers use IaC and source control when supporting:

- Virtual networks
- Virtual machines
- Firewalls
- Security groups
- Load balancers
- Databases
- Storage
- CI/CD pipelines
- Disaster recovery
- Compliance
- Multi-region deployments
- DevOps workflows
- Git repositories

---

## Skills Practiced

- Explaining Infrastructure as Code
- Documenting IaC structure
- Identifying configuration-drift risks
- Applying a playbook workflow
- Connecting playbooks to SOAR
- Documenting Git branch and merge workflows
- Identifying merge conflicts
- Connecting IaC to cloud engineering
