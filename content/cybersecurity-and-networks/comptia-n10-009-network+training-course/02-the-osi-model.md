---
draft: false
date: '2025-10-30T12:47:12+05:00'
title: 'The OSI Model'
linkTitle: '1.1: The OSI Model'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 2
---

## Understanding the OSI Model

What is the OSI model?
- Open Systems Interconnection Reference Model

It's a guide (thus the term "model")
- Don't get wrapped up in the details

This is not the OSI protocol suite
- Most of the OSI protocols didn't catch on

↻ There are unique protocols at every layer

You'll refer to this model for the rest of your career
- Often

↻ [**A**]ll [**P**]eople [**S**]eem [**T**]o [**N**]eed [**D**]ata [**P**]rocessing

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-1.webp)

**Protocol Data Unit:** The name given to data at a specific layer of the OSI Model i.e., Bits, Frames etc.
- To remember PDUs of first 4 layers, the mnemonic is [B]acon [F]rying [P]rodues [S]alivation

### Layer 1 — Physical Layer

The physics of the network
- Signaling, cabling, connectors
- This layer isn't about protocols
- Data is referred to as **Bits** at layer 1

"You have a physical layer problem."
- Fix your cabling, punch-downs, etc.
- Fun loopback tests, test/replace cables, swap adapter cards

### Layer 2 — Data Link Layer

The basic network "language"
- The foundation of communication at the data link layer

Decisions are made based on MAC Addresses at layer 2.
- A 48-bit address "burned-in" to a network interface card (NIC) by its manufacturer.
- The device at this layer is Ethernet Switch
- The data is referred to as **Frames**

Data Link Control (DLC) protocols
- MAC (Media Access Control) address on Ethernet

The "switching" layer

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-2.webp)

### Layer 3 — Network Layer

The "routing" layer
- The forwarding decisions based on Internet Protocol (IP) Address
- The PDU is **Packets** (or **Datagrams**)

Fragments frames to traverse different networks

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-3.webp)

### Layer 4 — Transport Layer

The "post office" layer, it concerns with network connections
- Parcels and letters
- The PDU at layer 4 is called **Segments**

There are two types of protocols at play at layer 4:
1) **Connection-oriented** TCP, Reliable
2) **Connectionless** UDP, Unreliable


TCP (Transmission Control Protocol) and UDP (User Datagram Protocol)

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-4.webp)

### Layer 5 — Session Layer

Communication management between devices
- Start, stop, restart
- SIP (session initiation protocol) for VoIP

Control protocols, tunneling protocols

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-5.webp)

### Layer 6 — Presentation Layer

- The layer we see
- Displaying an image or ASCII
- Character encoding
- Application encryption
- Often combined with the Application Layer

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-6.webp)

### Layer 7 — Application Layer

- The Protocols that give us network functionality, not the graphics display
- HTTP/s, FTP, DNS, POP3

![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-7.webp)

### Real-World to OSI Model

| Layer 7: Application  | Your eyes                                                                              |
| --------------------- | -------------------------------------------------------------------------------------- |
| Layer 6: Presentation | Application encryption (SSL/TLS)                                                       |
| Layer 5: Session      | Control protocols, tunneling protocols                                                 |
| Layer 4: Transport    | TCP segments (connection-oriented, reliable), UDP datagram(connectionless, unreliable) | 
| Layer 3: Network      | IP address, Router, Packet                                                             |
| Layer 2: Data Link    | Frame, MAC address, Extended Unique Identifier (EUI-48, EUI-64), Switch                |
| Layer 1: Physical     | Bits, Cables, fiber, and the signal itself                                             |

OSI in the real world:
![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-8.webp)

Follow the conversation:
![](/notes/comptia-n10-009-network+training-course/02-the-osi-model-9.webp)