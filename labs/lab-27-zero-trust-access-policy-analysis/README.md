# Lab 27: Zero-Trust Access Policy Analysis

## Objective

Apply zero-trust principles to authentication, authorization, least privilege, and Secure Access Service Edge scenarios.

## Scenario

A company supports employees working from:

- Corporate headquarters
- Home offices
- Branch offices
- Mobile devices
- International locations

The company uses cloud applications, SaaS platforms, and private data-center systems.

The security team wants to reduce risk by applying zero-trust principles.

---

## Part 1: Authentication vs. Authorization

| Security Function | Meaning | Example |
| ----------------- | ------- | ------- |
| Authentication | Verifies identity | User signs in with password and MFA |
| Authorization | Determines allowed access | Help desk analyst receives read-only database access |

---

## Part 2: Policy-Based Authentication

### Scenario A: Low-Risk Access

```text
User: Long-term employee
Location: Corporate office
Device: Company-issued laptop
Certificate: Valid
Time: Normal working hours
Connection: Corporate network
```

### Recommended Decision

```text
Allow access using standard authentication policy
```

### Reason

The access attempt matches expected user, device, location, and time patterns.

---

### Scenario B: Higher-Risk Access

```text
User: Vendor
Location: Different country
Device: Unknown laptop
Certificate: Not verified
Time: Unusual hour
Connection: VPN from unfamiliar IP address
```

### Recommended Decision

```text
Require additional authentication factors or deny access
```

### Reason

The access attempt includes multiple risk indicators.

---

## Part 3: Least-Privilege Access Matrix

| User Role | Required Access | Recommended Permission |
| --------- | --------------- | ---------------------- |
| Help desk analyst | View hardware inventory | Read-only access |
| Help desk manager | Update hardware inventory | Read and modify access |
| Finance analyst | Review financial records | Read access to finance system only |
| System administrator | Maintain approved systems | Administrative access only where required |
| Unrelated employee | No business need | No access |

### Key Takeaway

```text
Provide only the minimum permissions required for the job.
```

---

## Part 4: Device Trust Evaluation

| Device Context | Recommended Trust Level | Recommended Action |
| -------------- | ----------------------- | ------------------ |
| Corporate laptop with valid certificate | Higher trust | Allow approved access |
| Personal laptop without certificate | Lower trust | Restrict access or require additional verification |
| Outdated device without security updates | Lower trust | Deny or remediate before access |
| Managed encrypted device | Higher trust | Apply standard approved access |
| Unknown mobile device | Lower trust | Require additional controls |

---

## Part 5: SASE Design Scenario

### Business Requirement

Users need secure access to applications located in:

- Public cloud
- Private data center
- SaaS platforms
- Internet services

### Recommended Design

```text
User device
→ SASE client
→ Cloud-delivered security and networking controls
→ Approved application
```

### SASE Capabilities

| Capability | Purpose |
| ---------- | ------- |
| Network as a Service | Provides routing and connectivity |
| Quality of Service | Prioritizes important traffic |
| ZTNA | Controls access based on identity and policy |
| FWaaS | Provides cloud-delivered firewall protection |
| DNS security | Protects against unsafe domain activity |

---

## Part 6: Zero-Trust Decision Checklist

Before granting access, evaluate:

- Who is the user?
- What role does the user have?
- Where is the user located?
- What IP address is being used?
- What time is the access attempt?
- What type of connection is being used?
- Is the device managed?
- Does the device have a valid certificate?
- Is the requested access necessary?
- Does the user have the minimum required permissions?

---

## What I Observed

Zero trust assumes that every access request must be verified.

Authentication confirms:

```text
Who the user is
```

Authorization determines:

```text
What the user can access
```

Least privilege ensures:

```text
The user receives only the permissions required for the job
```

SASE provides:

```text
Cloud-delivered secure access for users and applications in different locations
```

---

## Important Limitation

Zero trust is not a single product.

It is a security strategy that requires multiple controls, including:

- Authentication
- Authorization
- Least privilege
- Device verification
- Monitoring
- Encryption
- Network segmentation
- Policy enforcement
- Cloud-delivered security services

---

## Cloud Engineering Connection

Cloud engineers apply zero-trust principles when supporting:

- Identity and access management
- Hybrid cloud security
- SaaS access
- Cloud firewalls
- Zero Trust Network Access
- Device posture checks
- Least-privilege policies
- Remote workforce access
- Branch-office connectivity
- Network segmentation
- Cloud migrations

---

## Skills Practiced

- Distinguishing authentication and authorization
- Evaluating policy-based authentication
- Applying adaptive-identity concepts
- Applying least-privilege access
- Evaluating device trust
- Identifying SASE capabilities
- Connecting zero trust to cloud engineering
- Documenting security-policy analysis in GitHub
