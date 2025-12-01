---
draft: false
date: '2025-11-29T12:36:01+05:00'
title: 'Attack Types'
linkTitle: '4.2: Attack Types'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 20
---

## Denial of Service

Force a service to fail
- Overload the service

Take advantage of a design failure or vulnerability
- Keep your systems patched!

Cause a system to be unavailable
- Competitive advantage

Create a smokescreen for some other exploit
- Precursor to a DNS spoofing attack

Doesn't have to be complicated
- Turn off the power

### A "friendly" DoS

Unintentional DoSing
- It's not always a ne'er-do-well

Network DoS
- Layer 2 loop without STP

Bandwidth DoS
- Downloading multi-gigabyte Linux distribution over a DSL line

The water line breaks
- Get a good shop vacuum

### Distributed Denial of Service (DDoS)

Launch an army of computers to bring down a service
- Use all the bandwidth or resources — traffic spike

This is why the attackers have botnets
- Thousands or millions of computers at your command
- At its peak, Zeus botnet infected over 3.6 million PCs
- Coordinated attack

Asymmetric threat
- The attacker may have fewer resources than the victim

### DDoS reflection and amplification

Turn your small attack into a big attack
- Often reflected off another device or service

An increasingly common network DDoS technique
- Turn Internet services against the victim

Uses protocols with little (if any) authentication or checks
- NTP, DNS, ICMP
    - Simple DNS query returns much more data than simple domain response
- A common example of protocol abuse

![](/notes/comptia-n10-009-network+training-course/20-attack-types-1.webp)

## VLAN Hopping

Define different VLANs
- Organizational, network engineering, security

You only have access to your VLAN
- Good security best practice

"Hop" to another VLAN
- This shouldn't happen

Two primary methods
- Switch spoofing
- Double tagging

### Switch Spoofing

Some switches support automatic configuration
- Is the switch port for a device, or is it a trunk?

There is no authentication required
- Pretend to be a switch
- Send trunk negotiation

Now you have got a trunk link to a switch
- Send and receive from any configured VLAN

Switch administrators should disable trunk negotiation
- Administratively configure trunk interfaces and device/access interfaces

### Double Tagging

Craft a packet that includes two VLAN tags
- Takes advantage of the "native" VLAN configuration

The first native VLAN tag is removed by the first switch
- The second "fake" tag is now visible to the second switch
- Packet is forwarded to the target

This is one-way trip
- Responses don't have a way back to the source host
- Good for DoS

Don't put any devices on the native VLAN
- Change the native VLAN ID
- Force tagging of the native VLAN

![](/notes/comptia-n10-009-network+training-course/20-attack-types-2.webp)

## MAC Flooding

### The MAC address

Ethernet Media Access Control Address
- The "physical" address of a network adapter
- Unique to a device

48 bits/6 bytes long

![](/notes/comptia-n10-009-network+training-course/20-attack-types-3.webp)

### LAN Switching

Forward or drop frames
- Based on the destination MAC address

Gather a constantly updating list of MAC addresses
- Builds the list based on the source MAC address of incoming traffic
- These age out periodically, often in 5 minutes

Maintain a loop-free environment
- Using Spanning Tree Protocol (STP)

### Learning the MACs

Switches examine incoming traffic
- Makes a note of the source MAC address

Adds unknown MAC addresses to the MAC address table
- Sets the output interface to the received interface

![](/notes/comptia-n10-009-network+training-course/20-attack-types-4.webp)

![](/notes/comptia-n10-009-network+training-course/20-attack-types-5.webp)

### Frame Switching

![](/notes/comptia-n10-009-network+training-course/20-attack-types-6.webp)

### MAC Flooding

The MAC table is only so big

Attackers starts sending traffic with different source MAC addresses
- Force out the legitimate MAC addresses

The table fills up
- Switch begins flooding traffic to all interfaces

This effectively turns the switch into a hub
- All traffic is transmitted to all interfaces
- No interruption in traffic flows

Attacker can easily capture all network traffic!

Flooding can be restricted in the switch's port security settings

## ARP and DNS Poisoning

### Spoofing and Poisoning

Pretend to be something you aren't
- Fake web server, fake DNS server, etc.

Email address spoofing
- The sending address of an email isn't really the sender

Caller ID spoofing
- The incoming call information is completely fake

On-path attacks
- The person in the middle of the conversation pretends to be both endpoints

### ARP Poisoning (IP Spoofing)

Simple ARP Request and response:
![](/notes/comptia-n10-009-network+training-course/20-attack-types-7.webp)
![](/notes/comptia-n10-009-network+training-course/20-attack-types-8.webp)

No security or authentication. That's what the attacker takes advantage of!

![](/notes/comptia-n10-009-network+training-course/20-attack-types-9.webp)

The attacker will capture the traffic, and then send to the legitimate target/router. Neither the router nor the client has any idea about the attacker in the middle who is monitoring their traffic.

### DNS Poisoning

Modify the DNS server
- Requires some crafty hacking
Modify the client host file
- The host file takes precedent over DNS queries

Send a fake response to a valid DNS request
- Requires a redirection of the original request or the resulting response
- Real-time redirection
- This is on-path attack

DNS spoofing/poisoning:

![](/notes/comptia-n10-009-network+training-course/20-attack-types-10.webp)

Attacker can poison the DNS server:

![](/notes/comptia-n10-009-network+training-course/20-attack-types-11.webp)