---
draft: false
date: '2025-11-19T12:46:31+05:00'
title: 'Switching Technologies'
linkTitle: '2.2: Switching Technologies'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 11
---

## VLANs and Trunking

### LANs

Local Area Networks
- A group of devices in the same broadcast domain

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-1.webp)

- Two switches, taking power
- Using double the rack space
- Harder to manage

### Virtual LANs

Virtual Local Area Networks
- A group of devices in the same broadcast domain
- Separated logically instead of physically

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-2.webp)

- One switch to manage, less power usage
- Cheaper to manage
- Lesser rack space
- Red and Blue VLANs will not be to communicate between them like physical LANs, except inside the red/blue VLAN only.

### Configuring VLANs

VLAN numbers and names are configured in the switch
- The VLAN database
- Instead of color, VLANs are represented by number, VLAN1, VLAN2 etc.

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-3.webp)

### VLANs on multiple switches

We want to communicate among VLAN1s on multiple switches
- One simple fix is to connect both VLAN100 on each switch with an Ethernet cable
- But, it quickly gets complicated when there are hundreds of switches with VLANs.

### VLAN Trunking

"VLAN trunking is a technology that allows multiple VLANs to share a single physical link between network switches. Instead of needing separate cables for each VLAN, a trunk link carries traffic for all VLANs simultaneously while keeping them logically separated."

- Trunk interface is used to connect VLANs on different physical switches.
- Single cable to carry packet for all switches

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-4.webp)

### 802.1Q trunking

How trunking identifies which packet belongs to which VLAN interface? By tagging!

- Take a normal Ethernet frame
    ![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-5.webp)
- Add a VLAN header in the frame
    ![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-6.webp)
- VLAN IDs -- 12 bits long, 4,096 VLANs
    - "Normal range" -- 1 through 1005, "Extended range" -- 1006 through 4094 -- 0 and 4,095 are reserved VLAN numbers
- Before 802.1Q, there was ISL (Inter-Switch Link)
    - ISL is no longer used; everyone now uses the 802.1Q standard

VLAN trunking:
- VLAN200 wants to send an Ethernet frame to VLAN200 on the other physical switch
- VLAN200 sends normal packet to the trunking interface
- Trunk adds a tag (VLAN200)
- Sends the frame to other VLAN200 device on the different switch
- The switch at the other receives the frame, sees the tag VLAN200, removes the tag, and sends it to the VLAN200.

Trunking between switches:
- It now needs a single packet to connect VLANs on different physical switches
![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-7.webp)

### The Native VLAN

This is different from the "default VLAN"
- The default VLAN is the VLAN assigned to an interface by default

Each trunk has a native VLAN
- The native VLAN doesn't add an 802.1Q header

The native VLAN connects switches without a tag
- Some devices won't talk 802.1Q 
- Just use the native VLAN!

Native VLAN should match between switches
- You'll get a message if the VLAN IDs don't match

### Layer 3 switches

A switch (layer 2) and router (layer 3) in the same physical device
- Layer 2 router?

Switching still operates at OSI Layer 2, routing still operates at OSI Layer 3
- There is nothing new or special happening here
- Just saving a space by putting the switch and router in a single physical device

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-8.webp)

The internal router connects to the VLANs over VLAN interfaces
- Also called switched virtual interfaces (SVI)

May need to enable routing on your switch
- Will operate as an L2 device until enabled
- May require a switch restart

Doesn't replace a standalone router
- Not all designs require extensive routing
- You probably use a layer 3 switch at home

### Working with Data and Voice

Old school: Connect computer to switch, connect phone to PBX (Private Branch Exchange)
- Two physical cables, two different technologies

Now: Voice over IP (VoIP)
- Connect all devices to the Ethernet switch
- One network cable for both

### Data and Voice cabling

- Computer connects to phone
- Phone connects to switch
- One cable, one run

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-9.webp)

### Just one problem...

Voice and data don't like each other
- Voice is very sensitive to congestion
- Data loves to congest the network

Put the computer on one VLAN and the phone on another
- But the switch interface is not a trunk
- How does that work?

Each switch interface has a data and a voice VLAN
- Configure each of them separately

### Configuring Voice and Data VLANs

- Data passes as a normal untagged access VLAN
- Voice is tagged with an 802.1Q header

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-10.webp)

## Interface Configuration

Speed and duplex
- Speed: 10/100/1,000/10 Gig
- Speed mismatch between switches, connection will not work at all.
- Duplex Half/Full
- Duplex mismatch, the connection will work but with degraded performance
- Automatic and manual
- Needs to match on both sides

IP address management
- Layer 3 interfaces
- VLAN interfaces
- Management interfaces
- IP address, subnet mask/CIDR block, default gateway, DNS (optional)

### Link Aggregation

Port bonding/Link aggregation (LAG)
- Multiple interfaces act like one big interface
- Four 10 Gbits interfaces will act as a single 40 Gbit interface

LACP
- Link Aggregation Control Protocol
- Adds additional automation and management

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-11.webp)

### Maximum Transmission Unit (MTU)

Maximum IP packet to transmit
- But not fragment

Fragmentation slows things down
- Losing a fragment loses en entire packet
- Requires overhead along the path

Difficult to know the MTU all the way through the path
- Automated methods are often inaccurate
- Especially when ICMP is filtered

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-12.webp)

### Jumbo Frames

Ethernet frames with more than 1,500 bytes of payload
- Up to 9,216 bytes of an MTU (9,000 is the accepted norm)

Increases transfer efficiency
- Per-packet size
- Fewer packets to switch/route

Ethernet devices must support jumbo frames
- Switches, interface cards
- Not all devices are compatible with others

## Spanning Tree Protocol

### Loop Protection

Connect two switches to each other
- Create a loop with two cables
- They will send traffic back and forth forever
- There's no "counting" mechanism at the MAC layer

This is an easy way to bring down a network
- And somewhat difficult to troubleshoot
- Relatively easy to resolve

IEEE standard 802.1D to prevent loops in bridged (switched) networks (1990)
- Spanning Tree Protocol
- Used practically everywhere

### STP Port States

Blocking
- Not forwarding to prevent a loop

Listening
- Not forwarding and cleaning the MAC table

Learning
- Not forwarding and adding to the MAC table

Forwarding
- Data passes through and is fully operational

Disabled
- Administrator has turned off the port

### Spanning Tree Protocol

If Network A wants to communicate with Network M, it can use Bridge 6
![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-13.webp)

If bridge 6 is unavailable for some reason, there is no other available root!!!

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-14.webp)

Spanning Tree recognizes the disconnection, and starts relearning the topology of the network, to clear out congestions. It reconfigures the STP port states to reestablish the connection between Network A and Network M through Bridge 5.

![](/notes/comptia-n10-009-network+training-course/11-switching-technologies-15.webp)

### RSTP (802.1w)

Rapid Spanning Tree Protocol (802.1w)
- A much-needed updated version of STP
- This is the latest standard

Faster convergence
- From 30 to 50 seconds to 6 seconds

Backwards-compatible with 802.1D STP
- You can mix both in your network

Very similar process
- An update, not a wholesale change