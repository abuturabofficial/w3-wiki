---
draft: false
date: '2025-09-29T11:10:07+05:00'
title: 'Architecture Models'
linkTitle: '3.1: Architecture Models'
menuPre: ''
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 11
---

> [!WARNING]
> The soaring Cloud Computing costs, unexpected high bills, and multitude of hidden charges, make Cloud a lot less viable option than on-prem options. Depending on the organization's needs and size, On-premise Cloud Computing will be a cheaper alternative.
> 
> [The Cloud Tipping Point | Lawrence Systems](https://www.youtube.com/watch?v=W0tsI-7iaWE) 
> 
> [Leaving the Cloud | The Rework Podcast](https://37signals.com/podcast/leaving-the-cloud/)
> 
> [Why you're addicted to cloud computing | Fireship](https://www.youtube.com/watch?v=4Wa5DivljOM)

## Cloud Responsibility Matrix

IaaS, PaaS, SaaS, etc.
- Who is responsible for security?

Security should be well documented
- Most cloud providers provide a matrix of responsibilities
- Everyone knows up front

These responsibilities can vary
- Different cloud providers
- Contractual agreements

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-1.webp)

### Hybrid Considerations

Hybrid cloud
- More than one public or private cloud
- This adds additional complexity

Network protection mismatches
- Authentication across platforms
- Firewall configurations
- Server settings

Different security monitoring
- Logs are diverse and cloud-specific

Data leakage
- Data is shared across public Internet

### Third-Party Vendors in the Cloud

You, the cloud provider, and the third parties
- Infrastructure technologies
- Cloud-based appliances

Ongoing vendor risk assessments
- Part of an overall vendor risk management policy

Include third-party impact for incident response
- Everyone is part of the process

Constant monitoring
- Watch for changes and unusual activity

### Infrastructure as Code

Describe an infrastructure
- Define servers, network, and applications as code

Modify the infrastructure and create versions
- The same way you version application code

Use the description (code) to build other application instances
- Build it the same way every time based on the code

An important concept for cloud computing
- Build a perfect version every time

### Serverless Architecture

Function as a Service (FaaS)
- Applications are separated into individual, autonomous functions
- Remove the OS from the equation

Developer still creates the server-side logic
- Runs in a stateless compute container

May be event triggered and ephemeral
- May only run for one event

Managed by a third-party
- All OS security concerns are at the third party

### Microservices and APIs

Monolithic applications
- One big application that does everything

Application contains all decision-making process
- User interface
- Business logic
- Data input and output

Code challenges
- Large codebase 
- Change control challenges

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-2.webp)

APIs
- Application Programming Interface

API is the "glue" for the microservices
- Work together to act as the application

Scalable
- Scale just the microservices you need

Resilient
- Outages are contained

Security and compliance
- Containment is built-in

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-3.webp)

## Network Infrastructure Concepts

### Physical Isolation

Devices are physically separate
- Air gap between Switch A and Switch B

Must be connected to provide communication
- Direct connect, or another switch or router

Web servers in one rack
- Database servers on another

Customer A on one switch, customer B on another
- No opportunity for mixing data

### Physical Segmentation

Separate devices
- Multiple units, separate infrastructure

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-4.webp)

### Logical Segmentation with VLANs

Virtual Local Area Networks (VLANs)
- Separated logically instead of physically
- Cannot communicate between VLANs without a Layer 3 device/router

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-5.webp)

### SDN (Software Defined Networking)

Networking devices have different functional planes of operation
- Data, control, and management planes

Split the functions into separate logical units
- Extend the functionality and management of a single device
- Perfectly built for the cloud

Infrastructure layer/Data plane
- Process the network frames and packets
- Forwarding, trunking, encrypting, NAT

Control layer/Control plane
- Manages the actions of the data plane
- Routing tables, session tables, NAT tables
- Dynamic routing protocol updates

Application layer/Management plane
- Configure and manage the device
- SSH, browser, API

### Extend the Physical Architecture

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-6.webp)

### SDN Data Flows

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-7.webp)

### SDN Security

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-8.webp)

## Other Infrastructure Concepts

### Attacks can happen anywhere

Two categories for IT security
- The on-premises data is more secure!
- The cloud-based data is more secure!

Cloud-based security is centralized and costs less
- No dedicated hardware, no data center to secure
- A third party handles everything

On-premises puts the security burden on the client
- Data center security and infrastructure costs

Attackers want your data
- They don't care where it is

### On-premises Security

Customize your security posture
- Full control when everything is in-house

On-site IT team can manage security better
- The local team can ensure everything is secure
- A local team can be expensive and difficult to staff

Local team maintains uptime and availability
- System checks can occur at any time
- No phone call for support

Security changes can take time
- New equipment, configurations, additional costs

### Centralized vs. Decentralized

Most organizations are physically decentralized
- Many locations, cloud providers, OSes, etc.

Difficult to manage and protect so many diverse systems
- Centralize the security management

A centralized approach
- Correlated alerts
- Consolidated log file analysis
- Comprehensive system status and maintenance/patching

It's not perfect
- Single point of failure, potential performance issues

### Virtualization

Virtualization
- Run different OSes on the same hardware

Each application instance has its own OS
-  Adds overhead and complexity
- Virtualization is relatively expensive

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-9.webp)

### Application Containerization

Container
- Contains everything you need to run an application
- Code and dependencies
- A standardized unit of software

An isolated process in a sandbox
- Self-contained
- Apps can't interact with each other

Container image
- A standard for portability
- Lightweight, uses the host kernel
- Secure separation between applications

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-10.webp)

#### Virtualized vs. Containerized

![](/notes/comptia-sy0-701-security+training-course/11-architecture-models-11.webp)

### IoT (Internet of Things)

Sensors
- Heating and cooling, lighting

Smart devices
- Home automation, video doorbells

Wearable technology
- Watches, health monitors

Facility automation
- Temperature, air quality, lighting

Weak defaults
- IOT manufacturers are not security professionals

### SCADA/ICS

Supervisory Control and Data Acquisition System
- Large-scale, multi-site Industrial Control Systems (ICS)

PC manages equipment
- Power generation, refining, manufacturing equipment
- Facilities, industrial, energy, logistics

Distributed control systems
- Real-time information
- System control

Requires extensive segmentation
- No access from the outside

### RTOS (Real-Time Operating System)

An OS with a deterministic processing schedule
- No time to wait for other processes
- Industrial equipment, automobiles
- Military environments

Extremely sensitive to security issues
- Non-trivial systems
- Need to always be available
- Difficult to know what type of security is in place

### Embedded Systems

Hardware and software designed for a specific function
- Or to create as part of a larger system

Is built with only this task in mind
- Can be optimized for size and/or cost

Common examples
- Traffic light controllers
- Digital watches
- Medical imaging systems

### High Availability

Redundancy doesn't mean always available
- May need to be powered on manually

HA (High availability)
- Always on, always available

Many include many components working together
- Active/active can provide scalability advantages

Higher availability almost always means higher costs
- There's always another contingency you could add
- Upgraded power, high-quality server components, etc.

## Infrastructure Consideration

### Availability

System uptime
- Access data, complete transactions
- A foundation of IT security

A balancing act with security
- Available, but only to the right people

WE spend a lot of time and money on availability
- Monitoring, redundant systems

An important metric
- We are often evaluated on total available time

### Resilience

Eventually, something will happen
- Can you maintain availability?
- Can you recover? How quickly?

Based on many variables
- The root cause
- Replacement hardware installations
- Software patch availability
- Redundant systems

Commonly referenced as MTTR
- Mean Time to Repair

### Cost

How much money is required?
- Everything ultimately comes down to cost

Initial installation
- Very different across platforms

Ongoing maintenance
- Annual ongoing cost

Replacement or repair costs
- You might need more than one

Tax implications
- Operating or capital expense

### Responsiveness

Request information
- Get a response
- How quickly did that happen?

Especially important for interactive applications
- Humans are sensitive to delays

Speed is an important metric
- All parts of the application contribute
- There's always the weakest link

### Scalability

How quickly and easily can we increase or decrease capacity?
- This might happen many times a day
- Elasticity

There's always a resource challenge
- What's preventing scalability?

Needs to include security monitoring
- Increases and decreases as the system scales

### Ease of Deployment

An application has many moving parts
- Web server, database, caching server, firewall, etc.

This might be an involved process
- Hardware resources, cloud budgets, change control

This might be very simple
- Orchestration/automation

Important to consider during the product engineering phase
- One missed detail can cause deployment issues

### Risk Transference

Many methods to minimize risk
- Transfer the risk to a third party

Cybersecurity insurance
- Attacks and downtime can be covered
- Popular with the rise in ransomware

Recover internal losses
- Outages and business downtime

Protect against legal issues from customers
- Limit the costs associated with legal proceedings

### Ease of Recover

Something will eventually go wrong
- Time is money
- How easily can you recover?

Malware infection
- Reload OS from original media — 1 hour
- Reload from corporate image — 10 minutes

Another important design criteria
- This may be critical to the final product

### Patch Availability

Software isn't usually static
- Bug fixes, security updates, etc.

This is often the first task after installation
- Make sure you're running the latest version

Most companies have regular updates
- Microsoft's monthly patch schedule

Some companies rarely patch
- This might be a significant concern

### Inability to Patch

What if patching wasn't an option?
- This often happens than you might think

Embedded systems
- HVAC controls
- Time clocks

Not designed for end-user updates
- This is a bit short-sighted
- Especially these days

May need additional security controls
- A firewall for your time clock

### Power

A foundational element
- This can require extensive engineering

Overall power requirements
- Data center vs. office building

Primary power
- One or more providers

Backup services
- UPS (Uninterruptible Power Supply)
- Generators

### Compute

An application's heavy lifting
- More than just a single Compute

The compute engine
- More options available in the cloud

May be limited to a single processor
- Easier to develop

Use multiple CPUs across multiple clouds
- Addtional complexity
- Enhanced scalability