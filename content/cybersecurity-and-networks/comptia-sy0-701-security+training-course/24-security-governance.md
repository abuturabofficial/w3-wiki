---
draft: false
date: '2025-10-22T11:40:14+05:00'
title: 'Security Governance'
linkTitle: '5.1: Security Governance'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 24
---

## Security Policies

## Security Policies Guidelines

What rules are you following to provide CIA?
- Confidentiality, Integrity, and Availability

High level strategies
- Data storage requirements, security events procedures

Detailed security goals
- Appropriate Wi-Fi usage, requirements for remote access

Security policies answer the "what" and "why"
- Technical security controls answer the "how"

### Information Security Policies

The big list of all security-related policies
- A centralized resource for processes

Compliance requirements
- Can be critical to an organization

Detailed security procedures
- What happens when...?

A list of roles and responsibilities
- You got this

This is just words and letters
- An organization must enforce the policy

### Acceptable Use Policies (AUP)

What is acceptable use of company assets?
- Detailed documentation 
- May be documented in the Rules of Behavior

Covers many topics
- Internet use, telephones, computers, mobile devices, etc.

Used by an organization to limit legal liability
- If someone is dismissed, these are the well-documented reasons why

### Business Continuity

Not everything goes according to plan
- Disasters can cause a disruption to the norm

We rely on our computer systems
- Technology is pervasive

There needs to be an alternative
- Manual transactions
- Paper receipts
- Phone calls for transaction approvals

These must be documented and tested before a problem occurs

### Disaster Recovery Plan

If a disaster happens, IT should be ready
- Part of business continuity planning
- Keep the organization up and running

Disasters are many and varied
- Natural disasters
- Technology or system failures
- Human-created disasters

A comprehensive plan
- Recovery location
- Data recovery method
- Application restoration
- IT team and employee availability

### Security Incidents

User clicks an email attachment and executes malware
- Malware then communicates with external servers

DDoS
- Botnet attack

Confidential information is stolen
- Thief wants money, or it goes public

### Incident Response Roles

Incident response team
- Specialized group, trained and tested

IT security management
- Corporate support

Compliance officers
- Intricate knowledge of compliance rules

Technical staff
- Your team in the trenches

User community
- They see everything

### NIST SP800-61

National Institute of Standards and Technology
- NIST Special Publication 800-61 Revision 2
- Computer Security Incident Handling Guide

The incident response lifecycle
- Preparation
- Detection and Analysis
- Containment, Eradication, and Recovery
- Post-incident Activity

### Software Development Lifecycle (SDLC)

Systems development life cycle
- Or application development life cycle

Many ways to get from idea to app
- And many moving parts
- Customer requirements
- Keep the process on schedule
- Stay in budget

There is no "best way"
- But it helps to have a framework
- There are many options

![](/notes/comptia-sy0-701-security+training-course/24-security-governance-1.webp)

### Change Management

How to make a change
- Upgrade software, change firewall configuration, modify switch ports

One of the most common risks in the enterprise
- Occurs very frequently

Often overlooked or ignored
- Did you feel that bite?

Have clear policies
- Frequency, duration, installation process, fallback procedures

Sometimes extremely difficult to implement
- It's hard to change organizational culture

## Security Standards

A formal definition for using security technologies and processes
- Complete documentation reproduces security risk
- Everyone understands the expectations

These may be written in-house
- Your requirements may be unique

Many standards are already available
- ISO (International Organization for Standardization)
- NIST (National Institute of Standards and Technology)

### Password

What makes a good password?
- Every organization has their own requirements
- Create a formal password complexity policy

Define acceptable authentication methods
- No local accounts, only LDAP to the AD database, etc.

Create policies for secure password resets
- Avoid unauthorized resets and access

Other password policies
- Password change frequency, secure password storage requirements, password manager options, etc.

### Access Control

How does an organization control access to data?
- Determine which information, at what time
- And number which circumstances

Define which access control types can be used
- No discretionary, mandatory only, etc.

Determine how a user gets access
- Require privilege documentation

Document how access may be removed
- Security issues, expiration, contract renewals, etc.

### Physical Security

Rules and policies regarding physical security controls
- Doors, building access, property security

Granting physical access
- Different for employees vs. visitors

Define specific physical security systems
- Electronic door locks, ongoing monitoring, motion detection, etc.

Additional security concerns
- Mandatory escorts, off-boarding, etc.

### Encryption

Define specific standards for encrypting and securing data
- All things cryptographic
- Can include implementation standards

Password storage
- Methods and techniques

Data encryption minimums
- Algorithms for data in use, data in transit, data at rest
- Will probably be different for each data state

## Security Procedures

### Change Management

A formal process for managing change
- Avoid downtime, confusion, and mistakes

Nothing changes without the process
- Determine the scope of the change
- Analyze the risk associated with the change
- Create a plan
- Get end-user approval
- Present the proposal to the change control board
- Have a backout plan if the change doesn't work
- Document the changes

### On-boarding

Bring a new person into the organization
- New hires or transfers

IT agreements need to be signed
- May be part of the employee handbook or a separate AUP

Create accounts
- Associate the user with proper groups and departments

Provide required IT hardware
- Laptops, tablets, etc.
- Preconfigured and ready to go

### Off-boarding

All good things...
- But you know this day would come

This process should be pre-planned
- You don't want to decide how to do things at this point

What happens to the hardware?

What happens to the data?

Account information is usually deactivated
- But not always deleted

### Playbooks

Conditional steps to follow; a broad process
- Investigate a data breach, recover from ransomware

Step-by-step set of processes and procedures
- A manual checklist
- Can be used to create automated activities

Often integrated with a SOAR platform
- Security Orchestration, Automation, and Response
- Integrate third-party tools and data sources
- Make security teams more effective

### Monitoring and Revision

IT security is constantly changing
- Processes and procedures also must change

Update to security posture
- Tighter change control, additional playbooks

Change to individual procedure
- Update the playbooks, include additional checks

New security concerns
- Protect against emerging threats

### Governance Structures

Boards
- A panel of specialists
- Sets the tasks or requirements for the committees

Committees
- Subject-matter experts
- Considers the input from a board
- Determines next steps for a topic at hand
- Presents the results to the board

Government entities
- A different kind of machine
- Legal concerns, administrative requirements, political issues
- Often open to public

Centralized/decentralized
- The source of the processes and procedures
- Centralized governance is located in one location with a group of decision makers
- Decentralized governance spreads the decision-making process around to other individuals or locations

## Security Considerations

### Regulatory

Regulations are often mandated
- Security processes are usually a foundational consideration
- Logging, data storage, data protection, and retention

Sarbanes-Oxley Act (SOX)
- The Public Company Accounting Reform and Investor Protection Act of 2002

The Health Insurance Portability and Accountability Act (HIPAA)
- Extensive healthcare standards for storage, use, and transmission of health care information

### Legal

The security team is often tasked with legal responsibilities
- Reporting illegal activities
- Holding data required for legal proceedings

Security breach notifications
- A legal requirement in many jurisdictions

Cloud computing can make this challenging
- Data moves between jurisdictions without human intervention
- The security team must follow legal guidelines

### Industry

The industry may require specific security considerations
- Every market is a bit different

Electrical power and public utilities
- Isolated and protected system controls

Medical
- Highly secure data storage and access logs
- Data encryption and protection

### Geographical Security

Local/regional
- City and state government records
- Uptime and availability of end-user services

National 
- Federal governments and national defense
- Multi-state organizations
- State secrets remain secret

Global
- Large multinational companies
- Global financial markets
- Legal concerns will vary widely

## Data Roles and Responsibilities

### Data Responsibilities

High-level data relationships
- Organizational responsibilities, not always technical

Data owner
- Accountable for specific data, often a senior officer
- VP of Sales owns the customer relationship data
- Treasurer owns the financial information

### Date Roles

Data controller
- Manages the purposes and means by which personal data is processed

Data processor
- Processes data on behalf of the data controller
- Often a third-party or different group

Payroll controller and processor
- Payroll department (data controller) defines payroll amounts and timeframes
- Payroll company (data processor) processes payroll and stores employee information

Data custodian/steward
- Responsible for data accuracy, privacy, and security

Works directly with the data
- Associates sensitivity labels to the data
- Ensures compliance with any applicable laws and standards
- Manages the access rights to the data
- Implements security controls

