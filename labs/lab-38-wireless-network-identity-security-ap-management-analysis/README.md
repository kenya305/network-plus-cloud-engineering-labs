# Lab 38: Wireless Network Identity, Security, and AP Management Analysis

## Objective

Analyze SSIDs, BSSIDs, ESSIDs, captive portals, wireless-security modes, antenna types, and centralized wireless management.

## Scenario

A company is designing Wi-Fi for:

- Employee laptops
- Guest users
- IoT devices
- Large office spaces
- Branch offices
- Centralized monitoring

The network team needs to select appropriate wireless identifiers, security models, antennas, and management approaches.

---

## Part 1: Wireless Identity Terms

| Term | Full Name | Purpose |
| ---- | --------- | ------- |
| IBSS | Independent Basic Service Set | Direct device-to-device wireless connection |
| SSID | Service Set Identifier | Visible wireless network name |
| BSSID | Basic Service Set Identifier | Hardware identifier for one AP |
| ESSID | Extended Service Set Identifier | Shared SSID across multiple APs |

---

## Part 2: IBSS Scenario

### Use Case

A smart lock needs initial setup before joining the normal Wi-Fi network.

### Workflow

```text
Phone
→ Connects directly to smart lock using ad hoc wireless
→ Sends Wi-Fi configuration
→ Smart lock joins normal access point
```

### Recommended Wireless Mode

```text
IBSS
```

---

## Part 3: SSID, BSSID, and ESSID Scenario

### Office Wireless Design

```text
Access Point 1
→ SSID: CorporateWiFi
→ BSSID: Unique AP hardware address

Access Point 2
→ SSID: CorporateWiFi
→ BSSID: Different AP hardware address
```

### Result

```text
Same SSID across multiple APs
→ ESSID
→ Seamless roaming
```

---

## Part 4: Captive Portal Scenario

### Guest Wi-Fi Requirement

Visitors need temporary internet access.

### Workflow

```text
Guest joins Wi-Fi
→ Captive portal appears
→ Guest accepts terms or authenticates
→ Access table updated
→ Temporary internet access granted
```

### Recommended Design

```text
Guest SSID
+
Captive portal
+
Time-limited access
```

---

## Part 5: Security Comparison

| Security Type | Best-Fit Use | Key Characteristic |
| ------------- | ------------ | ------------------ |
| Open system | Public access with low security | No authentication or encryption |
| OWE | Public access with encryption | Encrypted open wireless |
| WPA2/WPA3 Personal | Home or small office | Shared PSK |
| WPA2/WPA3 Enterprise | Business or enterprise | Individual 802.1X authentication |

---

## Part 6: Personal vs. Enterprise Authentication

### Small Office

```text
Users share one Wi-Fi password
→ WPA2/WPA3 Personal
→ PSK
```

### Enterprise

```text
Each employee signs in with unique credentials
→ WPA2/WPA3 Enterprise
→ 802.1X
```

### Benefit of Enterprise Security

```text
Employee leaves organization
→ Disable user account
→ Wireless access removed
```

---

## Part 7: Antenna Selection

| Scenario | Recommended Antenna |
| -------- | ------------------- |
| Access point in center of room | Omnidirectional |
| Coverage needed in one direction | Directional |
| Long-distance focused link | Yagi |
| Building-to-building high-gain link | Parabolic |

---

## Part 8: Antenna Gain

Antenna gain is commonly measured in:

```text
dB
```

A useful rule:

```text
Every 3 dB increase
→ Approximately doubles power
```

---

## Part 9: Autonomous vs. Lightweight APs

| Feature | Autonomous AP | Lightweight AP |
| ------- | ------------- | -------------- |
| Operates independently | Yes | No |
| Central controller required | No | Yes |
| Best fit | Home or small office | Enterprise |
| Centralized monitoring | Limited | Strong |
| Centralized configuration | Limited | Strong |
| CAPWAP support | Not typically required | Common |

---

## Part 10: CAPWAP and WLC

### CAPWAP

```text
Control and Provisioning of Wireless Access Points
```

### WLC

```text
Wireless LAN Controller
```

### Management Flow

```text
Administrator
→ Wireless LAN Controller
→ CAPWAP
→ Lightweight APs
```

### Benefits

- Central configuration
- Central monitoring
- Easier updates
- Reporting
- Enterprise scalability
- Single pane of glass

---

## Part 11: Design Recommendation

### Corporate Employees

```text
SSID: CorporateWiFi
Security: WPA2/WPA3 Enterprise
Authentication: 802.1X
Management: WLC with CAPWAP
```

### Guests

```text
SSID: GuestWiFi
Security: OWE or protected guest design
Access: Captive portal
Duration: Time-limited
```

### IoT Devices

```text
Initial setup: IBSS or ad hoc
Steady-state access: Dedicated IoT SSID
Segmentation: Separate VLAN or policy
```

---

## What I Observed

Wireless design includes more than choosing an access point.

A complete design considers:

```text
SSID
BSSID
ESSID
Roaming
Captive portals
Security mode
Authentication model
Antenna type
AP management model
CAPWAP
WLC
```

Large environments benefit from lightweight APs and centralized management.

Enterprise environments benefit from individual 802.1X authentication rather than shared passwords.

---

## Important Limitation

Wireless design depends on:

- Building layout
- Coverage requirements
- Security requirements
- User density
- Device compatibility
- IoT requirements
- Authentication systems
- Guest-access needs
- Regulatory requirements
- Monitoring
- Segmentation
- Budget

---

## Cloud Engineering Connection

Cloud engineers use these concepts when supporting:

- Branch offices
- Cloud-managed Wi-Fi
- Remote access
- IoT onboarding
- Zero-trust access
- Guest networking
- Centralized monitoring
- Identity integration
- SASE
- Hybrid cloud connectivity

---

## Skills Practiced

- Distinguishing SSID, BSSID, and ESSID
- Explaining IBSS
- Designing guest captive-portal access
- Comparing personal and enterprise wireless security
- Explaining PSK and 802.1X
- Selecting antenna types
- Comparing autonomous and lightweight APs
- Explaining CAPWAP
- Explaining WLC management
- Connecting wireless design to cloud engineering
