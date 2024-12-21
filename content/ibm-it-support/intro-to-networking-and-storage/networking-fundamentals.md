---
title: "Networking Fundamentals"
date: 2023-02-20 11:16:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
---

# **Network Topologies, Types, and Connections**

## **Types and Topologies**

### What is a computer network?
  
  Computer networking refers to connected computing devices and an array of IoT devices that communicate with one another.

### **Network Types**
  
  There are multiple network types:
- PAN (Personal Area Network)
- LAN (Local Area Network)
- MAN (Metropolitan Area Network)
- WAN (Wide Area Network)
- WLAN (Wireless LAN)
- VPN (Virtual Private Network)

#### PAN (Personal Area Network)
  
  A PAN enables communication between devices around a person. PANs can be wired or wireless.
- USB
- FireWire
- Infrared
- ZigBee
- Bluetooth
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals.png)

#### LAN (Local Area Network)
  
  A LAN is typically limited to a small, localized area, such as a single building or site.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-1.png)

#### MAN (Metropolitan Area Network)

- A MAN is a network that spans an entire city, a campus, or a small region.
- MANs are sometimes referred to as CANs (Campus Area Networks).
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-2.png)

#### WAN (Wide Area Network)
  
  A WAN is a network that extends over a large geographic area.
- Businesses
- Schools
- Government entities
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-3.png)

#### WLAN (Wireless LAN)
  
  A WLAN links two or more devices using wireless communication.
- Home
- School
- Campus
- Office building
- Computer Lab
  
  **Through a gateway device, a WLAN can also provide a connection to the wider Internet.**

#### VPN (Virtual Private Network)

- A private network connection across public networks.
- Encrypt your Internet traffic.
- Disguise your online identity
- Safeguard your data.

### **Topology**

- Topology defines a network’s structure
- A network’s topology type is chosen bases on the specific needs of the group installing that network
  
  1. **Physical Topology**: It describes how network devices are physically connected.
  2. **Logical Topology**: It describes how data flows across the physically connected network devices.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-4.png)

#### Star topology
  
  Star topology networks feature a central computer that acts as a hub.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-5.png)

#### Ring topology
  
  Ring topology networks connect all devices in a circular ring pattern, where data only flows in one direction (clockwise).
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-6.png)

#### Bus topology
  
  Bus topology networks connect all devices with a single cable or transmission line.
- Small networks, LAN.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-7.png)

#### Tree topology
  
  Tree topology networks combine the characteristics of bus topology and star topology.
- University campus
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-8.png)

#### Mesh topology
  
  Mesh topology networks connect all devices on the network together.
- This is called dynamic routing.
- It is commonly used in WAN network for backup purposes.
- It is not used in LAN implementations.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-9.png)

## **Wire Connections**

### Older Internet Connection Types
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-10.png)

### Newer Internet Connection Types
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-11.png)

### **Wired Networks**
  
  Wired networking refers to the use of wire connections that allow users to communicate over a network.
- Most computer networks still depend on cables or wires to connect devices and transfer data.

#### Wire Connections: Dial-Up
  
  Requires a modem and phone line to access the internet.
  
  **Pros**:
- Widely available
- Low cost
- Easy Setup
  
  **Cons**:
- Very slow speeds
- Can’t use phone and Internet at the same time

#### Wire Connections: DSL
  
  Connects to the Internet using a modem and two copper wires within the phone lines to receive and transmit data.
  
  **Pros**:
- Faster than dial-up
- Inexpensive
- Dedicated connection (no bandwidth sharing)
- Can provide Wi-Fi
- Uses existing phone lines
  
  **Cons**:
- Slow speeds (less than 100 Mbps)
- Not always available

#### Wired Connections: Cable
  
  Cable delivers Internet via copper coaxial television cable.
  
  **Pros**:
- Lower cost than fiber
- Fast speeds
- Better than DSL
- Long distances
- Lower latency
  
  **Cons**:
- Bandwidth congestion
- Slower uploads
- Electromagnetic interference

#### Wired Connection: Fiber Optic
  
  Transmit data by sending pulses of light across strands of glass (up to 200 Gbps).
  
  **Pros**:
- Efficient
- Reliable
- Covers long distances
- Fast speeds
- Streaming and hosting
  
  **Cons**:
- Expensive
- Not available everywhere

## **Cables**

### **Cables types**
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-12.png)

#### Hard Drive Cables
  
  Hard drive cables connect a hard drive to a motherboard or controller card.  May also be used to connect optical drives or older floppy drives.
- SATA
	- Next-generation
	- Carries high-speed data
	- Connects to storage devices
- IDE
	- Older tech
	- 40-wire ribbon
	- Connect motherboard to one or two drives
- SCSI
	- Supports variety of devices
	- Different cable types
	- Up to 16 connections
	  
	  ![Networking Fundamentals](/notes/Networking%20Fundamentals-13.png)

#### Network Cables
  
  In wired networks, network cables connect devices and route information from one network device to another.
  
  Cable need is determined by:
- Network topology
- Protocol
- Size
  
  Types:
- Coaxial
	- TV signals to cable boxes
	- Internet to home modems
		- Inner copper wire surrounded by shielding
		- Highly Resistant to signal interference
		- Supports greater cable lengths between devices
		- 10 Mbps capacity, uses DOCSIS standard
- Fiber optic
	- Work over long distances without much interference
	- Handles heavy volumes of data traffic
	- Two Types
		- **Single-Mode**
			- Carries one light path
			- Sourced by a laser
			- Longer transmission distance
		- **Multimode**
			- Multiple light paths
			- Sourced by an LED
- Ethernet
	- Consist of four pairs of twisted wires
	- Reduce interference
	- Wire a computer to LAN
	- Fast and Consistent
	- Two Types:
		- **Unshielded Twisted Pair (UTP)**
			- Cheaper and more common
		- **Shielded Twisted Pair (STP)**
			- More expensive
			- Designed to reduce interference
			  ![Networking Fundamentals](/notes/Networking%20Fundamentals-14.png)
			  
			  ![Networking Fundamentals](/notes/Networking%20Fundamentals-15.png)

#### Serial Cables
  
  A serial cable follows the **RS-232** standard:
  “Data bits must flow in a line, one after another, over the cable.”
  Used in:
- Modems
- Keyboards
- Mice
- Peripheral devices
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-16.png)

#### Video Cables
  
  Transmits video signals.
- VGA
	- Older, analog
- DisplayPort
	- Connects interface to display
- HDMI
	- High definition
	- Different connector types
	- Type A is common
- DVI
	- Can be digital or integrated
	- Can be single or dual link
- Mini-HDMI
	- Type C HDMI
	  
	  ![Networking Fundamentals](/notes/Networking%20Fundamentals-17.png)

#### Multipurpose Cables
  
  Multipurpose cables connect devices and peripherals without a network connection. They transfer both data and power.
- USB
	- Low speed 1.5 Mbps @3 meters
	- Full speed 12 Mbps @5 meters
- Lighting
	- Apple only
	- Connects to USB ports
- Thunderbolt
	- Apple only
	- Copper max length 3 meters
	- Optical max length 60 meters
	- 20-40 Gbps throughput

## **Wireless Connections**

### **Wireless network types**
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-18.png)

#### WPAN networking examples
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-19.png)

#### WLAN networking examples
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-20.png)

#### WMAN networking examples
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-21.png)

#### WWAN networking examples
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-22.png)

### Wired vs. wireless
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-23.png)

### Latest Networking Trends
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-24.png)

## **Advantages and Disadvantages of Network Types**

### Networks vs. devices
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-25.png)

### Smaller vs. larger
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-26.png)

### Wired vs. wireless
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-27.png)

### **Network Types**
  
  Basic network types are:
- Wired
- Wireless
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-28.png)

#### PAN
  
  A PAN enables communication between devices around a person. PANs are wired and WPANs are wireless.
  
  **Advantages**:
- Flexible and mobile
- One-time, easy setup
- Portable
  
  **Disadvantages:**
- Limited range
- Limited bandwidth

#### LAN
  
  **Advantages:**
- Reliable and versatile
- Higher data transmission rates
- Easier to manage
  
  **Disadvantages:**
- Smaller network coverage area
- Number of device affects speed
- Security risks

#### MAN
  
  A MAN is optimized for a larger geographical area, ranging from several building blocks to entire cities.
  
  **Advantages:**
- Cover multiple areas
- Easy to use, extend, and exchange
- Managed by an ISP, government entity, or corporation
  
  **Disadvantages:**
- Requires special user permissions
- Security risk

#### WAN
  
  WANs and WWANs provide global coverage. Examples include the Internet and cellular networks.
  
  **Advantages:**
- Global coverage
- More secure
  
  **Disadvantages:**
- Expensive
- Difficult to maintain

# **Hardware, Network Flow, and Protocols**

## **Networking Hardware Devices**

### Network Devices
  
  Network devices, or networking hardware, enable communication and interaction on a computer network.
  
  This includes:
- Cables
- Servers
- Desktops
- Laptops
- Tablets
- Smartphones
- IoT devices

### **What is a server?**

- Other computers or devices on the same network can access the server
- The devices that access the server are known as clients
- A user can access a server file or application from anywhere

#### What are nodes and clients?
  
  A node is a network-connected device that can send and receive information.
- All devices that can send, receive, and create information on a network are nodes.
- The nodes that access servers to get on the network are known as clients.

#### Client-server
  
  Client-server networks are common in businesses.
- They keep files up-to-date
- Easy-to-find
- One shared file in one location
  
  Examples of services that use client-server networks:
- FTP sites
- Web servers
- Web browsers

#### Peer-to-peer
  
  Peer-to-peer networks are common in homes on the Internet.
  
  Examples:
- File sharing sites
- Discussion forums
- Media streaming
- VoIP services

#### Hubs and Switches
  
  **A hub:**
- Connects multiple devices together
- Broadcasts to all devices except sender
  
  **A switch:**
- Keeps a table of MAC addresses
- Sends directly to correct address (More efficient than hubs)

#### Routers and modems
  
  Routers interconnect different networks or subnetworks.
- Manage traffic between networks by forwarding data packets
- Allow multiple devices to use the same Internet connection
  
  Routers use internal routing to direct packets effectively
  The router:
- Reads a packet's header to determine its path
- Consults the routing table
- Forwards the packet
  
  A modem converts data into a format that is easy to transmit across a network.
- Data reaches its destination, and the modem converts it to its original form
- Most common modems are cable and DSL modems

#### Bridges and gateways
  
  A **bridge** joins two separate computer networks, so they can communicate with each other and work as a single network.
  
  Wireless bridges can support:
- Wi-Fi to Wi-F i
- Wi-Fi to Ethernet
- Bluetooth to Wi-Fi
  
  A **gateway** is a hardware or software that allows data to flow from one network to another, for examples, a home network to the Internet.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-29.png)

#### Repeaters and WAPs
  
  **Repeaters**
- Receive a signal and retransmits it
- Used to extend a wireless signal
- Connect to wireless routers
  
  **Wireless Access Point (WAP)**
- Allows Wi-Fi devices to connect to a wired network
- Usually connects to a wired router as a standalone device
- Acts as a central wireless connection point for computers equipped with wireless network adapters

#### Network Interface Cards (NICs)
  
  NICs connect individual devices to a network.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-30.png)

#### Firewalls, proxies, IDS, and IPS
  
  A **firewall** monitors and controls incoming and outgoing network traffic based on predetermined security rules.
- Firewalls can be software or hardware
- Routers and operating systems have built-in firewalls
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-31.png)
  
  **A Proxy Server:**
- Works to minimize security risks
- Evaluates requests from clients and forwards them to the appropriate server
- Hides an IP address
- Saves bandwidth
  
  **IDS and IPS:**
- IDS monitors network traffic and reports malicious activity
- IPS inspects network traffic and removes, detains, or redirects malicious items
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-32.png)

## **Packets, IP Addressing, DNS, DHCP, and NAT**

### What is a packet?
  
  Everything you do on the Internet involves packets.
  
  Packets are also called:
- Frames
- Blocks
- Cells
- Segments

### Data Transmission Flow Types
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-33.png)

### IP Packets Transmission Modes
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-34.png)

### Data Transmission Flow
  
  When you send an email, it is broken down into individually labeled data packets and sent across the network.

### **IPv4 and IPv6**
- IPv4 is one of the core protocols for the Internet.
- IPv6 is the newest version of Internet Protocol.

#### What is an IP address?
  
  An IP address is used to logically identify each device (Host) on a given network.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-35.png)

#### IP Address Types
  
  **Static**: Static IP addresses are manually assigned.
  
  **Dynamic:** Dynamic IP addresses are automatically assigned.
  
  **Public:** Public IP address is used to communicate publically.
  
  **Private:** Private IP address is used to connect securely within an internal, private network.
  
  **Loopback:** Loopback is the range of IP addresses reserved for the local host.
  
  **Reserved:** Reserved IP addresses have been reserved by the **IETF and IANA**.

### DNS
  
  The DNS is the phone book of the internet.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-36.png)

### Dynamic Host Configuration Protocol (DHCP)
  
  The DHCP automates the configuring of IP network devices.
  
  A DHCP server uses a pool of reserved IP addresses to automatically assign dynamic IP addresses or allocate a permanent IP address to a device.
  
  **Static allocation:**
  The server uses a manually assigned “permanent” IP address for a device.
  
  **Dynamic allocation:**
  The server chooses which IP address to assign a device each time it connects to the network.
  
  **Automatic allocation:**
  The server assigns a “permanent” IP addresses for a device automatically.

### Subnetting (and Subnet Mask)
  
  Subnetting is the process of taking a large, single network and splitting it up into many individual smaller subnetworks or subnets.
- Identifies the boundary between the IP network and the IP host.
- Internal usage within a network.
- Routers use subnet masks to route data to the right place.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-37.png)

### Automatic Private IP Addressing (APIPA)
  
  APIPA is a feature in operating systems like Windows that let computers self-configure an IP address and subnet mask automatically when the DHCP server isn’t reachable.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-38.png)

### Network Address Translation (NAT)
  
  NAT is a process that maps multiple local private addresses to a public one before transferring the information.
- Multiple devices using a single IP address
- Home routers employ NAT
- Conserves public IP addresses
- Improves security
  
  **NAT instructions send all data packets without revealing private IP addresses of the intended destination.**
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-39.png)

### Media Access Control (MAC) Addresses
  
  A MAC address is the physical address of each device on a network.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-40.png)

## **Models, Standards, Protocols, and Ports**

### **Networking Models**
  
  A networking model describes:
- Architecture
- Components
- Design
  
  Two types:
  1. OSI Model: A conceptual framework used to describe the functions of a networking system.
  1. TCP/IP Model: A set of standards that allow computers to communicate on a network. TCP/IP is based on the OSI model.

#### 7 Layer OSI Model
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-41.png)

#### 5 Layer TCP/IP Model
  
  The TCP/IP model is a set of standards that allow computers to communicate on a network. TCP/IP is based on the OSI model.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-42.png)

### **Network Standards and their Importance**
  
  Networking standards define the rules for data communications that are needed for interoperability of networking technologies and processes.
  
  There are two types of network standards:
  1. **De-jure or Formal Standards:** Developed by an official industry or government body.
  
  **Examples:** HTTP, HTML, IP, Ethernet 802.3d
  
  2. **De-Facto Standards:** De-facto standards result from marketplace domination or practice.
  
  **Examples:** Microsoft Windows, QWERTY keyboard

#### Noted Network Standards Organizations
  
  Standards are usually created by government or non-profit organizations for the betterment of an entire industry.
  
  1. **ISO:** Established the well known OSI reference networking model.
  2. **DARPA:** Established the TCP/IP protocol suit.
  3. **W3C:** Established the World Wide Web (WWW) standard.
  4. **ITU:** Standardized international telecom, set standards for fair use of radio frequency.
  5. **IEEE:** Established the IEEE 802 standards.
  6. **IETF:** Maintains TCP/IP protocol suites. IETF also developed RFC standard.

### **Protocols**
  
  A network protocol is a set of rules that determines how data is transmitted between different devices in the same network.
  
  1. **Security**:
  	- Encryption
  	- Authentication
  	- Transportation
  1. **Communication**:
  	- Encryption
  	- Authentication
  	- Transportation
  1. **Network Management**:
  	- Connection
  	- Link Aggregation
  	- Troubleshooting

#### Protocols – TCP vs. UDP
  
  | TCP                       | UDP                        |
  | ------------------------- | -------------------------- |
  | Slower but more reliable  | Faster but not guaranteed  |
  | Typical applications      | Typical application        |
  | 1) File transfer protocol | 1) Online games            |
  | 2) Web browsing           | 2) Calls over the internet | 
  | 3) EMAIL                  |                            |

#### Protocols – TCP/IP
  
  The TCP/IP suite is a collection of protocols.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-43.png)

#### Protocols – Internet of Things
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-44.png)

#### Protocols – Crypto Classic
  
  The Crypto Classic protocol is designed to serve as one of the most efficient, effective, and secure payment methods built on the blockchain network.
  
  **Bitcoin Protocol:** A peer-to-peer network operating on a cryptographic protocol used for bitcoin transactions and transfers on the Internet.
  
  **Blockchain Protocol:** An open, distributed ledger that can record transactions between two parties efficiently and in a verifiable and permanent way.

### Commonly Used Ports
  
  Ports are the first and last stop for information sent across a network.
- A port is a communication endpoint.
- A port always has an associated protocol and application.
- The protocol is the path that leads to the application’s port.
- A network device can have up to **65536** ports.
- Port numbers do not change.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-45.png)

## **Wireless Networks and Standards**

### **Network types**
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-46.png)

#### WPAN
  
  A WPAN connects devices within the range of an individual person (10 meters). WPANs use signals like **infrared, Zigbee, Bluetooth, and ultra-wideband**.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-47.png)

#### WLAN
  
  A WLAN connects computers and devices within homes, offices, or small businesses. WLANs use Wi-Fi signals from routers, modems, and wireless access points to wirelessly connect devices.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-48.png)

#### WMAN
  
  A WMAN spans a geographic area (size of a city). It serves ranges greater than 100 meters.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-49.png)

#### WWAN
  
  A WWAN provides regional, nationwide, and global wireless coverage. This includes private networks of multinational corporations, **the Internet, and cellular networks like 4G, 5G, LTE, and LoRaWAN**.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-50.png)

#### Wireless ad hoc network
  
  A WANET uses Wi-Fi signals from whatever infrastructure happens to be available to connect devices instantly, anywhere. WANETs are similar in size to WLANs, but use technology that is closer to WWANs and cellular network.
  
  **Advantages:**
- Flexible
- No required infrastructure
- Can be set up anywhere instantly
  
  **Disadvantages:**
- Limited bandwidth quality
- Not robust
- Security risks
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-51.png)

### **Cellular networks**
  
  A cellular network provides regional, nationwide, and global mesh coverage for mobile devices.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-52.png)
  
  **Advantages**
- Flexibility
- Access
- Speed and efficiency
  
  **Disadvantages**
- Expensive
- Decreased coverage
- Hardware limitations

#### IEEE 802.20 and IEEE 802.22
  
  The IEEE 802.20 and 802.22 standards support WWANs, cellular networks and WANETs.
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-53.png)
  
  **IEEE 802.20**
- Optimizes bandwidth to increase coverage or mobility
- Used to fill the gap between cellular and other wireless networks
  
  **IEEE 802.22**
- Uses empty spaces in the TV frequency spectrum to bring broadband to low-population, hard-to-reach areas

## **Protocol Table**

### Web page protocols
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-54.png)

### File transfer protocols
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-55.png)

### Remote access protocols
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-56.png)

### Email protocols
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-57.png)

### Network Protocols
  
  ![Networking Fundamentals](/notes/Networking%20Fundamentals-58.png)
