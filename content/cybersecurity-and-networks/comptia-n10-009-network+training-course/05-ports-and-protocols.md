---
draft: false
date: '2025-11-05T12:11:56+05:00'
title: 'Ports and Protocols'
linkTitle: '1.4: Ports and Protocols'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 5
---

## Introduction to IP

### A Series of moving Vans

Efficiently move large amounts of data
- Use a shipping truck

The network topology is the road
- Ethernet, DSL, cable system

The truck is the Internet Protocol (IP)
- We have designed the roads for this truck

The boxes hold your data
- Boxes of TCP and UDP

Inside the boxes are more things
- Application information

### IP — Internet Protocol

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-1.webp)

### TCP and UDP

Transported inside of IP
- Encapsulated by the IP protocol

Two ways to move data from place to place
- Different features for different applications

OSI layer 4
- The transport layer

Multiplexing
- Use many applications at the same time
- TCP and UDP

### TCP — Transmission Control Protocol

Connection-oriented
- A formal connection setup and close

"Reliable" delivery
- Recovery from errors
- Can manage out-of-order messages or retransmissions

Flow control
- The receiver can manage how much data is sent

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-2.webp)

### UDP — User Datagram Protocol

Connectionless
- No formal open or close to the connection

"Unreliable" delivery
- No error recovery
- No reordering of data or retransmissions

No flow control
- Sender determines the amount of data transmitted

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-3.webp)

### Speedy delivery

The IP delivery truck delivers from one (IP) address to another (IP) address
- Every house has an address, every computer has an IP address

Boxes arrive at the house/IP address
- Where do the boxes go?
- Each box has a room name

Port is written on the outside box
- Drop the box into the right room

### Lots of Ports

IPv4 sockets
- Server IP address, protocol, server application port number
- Client IP address, protocol, client port number

Non-ephemeral ports — permanent port numbers
- Ports `0` through `1023`
- Usually on a server or service

Ephemeral ports — temporary port numbers
- Ports `1024` through `65,535`

### Port Numbers

TCP and UDP ports can be any number between 0 and 65,535

Most servers (services) use non-ephemeral (not temporary) port numbers
- This isn't always the case
- It's just a number

Port numbers are for communication, not security

Service port numbers need to be "well-known"

TCP port numbers aren't the same as UPD port numbers

Ports on the Network:
![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-4.webp)

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-5.webp)

## Common Ports

### FTP — File Transfer Protocol

Transfers files between systems
- Generic file transfer method
- Not specific to an OS

`tcp/20` (active mode data), `tcp/21` (control)
- Authenticates with a username and password

Full-featured functionality
- List, add, delete, etc.

### SSH — Secure Shell

Text-based console communication

Encrypted communication link - `tcp/22`

### SFTP — Secure FTP

Generic file transfer with security
- Encrypted network communication

Uses the SSH File Transfer Protocol
- `tcp/22`

Provide files system functionality
- Resuming interrupted transfers, directory listings, remote file removal

Uses SSH (port 22)
- SSH isn't just for console communication

### Telnet

Telnet — Telecommunication Network
- tcp/23

Console access
- Similar functionality to SSH

In-the-clear communication
- Not the best choice for production systems

### SMTP — Simple Mail Transfer Protocol

SMTP
- Server to server email transfer
- `tcp/25` (SMTP using plaintext)
- `tcp/587` (SMTP using TLS encryption)

Also used to send mail from a device to a mail server
- Commonly configured on mobile devices and email clients

Other protocols are used for clients to receive email
- IMAP, POP3

### DNS — Domain Name System

Converts names to IP address - `udp/53`
- www.professormesser.com = 162.159.246.164
- Large transfers may use `tcp/53`

These are very critical resources
- Usually multiple DNS servers are in production

### DHCP — Dynamic Host Configuration Protocol

Automated configuration of IP address, subnet mask and other options
- `udp/67` And `udp/68`
- Requires a DHCP server
- Server, appliance, integrated into a SOHO router, etc.

Dynamic/pooled
- IP addresses are assigned in real-time from a pool
- Each system is given a lease, must renew at set intervals

DHCP reservation
- Addresses are assigned by MAC address in DHCP server
- Quickly manage addresses from one location

### TFTP — Trivial File Transfer Protocol

TFTP
- `udp/69`

Very simple file transfer application
- Read files and write files

No authentication
- Not used on highly secure systems

Useful when starting a system
- Transfer configuration files
- Quick and easy

### HTTP and HTTPS

Hypertext Transfer Protocol
- Communication in the browser
- And by other applications

In the clear or encrypted
- SSL (Secure Sockets Layer) or TLS (Transport Layer Security)

| Protocol | Port    | Name                        | Description                              |
| -------- | ------- | --------------------------- | ---------------------------------------- |
| HTTP     | tcp/80  | Hypertext Transfer Protocol | Web server communication                 |
| HTTPS    | tcp/443 | HTTP over TLS or SSL        | Web server communication with encryption | 

### NTP — Network Time Protocol

Switches, routers, firewalls, servers, workstations
- Every device has its own clock
- `udp/123`

Synchronizing the clocks becomes critical 
- Log files, authentication information, outage details

Automatic updates
- No flashing 12:00 lights

Flexible — You control how clocks are updated

Very accurate
- Accuracy is better than 1 millisecond on a local network

### SNMP — Simple Network Management Protocol

Gather statistics from network devices
- `udp/161`

v1 — The original 
- Structured tables
- In-the-clear

v2 — A good step ahead
- Data type enhancements
- Bulk transfers
- Still in-the-clear

v3 — A secure standard
- Message integrity
- Authentication
- Encryption

SNMP traps
- Alerts and notifications from the network devices
- `udp/162`

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-6.webp)

### LDAP/LDAPS

LDAP (Lightweight Directory Access Protocol)
- `tcp/389`
- Store and retrieve information in a network directory

LDAPS (LDAP Secure)
- A non-standard implementation of LDAP over SSL
- `tcp/636`

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-7.webp)

### SMB — Server Message Block

Protocol used by Microsoft Windows
- File sharing, printer sharing
- Also called CIFS (Common Internet File System)

Integrated into the OS
- Access rights integration across systems
- File share publishing
- File locking

Direct over `tcp/445` (NetBIOS-less)
- Direct SMB communication over TCP

### Syslog

Standard for message logging
- Diverse systems, consolidated log
- udp/514

Usually a central log collector
- Integrated into the SIEM
- Security information and Event Manager

You're going to need a lot of disk space
- No, more. More than that.
- Data storage from many devices over an extended timeframe

### Databases

Collection of information
- Many types of data
- One common method to store and query

Structured Query Language (SQL)
- A standard language across database servers
```sql
SELECT * FROM Customers WHERE Last_Name = 'Messer';
```

Microsoft SQL Server
- MS-SQL (Microsoft Structured Query Language)
- `tcp/1433`

![](/notes/comptia-n10-009-network+training-course/05-ports-and-protocols-8.webp)

### RDP — Remote Desktop Protocol

Share a desktop from a remote location over `tcp/3389`
- Connect to an entire desktop or just an application

Remote Desktop Services on many Windows versions
- Clients for Windows, macOS, Linux, Unix, iPhone, and others

### SIP — Session Initiation Protocol

Voice over IP (VoIP) signaling
- `tcp/5060` And `tcp/5061`

Setup and manage VoIP sessions
- Call, ring, play busy signal, hang up

Extend voice communication
- Video conferencing
- Instant messaging
- File transfer etc.

