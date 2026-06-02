# Lab 09: Wireless Network Interface Audit

## Objective

Use Terminal commands on a Mac to identify the wireless network interface and review Wi-Fi connection details.

## Scenario

A cloud engineer or network administrator may need to inspect a device's wireless interface while troubleshooting connectivity, performance, or signal-quality issues.

This lab identifies the Wi-Fi network interface and collects wireless-network information from macOS.

---

## Commands Used

```bash
networksetup -listallhardwareports
system_profiler SPAirPortDataType
```

### Command Breakdown

| Command | Meaning |
| ------- | ------- |
| `networksetup -listallhardwareports` | Lists the hardware ports and device names configured on the Mac |
| `system_profiler SPAirPortDataType` | Displays Wi-Fi hardware and current wireless-network information |

---

## Steps Performed

1. Opened Terminal on macOS.
2. Ran the following command to identify the Wi-Fi hardware interface:

```bash
networksetup -listallhardwareports
```

3. Located the section labeled:

```text
Hardware Port: Wi-Fi
```

4. Documented the Wi-Fi device name, such as `en0` or `en1`.
5. Ran the following command to review wireless-network details:

```bash
system_profiler SPAirPortDataType
```

6. Reviewed the output for information such as:
   - Supported PHY modes
   - Supported channels
   - Current network
   - PHY mode
   - Channel
   - Signal information
   - Transmit rate

---

## Wi-Fi Interface Output

```text
Hardware Port: Wi-Fi
Device: en0
Ethernet Address: [REDACTED]
```

---

## Wireless Network Output

```text
Interfaces:
  en0:
    Card Type: Wi-Fi
    MAC Address: [REDACTED]
    Country Code: US
    Supported PHY Modes: 802.11 a/b/g/n/ac
    Status: Connected
    Current Network Information:
      SSID: [REDACTED]
      PHY Mode: 802.11n
      Channel: 1 (2GHz, 20MHz)
      Network Type: Infrastructure
      Security: WPA2/WPA3 Personal
      Signal / Noise: -41 dBm / -97 dBm
      Transmit Rate: 144
      MCS Index: 15
```

---

## Wireless Interface Analysis

| Detail | Result |
| ------ | ------ |
| Wi-Fi hardware interface | `en0` |
| Supported PHY modes | `802.11 a/b/g/n/ac` |
| Current PHY mode | `802.11n` |
| Current channel | `1` |
| Current frequency band | `2.4 GHz` |
| Channel width | `20 MHz` |
| Network type | Infrastructure |
| Wireless security | WPA2/WPA3 Personal |
| Transmit rate | `144 Mbps` |
| Signal level | `-41 dBm` |
| Noise level | `-97 dBm` |
| MCS index | `15` |

---

## Privacy Note

Sensitive wireless-network details were redacted before publishing this lab.

The following details were intentionally removed:

- Wi-Fi network name, also called SSID
- MAC addresses
- Nearby wireless-network names
- Nearby access-point details
- Device identifiers

This keeps the GitHub portfolio focused on technical skills without exposing private network information.

---

## What I Observed

The Mac used the Wi-Fi hardware interface:

```text
en0
```

The current wireless connection used:

```text
802.11n
```

The device was connected on:

```text
Channel 1
2.4 GHz frequency band
20 MHz channel width
```

The wireless security configuration was:

```text
WPA2/WPA3 Personal
```

The transmit rate was:

```text
144 Mbps
```

The signal and noise measurements were:

```text
Signal: -41 dBm
Noise:  -97 dBm
```

The signal level was stronger than the noise level, which indicates a usable wireless connection.

---

## Wireless Standard Connection

The current PHY mode was:

```text
802.11n
```

This standard is commonly associated with:

```text
Wi-Fi 4
```

The supported PHY modes on the device included:

```text
802.11a
802.11b
802.11g
802.11n
802.11ac
```

This means the wireless adapter supports multiple Wi-Fi generations and can connect to different compatible wireless networks.

---

## Cloud Engineering Connection

Cloud engineers and network administrators use wireless-interface details when troubleshooting:

- Remote-user connectivity
- Signal-strength issues
- Wireless interference
- Frequency-band selection
- Channel congestion
- Access-point connectivity
- IoT-device connectivity
- Branch-office wireless networks
- Hybrid work environments

Understanding the wireless standard, channel, frequency band, signal level, and transmit rate helps identify whether a connectivity issue is caused by the local wireless network rather than the cloud application itself.

---

## Skills Practiced

- Identifying a Wi-Fi hardware interface on macOS
- Reviewing wireless-network configuration
- Identifying supported PHY modes
- Identifying the current PHY mode
- Reviewing wireless channels
- Identifying the current frequency band
- Interpreting signal and noise values
- Reviewing wireless security settings
- Applying privacy controls before publishing technical output
- Documenting a wireless-network audit in GitHub
