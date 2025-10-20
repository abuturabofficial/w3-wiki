---
draft: false
date: '2025-10-15T10:35:53+05:00'
title: 'Enterprise Security'
linkTitle: '4.5: Enterprise Security'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 19
---

## Firewalls

### Network-based Firewalls

Filter traffic by port number of application
- Traditional vs. NGFW

Encrypt traffic
- VPN between sites

Most firewalls can be layered 3 devices (router)
- Often sits on the ingress/egress of the network
- Network Address Translation (NAT)
- Dynamic routing

### Next-generation Firewalls (NGFW)

The OSI Application Layer
- Layer 7 firewall

Can be called different names
- Application layer gateway
- Stateful multilayer inspection
- Deep packet inspection

Requires some advanced decodes
- Every packet must be analyzed, categorized, and a security decision determined

### Ports and Protocols

Make a forwarding decisions based on protocols (TCP or UDP) and port number
- Traditional port-based firewalls
- Add to an NGFW for additional security policy options

Based on destination protocol and port
- Web server: tcp/80, tcp/443
- SSH server: tcp/22
- Microsoft RDP: tcp/3389
- DNS query: udp/53
- NTP:udp/123


Firewall Security Policies:
![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-1.webp)

### Firewall Rules

A logical path
- Usually top-to-bottom

Can be very general or very specific
- Specific rules are usually at the top

Implicit deny
- Most firewalls include deny at the bottom
    - Even if you didn't put one

Access control lists (ACLS)
- Allow or disallow traffic
- Groupings of categories — Source IP, Destination IP, port number, time of day, application, etc.

### Web Server Firewall Ruleset

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-2.webp)

### Screened subnet

An additional layer of security between you and the Internet
- Public access to public resources
- Private data remains inaccessible

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-3.webp)

### IPS Rules

Intrusion Prevention System
- Usually integrated into an NGFW

Different ways to find malicious traffic
- Look at traffic as it passes by

Signature-based
- Look for a perfect match

Anomaly-based
- Build a baseline of what's "normal"
- Unusual traffic patterns are flagged

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-4.webp)

You determine what happens when unwanted traffic appears
- Block, allow, send an alert, etc.

Thousands of rules
- Or more

Rules can be customized by group
- Or as individual rules

This can take time to find the right balance
- Security/alert "noise"/false positives

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-5.webp)

## Web Filtering

### Content filtering

Control traffic based on data within the content
- URL filtering, website category filtering

Corporate control of outbound and inbound data
- Sensitive materials

Control of inappropriate content
- Not safe for work
- Parental controls

Protection against evil
- Anti-virus, anti-malware

### URL Scanning

Allow or restrict on Uniform Resource Locator (URL)
- Also called a Uniform Resource Identifier (URI)
- Allow list/Block list

Managed by category
- Auction, hacking, malware, travel, recreation, etc.

Can have limited control
- URLs aren't the only way to surf

Often integrated into an NGFW
- Filters traffic based on category or specific URL

### Agent Based

Install client software on the user's device
- Usually managed from a central console

Users can be located anywhere
- The local agent makes the filtering decisions
- Always-on, always filtering

Updates must be distributed to all agents
- Cloud-based updates
- Update status shown at the console

### Proxies

- Sits between the users and the external network
- Receive the user requests and sends the request on their behalf (the proxy)
- Useful for caching information, access control, URL filtering, content scanning
- Applications may need to know how to use the proxy (explicit)
- Some proxies are invisible (transparent)

### Forward Proxy

A centralized "internal proxy"
- Commonly used to protect and control user access to the Internet

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-6.webp)

### Block Rules

Based on specific URL
- *.professormesser.com:Allow

Category of site content
- Usually divided into over 50 different topics
- Adult, Educational, Gambling, Government, Home and Garden, Legal, Malware, News, etc.

Different dispositions
- Educational: Allow
- Home and Garden: Allow and Alert
- Gambling: Block

### Reputation

Filters URLs based on perceived risk
- A good reputation is allowed 
- A bad reputation is blocked
- Risk: Trustworthy, Low risk, Medium risk, Suspicious, High risk

Automated reputation
- Sites are scanned and assigned a reputation

Manual reputation
- Managers can administratively assign a rep

Add these dispositions to the URL filter
- High risk: Block, Trustworthy: Allow

### DNS filtering

Before connecting to a website, get the IP address
- Perform a DNS lookup

DNS is updated with real-time threat intelligence
- Both commercial and public lists

Harmful sites are not connection
- No IP address, no connection

This works for any DNS lookup
- Not just web filtering

## Operating System Security

### Active Directory

A database of everything on the network
- Computers, user accounts, file shares, printers, groups, and more
- Primarily Windows-based

Manage authentication
- Users login using their AD credentials

Centralized access control
- Determine which users can access resources

Commonly used by the help desk
- Reset passwords, add and remove accounts

### Group Policy

Manage the computers or users with Group Policies
- Local and Domain policies
- Group Policy Management Editor

A central console
- Login scripts
- Network configurations (QoS)
- Security parameters

Comprehensive control
- Hundreds of configuration options

### Security-Enhanced Linux (SELinux)

Security patches for Linux Kernel
- Adds mandatory access control (MAC) to Linux
- Linux traditionally uses discretionary Access Control (DAC)

Limits application access
- The Least privilege
- A potential breach will have limited scope

Open-source
- Already included as an option with many Linux distributions

## Secure Protocols

### Unencrypted Network Data

Network traffic is important data
- Everything must be protected

Some protocols aren't encrypted
- All traffic sent in the clear
- Telnet, FTP, SMTP, IMAP

Verify with a packet capture
- View everything sent over the network

### Protocol Selection

Use a secure application protocol
- Built-in encryption

A secure protocol may not be available
- This may be a deal-breaker

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-7.webp)

### Port Selection

Secure and insecure application connections may be available
- It's common to run secure and insecure on different ports

HTTP and HTTPS
- In-the-clear and encryption web browsing
- HTTP: Port 80
- HTTPS: Port 443

The port number does not guarantee security
- Confirm the security features are enabled
- Packet captures may be necessary

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-8.webp)

### Transport method

Don't rely on the application
- Encrypt everything over the current network transport

802.11 Wireless
- Open access point: No transport-level encryption
- WPA3: All user data is encrypted

Virtual Private Network (VPN)
- Create an encrypted tunnel
- All traffic is encrypted and protected 
- Often requires third-party services and software

VPN Tunnel:
![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-9.webp)

## Email Security

### Email Security Challenges

The protocols used to transfer emails include relatively few security checks
- It's very easy to spoof an email

Spoofing happens all the time
- Check your spam folder

The email looks as if it originated from james@professormesser.com
- But did it? How can you tell?

A reputable sender will configure email validation
- Publicly available on the sender's DNS server

### Mail Gateway

The gatekeeper
- Evaluates the source of inbound email messages
- Blocks it at the gateway before it reaches the user
- On-site or cloud-based

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-10.webp)

### Sender Policy Framework (SPF)

SPF protocol
- Sender configures a list of all servers authorized to send emails for a domain

List of authorized mail servers are added to a `DNS TXT` record
- Receiving mail servers perform a check to see if incoming mail really did come from an authorized host

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-11.webp)

### Domain Keys Identified Mail (DKIM)

A mail server digitally signs all outgoing mail
- The public key is in the DKIM TXT record

The signature is validated by the receiving mail servers
- Not usually seen by the end user

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-12.webp)

### DMARC

Domain-based Message Authentication, Reporting, and Conformance (DMARC)
- An extension of SPF and DKIM 

The domain owner decides what receiving email servers should do with emails not validating using SPF and DKIM
- That policy is written into a `DNS TXT` record
- Accept all, send to spam, or reject the email

Compliance reports are sent to the email administrator
- The domain owner can see how emails are received

![](/notes/comptia-sy0-701-security+training-course/19-enterprise-security-13.webp)

## Monitoring Data

### FIM (File Integrity Monitoring)

Some files change all the time
- Some files should NEVER change

Monitor important OS and application files
- Identify when changes occur

Windows — SFC (System File Checker)

Linux — Tripwire

Many host-based IPS options

### Data Loss Prevention (DLP)

Where's your data?
- Social Security Numbers, credit card numbers, medical records

Stop the data before the attackers get it
- Data "leakage"

So many sources, so many destinations
- Often requires multiple solutions in different places

### Data Loss Prevention (DLP) Systems

On your computer
- Data in use
- Endpoint DLP

On your network
- Data in motion

On your server
- Data at rest

### USB Blocking

DLP on a workstation
- Allow or deny certain tasks

November 2008 — U.S. Department of Defense
- Worm virus "agent.btz" replicates using USB storage
- Bans removable flash media and storage devices

All devices had to be updated
- Local DLP agent handled USB blocking

Ban was lifted in February 2010
- Replaced with strict guidelines

### Cloud-based DLP

Located between users and the Internet
- Watch every byte of network traffic
- No hardware, no software

Block custom defined data strings
- Unique data for your organization

Manage access to URLs
- Prevent file transfers to cloud storage

Block viruses and malware
- Anything traversing the network

### DLP and Email

Email continue to be the most critical risk vector
- Inbound threats, outbound data loss

Check every email inbound and outbound
- Internal system or cloud-based

Inbound
- Block keywords, identify impostors, quarantine email messages

Outbound
- Fake wire transfers, W-2 transmissions, employee information

### Emailing a spreadsheet template

November 2016

Boeing employee emails spouse a spreadsheet to use as a template

Contained the personal information of 36000 Boeing employees
- In hidden columns
- Social security numbers, data of birth, etc.

Boeing sells its own DLP software
- But only uses it for classified work

## Endpoint Security

### The endpoint

The user's access
- Applications and data

Stop the attackers
- Inbound attacks
- Outbound attacks

Many platforms
- Mobile, desktop

Protection is multi-faceted
- Defense in depth

### Edge vs. Access Control

Control at the edge
- Your Internet link
- Managed primarily through firewall rules
- Firewall rules rarely change

Access control
- Control from wherever you are
    - Inside or outside
- Access can be based on many rules
    - By user, group, location, application, etc.
- Access can be easily revoked or changed
    - Change your security posture at any time

### Posture Assessment

You can't trust everyone's computer
- BYOD (Bring Your Own Device)
- Malware infections/missing anti-malware
- Unauthorized applications

Before connecting to the network, perform a health check
- Is it a trusted device?
- Is it running anti-virus? Which one? Is it updated?
- Are corporate applications installed?
- Is it a mobile device? Is the disk encrypted?
- The type of device doesn't matter — Windows, Mac, Linux, iOS, Android

### Health Checks/Posture Assessment

Persistent agents
- Permanently installed onto a system
- Periodic updates may be required

Dissolvable agents
- No installation is required
- Runs during the posture assessment 
- Terminates when no longer required

Agentless NAC
- Integrated with AD
- Checks are made during login and logoff
- Can't be scheduled

### Failing your Assessment

What happens when a posture assessment fails?
- Too dangerous to allow access

Quarantine network, notify administrators
- Just enough network access to fix the issues

Once resolved, try again
- May require additional fixes

### Endpoint Detection and Response (EDR)

A different method of threat protection
- Scale to meet the increasing number of threats

Detect a threat
- Signatures aren't the only detection tool
- Behavioral analysis, machine learning, process monitoring
- Lightweight agent on the endpoint

Investigate the threat
- Root cause analysis

Respond to the threat
- Isolate the system, quarantine the threat, rollback to a previous config
- API driven, no user or technician intervention required

### Extended Detection and Response (XDR)

An evolution of EDR
- Improve missed detections, false positives, and long investigation times
- Attacks involve more than just the endpoint

Add network-based detection
- Investigate and respond to network anomalies

Correlate endpoint, network, and cloud data
- Improve detection rates
- Simplify security event investigation

### User Behavior Analytics

XDR commonly includes user behavior analytics
- Extend the scope of anomaly detection

Watch users, hosts, network traffic, data repositories, etc.
- Create a baseline or normal activity
- Requires data analysis over an extended period

Watch for anything unusual 
- Use a set of rules, pattern matching, statistical analysis

Real-time detection of unusual activity
- Catch the threat early