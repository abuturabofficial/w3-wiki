---
draft: false
date: '2025-09-22T09:31:05+05:00'
title: 'Cryptographic Solutions'
linkTitle: '1.4: Cryptographic Solutions'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 5
---

## Public Key Infrastructure (PKI)

**Policies, procedures, hardware, software, people**
- Digital certificates: create, distribute, manage, store, revoke

**This is a big, big, endeavor**
- Lots of planning

**Also refers to the binding of public keys to people or devices**
- The certificate authority (CA)
- It's all about trust

### Symmetric Encryption

**A single, shared key**
- Encrypt with the key
- Decrypt with the same key
- If it gets out, you'll need another key

**Secret key algorithm**
- A shared secret

**Doesn't scale very well**
- Can be challenging to distribute

**Very fast to use**
- Less overhead than asymmetric encryption
- Often combined with asymmetric encryption

### Asymmetric Encryption

**Public key cryptography**
- Two (or more) mathematically related keys

**Private Key**
- Keep this private

**Public Key**
- Anyone can see this key
- Give it away

**The private key is the only key that can decrypt data encrypted with public key**
- You cannot derive the private key from the public key

### The Key Pair

**Asymmetric encryption**
- Public Key Cryptography

**Key generation**
- Build both the public and private key at the same time
- Lots of randomization
- Large prime numbers
- Lots and lots of math

**Everyone can have the public key**
- Only Alice has the private key

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-1.webp)

**Asymmetric Encryption**

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-2.webp)

### Key Escrow

**Someone else holds your decryption keys**
- Your private keys are in the hands of a 3<sup>rd</sup> Party
- This may be within your own organization

**This can be a legitimate business arrangement**
- A business might need access to employee information
- Government agencies may need to decrypt partner data

**Controversial?**
- Of course
- But may still be required

## Encrypting Data
