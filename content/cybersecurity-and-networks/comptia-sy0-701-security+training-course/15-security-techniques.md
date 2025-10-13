---
draft: false
date: '2025-10-04T09:23:44+05:00'
title: 'Security Techniques'
linkTitle: '4.1: Security Techniques'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 15
---

## Secure Baselines

The security of an application environment should be well-defined
- All application instances must follow this baseline
- Firewall settings, patch levels, OS file versions
- May require constant updates

Integrity measurements check for the secure baseline
- These should be performed often
- Check against well-documented baselines
- Failure requires an immediate correction

### Establish Baselines

Create a series of baselines
- Foundational security policies

Security baselines are often available from the manufacturer
- Application developer
- OS manufacturer
- Appliance manufacturer

Many OSes have extensive options
- There are over 3000 group policy settings in Windows 10
- Only some of those are associated with security

> [!TIP]
> Microsoft Security Baselines [Guide](https://learn.microsoft.com/en-us/windows/security/operating-system-security/device-management/windows-security-configuration-framework/windows-security-baselines)

### Deploy Baselines

We now have established detailed security baselines
- How do we put those baselines into action?

Deploy the baselines
- Usually managed through a centrally administered console

May require multiple deployment mechanisms
- Active Directory group policy, MDM, etc.

Automation is the key
- Deploy to hundreds or thousands of devices

### Maintain Baselines

Many of these are best practices
- They rarely change

Other baselines may require ongoing updates
- A new vulnerability is discovered
- An updated application has been deployed 
- A new OS is installed

Test and measure to avoid conflicts
- Some baselines may contradict others
- Enterprise environments are complex

## Hardening Targets

No system is secure with the default configurations
- You need some guidelines to keep everything safe

Hardening guides are specific to the software or platform
- Get feedback from the manufacturer or Internet interest group
- They will have the best details

Other general-purpose guides are available online

### Mobile Devices

Always-connected mobile technologies
- Phones, tablets, etc.
- Hardening checklists are available from manufacturers

Updates are critical
- Bug fixes and security patches
- Prevent any known vulnerabilities

Segmentation can protect data
- Company and user data are separated

Control with an MDD
- Mobile Device Manager

### Workstations

User desktops and laptops
- Windows, macOS, Linux, etc.

Constant monitoring and updates
- OSes, applications, firmware, etc.

Automate the monthly patches
- There's likely an existing process

Connect to a policy management system
- Active Directory group policy

Remove unnecessary software
- Limit the threats

### Network Infrastructure Devices

Switches, routers, etc.
- You never see them, but they're always there

Purpose-built devices
- Embedded OS, limited OS access

Configure authentication
- Don't use the defaults

Check with the manufacturer
- Security updates
- Not usually updated frequently
- Updates are usually important

### Cloud Infrastructure

Secure the cloud management workstation
- The keys to the kingdom

Least privilege
- All services, network settings, application rights and permissions

Configure Endpoint Detection and Response (EDR)
- All devices accessing the cloud should be secure

Always have backups
- Cloud to Cloud (C2C)

### Servers

Many and varied
- Windows, Linux, etc.

Updates
- OS updates/service packs, security patches

User accounts
- Minimum password lengths and complexity
- Account limitations

Network access and security
- Limit network access

Monitor and secure
- Anti-virus, anti-malware

### SCADA/ICS

Supervisory Control and Data Acquisition System
- Large-scale, multi-site Industrial Control Systems (ICS)

PC manages equipment
- Power generation, refining, manufacturing equipment
- Facilities, industrial, energy, logistics

Distributed control systems
- Real-time information
- System control

Requires extensive segmentation
- No access from the outside

### Embedded Systems

Hardware and software designed for a specific function
- Or to operate as part of a larger system

Can be difficult to upgrade
- Watches and televisions are relatively easy
- Other devices may not be easily modified

Correct vulnerabilities
- Security patches remove potential threats

Segment and firewall
- Prevent access from unauthorized users

### RTOS (Real-Time Operating System)

An OS with a deterministic processing schedule
- No time to wait for other processes
- Industrial equipment, automobiles, military environments

Isolate the system
- Prevent access from other areas

Run with the minimum services
- Prevent the potential for exploit

Use secure communication
- Protect with a host-based firewall

### IoT Devices

Heating and cooling, lighting, home automation, wearable technology, etc.

Weak defaults
- IoT manufacturers are not security professionals
- Change those passwords

Deploy updates quickly
- Can be a significant security concern

Segmentation
- Put IoT devices on their own VLAN

## Securing Wireless and Mobile

### Site Surveys

Determine existing wireless landscape
- Sample the existing wireless spectrum

Identify existing access points
- You may not control all of them

Work around existing frequencies
- Layout and plan for interference

Plan for ongoing site surveys
- Things will certainly change

Heat maps
- Identify wireless signal strengths

### Wireless Survey Tools

- Signal coverage
- Potential interference
- Built-in tools
- 3rd-party tools
- Spectrum analyzer

![](/notes/comptia-sy0-701-security+training-course/15-security-techniques-1.webp)

### Mobile Device Management (MDM)

Manage company-owned and user-owned mobile devices
- BYOD — Bring Your Own Device

Centralized management of the mobile devices
- Specialized functionality

Set policies on apps, data, camera, etc.
- Control the remote device
- The entire device or a "portion"

Manage access control
- Force screen locks and PINs on these single user devices

### BYOD

Bring Your Own Device OR Bring Your Own Technology

Employee owns the device
- Need to meet the company's requirements

Difficult to secure
- It's both a home device and a work device
- How is data protected?
- What happens to the data when a device is sold or traded in?

### COPE

Corporate owned, personally enabled
- Company buys the device
- Used as both a corporate device and a personal device

Organization keeps full control of the device
- Similar to company-owned laptops and desktops

Information is protected using corporate policies
- Information can be deleted at any time

CYOD — Choose Your Own Device
- Similar to COPE, but with the user's choice of device

### Cellular Networks

Mobile devices
- "Cell" phones
- 4G, 5G

Separate land into "cells"
- Antenna coverages a cell with certain frequencies

Security concerns
- Traffic monitoring
- Location tracking
- Worldwide access to a mobile device

### Wi-Fi

Local network access
- Local security problems

Same security concerns as other Wi-Fi devices

Data capture
- Encrypt your data!

On-path attack
- Modify and/or monitor data

Denial of service
- Frequency interference

### Bluetooth

High speed communication over short distances
- PAN (Personal Area Network)

Connects our mobile devices
- Smartphones, tethering, headsets and headphones, smartwatches, etc.

Do not connect to unknown Bluetooth devices
- There's a formal pairing process to prevent unauthorized connections

## Wireless Security Settings

### Securing a Wireless Network

An organization's wireless network can contain confidential information
- Not everyone is allowed access

Authenticate the users before granting access
- Who gets access to the wireless network?
- Username, password, multifactor authentication

Ensure that all communication is confidential
- Encrypt the wireless data

Verify the integrity of all communication
- The received data should be identical to the original sent data
- A message integrity check (MIC)

### The WPA2 PSK Problem

WPA2 has a PSK brute-force problem
- Listen to the four-way handshake
    - Some methods can derive the PSK hash without the handshake
- Compute the hash

With the hash, attackers can brute force the pre-shared key (PSK)

This has become easier as technology improves
- A weak PSK is easier to brute-force
- GPU processing speeds
- Cloud-based password cracking

Once you have the PSK, you have everyone's wireless key
- There's no forward secrecy

### WPA3 and GCMP

Wi-Fi Protected Access 3 (WPA3)
- Introduced in 2018

GCMP block cipher mode
- Galois/Counter Mode Protocol
- A stronger encryption than WPA2

GCMP security services
- Data confidentiality with AES
- Message Integrity Check (MIC) with Galois Message Authentication (GMAC)

### SAE

WPA3 changes the PSK authentication process
- Includes mutual authentication
- Creates a shared session key without sending that key across the network
- No more four-way handshakes, no hashes, no brute force attacks

Simultaneous Authentication of Equals (SAE)
- A Diffie-Hellman derived key exchange with an authentication component
- Everyone uses a different session key, even with the same PSK
- An IEEE standard — the dragonfly handshake

### Wireless Authentication Methods

Gain access to a wireless network
- Mobile users
- Temporary users

Credentials
- Shared password/pre-shared key (PSK)
- Centralized authentication (802.1X)

Configuration
- Part of the wireless network connection
- Prompted during the connection process

### Wireless Security Modes

Configure the authentication on your wireless access point/wireless router

Open System
- No authentication password is required

WPA3-Personal/WPA3-PSK
- WPA2 or WPA3 with a pre-shared key 
- Everyone uses the same 256-bit key

WPA3-Enterprise/WPA3-802.1X
- Authenticates users individually with an authentication server (i.e, RADIUS)

### AAA Framework

Identification
- This is who you claim to be
- Usually your username

Authentication
- Prove you are who you say you are
- Password and other authentication factors

Authorization
- Based on your identification and authentication, what access do you have?

Accounting
- Resources use: Login time, data sent and received, logout time

![](/notes/comptia-sy0-701-security+training-course/15-security-techniques-2.webp)

### RADIUS (Remote Authentication Dial-in User Service)

One of the more common AAA protocols
- Supported on a wide variety of platforms and devices

Centralize authentication for users
- Routers, switches, firewalls
- Server authentication
- Remote VPN access
- 802.1X network access

RADIUS services available on almost any server operating system

### IEEE 802.1X

IEEE 802.1X
- Port-based Network Access Control (NAC)
- You don't get access to the network until you authenticate

Used in conjunction with an access database
- RADIUS, LDAP, TACACS+

### EAP

Extensible Authentication Protocol (EAP)
- An authentication framework

Many ways to authenticate based on RFC standards
- Manufacturers can build their own EAP methods

EAP integrates with 802.1X
- Prevents access to the network until the authentication succeeds

### IEEE 802.1X and EAP

Supplicant — the client
Authenticator — The device that provides access
Authentication server — Validates the client credentials

![](/notes/comptia-sy0-701-security+training-course/15-security-techniques-3.webp)

## Application Security

### Secure Coding Concepts

A balance between time and quality
- Programming with security in mind is often secondary

Testing, testing, testing
- The Quality Assurance (QA) process

Vulnerabilities will eventually be found
- And exploited

### Input Validation

What is the expected input?
- Validate actual vs. expected

Document all input methods
- Forms, fields, type

Check and correct all input (normalization)
- A zip code should be only X characters long with a letter in the X column
- Fix any data with improper input

The fuzzers will find what you missed
- Don't give them an opening

### Cookies

Cookies
- Information stored on your computer by the browser

Used for tracking, personalization, session management
- Not executable, not generally a security risk
    - Unless someone gets access to them

Secure cookies have a Secure attribute set
- Browser will only send it over HTTPS

Sensitive information should not be saved in a cookie
- This isn't designed to be secure storage

### Static Code Analyzers

Static Application Security Testing (SAST)
- Help to identify security flaws

Many security vulnerabilities found easily 
- Buffer overflows, database injections, etc.

Not everything can be identified through analysis
- Authentication security, insecure cryptography, etc.
- Don't rely on automation for everything

Still have to verify each finding
- False positives are an issue

![](/notes/comptia-sy0-701-security+training-course/15-security-techniques-4.webp)

### Code Signing

An application is deployed
- Users run application executables or scripts

So many security questions
- Has the application been modified in any way?
- Can you confirm that the application was written by a specific developer?

The application code can be digitally signed by the developer
- Asymmetric encryption
- A trusted CA signs the developer's public key
- Developer signs the code with their private key
- For internal apps, use your own CA

### Sandboxing

Applications cannot access unrelated resources
- They play in their own sandbox

Commonly used during development
- Can be useful production technique

Used in many deployments
- Virtual machines
- Mobile devices
- Browser iframes (Inline Frames)
- Windows User Account Control (UAC)

### Application Security Monitoring

Real-time information
- Application usage, access demographics

View blocked attacks
- SQL injection attempts, patched vulnerabilities

Audit the logs
- Find the information gathering and hidden attacks

Anomaly detection
- Unusual file transfer
- Increase in client access

