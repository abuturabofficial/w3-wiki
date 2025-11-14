---
draft: false
date: '2025-11-11T11:30:38+05:00'
title: 'Ipv4 Addressing'
linkTitle: '1.7: Ipv4 Addressing'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 8
---

## Binary Math

A bit — a zero or a one
- One digit. Off or on. Cold or hot. 0 or 1.

A byte — Eight bits
- Often called an "octet" to avoid ambiguity

A binary-to-decimal conversion chart

| 1024 | 512 | 256 | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0    | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0    |


### Binary to Decimal

What is binary `00000010` in decimal?
![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-1.webp)

What is binary `10000010` in decimal?
![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-2.webp)

What is binary `11111111` in decimal?
![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-3.webp)

### Decimal to Binary Conversion

What is decimal 154 in binary?
![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-4.webp)

### More bits, more addresses

More bits, more addresses:
![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-5.webp)

Power of two
- Useful for binary calculations and subnetting

| 2<sup>12</sup> | 2<sup>11</sup> | 2<sup>10</sup> | 2<sup>9</sup> | 2<sup>8</sup> | 2<sup>7</sup> | 2<sup>6</sup> | 2<sup>5</sup> | 2<sup>4</sup> | 2<sup>3</sup> | 2<sup>2</sup> | 2<sup>1</sup> | 2<sup>0</sup> |
| -------------- | -------------- | -------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 4,096          | 2,048          | 1,024          | 512           | 256           | 128           | 64            | 32            | 16            | 8             | 4             | 2             | 1             | 

## IPv4 Addressing

### Networking with IPv4

IP Address, e.g., `192.168.1.165`
- Every device needs a unique IP address

Subnet mask, e.g., `255.255.255.0`
- Used by the local device to determine what subnet it's on
    - The subnet mask isn't (usually) transmitted across the network
    - You will ask for the subnet mask all the time

Default gateway, e.g., `192.168.1.1`
- The router that allows you to communicate outside your local subnet
- The default gateway must be an IP address on the local subnet

### Special IPv4 Addresses

Loopback address
- An address to yourself
- Ranges from `127.0.0.1` through `127.255.255.254`
- An easy way to self-reference (ping `127.0.0.1`)

Reserved addresses
- Set aside for future use or testing
- `240.0.0.1` through `254.255.255.254`
- All "Class E" addresses

Virtual IP addresses (VIP)
- Not associated with a physical network adapter
- Virtual machine, internal router address

### IPv4 addresses

Internet Protocol version 4
- OSI Layer 3 address

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-6.webp)

Since one byte is 8 bits, the maximum decimal value for each byte is 255

### DHCP

IPv4 address configuration used to be a manual process
- IP address, subnet mask, gateway, DNS servers, NTP servers, etc.

Dynamic Host Configuration Protocol
- Provides automatic address and IP configuration for almost all devices

### Automatic Private IP Addressing (APIPA)

A link-local address
- Can only communicate to other local devices
- No forwarding by routers

IETF has reserved `169.254.0.1` through `169.254.255.254`
- First and last 256 addresses are reserved
- Functional block of `169.254.1.0` through `169.254.1.0`

Automatically assigned
- Uses ARP to confirm the address isn't currently in use

### The IPv4 address problem

There are far more devices than IPv4 addresses
- This Internet thing could be big

The use and registration of IP address ranges is problematic
- Unused and non-continuous address blocks
- Complete depletion of available addresses

### Private IP address ranges

More public IP addresses
- More Internet connectivity

Huge private IP address ranges
- Properly design and scale large networks

Private IP addresses are not Internet-routable
- But can be routed internally
- Use NAT for everything else

Defined in RFC 1918
- Request for Comment

### Public addresses vs. Private addresses

RFC 1918 private IPv4 addresses

| IP address                    | Number of addresses | Classful description    | Largest CIDR block (subnet mask) | Host ID size |
| ----------------------------- | ------------------- | ----------------------- | -------------------------------- | ------------ |
| 10.0.0.0–10.255.255.255       | 16,777,216          | single class A          | 10.0.0.0/8 (255.0.0.0)           | 24 bits      |
| 172.16.0.0–172.31.255.255   | 1,048,576           | 16 contiguous class Bs  | 172.16.0.0/12 (255.240.0.0)      | 20 bits      |
| 192.168.0.0–192.168.255.255 | 65,536              | 256 contiguous class Cs | 192.168.0.0/16 (255.255.0.0)     | 16 bits      | 

## Classful Subnetting

Very specific subnetting architecture
- Not used since 1993
    - But still referenced in casual conversation

Used as a starting point when subnetting
- Standard values

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-7.webp)

### Subnet Classes

|        Class        |  Leading Bits  | Network Bits | Remaining Bits | Number of Networks | Hosts per Network | Default Subnet Mask |
|:-------------------:|:--------------:|:------------:|:--------------:|:------------------:|:-----------------:|:-------------------:|
|       Class A       |  0xxx (0-127)  |      8       |       24       |        128         |    16,777,214     |      255.0.0.0      |
|       Class B       | 10xx (128-191) |      16      |       16       |       16,384       |      65,534       |     255.255.0.0     |
|       Class C       | 110x (192-223) |      24      |       8        |     2,097,152      |        254        |    255.255.255.0    |
| Class D (multicast) | 1110 (224-239) | Not defined  |  Not defined   |    Not defined     |    Not defined    |     Not defined     |
| Class E (reserved)  | 1111 (240-255) | Not defined  |  Not defined   |    Not defined     |    Not defined    |     Not defined     | 

The 127.0.0.0/8 network is reserved as a loopback address.

### What IP class?

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-8.webp)

### The Construction of a Subnet

Network address
- The first IP address of a subnet
- Set all host bits to 0 (0 decimal)

First usable host address
- One number higher than the network address

Network broadcast address
- The last IP address of a subnet
- Set all hosts bits to 1 (255 decimal)

Last usable host address
- One number lower than the broadcast address

### Subnet calculations

IP address: 10.74.222.11
- Class A
- Subnet mask 255.0.0.0

|                                            | Network |    Host     |
| ------------------------------------------ |:-------:|:-----------:|
|                                            |   10.   |  74.222.11  |
| Network Address (Set all host bits to 0)   |   10.   |    0.0.0    |
| First host address (add one)               |   10.   |    0.0.1    |
| Broadcast address (Set all host bits to 1) |   10.   | 255.255.255 |
| Last host address (subtract one)           |   10.   | 255.255.254 |

IP address: 172.16.88.200
- Class B
- Subnet mask 255.255.0.0

|                                                      | Network |  Host   |
| ---------------------------------------------------- |:-------:|:-------:|
|                                                      | 172.16. | 88.200  |
| Network Address (Set all host bits to 0)             | 172.16. |   0.0   |
| First host address (add one)                         | 172.16. |   0.1   |
| Broadcast address (Set all host bits to 1)           | 172.16. | 255.255 |
| Last host address (subtract one from broadcast addr) | 172.16. | 255.254 |


IP address: 192.168.4.77
- Class C
- Subnet mask 255.255.255.0

|                                                      |  Network   | Host |
| ---------------------------------------------------- |:----------:|:----:|
|                                                      | 192.168.4. |  77  |
| Network address (Set all host bits to 0)             | 192.168.4. |  0   |
| First host address (add one)                         | 192.168.4. |  1   |
| Broadcast address (Set all host bit to 1)            | 192.168.4. | 255  |
| Last host address (subtract one from broadcast addr) | 192.168.4. | 254  |


## IPv4 Subnet Masks

### Classless Subnetting

CIDR (Classless Inter-Domain Routing)
- Created around 1993
- Removed the restrictions created by classful subnet masks
- "Cider" block notation

Subnet masks can be expressed as decimal or in CIDR notation
- IP address, slash, number of subnet bits; 192.168.1.44/24

You will usually be provided an IP address, subnet mask, default gateway, and DNS servers
- Some OSes are expecting decimal masks
- Some OSes are expecting CIDR notation masks

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-9.webp)

### The subnet mask

Contiguous series of ones
- Ones on the left
- Zeros on the right

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-10.webp)

### Binary to CIDR-block notation

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-11.webp)

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-12.webp)

![](/notes/comptia-n10-009-network+training-course/08-ipv4-addressing-13.webp)

### Subnet Masks — Binary to Decimal 

|  Binary  | Decimal |
|:--------:|:-------:|
| 00000000 |    0    |
| 10000000 |   128   |
| 11000000 |   192   |
| 11100000 |   224   |
| 11110000 |   240   |
| 11111000 |   248   |
| 11111100 |   252   |
| 11111110 |   254   |
| 11111111 |   255   | 

Now we can calculate binary to CIDR-block notation:

```
11111111.11110000.00000000.00000000
255     .   240  .    0   .    0
                /12

Network = 12 bits, Host = 20 bits
```

```
11111111.11111111.11100000.0000000
255     .    255 .    224 .   0
                /19

Network = 19 bits, Host = 13 bits
```

It can be done in the reverse too. From CIDR-block notion to decimal.

```
                /26
11111111.11111111.11111111.11000000
255     .   255  .   255  .    192

Network = 26 bits, Host = 6 bits
```

```
                /20
11111111.11111111.11110000.00000000
255     .   255  .   240  .    0

Network = 20 bits, Host = 12 bits
```

