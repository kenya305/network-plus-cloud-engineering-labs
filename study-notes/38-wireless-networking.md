# Network+ N10-009 Study Notes: Wireless Networking

## Video Topic

Wireless Networking

## Summary

Wireless networking includes more than connecting to an access point.

A complete wireless design may include:

- Ad hoc connections
- SSIDs
- BSSIDs
- ESSIDs
- Seamless roaming
- Captive portals
- Wireless security modes
- Pre-shared keys
- Enterprise authentication
- Antenna types
- Autonomous access points
- Lightweight access points
- CAPWAP
- Wireless LAN controllers

This lesson explains how wireless devices identify networks, authenticate users, extend coverage, and centralize management.

---

## IBSS

IBSS stands for:

```text
Independent Basic Service Set
```

IBSS is also called:

```text
Ad hoc wireless networking
```

It allows wireless devices to connect directly to each other without using an access point.

### Example

```text
Phone
→ Direct wireless connection
→ Smart lock
```

### Common Use Case

An IoT device may temporarily create an ad hoc network so a user can configure:

- Wi-Fi network name
- Password
- Initial setup details

After setup, the device connects to the normal access point.

### Key Takeaway

```text
IBSS = Direct device-to-device wireless connection without an access point
```

---

## SSID

SSID stands for:

```text
Service Set Identifier
```

The SSID is the visible wireless network name.

### Example

```text
SGC1
```

When a user opens the Wi-Fi list on a phone or laptop, the displayed network name is the SSID.

### Key Takeaway

```text
SSID = Wireless network name
```

---

## BSSID

BSSID stands for:

```text
Basic Service Set Identifier
```

The BSSID is the hardware address associated with a specific wireless access point radio.

### Example

```text
60:3D:26:11:22:33
```

### Why BSSID Matters

Multiple access points may use the same SSID.

The BSSID helps distinguish one physical access point from another.

### Key Takeaway

```text
BSSID = Hardware identifier for a specific access point
```

---

## ESSID

ESSID stands for:

```text
Extended Service Set Identifier
```

An ESSID represents a shared wireless network name used across multiple access points.

### Example

```text
Access Point 1
→ SSID: SGC1
→ BSSID: Unique hardware address

Access Point 2
→ SSID: SGC1
→ BSSID: Different hardware address
```

Because both access points use the same SSID, users can roam seamlessly.

### Key Takeaway

```text
ESSID = Shared SSID across multiple access points
```

---

## Seamless Roaming

Seamless roaming allows a device to move between access points without interrupting connectivity.

### Example

```text
User walks across building
→ Device leaves Access Point 1 range
→ Device enters Access Point 2 range
→ Same SSID remains available
→ Device reconnects automatically
```

### Key Takeaway

```text
Same ESSID across APs
→ Seamless user roaming
```

---

## SSID vs. BSSID vs. ESSID

| Term | Meaning | Example |
| ---- | ------- | ------- |
| SSID | Visible wireless network name | `SGC1` |
| BSSID | Hardware identifier for one access point | MAC-like address |
| ESSID | Shared SSID across multiple access points | Same network name across building |

---

## Captive Portal

A captive portal is a web-based login or acceptance screen shown before network access is granted.

### Common Captive Portal Requirements

- Accept terms and conditions
- Enter username
- Enter password
- Provide email address
- Enter room number
- Use another authentication factor

### Example

```text
User connects to hotel Wi-Fi
→ Browser opens captive portal
→ User accepts terms
→ Access table updated
→ Internet access granted
```

### Time-Limited Access

A captive portal may authorize a user for a limited period.

```text
Access allowed for 24 hours
→ Reauthentication required later
```

### Key Takeaway

```text
Captive portal = Web-based authentication or access-acceptance page
```

---

## Wireless Security Modes

Wireless networks may use several security methods.

| Security Mode | Meaning |
| ------------- | ------- |
| Open system | No authentication or encryption |
| WEP | Older insecure wireless encryption |
| WPA | Older wireless-security standard |
| WPA2 Personal | Shared password using PSK |
| WPA3 Personal | Newer shared-password wireless security |
| WPA2/WPA3 Enterprise | Individual authentication, often using 802.1X |
| OWE | Opportunistic Wireless Encryption |

---

## Open System

An open system provides:

```text
No authentication
No encryption
```

### Risk

Anyone can join and communicate on the wireless network unless other protections are applied.

### Key Takeaway

```text
Open system = No wireless security
```

---

## OWE

OWE stands for:

```text
Opportunistic Wireless Encryption
```

OWE allows users to connect without a shared password while still encrypting wireless communication.

It may also isolate wireless clients from each other depending on implementation.

### Key Takeaway

```text
OWE = Encrypted open wireless access
```

---

## Personal Wireless Security

Personal security commonly uses:

```text
PSK
```

PSK stands for:

```text
Pre-Shared Key
```

All users share the same wireless password.

### Example

```text
Coffee shop Wi-Fi password:
hotcoffee
```

### Limitation

If one person leaves, the shared password may still be known unless the key is changed.

### Key Takeaway

```text
Personal security = Shared wireless password
```

---

## Enterprise Wireless Security

Enterprise wireless security commonly uses:

```text
802.1X
```

Each user authenticates with individual credentials.

### Example

```text
Employee username
+
Employee password
+
Possible MFA or certificate
→ Wireless access
```

### Benefits

- Individual user accountability
- Easier offboarding
- Centralized control
- Better enterprise security
- No shared Wi-Fi password required

### Key Takeaway

```text
Enterprise wireless security = Individual authentication
```

---

## Personal vs. Enterprise Security

| Feature | Personal | Enterprise |
| ------- | -------- | ---------- |
| Authentication model | Shared password | Individual credentials |
| Common term | PSK | 802.1X |
| Best fit | Home or small office | Business or enterprise |
| User offboarding | Shared key may need to change | Disable user account |
| Security control | Basic | More centralized and granular |

---

## Omnidirectional Antenna

An omnidirectional antenna sends wireless signals in many directions around the antenna.

### Best Fit

- Home access points
- Central room placement
- General indoor coverage

### Limitation

If placed in a corner, much of the signal may be wasted.

### Key Takeaway

```text
Omnidirectional = Signal spreads in many directions
```

---

## Directional Antenna

A directional antenna focuses wireless energy in one direction.

### Best Fit

- Long-distance links
- Building-to-building connections
- Hallways
- Corners of buildings
- Targeted coverage

### Key Takeaway

```text
Directional = Signal focused toward one area
```

---

## Antenna Gain

Antenna gain is measured in:

```text
dB
```

A common rule:

```text
Every 3 dB increase
→ Approximately doubles power
```

### Key Takeaway

```text
+3 dB ≈ Double the power
```

---

## Yagi Antenna

A Yagi antenna is a highly directional antenna.

### Common Use

- Focused long-range communication
- Point-to-point wireless links
- Building-to-building connectivity

### Key Takeaway

```text
Yagi = Directional antenna with focused gain
```

---

## Parabolic Antenna

A parabolic antenna focuses signals toward a central feed point.

### Common Use

- Long-distance wireless connections
- High-gain directional links
- Focused point-to-point communication

### Key Takeaway

```text
Parabolic = High-gain directional antenna
```

---

## Autonomous Access Point

An autonomous access point operates independently.

It does not require a centralized controller.

### Best Fit

- Home networks
- Small offices
- Simple deployments

### Key Takeaway

```text
Autonomous AP = Standalone access point
```

---

## Lightweight Access Point

A lightweight access point relies on centralized management.

The intelligence and configuration are commonly managed through a wireless LAN controller.

### Benefits

- Lower-cost deployment
- Centralized configuration
- Easier monitoring
- Easier updates
- Enterprise scalability

### Key Takeaway

```text
Lightweight AP = Centrally managed access point
```

---

## CAPWAP

CAPWAP stands for:

```text
Control and Provisioning of Wireless Access Points
```

CAPWAP allows wireless access points to be centrally managed.

### Functions

- Configure APs
- Monitor APs
- Deploy changes
- Manage performance
- Centralize reporting

### Key Takeaway

```text
CAPWAP = Centralized wireless AP management protocol
```

---

## Wireless LAN Controller

A Wireless LAN Controller is commonly abbreviated as:

```text
WLC
```

A WLC provides centralized management for wireless access points.

### Common WLC Functions

- Deploy new APs
- Configure SSIDs
- Push settings
- Monitor usage
- View performance
- Generate reports
- Manage lightweight APs

### Key Takeaway

```text
WLC = Central management platform for wireless access points
```

---

## Single Pane of Glass

A centralized management dashboard is often described as:

```text
Single pane of glass
```

This means administrators can view and manage the wireless environment from one interface.

---

## Autonomous AP vs. Lightweight AP

| Feature | Autonomous AP | Lightweight AP |
| ------- | ------------- | -------------- |
| Management | Local to AP | Centralized |
| Controller required | No | Yes |
| Best fit | Home or small office | Enterprise |
| Scaling | Limited | Strong |
| Central reporting | Limited | Common |
| CAPWAP use | Not typically required | Common |

---

## Cloud Engineering Connection

Cloud engineers encounter these concepts when supporting:

- Branch-office networking
- Cloud-managed Wi-Fi
- Remote access
- IoT devices
- Zero-trust onboarding
- Enterprise identity systems
- Wireless LAN controllers
- Centralized monitoring
- CAPWAP deployments
- Hybrid cloud environments
- SASE architectures

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Direct device-to-device wireless connection | IBSS or ad hoc |
| Visible Wi-Fi network name | SSID |
| Hardware identifier for one access point | BSSID |
| Shared SSID across multiple APs | ESSID |
| Login or terms page before internet access | Captive portal |
| Shared Wi-Fi password | PSK |
| Individual enterprise credentials | 802.1X |
| Encrypted open Wi-Fi | OWE |
| Signal spreads around antenna | Omnidirectional |
| Focused long-distance antenna | Directional |
| Highly directional antenna | Yagi or parabolic |
| Standalone access point | Autonomous AP |
| Centrally managed AP | Lightweight AP |
| Wireless-controller protocol | CAPWAP |
| Central AP management platform | WLC |

---

## Memory Trick

```text
SSID  = Network name
BSSID = Access-point hardware ID
ESSID = Shared SSID across APs

IBSS  = Ad hoc device-to-device

PSK   = Shared password
802.1X = Individual enterprise login

CAPWAP = Manage APs centrally
WLC    = Wireless LAN controller
```

---

## Practice Questions

### 1. What does SSID stand for?

Answer:

```text
Service Set Identifier
```

### 2. What does BSSID stand for?

Answer:

```text
Basic Service Set Identifier
```

### 3. What does ESSID stand for?

Answer:

```text
Extended Service Set Identifier
```

### 4. What is IBSS?

Answer: A direct device-to-device ad hoc wireless connection without an access point.

### 5. What is a captive portal?

Answer: A web-based page requiring terms acceptance or authentication before network access.

### 6. What does PSK stand for?

Answer:

```text
Pre-Shared Key
```

### 7. What is the main difference between personal and enterprise wireless security?

Answer: Personal security uses a shared password, while enterprise security uses individual authentication.

### 8. What is an omnidirectional antenna?

Answer: An antenna that distributes signal in many directions around the antenna.

### 9. What is a directional antenna?

Answer: An antenna that focuses wireless energy toward one direction.

### 10. What does CAPWAP stand for?

Answer:

```text
Control and Provisioning of Wireless Access Points
```

### 11. What is a WLC?

Answer:

```text
Wireless LAN Controller
```

A centralized management platform for wireless access points.
