---
draft: false
date: '2025-10-14T10:36:45+05:00'
title: 'Security Monitoring'
linkTitle: '4.4: Security Monitoring'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 18
---

## Security Monitoring

The attackers never sleep
- 24/7/365

Monitor all entry points
- Logins, publicly available services, data storage locations, remote access

React to security events
- Account access, firewall rule base, additional scanning

Status dashboards
- Get the status of all systems at a glance

### Monitoring Computing Resources

Systems
- Authentication — logins from strange places
- Server monitoring — Service activity, backups, software versions

Applications
- Availability — Uptime and response times
- Data transfers — Increases or decreases in rates

Infrastructure
- Remote access systems — Employees, vendors, guests
- Firewall and IPS reports — Increase or type of attack

### Log Aggregation

SIEM or SEM (Security Information and Event Manager)
- Consolidate different logs to a central database
- Servers, firewalls, VPN concentrators, SANs, cloud services

Centralized reporting
- All information in one place

Correlation between diverse systems
- View authentication and access
- Track application access
- Measure and report on data transfers

### Scanning

A constantly changing threat landscape
- New vulnerabilities discovered daily
- Many business applications and services
- Systems and people are always moving

Actively check systems and devices
- OS types and versions
- Device driver options
- Installed applications
- Potential anomalies

Gather the raw details
- A valuable database of information

### Reporting

Analyze the collected data
- Create "actionable" reports

Status information
- Number of devices up to date/in compliance
- Devices running older OSes

Determine best next steps
- A new vulnerability is announced
- How many systems are vulnerable?

Ad hoc information summaries
- Prepare for the unknown

### Archiving

It takes an average of about 9 months for a company to identify and contain a breach
- IBM security report, 2022

Access to data is critical
- Archive over an extended period

May have a mandate
- State for federal law
- Or organizational requirements

### Alerting

Real-time notification of security events
- Increase in authentication errors
- Large file transfers

Actionable data
- Keep the right people informed
- Enable quick response and status information

Notification methods
- SMS/text
- Email
- Security console/SOC

### Alert Response and Remediation

Quarantine
- A foundational security response
- Prevent a potential security issue from spreading

Alert tuning
- A balancing act
- Prevent false positives and false negatives

An alert should be accurate
- This is an ongoing process
- The tuning gets better as time goes on

## Security Tools

### Security Content Automation Protocol (SCAP)

Many security tools on the market
- NGFWs, IPS, vulnerability scanners, etc.
- They all have their own way of evaluating a threat

Managed by National Institute of Standards and Technology (NIST)
- https://scap.nist.gov

Allows tools to identify and act on the same criteria
- Validate the security configuration
- Confirm patch installs
- Scan for a security breach

### Using SCAP

SCAP content can be shared between tools
- Focused on configuration compliance
- Easily detect applications with known vulnerabilities

Especially useful in large environments
- Many OSes and applications

This specification standard enables automation
- Even between different tools

Automation types
- Ongoing monitoring
- Notification and alerting
- Remediation of noncompliant systems

### Benchmarks

Apply security best-practices to everything
- OSes, cloud providers, mobile devices, etc.
- The bare minimum for security settings

Example: Mobile device
- Disable screenshots, disable screen recordings, prevent voice calls when locked, force encryption backups, disable additional VPN profiles, configure a "lost phone" message, etc.

Popular benchmarks — Center for Internet Security (CIS)
- https://www.cisecurity.org/cis-benchmarks

### Agents/Agentless

Check to see if the device is in compliance
- Install a software agent onto the device
- Run an on-demand agentless check

Agents can usually provide more details
- Always monitoring for real-time notifications
- Must be maintained and updated

Agentless runs without a formal install
- Performs the check, then disappears
- Does not require ongoing updates to an agent
- Will not inform or alert if not running

### SIEM

Security Information and Event Management
- Logging of security events and information

Log collection of security alerts
- Real-time information

Log aggregation and long-term storage
- Usually includes advanced reporting features

Data correlation
- Link diverse data types

Forensic analysis
- Gather details after an event

### Anti-virus and Anti-malware

Anti-virus is the popular term
- Refers specifically to a type of malware
- Trojans, worms, macro viruses

Malware refers to the broad malicious software category
- Anti-malware stops spyware, ransomware, fileless malware

The terms are effectively the same these days
- The names are more of a marketing tool
- Anti-virus software is also anti-malware software now
- Make sure your system is using a comprehensive solution

### Data Loss Prevention (DLP)

Where's your data?
- Social Security Numbers, Credit Card Numbers, Medical Records

Stop the data before the attacker gets it
- Data "leakage"

So many sources, so many destinations
- Often requires multiple solutions
- Endpoint clients
- Cloud-based systems 
    - Email, cloud storage, collaboration tools

### SNMP

Simple Network Management Protocol
- A database of data (MIB) — Management Information Base
- The database contains OIDS — Object identifiers
- Poll devices over `udp/161`

Request statistics from a device
- Server, firewall, workstation, switch, router, etc.

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-1.webp)

#### Graphing with SNMP

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-2.webp)

### SNMP traps

Most SNMP operations expect a poll
- Devices then respond to the SNMP request
- This requires constant polling

SNMP traps can be configured on the monitored device
- Communicates over `udp/162`

Set a threshold for alerts
- If the number of CRC errors increases by 5, send a trap
- Monitoring station can be reacted immediately

### NetFlow

Gather traffic statistics from all the traffic flows
- Shared communication between devices

NetFlow
- Standard collection method
- Many products and options

Probe and collector
- Probe watches network communication
- Summary records are sent to the collector

Usually a separate reporting app
- Closely tied to the collector

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-3.webp)

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-4.webp)

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-5.webp)

### Vulnerability Scanner

Usually minimally invasive
- Unlike a penetration test

Port scan
- Poke around and see what's open

Identify systems
- And security devices

Test from the outside and inside
- Don't dismiss insider threats

Gather as much information as possible
- We'll separate wheat from chaff later

![](/notes/comptia-sy0-701-security+training-course/18-security-monitoring-6.webp)