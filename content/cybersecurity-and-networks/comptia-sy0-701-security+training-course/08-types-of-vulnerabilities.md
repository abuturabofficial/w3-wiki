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