# Network+ N10-009 Study Notes: Zero Trust

## Video Topic

Zero Trust

## Summary

Zero trust is a security model that assumes every user, device, application, and network connection is untrusted until verified.

Traditional security models often focused on protecting the edge of the network. Once a user entered the internal network, many resources were broadly accessible.

Zero trust improves security by continuously evaluating identity, device posture, context, and access requirements.

This lesson covers:

- Zero trust
- Policy-based authentication
- Adaptive identity
- Context-aware access
- Least privilege
- Authorization
- Secure Access Service Edge
- Zero Trust Network Access
- Firewall as a Service
- DNS security
- Network as a Service

---

## Traditional Network Security

Traditional network security often focused on protecting the perimeter.

```text
Outside network
→ Firewall or edge control
→ Internal network
```

### Limitation

Once a user entered the internal network, many internal resources could be broadly accessible.

This creates risk if:

- Credentials are stolen
- Malware enters the network
- A user receives excessive permissions
- A compromised device moves laterally
- An insider misuses access

### Key Takeaway

```text
Traditional model
= Strong perimeter
= More trust inside the network
```

---

## Zero Trust

Zero trust assumes that no user, device, application, or connection should be trusted automatically.

### Core Principle

```text
Never trust automatically
Always verify
```

### Zero-Trust Scope

Zero trust evaluates:

- Users
- Devices
- Applications
- Network traffic
- Authentication attempts
- Authorization requests
- Locations
- IP addresses
- Connection types
- Device certificates
- Time of access
- Risk signals

### Key Takeaway

```text
Zero trust = Verify every access request
```

---

## Zero-Trust Security Controls

Organizations may use multiple controls to support zero trust.

| Security Control | Purpose |
| ---------------- | ------- |
| Authentication | Verifies user identity |
| Encryption | Protects data in transit |
| Firewalls | Restrict network traffic |
| Monitoring | Detects suspicious activity |
| Device verification | Confirms device trust level |
| Policy enforcement | Applies context-aware access rules |
| Least privilege | Limits permissions to required access only |

---

## Authentication

Authentication confirms that a user is who they claim to be.

### Common Authentication Factors

- Username
- Password
- Security token
- Authentication app
- Biometrics
- Certificate
- Hardware key
- One-time passcode

### Key Takeaway

```text
Authentication = Verify identity
```

---

## Authorization

Authorization determines what an authenticated user is allowed to access.

### Example

| User Role | Access Level |
| --------- | ------------ |
| Help desk analyst | View hardware database |
| Help desk manager | View and modify hardware database |
| Unrelated employee | No access |

### Key Takeaway

```text
Authentication = Who are you?
Authorization  = What are you allowed to do?
```

---

## Policy-Based Authentication

Policy-based authentication evaluates additional context before allowing access.

The access decision is not based only on a username and password.

### Contextual Factors

- User identity
- Job role
- Employment history
- Location
- Country
- IP address
- Time of day
- Connection type
- Device ownership
- Device certificate
- VPN usage
- Risk level

### Example

```text
Correct username and password
+ Normal office location
+ Corporate laptop
+ Normal working hours
→ Allow access
```

```text
Correct username and password
+ Unknown IP address
+ Different country
+ VPN connection
+ Unusual time
→ Require additional authentication or deny access
```

---

## Adaptive Identity

Adaptive identity changes the authentication process based on risk.

### Example

```text
Low-risk access attempt
→ Username and password may be sufficient
```

```text
Higher-risk access attempt
→ Require additional authentication factor
```

### Key Takeaway

```text
Adaptive identity = Authentication changes based on context and risk
```

---

## Least Privilege

Least privilege means users should receive only the permissions required to complete their job responsibilities.

### Example

```text
User needs read-only access
→ Provide read access only
→ Do not provide administrator rights
```

### Why Least Privilege Matters

Administrative access can increase risk.

If malware compromises a device used by an administrator, the malware may gain access to sensitive systems and data.

### Key Takeaway

```text
Least privilege = Minimum required access only
```

---

## Device Trust

Zero-trust decisions may also evaluate the device.

### Device-Trust Factors

- Corporate-owned laptop
- Valid device certificate
- Approved operating system
- Updated security software
- Compliance status
- Encryption status
- Managed-device status

### Example

```text
Corporate laptop with verified certificate
→ Higher trust level
```

```text
Unknown personal device
→ Lower trust level
→ Additional restrictions may apply
```

---

## SASE: Secure Access Service Edge

SASE stands for:

```text
Secure Access Service Edge
```

SASE provides cloud-delivered networking and security services.

It can help users securely access applications regardless of where the users or applications are located.

### Common User Locations

- Corporate office
- Home office
- Mobile device
- Field location
- Remote branch office

### Common Application Locations

- Public cloud
- Private data center
- SaaS platform
- Internet service
- Hybrid cloud environment

### Key Takeaway

```text
SASE = Cloud-delivered networking and security close to users and applications
```

---

## SASE Capabilities

| Capability | Purpose |
| ---------- | ------- |
| Network as a Service | Provides routing and connectivity |
| Quality of Service | Prioritizes important traffic |
| Zero Trust Network Access | Controls access based on identity and policy |
| Firewall as a Service | Provides cloud-delivered firewall protections |
| DNS security | Protects against unsafe domain activity |
| Cloud security services | Applies security controls close to applications |

---

## ZTNA: Zero Trust Network Access

ZTNA stands for:

```text
Zero Trust Network Access
```

ZTNA provides secure access to resources based on identity, device posture, and policy.

### Key Takeaway

```text
ZTNA = Secure resource access based on zero-trust principles
```

---

## Firewall as a Service

Firewall as a Service is commonly abbreviated as:

```text
FWaaS
```

FWaaS provides firewall functionality through a cloud-delivered service.

### Key Takeaway

```text
FWaaS = Firewall protection delivered from the cloud
```

---

## SASE Client

A SASE client may be installed on user devices.

The client applies secure access automatically.

### User Experience

```text
User opens device
→ SASE client connects automatically
→ Security policies apply
→ User accesses approved resources
```

### Key Takeaway

```text
SASE security can operate automatically without requiring users to manually enable a VPN
```

---

## Zero Trust vs. Traditional Perimeter Security

| Traditional Perimeter Model | Zero-Trust Model |
| --------------------------- | ---------------- |
| Trust increases after entering network | Every request is evaluated |
| Strong focus on network edge | Security applies throughout environment |
| Internal access may be broad | Access is limited by policy |
| Username and password may be enough | Context and risk may affect decision |
| Permissions may be excessive | Least privilege is enforced |

---

## Cloud Engineering Connection

Cloud engineers use zero-trust and SASE concepts when supporting:

- Cloud applications
- Hybrid cloud environments
- SaaS applications
- Remote workforces
- Branch offices
- Identity and access management
- Device posture checks
- Cloud firewalls
- DNS security
- Zero Trust Network Access
- Network segmentation
- Least-privilege access
- Policy automation
- Secure cloud migrations

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Never trust automatically | Zero trust |
| Verify every user, device, and application | Zero trust |
| Evaluate location, IP address, time, and device | Policy-based authentication |
| Change authentication based on risk | Adaptive identity |
| Minimum permissions required for job | Least privilege |
| Determine what a user can access | Authorization |
| Verify who a user is | Authentication |
| Secure cloud-delivered access service | SASE |
| Zero Trust Network Access | ZTNA |
| Cloud-delivered firewall | FWaaS |
| DNS-based security filtering | DNS security |

---

## Memory Trick

```text
Zero trust       = Verify everything
Authentication   = Who are you?
Authorization    = What can you access?
Least privilege  = Only what you need
Adaptive identity = Change controls based on risk
SASE             = Cloud-delivered secure access
ZTNA             = Zero-trust resource access
FWaaS            = Cloud firewall service
```

---

## Practice Questions

### 1. What is the main idea of zero trust?

Answer: Every user, device, application, and connection should be treated as untrusted until verified.

### 2. What is authentication?

Answer: Verification of a user's identity.

### 3. What is authorization?

Answer: Determining what an authenticated user is allowed to access.

### 4. What is adaptive identity?

Answer: An authentication process that changes based on risk and context.

### 5. What does least privilege mean?

Answer: Users receive only the minimum permissions required for their job.

### 6. What does SASE stand for?

Answer:

```text
Secure Access Service Edge
```

### 7. What does ZTNA stand for?

Answer:

```text
Zero Trust Network Access
```

### 8. What does FWaaS stand for?

Answer:

```text
Firewall as a Service
```

### 9. Which factors may affect a policy-based authentication decision?

Answer: User identity, role, location, IP address, time, connection type, device certificate, and risk level.

### 10. Why is least privilege important?

Answer: It reduces the risk that users or malware gain unnecessary access to sensitive systems and data.
