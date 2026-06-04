# Lab 40: Wireless Encryption Security Analysis

## Objective

Compare WEP, WPA, WPA2, and WPA3 and document how authentication, confidentiality, and message integrity protect wireless traffic.

## Scenario

A company is upgrading wireless security for:

- Employee laptops
- Mobile devices
- Guest Wi-Fi
- IoT devices
- Branch offices
- Cloud-managed access points

The company wants to select the strongest practical wireless-security configuration.

---

## Part 1: Wireless-Security Goals

| Security Goal | Purpose |
| ------------- | ------- |
| Authentication | Confirms that a user or device is allowed to connect |
| Confidentiality | Prevents unauthorized users from reading wireless traffic |
| Message integrity | Confirms that transmitted data was not altered |

---

## Part 2: Protocol Comparison

| Protocol | Full Name | Security Status | Recommendation |
| -------- | --------- | --------------- | -------------- |
| WEP | Wired Equivalent Privacy | Obsolete and insecure | Do not use |
| WPA | Wi-Fi Protected Access | Transitional improvement | Avoid for modern deployments |
| WPA2 | Wi-Fi Protected Access version 2 | Strong when configured properly | Use if WPA3 unavailable |
| WPA3 | Wi-Fi Protected Access version 3 | Modern preferred standard | Use when supported |

---

## Part 3: WEP Analysis

### Problem

```text
WEP
→ Serious cryptographic weaknesses
→ Traffic may be compromised
```

### Recommendation

```text
Replace WEP immediately.
```

---

## Part 4: WPA Analysis

### Role

```text
WEP weaknesses discovered
→ WPA introduced as temporary improvement
→ Existing hardware could often continue operating
→ WPA2 later replaced WPA
```

### Recommendation

```text
Do not deploy WPA for modern networks.
```

---

## Part 5: WPA2 Analysis

### Protection Method

```text
WPA2
→ AES encryption
→ CCMP protection
```

### CCMP

```text
Counter Mode with Cipher Block Chaining Message Authentication Code Protocol
```

### Security Functions

| Function | Technology |
| -------- | ---------- |
| Confidentiality | AES |
| Integrity | CBC-MAC within CCMP |

---

## Part 6: WPA3 Analysis

### Protection Method

```text
WPA3
→ Modern stronger wireless-security protections
→ AES-based encryption
→ Modern integrity protections
```

### GCMP

```text
Galois/Counter Mode Protocol
```

### GMAC

```text
Galois Message Authentication Code
```

### Security Functions

| Function | Technology |
| -------- | ---------- |
| Confidentiality | AES |
| Integrity | GMAC in GCMP-based implementations |

---

## Part 7: Accuracy Note

The transcript refers to:

```text
GCMHP
```

The correct protocol name is:

```text
GCMP
```

which stands for:

```text
Galois/Counter Mode Protocol
```

---

## Part 8: Security Selection Matrix

| Environment | Recommended Security |
| ----------- | -------------------- |
| Modern corporate Wi-Fi | WPA3 when supported |
| Mixed older and newer devices | WPA2 or WPA2/WPA3 transition mode as appropriate |
| Guest Wi-Fi | Strongest supported method with guest isolation and policy controls |
| Legacy device requiring WEP | Replace or isolate legacy device |
| IoT network | Strongest supported method plus segmentation |

---

## Part 9: Wireless-Security Upgrade Plan

```text
1. Inventory access points.
2. Inventory client-device support.
3. Identify WEP or WPA dependencies.
4. Replace unsupported legacy devices where possible.
5. Enable WPA3 when supported.
6. Use WPA2 only where necessary.
7. Segment IoT and guest devices.
8. Test connectivity.
9. Monitor authentication failures.
10. Document final configuration.
```

---

## Part 10: Cloud Security Scenario

### Requirement

Employees access cloud applications from branch-office Wi-Fi.

### Recommended Design

```text
Employee device
→ Strong wireless authentication
→ WPA3 or strongest supported encryption
→ Secure branch network
→ Cloud applications
```

### Additional Controls

- Zero-trust access
- MFA
- Identity-based policies
- Device posture checks
- Network segmentation
- Logging
- Monitoring

---

## What I Observed

Wireless security requires more than a password.

A complete wireless-security design includes:

```text
Authentication
Encryption
Message integrity
Modern protocols
Client compatibility
Access-point compatibility
Segmentation
Monitoring
```

The protocol evolution is:

```text
WEP
→ WPA
→ WPA2
→ WPA3
```

The preferred approach is:

```text
Use WPA3 when supported.
Use WPA2 when WPA3 is unavailable.
Avoid WPA and WEP.
```

---

## Important Limitation

Wireless encryption does not replace:

- Strong authentication
- MFA
- Network segmentation
- Guest isolation
- Firewall rules
- Monitoring
- Logging
- Device management
- Patch management
- Zero-trust policies

---

## Cloud Engineering Connection

Cloud engineers apply wireless-security concepts when supporting:

- Branch offices
- Cloud-managed Wi-Fi
- Remote workers
- Zero-trust access
- SASE
- Identity providers
- IoT networks
- Guest access
- Compliance
- Incident response
- Security monitoring

---

## Skills Practiced

- Explaining wireless-security goals
- Comparing WEP, WPA, WPA2, and WPA3
- Identifying obsolete protocols
- Explaining AES
- Explaining CCMP
- Explaining GCMP
- Explaining GMAC
- Selecting stronger wireless-security options
- Connecting wireless encryption to cloud engineering
