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

