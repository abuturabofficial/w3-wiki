---
draft: false
date: '2025-09-27T07:51:27+05:00'
title: 'An Overview of Malware'
linkTitle: '2.4: Indicators of Malicious Acitivity'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 9
---

## Malware

Malicious Software
- These can be very bad

Gather information
- Keystrokes

Show you advertising
- Big money

Viruses and worms
- Encrypt your data
- Ruin your day

### Malware Types and Methods

- Viruses
- Worms
- Ransomware
- Trojan Horse
- Rootkit
- Keylogger
- Spyware
- Bloatware
- Logic bomb

### How You Get Malware

These all work together
- A worm takes advantage of a vulnerability
- Installs malware that includes a remote access backdoor
- Additional malware may be installed later

Your computer must run a program
- Email link — Don't click links
- Web page pop-up
- Drive-by download
- Worm

Your computer is vulnerable
- OS — Keep your OS updated
- Applications — Check with the publisher

### Your Data is Valuable

Personal Database
- Family pictures and videos
- Important documents

Organization data
- Planning documents
- Employee personally identifiable information (PII)
- Financial records
- Company private data

How much is it worth?
- There's a number

## Ransomware

A particularly nasty malware
- Your data is unavailable until you provide cash

Malware encrypts your data files
- Pictures, documents, music, movies, etc.
- Your OS remains available

You must pay the attackers to obtain the decryption key
- Untraceable payment system
- An unfortunate use of public-key cryptography

### Protecting against Ransomware

Always have a backup
- An offline backup, ideally

Keep your OS up to date
- Patch those vulnerabilities

Keep your applications up-to-date
- Security patches

Keep your anti-virus/anti-malware signatures up-to-date
- New attacks every hour

Keep everything up-to-date

# Viruses and Worms

## Virus

Malware that can reproduce itself
- It needs you to execute a program

Reproduces through file systems or the network
- Just running a program can spread a virus

May or may not cause problems
- Some viruses are invisible, some are annoying

Anti-virus is very common
- Thousands of new viruses every week
- Is your signature file updated?

### Virus Types

Program viruses
- It's part of the application

Boot sector viruses
- Who need an OS?

Script viruses
- OS and browser-based

Macro viruses
- Common in Microsoft Office

### Fileless Virus

A stealth attack
- Does a good job of avoiding anti-virus detection

Operates in memory
- But never installed in a file or application

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-1.webp)

## Worms

Malware that self-replicates
- Doesn't need you to do anything
- Uses the network as a transmission medium
- Self-propagates and spreads quickly

Worms are pretty bad things
- Can take over many systems very quickly

Firewalls and IDS/IPS can mitigate many worms infestations
- Doesn't help much once the worm gets inside

### Wannacry Worm

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-2.webp)

# Spyware and Bloatware

## Spyware

Malware that spies on you
- Advertising, identity theft, affiliate fraud

Can trick you into installing
- Peer to peer, fake security software

Browser monitoring
- Capture surfing habits

Keyloggers
- Capture every keystroke
- Send your keystrokes back to the attacker

### Protecting Against Spyware

Maintain your anti-virus/anti-malware
- Always have the latest signatures

Always know what you're installing
- And watch your options during the installation

Where's your backup?
- You might need it someday
- Cleaning adware isn't easy

Run some scans
- Malwarebytes

## Bloatware

A new computer or phone
- Includes the OS and important apps

Also includes applications you didn't expect
- And often don't need

Apps are installed by the manufacturer
- You didn't get a choice

Uses valuable storage space
- May also add to overall resource usage
- The system may be slower than expected
- Could open your system to exploits

### Removing Bloatware

Identify and remove
- This may be easier said than done

Use the built-in uninstaller
- Works for most applications

Some apps have their own uninstaller
- That's how bad they are

Third-party uninstallers and cleaners
- Probably not the first option
- Always have a backup

# Other Malware Types

## Keyloggers

Your keystrokes contain valuable information
- Website login URLs, passwords, email messages

Save all of your input
- Send it to the bad guys

Circumvent encryption protections
- Your keystrokes are in the clear

Other data logging
- Clipboard logging, screen logging, instant messaging, search engine queries

### Keylogger in action

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-3.webp)

## Logic Bomb

Waits for a predefined event
- Often left by someone with grudge

Time bomb
- Time or date

User event
- Logic bomb

Difficult to identify
- Difficult to recover if it goes off

### Real-world Logic Bomb

March 19, 2013, South Korea
- Email wit malicious attachment sent to South Korean organizations
- Posed as a bank email
- Trojan installs a malware

March 20, 2013, 2 PM local time
- Malware time-based logic bomb activates
- Storage and master boot record (MBR) deleted, system reboots

```log
Boot device not found.
Please install an Operating System on your hard disk.
```

### Preventing a Logic Bomb

Difficult to recognize
- Each is unique
- No predefined signatures

Process and procedures
- Formal change control

Electronic monitoring
- Alerts on changes
- Host-based intrusion detection, Tripwire, etc.

Constant auditing
- An administrator can circumvent existing systems

## Rootkits

Originally a Unix technique
- The `root` in rootkit

Modifies core system files
- Part of the kernel

Can be invisible to the OS
- Won't see it in the Task Manager

Also, invisible to traditional anti-virus utilities
- If you cannot see it, you cannot stop it

### Finding and Removing Rootkits

Look for the unusual
- Anti-malware scans

Use a remover specific the rootkit
- Usually built after the rootkit is discovered

Secure boot with UEFI
- Security in the BIOS

# Physical Attacks

## Physical Attacks

Old school security
- No keyboard, no mouse, no command line

Many ways to circumvent digital security
- A physical approach must be considered

If you have physical access to a server, you have full control
- An OS can't stop an in-person attack

Door locks keep out the honest people
- There's always a way in

### Brute Force

The physical version
- No password required

Push through the obstruction
- Brawn beats brains

Check your physical security
- Check the windows
- Try the doors

Attackers will try everything
- You should be prepared for anything

### RFID Cloning

RFID is everywhere
- Access badges
- Key fobs

Duplicators are on Amazon
- Less than $50

The duplication process takes seconds
- Read one card
- Copy to another

This is why we have MFA
- Use another factor with the card

### Environmental Attacks

Attack everything supporting the technology
- The operating environment

Power monitoring
- An obvious attack

HVAC (Heating, Ventilation, and Air conditioning) and humidity controls
- Large data centers must be properly cooled

Fire suppression
- Watch for smoke or fire

# Denial of Service

## Denial of Service

Force a service to fail
- Overload the service

Take advantage of a design failure or vulnerability
- Keep your system patched!

Cause a system to be unavailable
- Competitive advantage

Create a smokescreen for some other exploit
- Precursor to a DNS spoofing attack

Doesn't have to be complicated
- Turn off the power

### A "Friendly" DoS

Unintentional DoSing
- It's not always an né'er-do-well

Network DoS
- Layer 2 loop without STP

Bandwidth DoS
- Downloading multi-gigabyte Linux distribution over a DSL line

The water line breaks
- Get a good shop vacuum

### Distributed Denial of Service (DDoS)

Launch an army of computers to bring down a service
- Use all the bandwidth or resources — traffic spike

This is why the attackers have botnets
- Thousands or millions of computers at your command
- At its peak, Zeus botnet infected over 3.6 million PCs
- Coordinated attack

Asymmetric threat
- The attacker may have fewer resources than the victim

### DDoS Reflection and Amplification

Turn your small attack into a big attack
- Often reflected off another device or service

An increasingly common network DDoS technique
- Turn Internet services against the victim

Uses protocols with little (if any) authentication or checks
- NTP, DNS, ICMP
- A common example of protocol abuse

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-4.webp)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-5.webp)

# DNS Attacks

## DNS Poisoning

Modify the DNS server
- Requires some crafty hacking

Modify the client host file
- The host file takes precedent over DNS queries

Send a fake response to a valid DNS request
- Requires a redirection of the original request or the resulting response
- Real-time redirection
- This is an on-path attack

### DNS Spoofing/Poisoning in Action

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-6.webp)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-7.webp)

### Domain Hijacking

Get access to the domain registration, and you have control where the traffic flows
- You don't need to touch the actual servers
- Determines the DNS names and DNS IP addresses

Many ways to get into the account
- Brute-force
- Social engineer the password
- Gain access to the email address that manages the account
- The usual things

Saturday, October 22, 2016, 1 PM
- Domain name registrations of 36 domains were changes
- Brazilian bank
- Desktop domains, mobile domains, and more

Under hacker control for 6 hours
- The attackers became the bank

5 million customers, $27 billion in assets
- Results of the hack have not been publicly released

### URL Hijacking

Make money from your mistakes
- There's a lot of advertising on the Internet

Sell the badly spelled domain to the actual owner
- Sell a mistake

Redirect to a competitor
- Not as common, legal issues

Phishing site
- Looks like the real site, please log in

Infect with a drive-by download
- You've got malware!

### Types of URL Hijacking

Typosquatting/brandjacking
- Take advantage of poor spelling

Outright misspelling
- professormesser.com vs. professormessor.com

A typing error
- professormeser.com

A different phrase
- professormessers.com

Different top-level domain
- professormesser.org