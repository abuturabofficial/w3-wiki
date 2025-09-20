---
draft: false
date: '2025-09-20T09:09:39+05:00'
title: 'The CIA Triad'
linkTitle: '1.2: The CIA Triad'
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


![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-1.webp)

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

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-2.webp)

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-3.webp)

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

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-4.webp)

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

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-5.webp)

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

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-6.webp)

#### Using an Authorization Model

- **Add an abstraction**
    - Reduce complexity
    - Create a clear relationship between the user and the resource
- **Administration is streamlined**
    - Easy to understand the authorizations
    - Support any number of users or resources

![](/notes/comptia-sy0-701-security+training-course/03-the-cia-triad-7.webp)

## Gap Analysis
