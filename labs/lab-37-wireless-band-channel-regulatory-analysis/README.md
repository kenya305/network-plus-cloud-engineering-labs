# Lab 37: Wireless Band, Channel, and Regulatory Analysis

## Objective

Inspect a Mac wireless interface and analyze Wi-Fi frequency bands, channels, channel widths, band steering, DFS, TPC, and regulatory details.

## Scenario

A cloud engineer or network administrator may need to validate wireless connectivity during troubleshooting.

This lab uses macOS Terminal output to inspect the active Wi-Fi connection without changing any network settings.

---

## Command Used

```bash
system_profiler SPAirPortDataType
```

### Command Purpose

| Command | Meaning |
| ------- | ------- |
| `system_profiler SPAirPortDataType` | Displays detailed macOS Wi-Fi interface, channel, security, and nearby-network information |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran:

```bash
system_profiler SPAirPortDataType
```

3. Reviewed the active Wi-Fi interface.
4. Identified:
   - Interface
   - Regulatory locale
   - Country code
   - Supported PHY modes
   - Supported channels
   - Connection status
   - Current PHY mode
   - Channel
   - Frequency band
   - Channel width
   - Security type
   - Signal and noise values
   - Transmit rate
5. Reviewed nearby wireless-network patterns.
6. Redacted sensitive local-network details before publishing.

---

## Redacted Wi-Fi Inspection Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % system_profiler SPAirPortDataType
Wi-Fi:

  Interfaces:
    en0:
      Card Type: Wi-Fi
      Firmware Version: [REDACTED FIRMWARE DETAILS]
      MAC Address: [REDACTED MAC ADDRESS]
      Locale: FCC
      Country Code: US
      Supported PHY Modes: 802.11 a/b/g/n/ac
      Supported Channels:
        2.4 GHz: 1 through 13
        5 GHz: 36, 40, 44, 48, 52, 56, 60, 64,
               100, 104, 108, 112, 116, 120, 124,
               128, 132, 136, 140, 144, 149, 153,
               157, 161, 165
      Wake On Wireless: Supported
      AirDrop: Supported
      Auto Unlock: Supported
      Status: Connected

      Current Network Information:
        SSID: [REDACTED]
        PHY Mode: 802.11ac
        Channel: 157 (5 GHz, 80 MHz)
        Country Code: US
        Network Type: Infrastructure
        Security: WPA2/WPA3 Personal
        Signal / Noise: -50 dBm / -87 dBm
        Transmit Rate: 585 Mbps
        MCS Index: 6

      Other Local Wi-Fi Networks:
        SSIDs: [REDACTED]
        Nearby channels observed:
          2.4 GHz: 1, 6, 11
          5 GHz: 44, 48, 100, 112, 157
        Nearby channel widths observed:
          20 MHz
          40 MHz
          80 MHz

    awdl0:
      MAC Address: [REDACTED MAC ADDRESS]
      Current Network Information:
        Network Type: Infrastructure
```

---

## Current Connection Analysis

| Wireless Detail | Result |
| --------------- | ------ |
| Active interface | `en0` |
| Status | `Connected` |
| Regulatory locale | `FCC` |
| Country code | `US` |
| Current PHY mode | `802.11ac` |
| Wi-Fi generation | Wi-Fi 5 |
| Current channel | `157` |
| Current frequency band | `5 GHz` |
| Current channel width | `80 MHz` |
| Network type | `Infrastructure` |
| Security | `WPA2/WPA3 Personal` |
| Signal strength | `-50 dBm` |
| Noise level | `-87 dBm` |
| Approximate signal-to-noise ratio | `37 dB` |
| Transmit rate | `585 Mbps` |
| MCS index | `6` |

---

## Supported Wireless Modes

The active wireless interface reported support for:

```text
802.11a
802.11b
802.11g
802.11n
802.11ac
```

The active connection used:

```text
802.11ac
```

This corresponds to:

```text
Wi-Fi 5
```

---

## Supported Wireless Bands

The interface reported support for:

```text
2.4 GHz
5 GHz
```

The active connection used:

```text
5 GHz
```

The output did not show a `6 GHz` connection or supported `6 GHz` channels for this interface.

---

## Channel Analysis

The active connection used:

```text
Channel 157
```

with:

```text
5 GHz
80 MHz channel width
```

Nearby wireless networks were observed on:

```text
2.4 GHz:
1
6
11

5 GHz:
44
48
100
112
157
```

### Observation

The nearby `2.4 GHz` networks commonly used:

```text
1
6
11
```

These are the common non-overlapping channels used in the `2.4 GHz` range.

---

## Channel-Width Analysis

Nearby wireless networks used:

```text
20 MHz
40 MHz
80 MHz
```

The active connection used:

```text
80 MHz
```

### Tradeoff

```text
Wider channel
→ Greater throughput potential
→ More spectrum consumed
```

```text
Narrower channel
→ Less spectrum consumed
→ Better fit for dense environments
```

---

## Signal and Noise Analysis

The active connection reported:

```text
Signal: -50 dBm
Noise:  -87 dBm
```

The approximate signal-to-noise ratio was:

```text
-50 - (-87) = 37 dB
```

### Observation

The signal was meaningfully stronger than the measured noise floor.

This is consistent with an active wireless connection capable of a reported transmit rate of:

```text
585 Mbps
```

---

## Band-Steering Analysis

The active interface supports both:

```text
2.4 GHz
5 GHz
```

The current connection used:

```text
5 GHz
```

### Example

```text
Device supports 2.4 GHz and 5 GHz
→ Access point may steer device toward 5 GHz
→ Reduce 2.4 GHz congestion
→ Improve throughput when conditions support it
```

### Important Note

The Terminal output confirms the active band.

It does not prove whether band steering caused the band selection.

---

## DFS Analysis

DFS stands for:

```text
Dynamic Frequency Selection
```

The interface supports several `5 GHz` channels that may be subject to DFS rules depending on the environment and regulatory requirements.

### Purpose

```text
Access point scans environment
→ Avoids conflicting frequencies
→ Changes channel when required
→ Connected clients follow access point
```

---

## TPC Analysis

TPC stands for:

```text
Transmit Power Control
```

### Purpose

```text
Access point evaluates conditions
→ Adjusts transmit power
→ Reduces unnecessary interference
→ Supports wireless coexistence
```

The Terminal output does not directly confirm whether TPC was actively applied during this connection.

---

## Regulatory Analysis

| Organization or Setting | Purpose |
| ----------------------- | ------- |
| IEEE | Creates wireless networking standards |
| FCC | Regulates wireless spectrum in the United States |
| ITU | Publishes international telecommunications guidance |
| Locale: `FCC` | Interface is operating under U.S. regulatory rules |
| Country Code: `US` | Wireless settings align with the United States |

---

## What I Observed

The Mac was connected using:

```text
802.11ac
Channel 157
5 GHz
80 MHz
WPA2/WPA3 Personal
```

The interface supported both `2.4 GHz` and `5 GHz` wireless channels.

Nearby wireless networks used common `2.4 GHz` channels:

```text
1
6
11
```

Nearby `5 GHz` networks used multiple channels and widths.

The output demonstrated why wireless design requires attention to:

```text
Frequency band
Channel
Channel width
Signal strength
Noise level
Device compatibility
Regulatory rules
DFS
TPC
```

---

## Privacy Note

Sensitive local-network details were redacted before publishing this lab.

The following values were removed or generalized:

- SSID
- Nearby network names
- MAC addresses
- Hardware-specific identifiers
- Detailed firmware identifiers
- Device-specific identifiers

The redacted output still demonstrates the wireless-network concepts without exposing unnecessary local-network details.

---

## Important Limitation

Wireless performance depends on the physical environment.

A network engineer should still evaluate:

- Walls
- Floors
- Building materials
- Distance
- Interference
- Client density
- Access-point placement
- Legacy devices
- Regulatory requirements
- Channel width
- Security configuration
- Monitoring

---

## Cloud Engineering Connection

Cloud engineers use wireless concepts when supporting:

- Branch-office connectivity
- Remote workforces
- Cloud-managed Wi-Fi
- IoT devices
- SASE
- Zero-trust access
- Cloud applications
- Network monitoring
- User-experience troubleshooting

---

## Skills Practiced

- Inspecting Wi-Fi configuration on macOS
- Identifying active wireless interface
- Identifying PHY mode
- Identifying Wi-Fi generation
- Identifying channel and frequency band
- Identifying channel width
- Reviewing signal and noise values
- Comparing `2.4 GHz` and `5 GHz`
- Recognizing common non-overlapping channels
- Explaining band steering
- Explaining DFS
- Explaining TPC
- Identifying FCC regulatory context
- Redacting sensitive wireless details before publishing
