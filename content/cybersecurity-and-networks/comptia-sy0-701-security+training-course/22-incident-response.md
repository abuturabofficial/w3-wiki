---
draft: false
date: '2025-10-21T11:47:49+05:00'
title: 'Incident Response'
linkTitle: '4.8: Incident Response'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 22
---

## Incident Response

### Security incidents

User clicks an email attachment and executes malware
- Malware then communicates with external servers

DDoS
- Botnet attack

Confidential information is stolen
- Thief wants money, or it goes public

User installs peer-to-peer software and allows external access to internal servers

### NIST SP800-61

National Institute of Standards and Technology
- NIST Special Publication 800-61 Revision 2
- Computer Security Incident Handling Guide

The incident response lifecycle:
- Preparation
- Detection and Analysis
- Containment, Eradication, and Recovery
- Post-incident Activity

### Preparing for an Incident

Communication methods
- Phones and contact information

Incident handling hardware and software
- Laptops, removable media, forensic software, digital cameras, etc.

Incident analysis resources
- Documentation, network diagrams, baselines, critical file hash values

Incident mitigation software
- Clean OS and application images

Policies needed for incident handling
- Everyone knows what to do

### The Challenge of Detection

Many detection sources
- Different levels of detail, different levels of perception

A large amount of "volume"
- Attacks are incoming all the time
- How do you identify the legitimate threats?

Incidents are almost always complex
- Extensive knowledge needed

### Analysis

An incident might occur in the future
- This is your heads-up

Web server log
- Vulnerability scanner in use

Exploit announcement
- Monthly Microsoft patch release, Adobe PDF software update

Direct threats
- A hacking group doesn't like you

An attack is underway
- Or an exploit is successful

Buffer overflow attempt
- Identified by an intrusion detection/prevention system

Anti-virus software identifies malware
- Deletes from OS and notifies administrator

Host-based monitor detects a configuration change
- Constantly monitors system files

Network traffic flows detect deviate from the norm
- Requires constant monitoring

### Isolation and Containment

Generally a bad idea to let things run their course
- an incident can spread quickly
- It's your fault at that point

Sandboxes
- An isolated OS
- Run malware and analyze the results
- Clean out the sandbox when done

Isolation can be sometimes be problematic
- Malware or infections can monitor connectivity
- When connectivity is lost, everything could be deleted/encrypted/damaged

### Recovery after an Incident

Get things back to normal 
- Remove the bad, keep the good

Eradicate the bug
- Remove malware
- Disable breached user accounts
- fix vulnerabilities

Recover the system
- Restore from backups
- Rebuild from scratch
- Replace compromised files
- Tighten down the perimeter

### Lessons Learned

Learn and improve
- No system is perfect

Post-incident meeting
- Invite everyone affected by the incident

Don't wait too long
- Memories fade over time
- Some recommendations can be applied to the next event

### Answer the Tough Questions

What happened, exactly?
- Timestamps of the event

How did your incident plans work?
- Did the process operate successfully?

What would you do differently next time?
- Retrospective views provide context

Which indicators would you watch next time?
- Different precursors may give you better alerts

### Training for an Incident

There is limited on-the-job training when a security event occurs
- Be ready when an incident is identified

Train the team prior to an incident
- Initial response
- Investigation plans
- Incident reporting
- And more

This can be an expensive endeavor
- Especially with larger response teams

## Incident Planning

### Exercising

Test yourselves before an actual event
- Scheduled update sessions (annual, semi-annual, etc.)

Use well-defined rules of engagement
- Do not touch the production systems

Very specific scenario
- Limited time to run the event

Evaluate response
- Document and discuss

### Tabletop Exercises

Performing a full-scale disaster drill can be costly
- And time-consuming

Many of the logistics can be determined through analysis
- You don't physically have to go through a disaster or drill

Get key players together for a tabletop exercise
- Talk through a simulated disaster

### Simulation

Test with a simulated event
- Phishing attack, password requests, data breaches

Going phishing
- Create a phishing email attack
- Send to your actual user community
- See who bites

Test internal security
- Did the phishing get past the filter?

Test the users
- Who clicked?
- Additional training may be required

### Root Cause Analysis

Determine the ultimate cause of an incident
- Find the root cause by asking "why"

Create a set of conclusions regarding the incident
- Backed up by the facts

Don't get tunnel vision
- There can be more than a single root cause

Mistakes happen
- The response to the mistake is the difference

### Threat Hunting

The constant game of cat and mouse
- Find the attacker before they find you

Strategies are constantly changing
- Firewalls get stronger, so phishing gets better

Intelligence data is reactive
- You can't see the attack until it happens

Speed up the reaction time
- Use technology to fight

### Digital Forensics

Collect and protect information relating to an intrusion
- Many data sources and protection mechanisms

RFC 3227 — Guidelines for Evidence Collection and Archiving
- A good set of best practices

Standard digital forensic process
- Acquisition, analysis, and reporting

Must be detail oriented
- Take extensive notes

### Legal Hold

A legal technique to preserve relevant information
- Prepare for impending litigation
- Initiated by legal counsel

Hold notification
- Custodians are instructed to preserve data

Separate repository for electronically stored information (ESI)
- Many data sources and types
- Unique workflow and retention requirements

Ongoing preservation
- Once notified, there's an ongoing obligation to preserve data

### Chain of Custody

Control evidence
- Maintain integrity

Everyone who contacts the evidence
- Use hashes and digital signatures
- Avoid tampering

Label and catalog everything
- Digitally tag all items for ongoing documentation
- Seal and store

### Acquisition

Obtain the data
- Disk, RAM, firmware, OS files, etc.

Some data may not be on a single system
- Servers, network data, firewall logs

For virtual systems, get a snapshot
- Contains all files and information about a VM

Look for any left-behind digital items
- Artifacts
- Log information, recycle bins, browser bookmarks, saved logins, etc.

### Reporting

Document the findings
- For internal use, legal proceedings, etc.

Summary information 
- Overview of the security event

Detailed explanation of data acquisition
- Step-by-step method of the process

The findings
- An analysis of the data

Conclusion
- Professional results, given the analysis

### Preservation

Handling evidence
- Isolate and protect the data
- Analyze the data later without any alterations

Manage the collection process
- Work from copies
- Manage the data collection from mobile devices

Live collection has become an important skill
- Data may be encrypted or difficult to collect after powering down

Follow best practices to ensure admissibility of data in court
- What happens now affects the future

### E-discovery

Electronic discovery
- Collect, prepare, review, interpret, and produce electronic documents

E-discovery gathers data required by the legal process
- Does not generally involve analysis
- There's no consideration of intent

Works together with digital forensics
- The e-discovery process obtains a storage drive
- Data on the drive is smaller than expected
- Forensics experts determine that data was deleted and attempt to recover the data