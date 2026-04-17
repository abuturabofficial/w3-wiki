---
draft: false
date: '2025-11-03T09:17:52+05:00'
title: 'Network Appliances and Applications'
linkTitle: '1.2: Network Appliances and Applications'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 3
---

## Networking Devices

Many ways to forward traffic
- A data center full of equipment

Every device have a purpose
- The implementation may change over time
- Once installed, it can often be difficult to remove

There are new technologies all the time
- Always something to learn

### Analog Modems

Public Switched Telephone Network (PSTN)
- The worldwide telephone system
- The speeds were in bauds and bits per second (bps).
- Computer sends 0s and 1s via digital signals to modem
- Modem then converts those signals to the analog tones, which can be sent over the PSTN.
- The modem at the receiver ends, receives those analog tones, perform modulation/demodulation, and send the signals to the Server.

> **Modem (Modulator/Demodulator):** Modulates binary data into analog signals, and demodulates analog signals into binary data.
> 
> **Baud:** Number of tone changes per second
> 
> **Bits per Second (bps):** Number of 1s and 0s that can be transmitted over the line.

**300bps:** 300 baud using one channel

**2400 bps:** 2400 baud using one channel

**9600 bps:** 2400 baud using four channels

**28.8 kbps:** 2400 baud using twelve channels

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-7.webp)

### CSMA-CD vs. CSMA-CA

**Carrier-Sense Multiple Access with Collision Detection (CSMA/CD)**
- Can only have one packet on the network at a time
- Multiple packets can collide and in-turn corrupt the data.
- CSMA-CD detects if there are other packets on the line.
- If two computers sent the packet at the same time, collision will happen and detected by the CSMA-CD system, then they will set random back off timer, to send their respective packets at hopefully different times without collision.
- The collision is detected by the slight spike of the voltage signal.
![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-8.webp)

Then Ethernet Hub became popular and CSMA-CD was still effective.
- If there was a collision, the hub will send jam signal to everyone on the network.
![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-9.webp)

**Carrier-Sense Multiple Access with Collision Avoidance (CSMA/CA)**
- The more modern approach
- When Client 1 sends the radio signals, Client 2 also hears this transmission, and wait for the transmission to be over, to begin its transfer.
- There is **Hidden Node** Problem, when the Client 2 is far away from the Wireless Access Point. It cannot clearly hear the Client 1 transmission cycle going on, and falsely assumes that there is no transmission happening. The Client 2 then tries to send its signals, and collision happens.
- There is no voltage spike for collision detection, for wireless AP.
- We need some upper level protocol, that detects the collisions, and re-transmits the collided packets again.
![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-10.webp)

### Ethernet Hub

- Legacy device
- More modern form of Ethernet Bus
- Not intelligent, doesn't know which packets are destined for which device, and send those packets to everyone
- It needs to run with CSMA-CD protocol

### Switch

Bridging done in hardware
- Application-specific integrated circuit (ASIC)

An OSI layer 2 device
- Forwards traffic based on data link address
- Maintains a MAC addresses table for packet forwarding
- If the device isn't in the table, it sends flood signal

Many ports and features
- The core of an enterprise network
- May provide Power over Ethernet (PoE)

Multilayer switch
- Includes Layer 3 (routing) functionality

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-11.webp)

### Router

Routes traffic between IP subnets
- OSI layer 3 device
- Routers inside of switches sometimes called "layer 3 switches"
- Layer 2 = Switch, layer 3 = Router
- Maintains an IP Routing Table
- It doesn't need to know millions of IP routes on the Internet, it just needs to know the **Default Route**.
- Routing Table gets populated:
    - Maybe router is directly connected to the devices
    - Statically configured
    - Dynamic Routing Protocol IS-IS, BGP, RIP, EIGRP

> **Default Route:** A route that is used when a router doesn't have a more specific routing table entry for the destination network.

Often connects diverse network types
- LAN, WAN, copper, fiber

### Firewalls

Filter traffic by port number or application
- Traditional vs. NGFW

Encrypt traffic
- VPN between sites

Most firewalls can be layered 3 devices (routers)
- Often sits on the ingress/egress of the network
- Network Address Translation (NAT)
- Dynamic routing

### IDS and IPS

Intrusion Detection System/Intrusion Prevention System
- Watch network traffic

Intrusions
- Exploits against operating systems, applications, etc.
- Buffer overflows, cross-site scripting, other vulnerabilities

Detection vs. Prevention
- Detection — Alarm or alert
- Prevention — Stop before it gets into the network

### Balancing the load

Distribute the load
- Multiple servers
- Invisible to the end-user

Large-scale implementations
- Web server farms, database farms

Fault tolerance
- Server outages have no effect
- Very fast convergence

### Load Balancer

Configurable load
- Manage across servers

TCP offload
- Protocol overhead

SSL offload
- Encryption/Decryption

Caching
- Fast response

Prioritization
- QoS

Content switching
- Application-centric balancing

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-1.webp)

### Proxies

- Sits between the user and the external network
- Receives the user requests and sends the request on their behalf (the proxy)
- Useful for caching information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invisible (transparent)

### NAS vs. SAN

Network Attached Storage (NAS)
- Connect to a shared storage device across the network
- File-level access

Storage Area Network (SAN)
- Looks and feels like a local storage device
    - Block-level access (modified part of the files can be accessed only)
- Very efficient reading and writing

Requires a lot of bandwidth
- May use an isolated network and high-speed network technologies

### Access Point (AP)

Not a wireless router
- A wireless router is a router and an access point in a single device

An access point is a bridge
- Extends the wired network onto the wireless network
- OSI layer 2 devices

### Wireless networks everywhere

Wireless networking is pervasive
- And you probably don't just have a single access point

Your access points may not even be in the same building 
- One (or more) at every remote site

Configurations may change at any moment
- Access policy, security policies, AP configs

The network should be invisible to your users 
- Seamless network access, regardless of role

### Wireless LAN controllers

Centralized management of access points
- A single "pane of glass"

Deploy new access points

Performance and security monitoring

Configure and deploy changes to all sites

Report on access point use

Usually a proprietary system
- The wireless controller is paired with the access points

## Networking Functions

There's a lot happening behind the scenes
- Many networking functions are part of the infrastructure

Access to important data
- From anywhere in the world

Remote access
- Secure network communication

Traffic management
- Prioritize the important applications

Protocol support
- Maintain uptime and availability

### Content Delivery Network (CDN)

It takes time to get data from one place to another
- Speed up the process

Geographically distributed caching servers
- Duplicate the data
- Users get the data from a local server

You're using a CDN right now
- Used on many websites
- Invisible to the end user

### Virtual Private Network (VPN)

Secure private data traversing a public network
- Encrypted communication on an insecure medium

Concentrator/head-end
- Encryption/decryption access device
- Often integrated into a firewall

Many deployment options
- Specialized cryptographic hardware
- Software-based options available

Often used with client software
- Sometimes built into the OS

### Quality of Service (QoS)

Traffic shaping, packet shaping

Control by bandwidth usage or data rates

Set important applications to have higher priorities than other apps

Manage the QoS 
- Routers, switches, firewalls, QoS devices

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-2.webp)

### Time to live (TTL)

How long should data be available?
- Not all systems or protocols are self-regulating
- We sometimes need to tell a system when to stop

Create a timer
- Wait until traversing a number of hops, or wait until a certain amount of time elapses
- Then stop (or drop)

Many uses
- Drop a packet caught in a loop
- Clear a cache

### Routing loops

Router A thinks the next hop is to Router B
- Router B thinks the next hop is to router A
- And repeat

Easy to misconfigure
- Especially with static routing

This can't go on forever
- TTL is used to stop the loop

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-3.webp)

### IP (Internet Protocol)

Loops could cause a packet to live forever
- Drop the packet after a certain number of hops

Each pass through a router is a hop
- Default TTL for macOS/Linux is 64 hops
- Default TTL for Windows is 128 hops

The router decreases TTL by 1
- A TTL of zero is dropped by the router

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-4.webp)

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-5.webp)

### DNS (Domain Name System)

DNS lookups
- Resolve an IP address from a fully-qualified domain name
- www.professormesser.com = 172.67.41.114

A device caches the lookup for a certain amount of time
- How long? TTL seconds long.

![](/notes/comptia-n10-009-network+training-course/03-network-appliances-and-applications-6.webp)