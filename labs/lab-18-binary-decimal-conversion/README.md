# Lab 18: Binary and Decimal Conversion

## Objective

Practice converting values between binary and decimal to build a foundation for IP addressing and subnetting.

## Scenario

A cloud engineer or network administrator needs to understand binary math when planning IP-address ranges, configuring subnets, and troubleshooting network communication.

This lab performs manual binary-to-decimal and decimal-to-binary conversions and verifies the answers using a Terminal command.

---

## Binary Place-Value Chart

Use this 8-bit chart:

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |

### Memory Trick

```text
128  64  32  16  8  4  2  1
```

---

## Exercise 1: Convert Binary 00000010 to Decimal

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `0` | `0` | `0` | `0` | `0` | `0` | `1` | `0` |

### Calculation

```text
2 = 2
```

### Result

```text
00000010 in binary = 2 in decimal
```

---

## Exercise 2: Convert Binary 10000010 to Decimal

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `0` | `0` | `0` | `0` | `0` | `1` | `0` |

### Calculation

```text
128 + 2 = 130
```

### Result

```text
10000010 in binary = 130 in decimal
```

---

## Exercise 3: Convert Binary 11111111 to Decimal

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |

### Calculation

```text
128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
```

### Result

```text
11111111 in binary = 255 in decimal
```

---

## Exercise 4: Convert Decimal 154 to Binary

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `0` |

### Calculation

```text
128 + 16 + 8 + 2 = 154
```

### Result

```text
154 in decimal = 10011010 in binary
```

---

## Terminal Verification Command

Run the following command in Terminal:

```bash
python3 - <<'PY'
print("Binary 00000010 =", int("00000010", 2))
print("Binary 10000010 =", int("10000010", 2))
print("Binary 11111111 =", int("11111111", 2))
print("Decimal 154 =", format(154, "08b"))
PY
```

---

## Terminal Output

```text
kenya@Kenyas-MacBook-Pro-2 ~ % python3 - <<'PY'
print("Binary 00000010 =", int("00000010", 2))
print("Binary 10000010 =", int("10000010", 2))
print("Binary 11111111 =", int("11111111", 2))
print("Decimal 154 =", format(154, "08b"))
PY
Binary 00000010 = 2
Binary 10000010 = 130
Binary 11111111 = 255
Decimal 154 = 10011010
```

---

## Conversion Analysis

| Exercise | Conversion | Expected Result | Terminal Result | Status |
| -------- | ---------- | --------------- | --------------- | ------ |
| 1 | Binary `00000010` to decimal | `2` | `2` | Verified |
| 2 | Binary `10000010` to decimal | `130` | `130` | Verified |
| 3 | Binary `11111111` to decimal | `255` | `255` | Verified |
| 4 | Decimal `154` to binary | `10011010` | `10011010` | Verified |

---

## What I Observed

The Python verification confirmed that each manual binary and decimal conversion was correct.

The binary place-value chart is:

```text
128  64  32  16  8  4  2  1
```

Each position containing a binary `1` contributes its decimal value to the total.

Each position containing a binary `0` does not contribute to the total.

The verified conversions were:

```text
00000010 in binary = 2 in decimal
10000010 in binary = 130 in decimal
11111111 in binary = 255 in decimal
154 in decimal = 10011010 in binary
```

An 8-bit octet can represent decimal values from:

```text
0 through 255
```

---

## Important Limitation

The Terminal command verifies the calculations, but the CompTIA Network+ exam may require manual conversion.

The goal is to recognize binary place values quickly without relying entirely on a calculator or script.

---

## Cloud Engineering Connection

Cloud engineers use binary math when working with:

- IPv4 addresses
- Subnet masks
- CIDR notation
- Virtual networks
- Cloud subnets
- Route tables
- Network segmentation
- IP-address allocation
- Security groups
- Hybrid cloud connectivity

Understanding binary conversion helps engineers calculate subnet ranges and plan network architecture correctly.

---

## Skills Practiced

- Memorizing binary place values
- Converting binary to decimal
- Converting decimal to binary
- Identifying the range of an 8-bit octet
- Using Python to verify binary conversions
- Connecting binary math to subnetting
- Documenting a technical networking lab in GitHub
