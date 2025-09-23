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

### Encrypting Stored Data

**Protect data on storage devices**
- SSD, hard drive, USB drive, cloud storage, etc.
- This is data at rest

**Full-disk and partition/volume encryption**
- BitLocker, FileVault, etc.

**File encryption**
- EFS (Encrypting File System), third-party utilities

### Database Encryption

**Protecting stored data**
- And the transmission of that data

**Transparent encryption**
- Encrypt all database information with a symmetric key

**Record-level encryption**
- Encrypt individual columns
- Use separate symmetric keys for each column

Example Database:

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-3.webp)

You can encrypt the entire database

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-4.webp)

But this adds the extra overhead for database search and lookup. We have to decrypt the data every time we need to pull something from it.

One way to avoid, the overhead is to encrypt only the sensitive portion of the data, leaving rest as unencrypted.

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-5.webp)

### Transport Encryption

**Protect data traversing the network**
- You are probably doing this now

**Encrypting in the application**
- Browsers can communicate using HTTPS

**VPN (virtual private network)**
- Encrypts all data transmitted over the network, regardless of the application
- Client-based VPN using SSL/TLS
- Site-to-site VPN using IPsec

### Encryption Algorithms

**There are many, many ways to encrypt data**
- The proper "formula" must be used during encryption and decryption

**Both sides decide on the algorithm before encrypting the data**
- The details are often hidden from the end user

**There are advantages and disadvantages between algorithms**
- Security level, speed, complexity of implementation, etc.

### Encryption Algorithm Comparison

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-6.webp)


### Cryptographic Keys

**There's very little that is not known about the cryptographic process**
- The algorithm is usually a known entity
- The only thing you don't know is the key

**The key determines the output**
- Encrypted data
- Hash value
- Digital signature

**Keep your key private**
- It's the only thing protecting your data

### Key Lengths

**Larger keys tend to be more secure**
- Prevent brute-force attacks
- Attackers can try every possible key combination

**Symmetric encryption**
- 128-bit or larger symmetric keys are common
- These numbers get larger and larger as time goes on

**Asymmetric encryption**
- Complex calculations of prime numbers
- Larger keys than symmetric encryption
- Common to see key lengths of 3072 bits or larger

### Key Stretching

**A weak key is a weak key**
- By itself, it's not very secure

**Make a weak key stronger by performing multiple processes**
- Hash a password. Hash the hash of the password. And continue...
- Key stretching, key strengthening

**Brute force attacks would require reversing each of those hashes**
- The attacker has to spend much more time, even though the key is small

## Key Exchange

**A logistical challenge**
- How do you share an encryption key across an insecure medium without physically transferring the key?

**Out-of-band key exchange**
- Don't send the symmetric key over the network
- Telephone, courier, in-person, etc.

**In-band key exchange**
- It's on the network
- Protect the key with additional encryption
- Use asymmetric encryption to deliver a symmetric key

### Real-time Encryption/Decryption

**There is a need for fast security**
- Without compromising the security part

**Share a symmetric session key using asymmetric encryption**
- Client encrypts a random (symmetric) key with a server's public key
- The server decrypts this shared key and uses it to encrypt data
- This is the session key

**Implement session keys carefully**
- Need to be changed often (ephemeral keys)
- Need to be unpredictable

### Symmetric Key from Asymmetric Keys

**Use public and private key cryptography to create a symmetric key**
- Math is powerful

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-7.webp)

## Encryption Technologies

### Trusted Platform Module (TPM)

**A specification for cryptographic functions**
- Cryptography hardware on a device

**Cryptographic processor**
- Random number generator, key generators

**Persistent Memory**
- Unique keys burned in during manufacturing

**Versatile memory**
- Storage keys, hardware configuration information
- Securely store BitLocker keys

**Password protected**
- No dictionary attacks

### Hardware Security Module (HSM)

**Used in large environments**
- Clusters, redundant power
- Securely store thousands of cryptographic keys

**High-end cryptographic hardware**
- Plug-in card or separate hardware device

**Key backup**
- Secure storage in hardware

**Cryptographic accelerators**
- Offload that CPU overhead from other devices

### Key Management System

**Services are everywhere**
- On-premises, cloud-based
- Many keys for many services

**Manage all keys from a centralized manager**
- Often provided as third-party software
- Separate the encryption keys from the data

**All key management from one console**
- Create keys for a specific service or cloud provider (SSL/TLS, SSH, etc.)
- Associate keys with specific users
- Rotate keys on regular intervals
- Log key use and important events

### Keeping Data Private

**Our data is located in many places**
- Mobile phones, cloud, laptops, etc.
- The most private data is often physically closest to us

**Attackers are always finding new techniques**
- It's a race to stay one step ahead

**Our data is changing constantly**
- How do we keep this data protected?

### Secure Enclave

**A protected area of our secrets**
- Often implemented as a hardware processor
- Isolated from the main processor
- Many technologies and names

**Provides extensive security features**
- Has its own boot ROM
- Monitors the system boot process
- True random number generator
- Real-time memory encryption
- Performs AES encryption in hardware
- And more...

## Obfuscation

**The process of making something unclear**
- It's now much more difficult to understand

**But it's not impossible to understand**
- If you know how to read it

**Hid information in plain sight**
- Store payment information without storing a credit card number

**Hide information inside an image**
- Steganography

### Steganography

**Greek for "concealed writing"**
- Security through obscurity

**Message is invisible**
- But it's really there

**The covertext**
- The container document or file

#### Common Steganography Techniques

**Network based**
- Embed messages in TCP packets

**Use an image**
- Embed the message in the image itself

**Invisible watermarks**
- Yellow dots on printers

### Other Steganography Types

**Audio steganography**
- Modify the digital audio file
- Interlace a secret message within the audio
- Similar techniques to image steganography

**Video steganography**
- A sequence of images
- Use image steganography on a larger scale
- Manage the signal-to-noise ratio
- Potentially transfer much more information

### Tokenization

**Replace sensitive data with a non-sensitive placeholder**
- SSN 266-12-1112 is no 691-618539

**Common with credit card processing**
- Use a temporary token during payment
- An attacker capturing the card numbers can't use them later

**This isn't encryption or hashing**
- The original data and token aren't mathematically related

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-8.webp)

### Data Masking

**Data Obfuscation**
- Hide some original data

**Protects PII**
- And other sensitive data

**May only be hidden from view**
- The data may still be intact in storage
- Control the view based on permissions

**Many techniques**
- Substituting, shuffling, encrypting, masking out, etc.

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-9.webp)

## Hashing and Digital Signatures

### Hashes

**Represent data as a short string of text**
- A message digest, a fingerprint

**One-way trip**
- Impossible to recover the original message from the digest
- Use to store passwords/confidentiality

**Verify a downloaded document is the same as the original**
- Integrity

**Can be a digital signature**
- Authentication, non-repudiation, and integrity

### Collision

**Hash functions**
- Take an input of any size
- Create a fixed size string
- Message digest, checksum

**The hash should be unique**
- Different inputs should never create the same hash
- If they do, it's a collision

**MD5 has a collision problem**
- Found in 1996
- Don't use MD5 for anything important

### Practical Hashing

**Verify a downloaded file**
- Hashes may be provided on the download site
- Compare the downloaded files hash with the posted hash value

**Password Storage**
- Instead of storing the password, store a salted hash
- Compare hashes during the authentication process
- Nobody ever knows your actual password

### Adding Some Salt

**Salt**
- Random data added to a password when hashing

**Every user gets their own random salt**
- The salt is commonly stored with the password

**Rainbow tables won't work with salted hashes**
- Additional random value added to the original password

**This slows down the brute force process**
- It doesn't completely stop the reverse engineering

#### Salting the Hash

**Each user gets a different random hash**
- The same password creates a different hash

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-10.webp)

### Digital Signature

**Prove the message was not changed**
- Integrity

**Prove the source of the message**
- Authentication

**Make sure the signature isn't fake**
- Non-repudiation

**Sign with the private key**
- The message doesn't need to be encrypted
- Nobody else can sign this (obviously)

**Verify with the public key**
- Any change in the message will invalidate the signature

#### Creating a Digital Signature

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-11.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-12.webp)

## Blockchain Technology

**A distributed ledger**
- Keep track of transaction

**Everyone on the blockchain network maintains the ledger**
- Records and replicates to anyone and everyone

**Many practical applications**
- Payment processing
- Digital identification
- Supply chain monitoring
- Digital Voting

### The Blockchain Process

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-13.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-14.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-15.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-16.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-17.webp)

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-18.webp)

## Certificates

### Digital Certificates

**A public key certificate**
- Binds a public key with a digital signature
- And other details about the keyholder

**A digital signature adds trust**
- PKI uses Certificate Authorities for additional trust
- Web of Trust adds other users for additional trust

**Certificate creation can be built into the OS**
- Part of Windows Domain services
- Many 3rd-party options

### What's in a digital Certificate?

**X.509**
- Standard format

**Certificate Details**
- Serial number
- Version
- Signature algorithm
- Issuer
- Name of the cert holder
- Public key
- And more...

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-19.webp)

### Root of Trust

**Everything associated with IT security requires trust**
- A foundational characteristic

**How to build trust from something unknown?**
- Someone/something trustworthy provides their approval

**Refer to the root of trust**
- An inherently trusted component
- Hardware, software, firmware, or other component
- Hardware security module (HSM), Secure Enclave, Certificate Authority, etc.

### Certificate Authorities

**You connect to a random website**
- Do you trust it?

**Need a good way to trust an unknown entity**
- Use a trusted third-party
- An authority

**Certificate Authorization (CA) has digitally signed the website certificate**
- You trust the CA, therefore you trust the website
- Real-time verification

### Third-party Certificate Authorities

**Built-in to your browser**
- Any browser

**Purchase your website certificate**
- It will be trusted by everyone's browser

**CA is responsible for vetting the request**
- They will confirm the certificate owner
- Additional verification information may be required by the CA

### Certificate Signing Requests

**Create a key pair, then send the public key to the CA to be signed**
- A certificate signing request (CSR)

**The CA validates the request**
- Confirms DNS emails and website ownership

**CA digitally signs the cert**
- Returns to the applicant

![](/notes/comptia-sy0-701-security+training-course/05-cryptographic-solutions-20.webp)

### Private Certificate Authorities

**You are your own CA**
- Build it in-house
- Your devices must trust the internal CA

**Needed for medium-to-large organization**
- Many web servers and privacy requirements

**Implement as part of your overall computing strategy**
- Windows Certificate Services, OpenCA

### Self-signed Certificates

**Internal certificates don't need to be signed by a public CA**
- Your company is the only one going to use it
- No need to purchase trust for devices that already trust you

**Build your own CA**
- Issue your own certificates signed by your own CA

**Install the CA certificate/trusted chain on all devices**
- They will now trust any certificate signed by your internal CA
- Works exactly like a certificate you purchased

### Wildcard Certificates

**Subject Alternative Name (SAN)**
- Extension to an X.509 certificate
- Lists additional identification information
- Allows a certificate to support many domains

**Wildcard domain**
- Certificates are based on the name of the server
- A wildcard domain will apply to all server names in the domain

### Key Revocation

**Certificate Revocation List (CRL)**
- Maintained by the CA
- Can contain many revocations in a large file

**Many reasons**
- Changes all the time

**April 2014 — CVE-2014-0160**
- Heartbleed
- OpenSSL flaw put the private key of affected web servers at risk
- OpenSSL was patched, every web server certificate was replaced
- Older certificates were moved to the CRL

### OCSP Stapling

**Online Certificate Status Protocol**
- Provides scalability for OCSP checks

**The CA is responsible for responding to all client OCSP requests**
- This may not scale well

**Instead, have the certificate holder verify their own status**
- Status information is stored on the certificate holder's server

**OCSP status is "stapled" into the SSL/TLS handshake**
- Digitally signed by the CA

### Getting Revocation Details to the Browser

**OCSP (Online Certificate Status Protocol)**
- The browser can check certificate revocation

**Message usually sent to an OCSP responder via HTTP**
- Easy to support over Internet links
- More efficient than downloading a CRL

**Not all browsers/apps support OCSP**
- Early Internet Explorer versions didn't support OCSP
- Some support OCSP, but don't bother checking