---
draft: false
date: '2025-10-20T11:25:18+05:00'
title: 'Identity and Access Management'
linkTitle: '4.6: Identity and Access Management'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 20
---

## Identity and Access Management (IAM)

Identity lifecycle management
- Every entity (human and non-human) gets a digital identity

Access control
- An entit only get access to what they need

Authentication and authorization
- Entities must prove they are who they claim to be

Identity governance
- Track an entity's resource access
- It may be a regulatory requirement

### Provisioning/De-provisioning User Accounts

The user account creation process
- And the account removal process

Provisioning and de-provisioning occurs for certain events
- Hiring, transfers, promotions, job separation

Account details
- Name, attributes, group permissions, other permissions

An important part of the IAM process
- An initial checkpoint to limit access
- Nobody gets Administrator access

### Permission Assignments

Each entity gets limited permissions
- Just enough to do their job
- Group assignments are common

Storage and files can be private to that user
- Even if another person is using the same computer

No privilege access to the OS
- Specifically not allowed on a user account

### Identity Proofing

I could be anyone
- The IAM process should confirm who I am

Resolution
- Who the system thinks you are

Validation
- Gathering information from the user (password, security questions, etc.)

Verification/Attestation
- Passport, in-person meeting, etc.
- Automated verification is also an option

Gaining Access:
![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-1.webp)

### Single sign-on (SSO)

Provide credentials one time
- Get access to all available or assigned resources
- No additional authentication required

Usually limited by time
- A single authentication can work for 24 hours
- Authenticate again after the timer expires

The underlying authentication infrastructure must support SSO
- Not always an option

### LDAP (Lightweight Directory Access Protocol)

Protocol for reading and writing directories over an IP network
- An organized set of records, like a phone directory

X.500 specification was written by the International Telecommunications Union (ITU)
- They know directories!

DAP ran on the OSI protocol stack
- LDAP is lightweight

LDAP is the protocol used to query and update an X.500 directory
- Used in Windows Active Directory, Apple OpenDirectory, Novell eDirectory, etc.

### X.500 Distinguished Names

`attribute = value pairs`

Most specific attribute is listed first
- This may be similar to the way you already think

`CN=WIDGETWEB`, `OU=Marketing`, `O=Widget`, `L=London`, `ST=London`, `C=GB`, `DC=com`

![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-2.webp)


### X.500 Directory Information Tree

Hierarchical structure
- Builds a tree

Container objects
- Country, organization, organizational units

Leaf objects
- Users, computers, printers, files

![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-3.webp)

### Security Assertion Markup Language (SAML)

Open Standard for authentication and authorization
- You can authenticate through a third party to gain access
- One standard does it all, sort of

Not originally designed for mobile apps
- This has been SAML's largest roadblock

The SAML Authentication Flow:
![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-4.webp)

### OAuth

Authorization framework
- Determines what resources a user will be able to access

Created by Twitter, Google, and many others
- Significant industry support

Not an authentication protocol
- OpenID Connect handles the single sing-on authentication
- OAuth provides authorization between applications

![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-5.webp)

### Federation

Provide network access to others
- Not just employees — Partners, suppliers, customers, etc.
- Provides SSO and more

Third-parties can establish a federated network
- Authenticate and authorize between the two organizations
- Login with your Facebook credentials

The third party must establish a trust relationship
- And the degree of the trust

![](/notes/comptia-sy0-701-security+training-course/20-identity-and-access-management-6.webp)

### Interoperability

Many ways to communicate with an authentication server
- More than a simple login process

Often determined by what is at hand
- VPN concentrator can talk to an LDAP server
- We have an LDAP server

A new app uses OAuth
- Need to allow authentication API access

The interoperability is dependent on the environment
- This is often part of a much larger IAM strategy

## Access Controls

Authorization
- The process of ensuring only authorized rights are exercised
- Policy enforcement
- The process of determining rights
- Policy definition

User receive rights based on Access Control models
- Different business needs or mission requirements


### Least Privilege

Rights and permissions should be set to the bare minimum
- You only get exactly what's needed to complete your objective

All user accounts must be limited
- Applications should run with minimal privileges

Don't allow users to run with administrative privileges
- Limits the scope of malicious behavior

### Mandatory Access Control (MAC)

The OS limits the operation on an object
- Based on security clearance levels

Every object gets a label
- Confidential, secret, top secret, etc.

Labeling of objects uses predefined rules
- The administrator decides who gets access to what security level
- Users cannot change these settings

### Discretionary Access Control (DAC)

Used in most OSes
- A familiar access control model

You create a spreadsheet
- As the owner, you control who has access
- You can modify access at any time

Very flexible access control
- And very weak security

### Role-based Access Control (RBAC)

You have a role in your organization
- Manager, director, team lead, project manager

Administrators provide access based on the role of the user
- Rights are gained implicitly instead of explicitly

On Windows, use Groups to provide role-based access control
- You are in shipping and receiving, so you can use the shipping software
- You are the manager, so you can review shipping logs

Generic term for following rules
- Conditions other than who you are

Access is determined through system-enforced rules
- System administrators, not users

The rule is associated with the object
- System checks the ACLs for that object

Rules examples
- Lab network access is only available between 9 AM and 5 PM
- Only Chrome browsers may complete this web form

### Attribute-based Access Control (ABAC)

Users can have complex relationships to application and data
- Access may be based on many criteria

ABAC can consider many parameters
- A "next-generation" authorization model
- Aware of context

Combine and evaluate multiple parameters
- Resource information, IP address, time of day, desired action, relationship to the data, etc.

### Time-of-day Restrictions

Almost all security devices include a time-of-day option
- Restrict access during certain times or days of the week
- Usually not the only access control

Can be difficult to implement
- Especially in a 24-hour environment

Time-of-day restrictions
- Training room network is inaccessible between midnight and 6 AM
- Conference room access is limited after 8 PM
- R&D databases are only after between 8 AM and 6 PM

## Multifactor Authentication

Prove who you are
- Use different methods
- A memorized password
- A mobile app
- Your GPS location

Factors
- Something you know
- Something you have
- Something you are
- Somewhere you are

There are other factors as well

### Something You Know

Password
- Secret word/phrase, string of characters
- Very common authentication factor

PIN
- Personal Identification Number
- Not typically contained anywhere on a smart card or ATM card

Pattern
- Complete a series of patterns
- Only you know the right format

### Something You Have

Smart card
- Integrates with devices
- May require a PIN

USB security key
- Certificate is on the USB devices

Hardware or software tokens
- Generates pseudo-random authentication codes

Your phone
- SMS a code to your phone


### Something You are

Biometric authentication
- Fingerprints, iris scan, voiceprint

Usually stores a mathematical representation of your biometric
- Your actual fingerprint isn't usually saved

Difficult to change
- You can change your password
- You can't change your fingerprint

Used in very specific situations
- Not foolproof

### Somewhere You are

Provide a factor based on your location
- The transaction only completes if you are in a particular geography

IP address
- Not perfect, but can help provide more info
- Works with IPv4, not so much with IPv6

Mobile device location services
- Geolocation to a very specific area
- Must be in a location that can receive GPS information or near an identified mobile or 802.11 network
- Still not a perfect identifier of location

## Password Security

### Password Complexity and Length

Make your password strong
- Resist guessing or brute-force attack

Increase password entropy
- No single words, no obvious passwords
- Mix upper and lower case letters, numbers, and special characters

Stronger passwords are commonly at least 8 characters
- These requirements change as processing speed gets faster
- Consider a phrase or set of words

### Password Age and Expiration

Password age
- How long since a password was modified 

Password expiration
- Password works for a certain amount of time
- 30 days, 60 days, 90 days, etc.
- After the expiration date, the password doesn't work
- System remembers password history, requires unique passwords

Critical systems might change more frequently
- Every 15 days or every week

### Password Managers

Important to use different passwords for each account
- Remembering all of them would be impractical

Store all of your passwords in a single database
- Encrypted, protected
- Can include multifactor tokens

Built-in, many OSes
- And some browsers

Enterprise password managers
- Centralized management and recovery options

### Passwordless Authentication

Many breaches are due to poor password control
- Weak passwords, insecure implementation

Authenticate without a password
- This solves many password management issues

You may already be passwordless
- Facial recognition, security key, etc.

Passwordless may not be the primary authentication method
- Used with a password or additional factors

### Just-in-time permissions

In many organizations, the IT team is assigned administrator/root elevated account rights
- This would be a great account to attack

Grant admin access for a limited time
- No permanent administrator rights
- The principles of least privilege

A breached user account never has elevated rights
- Narrow the scope of a breach

Request access from a central clearinghouse
- Grants to denies based on predefined security policies

Password vaulting
- Primary credentials are stored in password vault
- The vault controls who get access to credentials

Accounts are temporary
- Just-in-time process creates a time-limited account
- Administrator receives ephemeral credentials
- Primary passwords are never released
- Credentials are used for one session then deleted

