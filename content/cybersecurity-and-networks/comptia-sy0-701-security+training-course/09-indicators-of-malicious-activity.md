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

# Wireless Attacks

## It started as a normal day

Surfing along on your wireless network
- And then you're not

And then it happens again
- and again

You may not be able to stop it
- There's (almost) nothing you can do
- Time to get a long patch cable

Wireless deauthentication
- A significant wireless denial of service (DoS) attack

### 802.11 management frames

802.11 wireless includes a number of management features
- Frames that make everything work
- You never see them

Important for the operation of 802.11 wireless
- How to find access points, manage QoS, associate/disassociate with an access point, etc.

Original wireless standards didn't add protection for management frames
- Sent in the clear, no authentication or validation

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-8.webp)

### Protecting against deauth attacks

IEEE has already addressed the problem
- Updates included with 802.11ac

Some important management frames are encrypted
- Disassociate, deauthenticate, channel switch announcement, etc.
- 

Not everything is encrypted
- Beacons, probes, authentication, association

## Radio Frequency (RF) Jamming

Denial of service
- Prevent wireless communication

Transmit interfering wireless signals
- Decrease the signal-to-noise ratio at the receiving device
- The receiving device can't hear the good signal

Sometimes it's not intentional
- Interference, not jamming
- Microwave oven, fluorescent lights

Jamming is intentional 
- Someone wants your network to not work

### Wireless Jamming

Many types
- Constant, random bits/Constant, legitimate frames
- Data sent at random times — random data and legitimate frames
- Reactive jamming — only when someone else tries to communicate

Needs to be somewhere close
- Difficult to be effective from a distance

Time to go fox hunting
- You'll need the right equipment to hunt down the jam
- Directional antenna, attenuator

# On-path Attacks

## On-path Network Attack 

How can an attacker watch without you knowing?
- Formerly known as man-in-the-middle

Redirects your traffic
- Then passes it on to the destination
- You never know your traffic was redirected

ARP poisoning
- On-path attack on the local IP subnet
- ARP has no security

### ARP Poisoning (Spoofing)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-9.webp)

## On-path Browser Attack

What if the middleman was on the same computer as the victim?
- Malware/Trojan does all the proxy work
- Formerly known as man-in-the-browser

Huge advantages for the attackers
- Relatively easy to proxy encrypted traffic
- Everything looks normal to the victim

The malware in your browser waits for you to log in to your bank
- And cleans you out

# Replay Attacks

## Replay Attacks

Useful information is transmitted over the network
- A crafty hacker will take advantage of this

Need access to the raw network data
- Network tap, ARP poisoning
- Malware on the victim computer

The gathered information may help the attacker
- Replay the data to appear as someone else

This is not an on-path attack
- The actual replay doesn't require the original workstation

### Pass the Hash

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-10.webp)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-11.webp)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-12.webp)

Avoid this type of replay attack with a salt or encryption
- Use a session ID with the password hash to create a unique authentication hash each time

### Browser Cookie and Session IDs

Cookies
- Information stored on your computer by the browser

Used for tracking, personalization, session management
- Not executable, not generally a security risk
    - Unless someone gets access to them

Could be considered be a privacy risk
- Lots of personal data in there

Session IDs are often stored in the cookie
- Maintains sessions across multiple browser sessions

#### Session Hijacking (Sidejacking)

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-13.webp)

### Header Manipulation

Information gathering
- Wireshark, Kismet

Exploits
- Cross-site scripting

Modify header
- Tamper, Firesheep, Scapy

Modify cookie
- Cookies Manager+ (Firefox add-on)

### Prevent Session Hijacking

Encrypt end-to-end
- They can't capture your session ID if they can't see it
- Additional load on the web server (HTTPS)
- Firefox extension: HTTPS Everywhere, Force TLS
- Many sites are now HTTPS-only

Encrypt end-to-somewhere
- At least avoid capture over a local wireless network
- Still in-the-clear for part of the journey
- Personal VPN

> [!INFO]
> Firefox and Chromium based browser now by-default support strict HTTPS configuration policy, you don't need a 3rd-party extension

# Malicious Code

## Exploiting a Vulnerability

An attacker can use many techniques
- Social engineering
- Default credentials
- Misconfiguration

These don't require technical skills
- The door is already unlocked

There are still ways to get into a well-secured system
- Exploit with malicious code
- Knock the pins out of a door hinge

### Malicious Code

The attackers use any opportunity
- The types of malicious code are varied

Many forms
- Executables, scripts, macro viruses, worms, Trojan horses, etc.

Protection comes from different sources
- Anti-malware
- Firewall
- Continuous updates and patches
- Secure computing habits

### Malicious Code Examples

WannaCry ransomware
- Executable exploited a vulnerability in Windows SMBv1
- Arbitrary code execution

British Airways cross-site scripting
- 22 lines of malicious JavaScript code placed on checkout pages
- Information stolen from 380,000 victims

Estonian Central Health Database
- SQL injection
- Breached all healthcare information for an entire country

# Application Attacks

## Application Attacks

### Injection Attacks

Code injection
- Adding your own information into a data stream

Enabled because of bad programming
- The application should properly handle input and output

So many injectable data types
- HTML, SQL, XML, LDAP, etc.

### Buffer Overflows

Overwriting a buffer of memory
- Spills over into other memory area

Developers need to perform bounds checking
- The attackers spend a lot of time looking for openings

Not a simple exploit
- Takes time to avoid crashing things
- Take time to make it do what you want

A really useful buffer overflow is repeatable
- Which means that a system can be compromised

### Replay attack

Useful information is transmitted over the network
- A crafty hacker will take advantage of this

Need to access to the raw network data
- Network tap, ARP poisoning.
- Malware on the victim

The gathered information may help the attacker
- Replay the data to appear as someone else

This is not an on-path attack
- The actual replay doesn't require the original workstation

### Privilege Escalation

Gain higher-level access to a system
- Exploit a vulnerability
- Might be a bug or design flaw

Higher-level access means more capabilities
- This commonly is the highest level access
- This is obviously a concern

These are high-priority vulnerability patches
- You want to get these holes closed very quickly

Horizontal privilege escalation
- User A can access user B resources

### Mitigating Privilege Escalation

Patch quickly
- Fix the vulnerability

Updates anti-virus/anti-malware software
- Block known vulnerabilities

Data Execution Prevention
- Only data in executable areas can run

Address space layout randomization
- Prevent a buffer overrun at a known memory address

#### Elevation of Privilege Vulnerability

CVE-2023-293366
- Win32k Elevation of privilege vulnerability

Win32k Kernel Driver
- Server 2008, 2008 R2, 2012, 2012 R2, 2016
- Windows 10

Attacker would gain SYSTEM privileges
- The highest level access

### Cross-site Request

Cross-site requests are common and legitimate
- You visit professormesser.com
- Your browser loads text from the professormesser.com server
- It loads a video from YouTube
- And pictures from Instagram

HTML on professormesser.com directs requests from your browser
- This is normal and expected
- Most of these are unauthenticated requests

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-14.webp)

### The Client and the Server

Website pages consist of client-side code and server-side code
- Many moving parts

Client-side
- Renders the page on the screen
- HTML, JavaScript

Server-side
- Performs requests from the client
- HTML, PHP
- Transfer money from one account to another
- Post a video on YouTube

### Cross-site Request Forgery

One-click attack, session riding
- XSRF, CSRF (sea surf)

Takes advantage of the trust that a web application has for the user
- The website trusts your browser
- Requests are made without your consent or your knowledge
- Attacker posts a Facebook status on your account

Significant web application development oversight
- The application should have anti-forgery techniques added
- Usually a cryptographic token to prevent a forgery

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-15.webp)

### Directory Transversal

Directory transversal/path transversal
- Read files from a web server that are outside the website's file directory
- Users shouldn't be able to browse the Windows Folder

Web server software vulnerability
- Won't stop users from browsing past the web server root

Web application code vulnerability
- Take advantage of badly written code

# Cryptographic Attacks

## Cryptographic Attacks

You've encrypted data and sent it to another person
- Is it really secure?
- How do you know?

The attacker doesn't have the combination (the key)
- So they break the safe (the cryptography)

Finding ways to undo the security
- There are many potential cryptographic shortcomings
- The problem is often the implementation

### Birthday Attack

In a classroom of 23 students, what is the chance of two students sharing a birthday?
- About 50%
- For a class of 30, the chance is about 70%

In the digital word, this is a hash collision
- A hash collision is the same hash value for two different plaintexts
- Find a collision through brute force

The attacker will generate multiple versions of plaintext to match the hashes
- Protect yourself with a large hash output size

### Collisions

Hash digests are supposed to be unique
- Different input data should not create the same hash

MD5 hash
- Message Digest Algorithm 5
- First published in April 1996

December 2008: Researchers created CA certificate that appeared legitimate when MD5 is checked
- Built other certificates that appeared to be legit and issued by RapidSSL

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-16.webp)

### Downgrade Attack

Instead of using perfectly good encryption, use something that's not so great
- Force the systems to downgrade their security

SSL stripping
- Combines an on-path attack with a downgrade attack
- Difficult to implement, but big returns for the attacker
- Attacker must sit in the middle of the conversation
- Victims browser page isn't encrypted
- Strips the **S** away from HTTPS

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-17.webp)

### Plaintext/Unencrypted Passwords

Some applications store passwords "in the clear"
- No encryption. You can read the stored password
- This is rare, thankfully.

<mark style="background: #FF5582A6;">Do not store passwords as plaintexts</mark>
- Anyone with access to the password file or database has every credential

What to do if your application saves passwords as plaintext
- Get a better application

## Hashing a password

Hashes represent data as a fixed-length string of text 
- A message digest, or "fingerprint"

Will not have a collision (hopefully)
- Different inputs will not have the same hash

One-way trip
- Impossible to recover the original message from the digest
- A common way to store passwords

### A Hash Example

SHA-256 hash
- Used in many applications

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-18.webp)

### The Password File

Different across OSes and applications
- Different hash algorithms

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-19.webp)

### Spraying Attack

Try to log in with an incorrect password
- Eventually you'll be locked out

There are some common passwords
- https://en.wikipedia.org/wiki/List_of_the_most_common_passwords

Attack an account with the top three (or more) passwords
- If they don't work, move to the next account
- No lockouts, no alarms, no alerts

### Brute-force

Try every possible password combination until the hash is matched

This might take some time
- A strong hashing algorithm slows things down

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-20.webp)

Brute-force attacks — Online
- Keep trying the login process
- Very slow
- Most accounts will lock out after a number of failed attempts

Brute-force the hash — Offline
- Obtain the list of users and hashes
- Calculate a password hash, compare it to a stored hash
- Large computational resource requirement

# Indicators of Compromise

## Indicators of Compromise (IOC)

An event that indicates an intrusion
- Confidence is high
- He's calling from inside the house

Indicators
- Unusual amount of network activity
- Change to file hash values
- Irregular international traffic
- Changes to DNS data
- Uncommon login patterns
- Spikes of read requests to certain files

### Account Lockout

Credentials are not working
- It wasn't you this time

Exceeded login attempts
- Account is automatically locked

Account was administratively disabled
- This would be a larger concern

This may be part of a larger plan
- Attacker locks account
- Calls support line to reset the password

### Concurrent Session Usage

It's challenging to be two places at one time
- Laws of Physics

Multiple account logins from multiple locations
- Interactive access from a single user
- You don't have a clone

This can be difficult to track down
- Multiple devices and desktops
- Automated processes

![](/notes/comptia-sy0-701-security+training-course/09-indicators-of-malicious-activity-21.webp)

### Blocked Content

An attacker wants to stay as long as possible
- Your system has been unlocked
- Keep the doors and windows open

There's probably a security patch available
- Time to play keep-away

Blocked content
- Auto-update connections
- Links to security patches
- Third-party anti-malware sites
- Removal tools

### Impossible Travel

Authentication logs can be telling
- Logon and logoff

Login from Omaha, Nebraska, United States
- The company headquarters

Three minutes later, a login from Melbourne, Victoria, Australia
- Alarm bells should be ringing

This should be easy to identify
- Log analysis and automation

### Resource Consumption

Every attacker's action has an equal and opposite reaction
- Watch carefully for significant changes

File transfers use bandwidth
- An unusual spike at 3 AM

Firewall logs show the outgoing transfer
- IP addresses, timeframes

Often the first real notification of an issue
- The attacker may have been here for months

### Resource Inaccessibility

The server is down
- Not responding

Network disruption
- A cover for the actual exploit

Server outage
- Result of an exploit gone wrong

Encrypted data
- A potential ransomware attack begins

Brute force attack
- Locks account access

### Out-of-Cycle Logging

Out-of-Cycle
- Occurs at an unexpected time

OS patch logs
- Occurring outside the normal patch day
- Keep that exploited system safe from other attackers!

Firewall log activity
- Timestamps of every traffic flow
- Protocols and applications used

### Missing logs

Log information is evidence
- Attackers will try to cover their tracks by removing logs

Information is everywhere
- Authentication logs
- File access logs
- Firewall logs
- Proxy logs
- Server logs

The logs may be incriminating
- Missing logs are certainly suspicious
- Logs should be secured and monitored

### Published/Documented

The entire attack and data exfiltration may go unnoticed
- It happens quite often

Company data may be published online
- The attackers post a portion or all data
- This may be in conjunction with ransomware

Raw data may be released without context
- Researchers will try to find the source