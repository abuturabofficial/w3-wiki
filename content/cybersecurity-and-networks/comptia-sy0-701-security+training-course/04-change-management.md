---
draft: false
date: '2025-09-22T08:17:32+05:00'
title: 'Change Management'
linkTitle: '1.3: Change Management'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 4
---

## Change Management

- **How to make a change**
    - Upgrade software, patch an application, change firewall configuration, modify switch ports
- **One of the most common risks in the enterprise**
    - Occurs very frequently
- **Often overlooked or ignored**
    - Did you feel that bit?
- **Have clear policies**
    - Frequency, duration, installation process, rollback procedures
- **Sometimes extremely difficult to implement**
    - It's hard to change corporate culture

### Change Approval Process

- **A formal process for managing change**
    - Avoid downtime, confusion, and mistakes
- **A typical approval process**
    - Complete the request forms
    - Determine the purpose of the change
    - Identify the scope of the change
    - Schedule a date and time of the change
    - Determine affected systems and the impact
    - Analyze the risk associated with the change
    - Get approval from the change control board
    - Get end-user acceptance after the change is complete

### Ownership

- **An individual or entity needs to make a change**
    - They own the process
    - They don't (usually) perform the actual change
- **The owner manages the process**
    - Process updates are provided to the owner
    - Ensures the process is followed, and acceptable
- **Address label printers needs to be upgraded**
    - Shipping and Receiving department owns the process
    - IT handles the actual change

### Stakeholders

- **Who is impacted by this change?**
    - They'll want to have input on the change management process
- **This may not be as obvious as you might think**
    - A single change can include one individual or the entire company
- **Upgrade software used for shipping labels**
    - Shipping/receiving
    - Accounting reports
    - Product delivery timeframes
    - Revenue recognition — CEO visibility

### Impact Analysis

- **Determine a risk value**
    - high, medium, low etc.
- **The risks can be minor or far-reaching**
    - The "fix" doesn't actually fix anything
    - The fix breaks something else
    - OS failures
    - Data corruption
- **What's the risk with NOT making the change?**
    - Security vulnerability
    - Application unavailability
    - Unexpected downtime to other services

### Test Results

- **Sandbox testing environment**
    - No connection to the real world or production system
    - A technological safe place
- **Use before making a change to production**
    - Try the upgrade, apply the patch
    - Test and confirm before deployment
- **Confirm the back out plan**
    - Move everything back to the original
    - A sandbox cannot consider every possibility

### Backout Plan

- **The change will work perfectly and nothing will ever go bad**
    - Of course it will
- **You should always have a way to revert your changes**
    - Prepare for the worst, hope for the best
- **This isn't as easy as it sounds**
    - Some changes are difficult to revert
- **Always have backups**
    - Always have good backups

### Maintenance Windows

- **When is the change happening**
    - This might be the most difficult part of the process
- **During the workday may not be the best option**
    - Potential downtime would affect a large part of production
- **Overnights are often a better choice**
    - Challenging for 24-hour production schedules
- **The time of year may be a consideration**
    - Retail networks are frozen during the holiday season

### Standard Operating Procedures

- **Change management is critical**
    - Affects everyone in the organization
- **The process must be well documented**
    - Should be available on the Internet
    - Along with all standard processes and procedures
- **Changes to the process are reflected in the standards**
    - A living document

## Technical Change Management

- **Put the change management process into action**
    - Execute the plan
- **There is no such thing as a simple upgrade**
    - Can have many moving parts
    - Separate events may be required
- **Change management is often concerned with "what" need to change**
    - The technical team is concerned with "how" to change it

### Allow List/Deny List

**Any application can be dangerous**
- Vulnerabilities, Trojan horses, malware

**Security policy can control app execution**
- Allow list, deny/block list

**Allow list**
- Nothing runs unless it's approved
- Very restrictive

**Deny list**
- Nothing on the "bad list" can be executed
- Anti-virus, anti-malware

### Restricted Activities

**The scope of a change is important**
- Defines exactly which components are covered

**A change approval isn't permission to make any change**
- The change control approval is very specific

**The scope may need to be expanded during the change window**
- It's impossible to prepare for all possible outcomes

**The change management process determines the next steps**
- There are processes in place to make the change successful

### Downtime

**Services will eventually be unavailable**
- The change process can be disruptive
- Usually scheduled during non-production hours

**If possible, prevent any downtime**
- Switch to secondary system, upgrade the primary, then switch back

**Minimize any downtime events**
- The process should be as automated as possible
- Switch back to secondary if issues appear
- Should be part of the backout plan

**Send emails and calendar updates**

### Restarts

**It's common to require a restart**
- Implement the new configuration
- Reboot the OS, power cycle the switch, bounce the service
- Can the system recover from a power outage?

**Services**
- Stop and restart the service or daemon
- May take seconds or minutes

**Applications**
- Close the application completely
- Launch a new application instance

### Legacy Applications

**Some applications were here before you arrived**
- They will here when you leave

**Often no longer supported by the developer**
- You're now the support team

**Fear of Unknown**
- Face your fears and document the system
- It may not be as bad as you think

**May be quirky**
- Create specific processes and procedures

**Become the expert**

### Dependencies

**To complete A, you must complete B**
- A service will not start without other active services
- An application requires a specific library version

**Modifying one component may require changing or restarting other components**
- This can be challenging to manage

**Dependencies may occur across systems**
- Upgrade the firewall code first
- Then upgrade the firewall management software

### Documentation

**It can be challenging to keep up with changes**
- Documentation can become outdated very quickly
- Require with the change management process

**Updating diagrams**
- Modifications to network configurations
- Address updates

**Updating policies/procedures**
- Adding new systems may require new procedures

### Version Control

**Track changes to a file or configuration data over time**
- Easily revert to a previous setting

**Many opportunities to manage versions**
- Router configurations
- Windows OS patches
- Application registry entries

**Not always straightforward**
- Some devices and OSes provide version control features
- May require additional management software