---
draft: false
date: '2025-11-28T10:42:51+05:00'
title: 'Network Access'
linkTitle: '3.5: Network Access'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 18
---

## VPNs

Virtual Private Networks
- Encrypted (private) data transversing a public network

Concentrator
- Encryption/Decryption access device
- Often integrated into a firewall

Many deployment options
- Specialized cryptographic hardware
- Software-based options available

Used with client software
- Sometimes built into the OS

### Client-to-site VPN

On-demand access from a remote device
- Software connects to a VPN concentrator

Some software can be configured as always-on

![](/notes/comptia-n10-009-network+training-course/18-network-access-1.webp)

### Site-to-site VPN

Always-on
- Or almost always

Firewalls often act as VPN concentrators
- Probably already have firewalls in place

![](/notes/comptia-n10-009-network+training-course/18-network-access-2.webp)

### Clientless VPNs

HyperText Markup Language version 5
- The language commonly used in web browsers

Includes comprehensive API support
- Application Programming Interface
- Web cryptography API

Create a VPN tunnel without a separate VPN application
- Nothing to install

Use an HTML5 compliant browser
- Communicate directly to the VPN concentrator

### Split Tunnel vs. Full Tunnel

Full Tunnel
- All traffic is sent through the VPN tunnel
- The client makes no additional forwarding decisions
- May require additional routing at the concentrator

Split Tunnel
- VPN traffic is sent through the tunnel
- Non-VPN traffic is sent normally
- Configured in the VPN software
    ![](/notes/comptia-n10-009-network+training-course/18-network-access-3.webp)

## Remote Access

### SSH (Secure Shell)

Encrypted console communication - `tcp/22`

Looks and acts the same as Telnet - `tcp/23`

### Graphical User Interface (GUI)

Share a desktop from a remote location
- It's like you're right there

RDP (Microsoft Remote Desktop Protocol)
- Clients for macOS, Linux, and others as well

VNC (Virtual Network Computing)
- Remote Frame Buffer (RFB) protocol
- Clients for many OSes
- Many are open source

Commonly used for technical support
- And for scammers

### API Integration

Control and manage devices
- Hundreds of firewall, routers, switches, and servers
- Log in to each device and make changes manually

Automate the command line
- Bath processes
- Very little control or error handling

Application programming interfaces (APIs)
- Interact with third-party devices and services
- Cloud services, firewalls, operating systems
- Talk their language

### Console

Directly connect to the device
- Traditionally a serial connection
- DB9 connector, RJ45 serial, USB connection

When all else fails
- The console will be available

A text-based serial interface
- The console

Requires a serial or USB connection
- May need a USB to DB9 serial adapter

![](/notes/comptia-n10-009-network+training-course/18-network-access-4.webp)

### Jump-Box

Access secure network zones
- Provides an access mechanism to a protected network

Highly-secured device
- Hardened and monitored

SSH/Tunnel/VPN to the jump server
- RDP, SSH, or jump from there

A significant security concern
- Compromise of the jump server is a significant breach

![](/notes/comptia-n10-009-network+training-course/18-network-access-5.webp)

### In-band Management

Assign an IP address to a device
- Switch, router, firewall, etc.

Maybe a separate Ethernet interface
- Often marked on the device

May be accessible from any connected device
- The IP address is inside the device

Access the device
- SSH
- Browser-based console

![](/notes/comptia-n10-009-network+training-course/18-network-access-7.webp)

### Out-of-band management

The network isn't available
- Or the device isn't accessible from the network

Most devices have a separate management interface
- Usually a serial connection/USB

Connect a modem to manage
- Or cable, DSL, satellite, etc.

Console router/ comm server
- Out-of-band access for multiple devices
- Connect to the console router, then choose where you want to go

![](/notes/comptia-n10-009-network+training-course/18-network-access-6.webp)