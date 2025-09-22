---
draft: false
date: '2025-09-20T09:09:39+05:00'
title: 'Security Concepts'
linkTitle: '1.2: Security Concepts'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 3
---

## The CIA Triad
- **Combination of principles**
    - The fundamentals of security
    - Sometimes referenced as **the AIC Triad**

1. **Confidentiality**
    - Prevent disclosure of information to unauthorized individuals or systems
2. **Integrity**
    - Messages can't be modified without detection
3. **Availability**
    - Systems and networks must be up and running


![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-1.webp)

### 1. Confidentiality

- **Certain information should only be known to certain people**
    - Prevent unauthorized information disclosure
- **Encryption**
    - Encode messages so only certain people can read it
- **Access Controls**
    - Selectively restrict access to a resource
- **Two-factor Authentication**
    - Additional confirmation before information is disclosed

### 2. Integrity

- **Data is stored and transferred as intended**
    - Any modification to the data would be identified.
- **Hashing**
    - Map data of an arbitrary length to data of a fixed length
- **Digital Signatures**
    - Mathematical scheme to verify the integrity of data
- **Certificates**
    - Combine with a digital signature to verify an individual
- **Non-repudiation**
    - Provides proof of integrity, can be asserted to be genuine!

### 3. Availability

- **Information is accessible to authorized users**
    - Always at your fingertips
- **Redundancy**
    - Build services that will always be available
- **Fault Tolerance**
    - System will continue to run, even when a failure occurs
- **Patching**
    - Stability
    - Close security holes

## Non-repudiation

- **You can't deny what you have said**
    - There is no taking it back
- **Signs a contract**
    - Your signature adds non-repudiation
    - You really did sign the contract
    - Others can see your signature
- **Adds a different perspective for cryptography**
    - Proof of integrity
    - Proof of origin, with high assurance of authenticity

### Proof of integrity

- **Verify data doesn't change**
    - The data remains accurate and consistent
- **In cryptography, we use a hash**
    - Represents data as a short string of text
    - A message digest, a fingerprint
- **If the data changes, the hash changes**
    - If the person changes, you get a different fingerprint
- **Does not necessarily associate data with an individual**
    - Only tells you if the data has changed

### Proof of Origin

- **Prove the message was not changed**
    - Integrity
- **Prove the source of the message**
    - Authentication
- **Make sure the signature isn't fake**
    - Non-repudiation
- **Sign with the private key**
    - The message doesn't need to be encrypted
    - Nobody else can sign this (obviously)
- **Verify with the public key**
    - Any change to the message will invalidate the signature


### Verifying a Digital Signature

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-2.webp)

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-3.webp)

## Authentication, Authorization, and Accounting (AAA) Framework

- **Identification**
    - This is who you claim to be
    - Usually your username
- **Authentication**
    - Prove you are who you say you are
    - Password and other authentication factors
- **Authorization**
    - Based on your identification and authentication, what access do you have?
- **Accounting**
    - Resources used: Login time, data sent and received, logout time

#### Authenticating People

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-4.webp)

### Authenticating Systems

- **You have to manage many devices**
    - Often devices that you will never physically see
- **A system can't type a password**
    - And you may not want to store one
- **How can you truly authenticate a device**
    - Put a digitally signed certificate on the device
- **Other business processes rely on the certificate**
    - Acess to the VPN from authorized devices
    - Management software can validate the end device

### Certificate Authentication

- **An organization has a trusted Certificate Authority (CA)**
    - Most organizations maintain their own CAs
- **The organization creates a certificate for a device**
    - And digitally signs the certificate with the organization's CA
- **The certificate can now be included on a device as an authentication factor**
    - The CA's digital signature is used to validate the certificate

#### Certificate-based Authentication

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-5.webp)

### Authorization Models

- **The user or device has now authenticated**
    - To what do they now have access?
    - Time to apply an authorization model
- **Users and services ⇾ data and applications**
    - Associating individual users to access rights doesn't scale
- **Put an authorization model in the middle**
    - Define by Roles, Organizations, Attributes, etc.

### No Authorization Model

- **A simple relationship**
    - User ⇾ Resource
- **Some issues with this method**
    - Difficult to understand why an authorization may exist
    - Doesn't scale

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-6.webp)

#### Using an Authorization Model

- **Add an abstraction**
    - Reduce complexity
    - Create a clear relationship between the user and the resource
- **Administration is streamlined**
    - Easy to understand the authorizations
    - Support any number of users or resources

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-7.webp)

## Gap Analysis

- **Where you are compared with where you want to be**
    - The "gap" between the two
- **This may require extensive research**
    - There is a lot to consider
- **This can take weeks or months**
    - An extensive study with numerous participants
    - Get ready for emails, data gathering, and technical research


### Choosing the Framework

- **Get the baseline of employees**
    - Formal experience
    - Current training
    - Knowledge of security policies and procedures
- **Examine the current processes**
    - Research existing IT systems
    - Evaluate existing security policies

### Compare and Contrast

- **The comparison**
    - Evaluate existing systems
- **Identify weakness**
    - Along with the most effective processes
- **A detailed analysis**
    - Examine broad security categories
    - Break those into smaller segments

### The Analysis and Report

- **The final comparison**
    - Detailed baseline objectives
    - A clear view of the current state
- **Need a path to get from the current security to the goal**
    - This will almost certainly include time, money, and lots of change control
- **Time to create the gap analysis report**
    - A formal description of the current state
    - Recommendations for meeting the baseline

### Gap Analysis Overview

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-8.webp)

## Zero Trust

- **Many networks are relatively open on the inside**
    - Once you're through the firewall, there are few security controls
- **Zero trust is a holistic approach to network security**
    - Covers every device, every process, every person
- **Everything must be verified**
    - Nothing is inherently trusted
    - Multi-factor authentication, encryption, system permissions, additional firewalls, monitoring, and analytics etc.

### Planes of Operation

- **Split the network into functional planes**
    - Applies to physical, virtual, and cloud components
- **Data Plane**
    - Process the frames, packets, and network data
    - Processing, forwarding, trunking, encrypting, NAT
- **Control Plane**
    - Manages the actions of the data plane
    - Define policies and rules
    - Determine how packets should be forwarded
    - Routing tables, session tables, NAT tables

### Extend the Physical Architecture

- Separate into functional tasks
    - Incorporate into hardware or software

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-9.webp)

### Controlling Trust

- **Adaptive Identity**
    - Consider the source and the requested resources
    - Multiple risk indicators — relationship to the organization, physical location, type of connection, IP address, etc.
    - Make the authentication stricter, if needed
- **Threat Scope Reduction**
    - Decrease the number of possible entry points
- **Policy-driven access control**
    - Combine the adaptive identity with a predefined set of rules

### Security Zone

- **Security is more than a one-to-one relationship**
    - Broad categorization provide a security-based foundation
- **Where are you coming from and where are you going**
    - Trusted, untrusted
    - Internal network, external network
    - VPN 1, VPN 5, VPN 11
    - Marketing, IT, Accounting, HR
- **Using the zones may be enough by itself to deny access**
    - For example, `Untrusted` to `Trusted` zone traffic
- **Some zones are implicitly trusted**
    - For example, `Trusted` to `Internal` zone traffic

### Policy Enforcement Point

- **Subjects and systems**
    - End users, applications, non-human entities
- **Policy enforcement point (PEP)**
    - The gatekeeper
- **Allow, monitor, and terminate connections**
    - Can consist of multiple components working together

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-10.webp)

### Applying Trust in the Planes

- **Policy Decision Point**
    - There's a process for making an authentication decision
- **Policy Engine**
    - Evaluates each access decision based on policy and other information sources
    - Grant, deny, or revoke
- **Policy Administration**
    - Communicates with the Policy Enforcement Point
    - Generates access tokens or credentials
    - Tells PEP to allow or disallow access

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-11.webp)

### Zero Trust Across Planes

![](/notes/comptia-sy0-701-security+training-course/03-security-concepts-12.webp)

## Physical Security
 
### Barricades/ Bollards

- **Prevent access**
    - There are limits to the prevention
- **Channel people through a specific access point**
    - And keep out other things
    - Allow people, prevent cars and trucks
- **Identify safety concerns**
    - And prevent injuries
- **Can be used to an extreme**
    - Concrete barriers/bollards
    - Moats (Water ditch around the facility)

### Access Control Vestibules

- **All doors normally unlocked**
    - Opening one door causes others to lock
- **All doors normally locked**
    - Unlocking one door prevents others from being unlocked
- **One door open/others locked**
    - When one is open, the other cannot be unlocked
- **One at a time, controlled groups**
    - Managed control through an area

### Fencing

- **Build a perimeter**
    - Usually very obvious
    - May not be what you're looking for
- **Transparent or opaque**
    - See through fence (or not)
- **Robust**
    - Difficult to cut the fence
- **Prevent Climbing**
    - Razor wire
    - Build it high

### Video Surveillance

- CCTV (Closed circuit television)
    - Can replace physical guards
- **Camera features are important**
    - Motion recognition can alarm and alert when something moves
    - Object detection can identify a license plate or person's face
- **Often many cameras**
    - Networked together and recorded over time

### Guards and Access Badges

- **Security Guard**
    - Physical protection at the reception area of a facility
    - Validate identification of existing employees
- **Two-person integrity/control**
    - Minimize exposure to an attack
    - No single person has access to a physical asset
- **Access badge**
    - Picture, name, other details
    - Must be worn at all times
    - Electronically logged

### Lighting

- **More light means more security**
    - Attackers avoid the light
    - Easier to see when lit
    - Non IR cameras can see better
- **Specialized design**
    - Consider overall light levels
    - Lighting angles may be important
- **Avoid shadows and glare**

### Sensors

- **Infrared**
    - Detects infrared radiation in both light and dark
    - Common in motion detectors
- **Pressure**
    - Detects a change in force
    - Floor and window sensors
- **Microwave**
    - Detects movement across large areas
- **Ultrasonic**
    - Send ultrasonic signals, receive reflected sound waves
    - Detect motion, collision detection etc.

## Deception and Disruption

### Honeypots

- **Attract the bad guys**
    - And trap them there
- **The "attacker" is probably a machine**
    - Makes for interesting recon
- **Honeypots**
    - Create a virtual world to explore
- **Many options**
    - Most are open source and available to download
- **Constant battle to discern the real from the fake**

### Honeynets

- **A real network includes more than a single device**
    - Servers, workstations, routers, switches, firewalls
- **Honeynets**
    - Build a larger deception network with one or more honeypots
- **More than one source of information**
    - Stop spammers — https://projecthoneypot.org

### Honeyfiles

- **Attract the attackers with more honey**
    - Create files with fake information
    - Something bright and shiny
- **Honeyfiles**
    - Bait for the honeynet (passwords.txt)
    - Add many honeyfiles to files shares
- **An alert is sent if the file is accessed**
    - A virtual bear trap

### Honeytokens

- **Track the malicious actors**
    - Add some traceable data to the honeynet
    - If the data is stolen, you will know where it came from
- **API Credentials**
    - Doesn't actually provide access
    - Notifications are sent when used
- **Fake email addresses**
    - Add it to a contact list
    - Monitor the internet to see who posts it
- **Many other honeytoken examples**
    - Database records, browser cookies, web page pixels