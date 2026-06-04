# Network+ N10-009 Study Notes: Wireless Technologies

## Video Topic

Wireless Technologies

## Summary

Wireless networks use IEEE 802.11 standards to communicate over radio frequencies.

Modern wireless networks may use:

- `2.4 GHz`
- `5 GHz`
- `6 GHz`

These frequency ranges are divided into channels so administrators can manage wireless communication more easily.

This lesson also covers:

- IEEE 802.11 standards
- Wi-Fi generations
- Wireless channels
- Channel bandwidth
- Non-overlapping channels
- Band steering
- Regulatory requirements
- FCC
- ITU
- IEEE 802.11h
- DFS
- TPC

---

## IEEE 802.11

Wireless networking standards are created by the:

```text
IEEE 802.11 committee
```

IEEE stands for:

```text
Institute of Electrical and Electronics Engineers
```

### Key Takeaway

```text
IEEE 802.11 = Wireless networking standards
```

---

## Wi-Fi Generations

Modern Wi-Fi standards may be referenced by either the IEEE name or the consumer-friendly Wi-Fi generation.

| IEEE Standard | Wi-Fi Generation |
| ------------- | ---------------- |
| `802.11ac` | Wi-Fi 5 |
| `802.11ax` | Wi-Fi 6 |
| `802.11ax` extended into 6 GHz | Wi-Fi 6E |
| `802.11be` | Wi-Fi 7 |

### Key Takeaway

```text
Wi-Fi generation names simplify IEEE wireless-standard names.
```

---

## Wireless Frequency Ranges

Modern Wi-Fi commonly operates in:

```text
2.4 GHz
5 GHz
6 GHz
```

### Comparison

| Frequency Range | General Characteristics |
| --------------- | ----------------------- |
| `2.4 GHz` | Longer range, more congestion, fewer non-overlapping channels |
| `5 GHz` | More channels, less congestion, shorter range than 2.4 GHz |
| `6 GHz` | More available spectrum, modern-device support required |

### Key Takeaway

```text
Lower frequency often travels farther.
Higher frequency often provides more available spectrum.
```

---

## Wireless Channels

A wireless channel represents a range of frequencies.

Instead of referring to an exact center frequency, administrators use channel numbers.

### Examples

```text
2.4 GHz channel 6
→ Center frequency: 2.437 GHz

5 GHz channel 44
→ Center frequency: 5.220 GHz
```

### Key Takeaway

```text
Channel number = Easier way to reference wireless frequencies
```

---

## Channel Bandwidth

Channel bandwidth describes how much wireless spectrum is used by one channel.

Common channel widths include:

```text
20 MHz
40 MHz
80 MHz
160 MHz
```

### Key Takeaway

```text
Wider channels can support more throughput but use more spectrum.
```

---

## 2.4 GHz Channels

The `2.4 GHz` range has fewer non-overlapping channels.

A common design uses:

```text
Channel 1
Channel 6
Channel 11
```

These channels are separated to reduce interference.

### Key Takeaway

```text
2.4 GHz commonly uses three non-overlapping channels: 1, 6, and 11.
```

---

## 5 GHz and 6 GHz Channels

The `5 GHz` and `6 GHz` bands provide more available spectrum.

### Benefits

- More available channels
- Less overlap
- More design flexibility
- Higher throughput options
- Better support for dense environments

### Key Takeaway

```text
5 GHz and 6 GHz provide more channel options than 2.4 GHz.
```

---

## Band Steering

Band steering encourages devices to connect to the most appropriate wireless band.

### Example

A phone supports both:

```text
2.4 GHz
5 GHz
```

Without band steering:

```text
Device chooses strongest signal
```

With band steering:

```text
Access point may encourage 5 GHz
→ Better throughput
→ Reduced congestion
```

### Key Takeaway

```text
Band steering = Guide capable devices toward a preferred wireless band
```

---

## Strongest Signal vs. Best Performance

The strongest signal is not always the best-performing connection.

### Example

```text
2.4 GHz
→ Stronger signal
→ More congestion

5 GHz
→ Slightly weaker signal
→ Better throughput
```

### Key Takeaway

```text
Best signal strength does not always mean best performance.
```

---

## Regulatory Requirements

Wireless frequencies are regulated.

Different countries determine how wireless spectrum may be used.

### United States

The regulatory authority in the United States is:

```text
FCC
```

FCC stands for:

```text
Federal Communications Commission
```

### Worldwide Coordination

The international organization that publishes global telecommunications guidelines is:

```text
ITU
```

ITU stands for:

```text
International Telecommunication Union
```

---

## IEEE 802.11h

IEEE `802.11h` adds interoperability features that help wireless networks coexist with other services.

### Key Features

```text
DFS
TPC
```

---

## DFS

DFS stands for:

```text
Dynamic Frequency Selection
```

DFS allows an access point to select channels that avoid interference with other services.

### Example

```text
Access point starts
→ Checks wireless environment
→ Selects appropriate channel
→ Avoids conflicting frequencies
```

If conditions change:

```text
Access point changes channel
→ Connected devices move with access point
```

### Key Takeaway

```text
DFS = Automatically avoid conflicting frequencies
```

---

## TPC

TPC stands for:

```text
Transmit Power Control
```

TPC allows the access point to manage transmit power.

### Example

```text
Access point detects strong signal
→ Instructs client to reduce transmit power
→ Reduces unnecessary interference
```

### Key Takeaway

```text
TPC = Access point manages wireless transmit power
```

---

## Wireless Design Considerations

When selecting bands and channels, consider:

- Interference
- Number of nearby access points
- Device compatibility
- Channel width
- Throughput requirements
- Coverage area
- Regulatory requirements
- Access-point placement
- Client density
- DFS behavior
- TPC behavior

---

## Cloud Engineering Connection

Cloud engineers encounter wireless technologies when supporting:

- Branch offices
- Remote work
- Hybrid networks
- Wireless access points
- Corporate device connectivity
- IoT networks
- Zero-trust access
- SASE
- Cloud-managed Wi-Fi
- Network monitoring
- Troubleshooting user connectivity

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| Wireless networking standards | IEEE 802.11 |
| `802.11ac` | Wi-Fi 5 |
| `802.11ax` | Wi-Fi 6 |
| `802.11be` | Wi-Fi 7 |
| Longer range but more congestion | `2.4 GHz` |
| More available channels | `5 GHz` or `6 GHz` |
| Guide users toward preferred band | Band steering |
| U.S. wireless regulator | FCC |
| Global telecommunications guidelines | ITU |
| Automatically avoid conflicting frequencies | DFS |
| Access point manages transmit power | TPC |
| `802.11h` | DFS and TPC |

---

## Memory Trick

```text
2.4 GHz = Longer range
5 GHz   = More channels
6 GHz   = More spectrum

Band steering = Choose better band
DFS           = Choose better channel
TPC           = Choose better power level
```

---

## Practice Questions

### 1. What IEEE committee creates wireless networking standards?

Answer:

```text
IEEE 802.11
```

### 2. Which IEEE standard is also called Wi-Fi 5?

Answer:

```text
802.11ac
```

### 3. Which IEEE standard is also called Wi-Fi 6?

Answer:

```text
802.11ax
```

### 4. Which IEEE standard is also called Wi-Fi 7?

Answer:

```text
802.11be
```

### 5. Which three frequency ranges are commonly used by modern Wi-Fi?

Answer:

```text
2.4 GHz
5 GHz
6 GHz
```

### 6. What are common non-overlapping 2.4 GHz channels?

Answer:

```text
1, 6, and 11
```

### 7. What is band steering?

Answer: A feature that guides capable devices toward a preferred wireless band.

### 8. What does DFS stand for?

Answer:

```text
Dynamic Frequency Selection
```

### 9. What does TPC stand for?

Answer:

```text
Transmit Power Control
```

### 10. Which organization regulates wireless spectrum in the United States?

Answer:

```text
FCC
```
