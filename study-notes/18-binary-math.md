# Network+ N10-009 Study Notes: Binary Math

## Video Topic

Binary Math

## Summary

Binary math is important for IP addressing and subnetting.

Computers use binary values to represent data.

Binary uses only two digits:

```text
0
1
```

Each binary digit is called a:

```text
Bit
```

Eight bits together form a:

```text
Byte
```

An 8-bit byte may also be called an:

```text
Octet
```

This lesson covers:

- Binary numbering
- Bits
- Bytes
- Octets
- Powers of two
- Binary-to-decimal conversion
- Decimal-to-binary conversion
- 8-bit value ranges
- Possible outcomes based on bit count

---

## Binary Overview

Binary is a number system that uses only:

```text
0
1
```

A binary value is made up of bits.

### Example

```text
00000010
```

This value contains:

```text
8 bits
```

### Key Takeaway

```text
Binary uses two values: 0 and 1.
```

---

## Bit

A bit is one binary digit.

A bit can have one of two possible values:

```text
0
1
```

### Key Takeaway

```text
Bit = One binary digit
```

---

## Byte and Octet

A byte contains:

```text
8 bits
```

An octet also refers to:

```text
8 bits
```

The term octet is useful because it clearly identifies an 8-bit value.

### Example

```text
11001010
```

This binary value contains:

```text
8 bits
```

Therefore, it is one byte or one octet.

### Key Takeaway

```text
8 bits = 1 byte = 1 octet
```

---

## Binary Place-Value Chart

Binary values are based on powers of two.

For an 8-bit binary value, use the following conversion chart:

| Bit Position | Decimal Value | Power of Two |
| ------------ | ------------- | ------------ |
| 8 | `128` | `2^7` |
| 7 | `64` | `2^6` |
| 6 | `32` | `2^5` |
| 5 | `16` | `2^4` |
| 4 | `8` | `2^3` |
| 3 | `4` | `2^2` |
| 2 | `2` | `2^1` |
| 1 | `1` | `2^0` |

### Conversion Chart

```text
128  64  32  16  8  4  2  1
```

### How to Build the Chart

Start on the right with:

```text
1
```

Then double each number as you move left:

```text
1
2
4
8
16
32
64
128
```

### Key Takeaway

```text
Binary place values increase by powers of two.
```

---

## Binary-to-Decimal Conversion Process

To convert binary to decimal:

1. Write the 8-bit binary value.
2. Place the binary conversion chart above it.
3. Identify each position containing a `1`.
4. Add the decimal values above those positions.
5. Ignore positions containing a `0`.

---

## Example 1: Convert Binary 00000010 to Decimal

### Binary Value

```text
00000010
```

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `0` | `0` | `0` | `0` | `0` | `0` | `1` | `0` |

The only position containing `1` is:

```text
2
```

### Calculation

```text
2 = 2
```

### Answer

```text
00000010 in binary = 2 in decimal
```

---

## Example 2: Convert Binary 10000010 to Decimal

### Binary Value

```text
10000010
```

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `0` | `0` | `0` | `0` | `0` | `1` | `0` |

The positions containing `1` are:

```text
128
2
```

### Calculation

```text
128 + 2 = 130
```

### Answer

```text
10000010 in binary = 130 in decimal
```

---

## Example 3: Convert Binary 11111111 to Decimal

### Binary Value

```text
11111111
```

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |

Every position contains `1`.

### Calculation

```text
128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
```

### Answer

```text
11111111 in binary = 255 in decimal
```

---

## Decimal-to-Binary Conversion Process

To convert decimal to binary:

1. Write the 8-bit conversion chart.
2. Start with the largest decimal place value.
3. Determine whether the place value is less than or equal to the remaining decimal value.
4. If yes, write `1` in that position and subtract the value.
5. If no, write `0` in that position.
6. Continue until all eight positions are completed.

---

## Example 4: Convert Decimal 154 to Binary

### Decimal Value

```text
154
```

### Place-Value Table

| Decimal Place Value | `128` | `64` | `32` | `16` | `8` | `4` | `2` | `1` |
| ------------------- | ----- | ---- | ---- | ---- | --- | --- | --- | --- |
| Binary Value | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `0` |

### Calculation

```text
128 + 16 + 8 + 2 = 154
```

### Answer

```text
154 in decimal = 10011010 in binary
```

---

## Decimal-to-Binary Walkthrough for 154

### Step 1

Ask:

```text
Is 128 less than or equal to 154?
```

Answer:

```text
Yes
```

Write:

```text
1
```

Remaining value:

```text
154 - 128 = 26
```

### Step 2

Ask:

```text
Is 64 less than or equal to 26?
```

Answer:

```text
No
```

Write:

```text
0
```

### Step 3

Ask:

```text
Is 32 less than or equal to 26?
```

Answer:

```text
No
```

Write:

```text
0
```

### Step 4

Ask:

```text
Is 16 less than or equal to 26?
```

Answer:

```text
Yes
```

Write:

```text
1
```

Remaining value:

```text
26 - 16 = 10
```

### Step 5

Ask:

```text
Is 8 less than or equal to 10?
```

Answer:

```text
Yes
```

Write:

```text
1
```

Remaining value:

```text
10 - 8 = 2
```

### Step 6

Ask:

```text
Is 4 less than or equal to 2?
```

Answer:

```text
No
```

Write:

```text
0
```

### Step 7

Ask:

```text
Is 2 less than or equal to 2?
```

Answer:

```text
Yes
```

Write:

```text
1
```

Remaining value:

```text
2 - 2 = 0
```

### Step 8

Ask:

```text
Is 1 less than or equal to 0?
```

Answer:

```text
No
```

Write:

```text
0
```

### Final Result

```text
10011010
```

---

## 8-Bit Value Range

An 8-bit octet can represent decimal values from:

```text
0 through 255
```

### Minimum Value

```text
00000000 = 0
```

### Maximum Value

```text
11111111 = 255
```

### Why This Matters

IPv4 addresses are commonly written as four decimal octets.

### Example IPv4 Address

```text
192.168.1.10
```

Each decimal section represents one 8-bit octet.

### Key Takeaway

```text
Each IPv4 octet can range from 0 through 255.
```

---

## Possible Outcomes Based on Number of Bits

The number of possible combinations increases as the number of bits increases.

Use the formula:

```text
2^n
```

Where:

```text
n = Number of bits
```

### Possible Outcomes Table

| Number of Bits | Calculation | Number of Possible Outcomes |
| -------------- | ----------- | --------------------------- |
| `1` | `2^1` | `2` |
| `2` | `2^2` | `4` |
| `3` | `2^3` | `8` |
| `4` | `2^4` | `16` |
| `5` | `2^5` | `32` |
| `6` | `2^6` | `64` |
| `7` | `2^7` | `128` |
| `8` | `2^8` | `256` |

### Important Clarification

Eight bits provide:

```text
256 possible outcomes
```

The decimal values range from:

```text
0 through 255
```

---

## Powers of Two Reference Table

| Power of Two | Decimal Value |
| ------------ | ------------- |
| `2^0` | `1` |
| `2^1` | `2` |
| `2^2` | `4` |
| `2^3` | `8` |
| `2^4` | `16` |
| `2^5` | `32` |
| `2^6` | `64` |
| `2^7` | `128` |
| `2^8` | `256` |

### Memory Trick

```text
128  64  32  16  8  4  2  1
```

Write this chart before solving subnetting questions.

---

## Cloud Engineering Connection

Cloud engineers use binary math when working with:

- IPv4 addresses
- Subnet masks
- CIDR notation
- Virtual networks
- Cloud subnets
- Route tables
- Security groups
- Network segmentation
- IP address planning
- Hybrid cloud connectivity
- Troubleshooting network communication

### Example

```text
Cloud subnet planning
→ Convert subnet mask values
→ Identify available IP-address ranges
→ Allocate addresses correctly
```

---

## Exam Clue Table

| If the exam mentions... | Think... |
| ----------------------- | -------- |
| One binary digit | Bit |
| Eight binary digits | Byte or octet |
| Binary values | `0` and `1` |
| 8-bit decimal range | `0` through `255` |
| Maximum value of one octet | `255` |
| Number of possible 8-bit combinations | `256` |
| Binary place values | Powers of two |
| Conversion chart | `128 64 32 16 8 4 2 1` |
| Subnetting preparation | Binary-to-decimal and decimal-to-binary conversion |

---

## Memory Trick

```text
Binary values = 0 and 1
8 bits        = 1 byte or octet
Octet range   = 0 through 255
Combinations  = 2^n
Place values  = 128 64 32 16 8 4 2 1
```

---

## Practice Questions

### 1. Which digits are used in binary?

Answer: `0` and `1`

### 2. What is one binary digit called?

Answer: A bit

### 3. How many bits are in one byte?

Answer: `8`

### 4. What is another name for an 8-bit byte?

Answer: An octet

### 5. What is the decimal value of binary `00000010`?

Answer: `2`

### 6. What is the decimal value of binary `10000010`?

Answer: `130`

### 7. What is the decimal value of binary `11111111`?

Answer: `255`

### 8. What is the binary value of decimal `154`?

Answer: `10011010`

### 9. What is the decimal range of one 8-bit octet?

Answer: `0` through `255`

### 10. How many possible combinations exist with 8 bits?

Answer: `256`

### 11. Which conversion chart should be memorized for subnetting?

Answer: `128 64 32 16 8 4 2 1`

### 12. Which formula determines the number of possible outcomes for a set of bits?

Answer: `2^n`, where `n` is the number of bits
