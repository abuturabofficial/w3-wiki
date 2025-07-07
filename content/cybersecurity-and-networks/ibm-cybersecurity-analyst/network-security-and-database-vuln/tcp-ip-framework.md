---
title: Introduction to the TCP/IP Protocol Framework
linkTitle: "TCP IP Framework"
date: 2023-03-13 11:47:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
---

## **Stateless Inspection**

- Stateless means that each packet is inspected one at a time with no knowledge of the previous packets.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework.webp)
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-1.webp)

### Stateless Inspection Use Cases

- To protect routing engine resources.
- To control traffic going in or your organization.
- For troubleshooting purposes.
- To control traffic routing (through the use of routing instances).
- To perform QoS/CoS (marking the traffic).

## **Stateful Inspection**

- A stateful inspection means that each packet is inspected with knowledge of all the packets that have been sent or received from the same session.
- A session consists of all the packets exchanged between parties during an exchange.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-2.webp)

### What if we have both types of inspection?
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-3.webp)

## **Firewall Filters – IDS and IPS System**

### Firewall Filter (ACLs) / Security Policies Demo…
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-4.webp)

### IDS
  
  An Intrusion Detection System (IDS) is a network security technology originally built for detecting vulnerability exploits against a target application or computer.
- By default, the IDS is a listen-only device.
- The IDS monitor traffic and reports its results to an administrator.
- Cannot automatically take action to prevent a detected exploit from taking over the system.

### Basics of an Intrusion Prevention System (IPS)
  
  An IPS is a network security/threat prevention technology that examines network traffic flows to detect and prevent vulnerability exploits.
- The IPS often sites directly behind the firewall, and it provides a complementary layer of analysis that negatively selects for dangerous content.
- Unlike the IDS – which is a passive system that scans traffic and reports back on threats – the IPS is placed inline (in the direct communication path between source and destination), actively analyzing and taking automated actions on all traffic flows that enter the network.

### How does it detect a threat?
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-5.webp)

## **The Difference between IDS and IPS Systems**
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-6.webp)

## **Network Address Translation (NAT)**
  
  Method of remapping one IP address space into another by modifying network address information in Internet Protocol (IP) datagram packet headers, while they are in transit across a traffic routing device.
- Gives you an additional layer of security.
- Allows the IP network of an organization to appear from the outside to use a different IP address space than what it is actually using. Thus, NAT allows an organization with non-globally routable addresses to connect to the Internet by translating those addresses into a globally routable addresses space.
- It has become a popular and essential tool in conserving global address space allocations in face of IPv4 address exhaustion by sharing one Internet-routable IP address of a NAT gateway for an entire private network.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-7.webp)

### Types of NAT
  
  1. **Static Address translation (static NAT)**: Allows one-to-one mapping between local and global addresses.
  2. **Dynamic Address Translation (dynamic NAT)**: Maps unregistered IP addresses to registered IP addresses from a pool of registered IP addresses.
  3. **Overloading**: Maps multiple unregistered IP addresses to a single registered IP address (many to one) using different ports. This method is also known as **Port Address Translation (PAT)**. By using overloading, thousands of users can be connected to the Internet by using only one real global IP address.

# **Network Protocols over Ethernet and Local Area Networks**

## **An Introduction to Local Area Networks**

### Network Addressing

- Layer 3 or network layer adds an address to the data as it flows down the stack; then layer 2 or the data link layer adds another address to the data.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-8.webp)

### Introduction to Ethernet Networks
  
  For a LAN to function, we need:
- Connectivity between devices
- A set of rules controlling the communication
  
  **The most common set of rules is called Ethernet.**
- To send a packet from one host to another host within the same network, we need to know the **MAC address**, as well as the **IP address** of the destination device.

## **Ethernet and LAN – Ethernet Operations**

### **How do devices know when the data if for them?**
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-9.webp)
  
  **Destination Layer 2 address:** MAC address of the device that will receive the frame.
  
  **Source Layer 2 address:** MAC address of the device sending the frame.
  
  **Types**: Indicates the layer 3 protocol that is being transported on the frame such as IPv4, IPv6, Apple Tall, etc.
  
  **Data:** Contains original data as well as the headers added during the encapsulation process.
  
  **Checksum:** This contains a Cyclic Redundancy Check to check if there are errors on the data.

#### MAC Address
  
  A MAC address is a 48-bits address that uniquely identifies a device’s NIC. The first 3 bytes are for the OUI and the last 3 bytes are reserved to identify each NIC.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-10.webp)

### Preamble and delimiter (SFD)
  
  Preamble and delimiter (SFD) are 7 byte fields in an Ethernet frame. **Preamble** informs the receiving system that a frame is starting and enables synchronization, while **SFD** (Start Frame Delimiter) signifies that the Destination MAC address field begin with the next byte.
  
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-11.webp)

### What if I need to send data to multiple devices?
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-12.webp)

## **Ethernet and LAN – Network Devices**

### Twisted Pair Cabling
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-13.webp)

### Repeater

- Regenerates electrical signals.
- Connects 2 or more separate physical cables.
- Physical layer device.
- Repeater has no mechanism to check for collision.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-14.webp)
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-15.webp)
### Bridge
  
  Ethernet bridges have 3 main functions:
- Forwarding frames
- Learning MAC addresses
- Controlling traffic
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-16.webp)
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-17.webp)
### Difference between a Bridge and a Switch
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-18.webp)

- VLANs provide a way to separate LANs on the same switch.
- Devices in one VLAN don’t receive broadcast from devices that are on another VLAN.
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-19.webp)

### Limitations of Switches:

- Network loops are still a problem.
- Might not improve performance with multicast and broadcast traffic.
- Can’t connect geographically dispersed networks.

# **Basics of Routing and Switching, Network Packets and Structures**

## **Layer 2 and Layer 3 Network Addressing**
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-20.webp)
  
  ![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-21.webp)

## **Address Resolution Protocol (ARP)**
  
  The process of using layer 3 addresses to determine layer 2 addresses is called ARP or Address Resolution Protocol.

## **Routers and Routing Tables**

### Routing Action
  
![TCP IP Framework](/notes/ibm-cybersecurity-analyst/TCP%20IP%20Framework-22.webp)
