---
draft: false
date: '2025-09-29T10:07:26+05:00'
title: 'Segmentation and Acess Control'
linkTitle: '2.5: Mitigation Techniques'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 10
---

## Segmenting the Network

Physical, logical, or virtual segmentation
- Devices, VLANs, virtual networks

Performance
- High-bandwidth applications

Security
- Users should not talk directly to database servers
- The only applications in the core are SQL and SSH

Compliance
- Mandated segmentation (PCI compliance)
- Makes change control much easier

### Access Control Lists (ACLs)

Allow or disallow traffic
- Groupings of categories
- Source IP, Destination IP, port number, time of day, application, etc.

Restrict access to network devices
- Limit by IP address, or other identifier
- Prevent regular user/non-admin access

Be careful when configuring these
- You can accidentally lock yourself out

List the permissions
- Bob can read files
- Fred can access the network
- James can access network 192.168.1.0/24 using TCP ports 80, 443, 8088

Many OSes use ACLs to provide access to files
- A trustee and the access rights allowed

### Application Allow List/Deny List

Any application can be dangerous
- Vulnerabilities, Trojan Horses, malware

Security policy can control app execution
- Allow list, deny/block list

Allow list
- Nothing runs unless it's approved
- Very restrictive

Deny list
- Nothing on the "bad list" can be executed
- Anti-virus, anti-malware

#### Examples of Allow and Deny Lists

Decisions are made in the OS
- Often built-in to the OS management

Application hash
- Only allows applications with this unique identifier

Certificate
- Allow digitally signed apps from certain publishers

Path
- Only run applications in these folders

Network Zone
- The apps can only run from this network zone

# Mitigation Techniques

## Mitigation Techniques

### Patching

Incredibly important
- System stability, security fixes

Monthly updates
- Incremental (and important)

Third-party updates
- Application developers, device drivers

Auto-update
- Not always the best option

Emergency out-of-band updates

### Encryption

Prevent access to application data files
- File system encryption

File level encryption
- Windows EFS

Full disk encryption (FDE)
- Encrypt everything on the drive
- BitLocker, FileVault, etc.

Application data encryption
- Managed by the app
- Stored data is protected

### Monitoring

Aggregate information from devices
- Built-in sensors, separate devices
- Integrated into servers, switches, routers, firewalls, etc.

Sensors
- Intrusion prevention systems, firewall logs, authentication logs, web server access logs, database transaction logs, email logs

Collectors
- Proprietary consoles (IPS, Firewall), SIEM consoles, syslog servers
- Many SIEMs include a correlation engine to compare diverse sensor data

### Least Privilege

Rights and permissions should be set to the base minimum
- You only get exactly what's needed to complete your objective

 All user accounts must be limited
- Applications should run with minimal privileges

Don't allow users to run with administrative privileges
- Limit the scope of malicious behavior

### Configuring Enforcement

Perform a posture assessment
- Each time a device connects

Extensive check
- OS patch version
- EDR (Endpoint Detection and Response) version
- Status of firewall and EDR
- Certificate status

Systems out of compliance are quarantined
- Private VLAN with limited access
- Recheck after making corrections

### Decommissioning

Should be a formal policy
- Don't throw your data into the trash
- Someone will find this later

Mostly associated with storage devices
- Hard drive
- SSD
- USB drives

Many options for physical devices
- Recycle the device for use in another system
- Destroy the device

# Hardening Techniques

## System Hardening

Many and varied
- Windows, Linux, iOS, Android, etc.

Updates
- OS updates/service packs, security patches

User accounts
- Minimum password lengths and complexity
- Account Limitations

Network access and security
- Limit network access

Monitor and secure
- Anti-virus, anti-malware

### Encryption

Prevent access to application data files
- File system encryption
- Windows Encrypting Files System (EFS)

Full disk encryption (FDE)
- Encrypt everything on the drive
- Windows BitLocker, macOS FileVault, etc.

Encrypt all network communication
- Virtual Private Network (VPN)
- Application encryption

### The Endpoint

The user's access
- Applications and data

Stop the attackers
- Inbound attacks
- Outbound attacks

Many platforms
- Mobile, Desktop

Protection is multi-faceted
- Defense in depth

### Endpoint Detection and Response (EDR)

A different method of threat detection
- Scale to meet the increasing number of threats

Detect a threat
- Signatures aren't the only detection tool
- Behavior analysis, machine learning, process monitoring
- Lightweight agent on the endpoint

Investigate the threat
- Root cause analysis

Respond to the threat
- Isolate the system, quarantine the threat, rollback to a previous config
- API driven, no user or technician intervention required

### Host-based Firewall

Software based firewall
- Personal firewall, runs on every endpoint

Allow or disallow incoming or outgoing application traffic
- Control by application process
- View all data

Identify and block unknown processes
- Stop malware before it can start

### Finding Intrusions

Host based Intrusion Prevention System (IPS)
- Recognize and block known attacks
- Secure OS and application configs, validate incoming service requests
- Often built into endpoint protection software

HIPS identification
- Signature, heuristics, behavioral
- Buffer overflows, registry updates, writing files to the Windows folder
- Access to non-encrypted data

### Open Ports and Services

Every open port is a possible entry point
- Close everything except required ports

Control access with a firewall
- NGFW would be ideal

Unused or unknown services
- Installed with the OS or from other applications

Applications with broad port ranges
- Open port `0` through `65,535`

Use `nmap` or similar port scanner to verify
- Ongoing monitoring is important

### Default Password Changes

Every network device has a management interface
- Critical systems, other device

Many applications also have management or maintenance interfaces
- These can contain sensitive data

Change default settings
- Passwords

Add additional security
- Require additional logon
- Add 3rd-party authentication

### Removal of Unnecessary Software

All software contains bugs
- Some of those bugs are security vulnerabilities

Every application seems to have a completely different patching process
- Can be challenging to manage ongoing updates

Remove all unused software
- Reduce your risk
- An easy fix