# Network+ N10-009 Study Notes: Intro to IP

## Video Topic

Introduction to Internet Protocol

## Summary

Internet Protocol, or IP, is used to move data from one device to another across a network.

A helpful analogy is a moving truck:

| Networking Concept     | Moving Truck Analogy                    |
| ---------------------- | --------------------------------------- |
| Network connection     | Road or highway                         |
| Internet Protocol (IP) | Moving truck                            |
| TCP or UDP             | Boxes inside the truck                  |
| Application data       | Items packed inside the boxes           |
| Destination IP address | Street address of the destination house |
| TCP or UDP port number | Room inside the house                   |

The IP address identifies the destination device.

The TCP or UDP port number identifies the application that should receive the data.

---

## Encapsulation

Encapsulation is the process of placing data inside multiple layers of protocols before sending it across the network.

Each layer adds information needed to deliver the data correctly.

### Simplified Encapsulation Flow

```text
Ethernet frame
└── IP packet
    └── TCP or UDP segment/datagram
        └── Application data
```

### Ethernet Frame Structure

| Frame Component  | Purpose                                                          |
| ---------------- | ---------------------------------------------------------------- |
| Ethernet header  | Contains Ethernet frame information                              |
| Ethernet payload | Carries IP packet information                                    |
| Ethernet trailer | Marks the end of the Ethernet frame and supports error detection |

### IP Packet Structure

| Packet Component | Purpose                                        |
| ---------------- | ---------------------------------------------- |
| IP header        | Contains IP addressing and routing information |
| IP payload       | Carries TCP or UDP data                        |

### TCP or UDP Structure

| Component          | Purpose                                                   |
| ------------------ | --------------------------------------------------------- |
| TCP or UDP header  | Contains transport-layer information such as port numbers |
| TCP or UDP payload | Carries application data                                  |

### Example

A web request may be packaged like this:

```text
Ethernet header
└── IP header
    └── TCP header
        └── HTTP website data
Ethernet trailer
```

---

## OSI Model Connection

TCP and UDP operate at:

```text
OSI Layer 4: Transport
```

IP operates at:

```text
OSI Layer 3: Network
```

Ethernet frames operate at:

```text
OSI Layer 2: Data Link
```

---

## Multiplexing

Multiplexing allows multiple applications to communicate across the network simultaneously between the same devices.

Port numbers help separate the traffic so that each application receives the correct data.

### Example

One server can support several applications at the same time:

| Application           | Protocol | Port |
| --------------------- | -------- | ---- |
| Web server            | TCP      | 80   |
| Voice-over-IP service | UDP      | 5004 |
| Email service         | TCP      | 143  |

The IP address identifies the server.

The TCP or UDP port identifies the application running on that server.

---

## TCP: Transmission Control Protocol

TCP stands for Transmission Control Protocol.

TCP is a connection-oriented protocol.

A formal communication session is established before data is transferred, and the session is formally closed when communication is complete.

### TCP Characteristics

| Characteristic      | Description                                                |
| ------------------- | ---------------------------------------------------------- |
| Connection-oriented | A session is established before communication              |
| Reliable delivery   | The receiving device sends acknowledgments                 |
| Error recovery      | Missing data can be retransmitted                          |
| Sequencing          | Packets are numbered so lost data can be identified        |
| Flow control        | Receiving device can request slower or faster transmission |

### TCP Example

```text
Sender transmits data
→ Receiver acknowledges successful delivery
→ Sender retransmits missing data when needed
```

### When TCP Is Useful

TCP is appropriate when complete and accurate delivery matters.

Examples include:

* Website traffic
* Email
* File transfers
* Application data requiring reliable delivery

---

## UDP: User Datagram Protocol

UDP stands for User Datagram Protocol.

UDP is a connectionless protocol.

There is no formal setup process before data is sent and no formal session teardown when communication ends.

### UDP Characteristics

| Characteristic     | Description                                           |
| ------------------ | ----------------------------------------------------- |
| Connectionless     | No session setup is required                          |
| No acknowledgments | Sender does not receive confirmation of delivery      |
| No retransmission  | Missing data is not automatically resent              |
| No flow control    | Receiver cannot request slower or faster transmission |
| Lower overhead     | Less communication is required between devices        |

### Important Clarification

UDP is called unreliable because delivery is not acknowledged or guaranteed.

This does not mean UDP packets are automatically more likely to fail.

It means the sender does not receive confirmation that delivery occurred.

### When UDP Is Useful

UDP is commonly useful when speed and low overhead matter more than guaranteed delivery.

Examples include:

* Streaming
* Voice-over-IP
* Real-time communication
* Some DNS traffic

---

## TCP vs. UDP Comparison

| Feature            | TCP                      | UDP                    |
| ------------------ | ------------------------ | ---------------------- |
| Communication Type | Connection-oriented      | Connectionless         |
| Acknowledgments    | Yes                      | No                     |
| Error Recovery     | Yes                      | No                     |
| Packet Sequencing  | Yes                      | No built-in sequencing |
| Flow Control       | Yes                      | No                     |
| Overhead           | Higher                   | Lower                  |
| Delivery Guarantee | Reliable delivery method | No delivery guarantee  |

---

## IP Addresses and Port Numbers

The destination IP address identifies the device that should receive the packet.

The TCP or UDP port number identifies the application that should receive the data after the packet arrives.

### Moving Truck Analogy

```text
IP address = destination house
Port number = room inside the house
```

### Common Examples

| Service | Common Port | Transport Protocol |
| ------- | ----------: | ------------------ |
| HTTP    |          80 | TCP                |
| HTTPS   |         443 | TCP                |
| NTP     |         123 | UDP                |
| IMAP    |         143 | TCP                |

---

## Sockets

A socket identifies one endpoint of a network conversation.

A socket is commonly represented by:

```text
IP address + transport protocol + port number
```

### Example Server Socket

```text
10.0.0.2 + TCP + port 80
```

### Example Client Socket

```text
10.0.0.1 + TCP + temporary client port 3000
```

Together, the client socket and server socket identify the network conversation.

---

## Client and Server Communication Example

A client at:

```text
10.0.0.1
```

communicates with a server at:

```text
10.0.0.2
```

### HTTP Example

| Endpoint | IP Address | Protocol | Port |
| -------- | ---------- | -------- | ---: |
| Client   | 10.0.0.1   | TCP      | 3000 |
| Server   | 10.0.0.2   | TCP      |   80 |

The client uses a temporary source port.

The server uses the standard destination port for HTTP.

When the server replies, the source and destination IP addresses and port numbers are reversed.

---

## Port Number Range

TCP and UDP ports can use values from:

```text
0 through 65,535
```

TCP port numbers and UDP port numbers are separate.

For example:

```text
TCP port 80 is different from UDP port 80.
```

### Official IANA Port Ranges

| Port Range  | Official IANA Category                     | Typical Purpose                      |
| ----------- | ------------------------------------------ | ------------------------------------ |
| 0–1023      | System Ports, also called Well-Known Ports | Common standard services             |
| 1024–49151  | User Ports, also called Registered Ports   | Registered applications and services |
| 49152–65535 | Dynamic and/or Private Ports               | Temporary or private use             |

### Exam Note

Professor Messer explains that client-side temporary ports are commonly selected from the broader range of 1024 through 65,535.

For current technical reference, the official IANA registry formally categorizes the Dynamic and/or Private Ports as:

```text
49152–65535
```

Operating systems may use temporary client-side ports from configurable ranges.

### Examples of Well-Known Ports

| Service | Protocol | Port |
| ------- | -------- | ---: |
| HTTP    | TCP      |   80 |
| HTTPS   | TCP      |  443 |
| IMAP    | TCP      |  143 |

---

## Port Numbers Are Not a Security Mechanism

Changing a port number does not automatically make an application secure.

Port numbers identify the application that should receive traffic.

A firewall is still needed to determine whether traffic should be allowed or blocked.

### Key Takeaway

```text
Port number = communication destination
Firewall rule = security control
```

---

## Exam Clue Table

| If the exam mentions...                                         | Think...                      |
| --------------------------------------------------------------- | ----------------------------- |
| Protocol responsible for moving packets across networks         | IP                            |
| Packaging application data inside larger protocol structures    | Encapsulation                 |
| Multiple applications using a network connection simultaneously | Multiplexing                  |
| Connection-oriented and reliable communication                  | TCP                           |
| Acknowledgments and retransmissions                             | TCP                           |
| Packet sequencing and flow control                              | TCP                           |
| Connectionless communication                                    | UDP                           |
| No acknowledgments or retransmissions                           | UDP                           |
| Destination device                                              | IP address                    |
| Application receiving the data                                  | TCP or UDP port number        |
| IP address plus protocol plus port number                       | Socket                        |
| Temporary client-side port                                      | Ephemeral port                |
| Standard server application port                                | Well-known or registered port |
| Traffic permission or blocking                                  | Firewall                      |

---

## Practice Questions

### 1. What protocol is responsible for moving packets from one network device to another?

Answer: IP

### 2. What is encapsulation?

Answer: Encapsulation is the process of placing data inside multiple protocol layers before sending it across a network.

### 3. At which OSI layer do TCP and UDP operate?

Answer: Layer 4, the Transport layer

### 4. Which protocol is connection-oriented?

Answer: TCP

### 5. Which protocol uses acknowledgments and retransmissions?

Answer: TCP

### 6. Which protocol is connectionless?

Answer: UDP

### 7. What does an IP address identify?

Answer: The destination device

### 8. What does a TCP or UDP port number identify?

Answer: The application or service that should receive the data

### 9. What information is commonly included in a socket?

Answer: IP address, transport protocol, and port number

### 10. Does changing a port number improve network security?

Answer: No. A firewall is needed to allow or block traffic.

### 11. Are TCP port 80 and UDP port 80 the same?

Answer: No. TCP and UDP maintain separate port-number spaces.
