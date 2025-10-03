---
draft: false
date: '2025-10-03T09:18:59+05:00'
title: 'Protecting Data'
linkTitle: '3.3: Protecting Data'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 13
---

## Data Types and Classification

### Data Types

Regulated 
- Managed by a third-party
- Government laws and statutes

Trade secret
- An organization's secret formulas
- Often unique to an organization

Intellectual property 
- May be publicly visible
- Copyright and trademark restrictions

Legal information
- Court records and documents, judge and attorney information, etc.
- PII and other sensitive details
- Usually stored in many systems

Financial information
- Internal company financial details
- Customer finances
- Payment records
- Credit card data, bank records, etc.

Human-readable
- Humans can understand the data
- Very clear and obvious

Non-human readable
- Not easily understood by humans
- Encoded data
- Barcodes
- Images

Some formats are a hybrid
- CSV, XML, JSON, etc.

### Classifying Sensitive Data

Not all data has the same level of categorization
- License tag numbers vs. health records

Different levels require different security and handling
- Additional permissions
- A different process to view
- Restricted network access

### Data Classifications

Proprietary
- Data that is the property of an organization
- May also include trade secrets
- Often data unique to an organization

PII — Personally Identifiable Information
- Data that can be used to identify an individual
- Name, data of birth, mother's maiden name, biometric information

PHI — Protected Health Information
- Health information associated with an individual
- Health status, health care records, payments for health care, and much more

Sensitive
- Intellectual property, PII, PHI

Confidential
- Very sensitive, must be approved to view

Public/Unclassified
- No restrictions on viewing the data

Private/Classified/Restricted
- Restricted access, may require an NDA

Critical
- Data should always be available

## States of Data

### Data at rest

The data is on a storage device
- Hard drive, SSD, flash drive, etc.

Encrypt the data
- Whole disk encryption
- Database encryption
- File or folder-level encryption

Apply permissions
- Access control lists
- Only authorized users can access the data

### Data in transit

Data transmitted over the network
- Also called data in-motion

Not much protection as it travels
- Many switches, routers, devices

Network-based protection
- Firewall, IPS

Provide transport encryption
- TLS (Transport Layer Security)
- IPsec (Internet Protocol Security)

### Data in use

Data is actively processing in memory
- System RAM, CPU registers and cache

The Data is almost always decrypted
- Otherwise, you couldn't do anything with it

The attackers can pick the decrypted information out of RAM
- A very attractive option

Target Corp. breach — November 2013
- 110 million credit cards
- Data in-transit encryption and data at-rest encryption
- Attackers picked the credit card numbers out of the point-of-sale RAM

### Data Sovereignty

Data sovereignty
- Data that resides in a country is subject to the laws of that country
- Legal monitoring, court orders, etc.

Laws may prohibit where data is stored
- GDPR (General Data Protection Regulation)
- Data collected on EU citizens must be stored in the EU
- A complex mesh of technology and legalities

Where is your data stored?
- Your compliance laws may prohibit moving data out of the country

### Geolocation

Location details
- Tracks within a localized area

Many ways to determine location
- 802.11, mobile providers, GPS

Can be used to manage data access
- Prevent access from other countries

Limit administrative tasks unless secure area is used
- Permit enhanced access when inside the building

## Protecting Data

### Geographic Restrictions

Network location
- Identify based on IP subnet
- Can be difficult with mobile devices

Geolocation — determine a user's location
- GPS — mobile devices, very accurate
- 802.11 wireless, less accurate
- IP address, not very accurate

Geo-fencing
- Automatically allow or restrict access when the user is in a particular location
- Don't allow this app to run unless you're near the office

A primary job task
- An organization is out of business without data

Data is everywhere
- ON a storage drive, on the network, in a CPU

Protecting the data
- Encryption, security policies

Data permissions
- Not everyone has the same access

### Encryption

Encode information into unreadable data
- Original information is plaintext, encrypted form is ciphertext

This is a two-way street
- Convert between one and the other
- IF you have the proper key

Confusion
- The encrypted data is drastically different from the plaintext

![](/notes/comptia-sy0-701-security+training-course/13-protecting-data-1.webp)

### Hashing

Represent data as a short string of text
- A message digest, a fingerprint

One-way trip
- Impossible to recover the original message from the digest
- Used to store passwords/confidentiality

Verify a downloaded document is the same as the original
- Integrity

Can be a digital signature
- Authentication, non-repudiation, and integrity

Will not have a collision (hopefully)
- Different messages will not have the same hash

![](/notes/comptia-sy0-701-security+training-course/13-protecting-data-2.webp)

### Obfuscation

Obfuscate
- Make something normally understandable very difficult to understand

Take perfectly readable code and turn it into nonsense
- The developer keeps the readable code and gives you the chicken scratch
- Both sets of code perform exactly the same way

Helps prevent the search for security holes
- Makes it more difficult to figure out what's happening
- But not impossible

![](/notes/comptia-sy0-701-security+training-course/13-protecting-data-3.webp)

### Masking

A type of obfuscation
- Hide some original data

Protects PII
- And other sensitive data

May only be hidden from view
- The data may still be intact in storage
- Control the view based on permissions

Many techniques
- Substituting, shuffling, encrypting, masking out, etc.

![](/notes/comptia-sy0-701-security+training-course/13-protecting-data-4.webp)

### Tokenization

Replace sensitive data with a non-sensitive placeholder

- SSN 266-12-1112 is now 691-618539

Common with credit card processing
- Use a temporary token during payment
- An attacker capturing the card numbers can't use them later

This isn't encryption or hashing
- The original data and token aren't mathematically related
- No encryption overhead

![](/notes/comptia-sy0-701-security+training-course/13-protecting-data-5.webp)

### Segmentation

Many organizations use a single data source
- One large database

One breach puts all the data at risk
- You're making it easy for the attacker

Separate the data
- Store it in different locations

Sensitive data should have stronger security
- The most sensitive data should be the most secure

### Permission Restrictions

Control access to an account
- It's more than jut username and password
- Determine what policies are best for an organization

The authentication process
- Password policies
- Authentication factor policies
- Other considerations

Permissions after login
- Another line of defense
- Prevent unauthorized access

