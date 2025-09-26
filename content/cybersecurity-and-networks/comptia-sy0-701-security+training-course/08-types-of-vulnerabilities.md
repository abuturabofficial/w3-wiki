---
draft: false
date: '2025-09-24T08:55:33+05:00'
title: 'Types of Vulnerabilities'
linkTitle: '2.3: Types of Vulnerabilities'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 8
---

## Finding Malware

Malware runs in memory
- Memory forensics can find the malicious code

Memory contains running processes
- DLLs (Dynamic Link Libraries)
- Threads
- Buffers
- Memory management functions
- And much more

Malware is hidden somewhere
- Malware runs in its own process
- Malware injects itself into a legitimate process

## Memory Injection

Add code into the memory of an existing process
- Hide malware inside the process

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-1.webp)

Get access to the data in that process
- And the same rights and permissions
- Perform a privilege escalation

## DLL Injection

Dynamic-Link Library
- A Windows library containing code and data
- Many applications can use this library

Attackers inject a path to a malicious DLL
- Runs as part of the target process

One of the most popular memory injection methods
- Relatively easy to implement

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-2.webp)

## Buffer Overflows

Overwriting a buffer of memory
- Spills over into other memory areas

Developers need to perform bounds checking
- The attackers spend a lot of time looking for openings

Not a simple exploit
- Takes time to avoid crashing things
- Takes time to make it do what you want

A really useful buffer overflow is repeatable
- Which means that a system can be compromised

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-3.webp)

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-4.webp)

# Race Conditions

## Race Condition

A programming conundrum
- Sometimes, things happen at the same time
- This can be bad if you've not planned for it

Time-of-check to time-of-use attack (TOCTOU)
- Check the system
- When do you use the results of your last check?
- Something might happen between the check and the use

### Race Condition Example

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-5.webp)

### Race Conditions can cause big problems

January 2004 — Mars rover "Spirit"
- Reboot when a problem is identified
- Problem is with the file system, so reboot because of the file system problem
- Reboot loop was the result

Pwn2Own Vancouver 2023 — Tesla Model 3
- TOCTOU attack against the Tesla infotainment using Bluetooth
- Elevated privileges to root
- Earned $100,000 US prize, and they keep the Tesla

# Malicious Updates

## Software Updates

Always keep your operating system and applications updated
- Updates often include bug fixes and security patches

This process has its own security concerns
- Note every update is equally secure

Follow best practices
- Always have a known-good backup
- Install from trusted sources
- Did I mention the backup?

### Downloading and updating

Install updates from a downloaded file
- Always consider your actions
- Every installation could potentially be malicious

Confirm the source
- A random pop-up during web browsing may not be legitimate

Visit the developer's site directly
- Don't trust a random update button or random downloaded file

Many OSes will only allow signed apps
- Don't disable your security controls

### Automatic Updates

The app updates itself
- Often includes security checks/digital signatures

Relatively trustworthy
- Comes directly from the developer

SolarWinds Orion supply chain attack
- Reported in December 2025
- Attackers gained access to the SolarWinds development system
- Added their own malicious code to the updates
- Gained access to hundreds of government agencies and companies

# Operating System Vulnerabilities

## Operating Systems

A foundational computing platform
- Everyone has an OS
- This makes the OS a very big target

Remarkably complex
- Millions of lines of code
- More code means more opportunities for a security issues

The vulnerabilities are already in there
- We've just not found them yet

## A month OS updates

A normal month of Windows updates
- Patch Tuesday — 2nd Tuesday of each month
- Other companies have similar schedules

May 9, 2023 — Nearly 50 security patches
- 8 Elevation of Privilege Vulnerabilities
- 4 Security Feature Bypass Vulnerabilities
- 12 Remote Code Execution Vulnerabilities
- 8 Information Disclosure Vulnerabilities
- 5 Denial of Service Vulnerabilities
- 1 Spoofing Vulnerability

Checkout Microsoft Security Center for latest patches and updates: https://msrc.microsoft.com/

### Best Practices for OS Vulnerabilities

Always update
- Monthly or on-demand updates
- It's a race between you and the attackers

May require testing before deployment
- A patch might break something else

May require a reboot
- Save all data

Have a fallback plan
- Where's that backup?

# SQL Injection

## Code Injection

Code Injection
- Adding your own information into a data stream

Enabled because of bad programming
- The application should properly handle input and output

So many data types
- HTML, SQL, XML, LDAP

## SQL Injection

SQL — Structured Query Language
- The most common relational database management system language

SQL injection (SQLi)
- Put your own SQL requests into an existing application
- Your application shouldn't allow this

Can often be executed in a web browser
- Inject in a form or field

### Building a SQL Injection

An example of website code:
```sql
"SELECT * FROM users WHERE name = '" + userName + "'";
```

How this looks to the SQL database
```sql
"SELECT * FROM users WHERE name = 'Professor'";
```

Add more information to the query (SQLi):
```sql
"SELECT * FROM users WHERE name = 'Professor' OR '1' = '1'";
```

This could be very bad
- View all database information, delete database information, add users, denial of service, etc.

### SQL Injection Demonstration

Source: https://owasp.org/www-project-webgoat/

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-6.webp)

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-7.webp)

# Cross-site Scripting

## XSS

XSS
- Cascading Style Sheets (CSS) are something else entirely

Originally called cross-site because of browser security flaws
- Information from one site could be shared with another

One of the most common web app vulnerabilities
- Takes advantage of the trust a user has for a site
- Complex and varied

XSS commonly uses JavaScript
- Do you allow scripts? Me too.

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-8.webp)

### Non-persistent (reflected) XSS Attack

Website allows scripts to run in user input
- Search box is a common source

Attacker emails a link that takes advantage of this vulnerability
- Runs a script that sends credentials/session IDs/Cookies to the attacker

Script embedded in the URL executes in the victim's browser
- As if it came from the server

Attacker uses credentials/session IDs/cookies to steal victim's information without their knowledge
- Very sneaky

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-9.webp)

![](/notes/comptia-sy0-701-security+training-course/08-types-of-vulnerabilities-10.webp)

### Persistent (stored) XSS Attack

Attacker posts a message to a social media
- Includes the malicious payload

It's now "persistent"
- Everyone gets the payload

No specific target
- All viewers to the page

For social networking, this can spread quickly
- Everyone who views the message can have it posted to their page
- Where someone else can view it and propagate it further

### Hacking a Subaru

June 2017, Aaron Guzman
- Security Researcher

When authenticating with Subaru, users get a token
- This token never expires (bad!)

A valid token allowed any service request
- Even adding your email address to someone else's account
- Now you have full access to someone else's car

Web front-end included an XSS vulnerability
- A user clicks a malicious link, and you have their token

### Protecting Against XSS

Be careful when clicking untrusted links
- Never blindly click in your email inbox, Never.

Consider disabling JavaScript
- Or control with an extension
- This offers limited protection

Keep your browser and applications updated
- Avoid the nasty browser vulnerabilities

Validate input
- Don't allow users to add their own scripts to an input field


## Hardware Vulnerabilities

We are surrounded by hardware devices
- Many don't have an accessible OS

These devices are potential security issues
- A perfect entry point for an attack

Everything is connecting to the network
- Light bulbs, garage doors, refrigerators, door locks
- IoT is everywhere

The security landscape has grown
- Time to change your approach

### Firmware

The software inside the hardware
- The OS of the hardware device

Vendors are the only ones who can fix their hardware
- Assuming they know about the problem
- And care about fixing it

Trane Comfortlink II thermostats
- Control the temperature from your phone
- Trane notified of three vulnerabilities in April 2014
- Two patched in April 2015, one in January 2016

### End-of-life

End of life (EOL)
- Manufacturer stops selling a product
- May continue supporting the product
- Important for security patches and updates

End of service life (EOSL)
- Manufacturer stops selling a product
- Support is no longer available for the product
- No ongoing security patches or updates
- May have a premium-cost support option

Technology EOSL is a significant concern
- Security patches are part of normal operation

### Legacy Platforms

Some devices remain installed for a long time
- Perhaps too long

Legacy devices
- Older OSes, applications, middleware

May be running end-of-life software
- The risk need to be compared to the return

May require additional security protections
- Additional firewall rules
- IPS signatures for older OSes

# Virtualization Vulnerabilities

## Virtualization Security

Quite different from non-virtual machines
- Can appear anywhere

Quantity of resources vary between VMs
- CPU, memory, storage

Many similarities to physical machines
- Complexity adds opportunity for the attackers

Virtualization vulnerabilities
- Local privilege escalations
- Command injection
- Information disclosure

### VM escape protection

The virtual machine self-contained
- There's no way out
- Or is there?

Virtual machine escape
- Break out of the VM and interact with the host OS or hardware

Once you escape the VM, you have great control
- Control the host and control other guests VMs

This would be a huge exploit
- Full control of the virtual world

### Escaping the VM

March 2017 — Pwn2Own competition
- Hacking contest
- You pwn it, you own it — along with some cash

JavaScript engine bug in Microsoft Edge
- Code execution in the Edge sandbox

Windows 10 kernel bug
- Compromise the guest OS

Hardware simulation bug in VMware
- Escape to the host

> Patches were released soon afterward

### Resource Reuse

The hypervisor manages the relationship between physical and virtual resources
- Available RAM, storage space, CPU availability, etc.

These resources can be reused between VMs
- Hypervisor host with 4 GB of RAM
- Supports three VMs with 2 GB of RAM each
- RAM is allocated and shared between VMs

Data can inadvertently be shared between VMs
- Time to update the memory management features
- Security patches can mitigate the risk

# Cloud Specific Vulnerabilities

## Security in the Cloud

Cloud adoption has been nearly universal
- It's difficult to find a company NOT using the cloud

We have put sensitive data in the cloud
- The attackers would like this data

We are not putting in the right protections
- 76% of organizations aren't using MFA for management of console users

Simple best-practices aren't being used
- 63% of code in production is unpatched
- Vulnerabilities rated high or critical (Common Vulnerability Scoring System - CVSS >= 7.0)

### Attack the service

Denial of Service (DoS)
- A fundamental attack type

Authentication bypass
- Take advantage of weak or faulty authentication

Directory transversal
- Faulty contiguration put data at risk

Remote code execution
- Take advantage of unpatched systems

### Attack the application

Web application attacks have increased
- Log4j and Spring Cloud Function
- Easy to exploit, rewards are extensive

Cross-site scripting
- Take advantage of poor input validation

Out of bound write
- Write to unauthorized memory areas
- Data corruption, crashing, or code execution

SQL injection
- Get direct access to a database

# Supply Chain Vulnerabilities

## Supply Chain Risk

The chain contains many moving parts
- Raw materials, suppliers, manufacturers, distributors, customers, consumers

Attackers can infect any step along the way
- Infect different parts of the chain without suspicion
- People trust their suppliers

One exploit can infect the entire chain
- There's a lot at stake

### Service Providers

You can control your own security posture
- You can't always control a service provider

Service providers often have access to internal services
- An opportunity for the attacker

Many types of providers
- Network, utility, office cleaning, payroll/accounting, cloud services, system administration, etc.

Consider ongoing security audits of all providers
- Should be included with the contract

### Target Service Provider Attack

Target Corp. breach — November 2013
- 40 million credit cards stolen

Heating and AC firm in Pennsylvania war infected
- Malware delivered in an email
- VPN credentials for HVAC techs were stolen

HVAC vendor was the supplier
- Attackers used a wide-open Target network to infect every cash register at 1800 stores

### Hardware Providers

Can you trust your new server/router/switch/firewall/software?
- Supply chain cybersecurity

Use a small supplier base
- Tighter control of vendors

Strict controls over policies and procedures
- Ensure proper security is in place

Security should be part of the overall design
- There's a limit to trust

### Cisco or not Cisco?

All network traffic flows
- A perfect visibility and pivot point

July 2022 — DHS arrests reseller CEO
- Sold more than $1 billion of counterfeit Cisco products
- Created over 30 different companies
- Had been selling these since 2013

Knock-offs made in China
- Sold as authentic Cisco products
- Until they started breaking and catching on fire

### Software providers

Trust is a foundation of security
- Every software installation questions our trust

Initial installation
- Digital signature should be confirmed during installation

Updates and patches
- Some software updates are automatic
- How secure are the updates?

Open source is not immune
- Compromising the source code itself

### SolarWinds Supply Chain Attack

SolarWinds Orion
- Used by 18000 customers
- Including Fortune 500 and US Federal Government

Software updates compromised in March and June 2020
- Upgrades to existing installations
- Not detected until December 2020

Additional breaches took advantage of the exploit
- Microsoft, Cisco, Intel, Deloitte
- Pentagon, Homeland Security, State Department, Department of Energy, National Nuclear Security Administration, Treasury

# Misconfiguration Vulnerabilities

## Open Permissions

Very easy to leave a door open
- The hackers will always find it

Increasingly common with cloud storage
- Statistical chance of finding an open permission

June 2017–14 million Verizon records exposed
- Third-party left an Amazon S3 data repository open
- Researcher found the data before anyone else

Many, Many other examples
- Secure your permissions!

### Unsecured Admin Accounts

The Linux root account
- The Windows Administrator or superuser account

Can be misconfiguration
- Intentionally configuring an easy-to-hack password
- 123456, ninja, football

Disable direct login to the root account
- Use the `su` or `sudo` option

Protect accounts with root or administrator access
- There should not be a lot of these

### Insecure Protocols

Some protocols aren't encrypted
- All traffic sent in the clear
- Telnet, FTP, SMTP, IMAP

Verify with a packet capture
- View everything sent over the network

Use the encrypted versions
- SSH, SFTP, IMAPS

### Default Settings

Every application and network device has a default login
- Not all of these are ever changed

Mirai Botnet
- Take advantage of default configurations
- Takes over Internet of Things (IoT) devices
- 60+ default configurations
- Camera, routers, doorbells, garage door openers, etc.

Mirai released as open-source software
- There's a lot more where that came from

### Open Ports and Services

Services will open ports
- It's important to manage access

Often managed with a firewall
- Manage traffic flows
- Allow or deny based on port number or application

Firewall rulesets can be complex
- It's easy to make mistake

Always test and audit
- Double and triple check