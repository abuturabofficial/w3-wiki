---
title: "SIEM Platforms"
date: 2023-04-30 11:59:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 4
---

## **SIEM Concepts, Benefits, Optimization, & Capabilities**
  
“At its core, System Information Event Management (SIEM) is a data aggregator, search and reporting system. SIEM gathers immense amounts of data from your entire networked environment, consolidates and makes that data human accessible. With the data categorized and laid out at your fingertips, you can research data security breaches with as much detail as needed.”
  
  **Key Terms:**
- Log collection
- Normalization
- Correlation
- Aggregation
- Reporting

### SIEM
  
1. A SIEM system collects logs and other security-related documentation for analysis.
2. The core function to manage network security by monitoring flows and events.
3. It consolidates log events and network flow data from thousands of devices, endpoints, and applications distributed throughout a network. It then uses an advanced Sense Analytics engine to normalize and correlate this data and identifies security offenses requiring investigation.
4. A SIEM system can be rules-based or employ a statistical correlation between event log entries.
5. Capture log event and network flow data in near real time and apply advanced analytics to reveal security offenses.
6. It can be available on premises and in a cloud environment.

### Events & Flows
  
  | Events                                                                                                                                       | Flows                                                                                                                                                                                                                |
  | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
  | Typically is a log of a specific action such as a user login, or a FW permit, occurs at a specific time and the event is logged at that time | A flow is a record of network activity between two hosts that can last for seconds to days depending on the activity within the session.                                                                             |
  |                                                                                                                                              | For example, a web request might download multiple files such as images, ads, video, and last for 5 to 10 seconds, or a user who watches a NetFlix movie might be in a network session that lasts up to a few hours. |

### Data Collection

- It is the process of collecting flows and logs from different sources into a common repository.
- It can be performed by sending data directly into the SIEM or an external device can collect log data from the source and move it into the SIEM system on demand or scheduled.
  
  To consider:
- Capture
- Memory
- Storage capacity
- License
- Number of sources

### Normalization

- The normalization process involves turning raw data into a format that has fields such as IP address that SIEM can use.
- Normalization involves parsing raw event data and preparing the data to display readable information.
- Normalization allows for predictable and consistent storage for all records, and indexes these records for fast searching and sorting.

### License Throttling

- Monitors the number of incoming events to the system to manage input queues and EPS licensing.

### Coalescing

- Events are parsed and then coalesced based on common attributes across events. In QRadar, Event coalescing starts after three events have been found with matching properties within a 10-second period.
- Event data received by QRadar is processed into normalized fields, along with the original payload. When coalescing is enabled, the following five properties are evaluated.
  - QID
  - Source IP
  - Destination IP
  - Destination port
  - Username
	  
![SIEM Platforms](/notes/SIEM%20Platforms.png)

## **SIEM Deployment**

### SIEM Deployment Considerations

- Compliance
- Cost-benefit
- Cybersecurity
  
  **QRadar Deployment Examples**
  
![SIEM Platforms](/notes/SIEM%20Platforms-1.png)

### Events
  
  **Event Collector:**
- The event collector collects events from local and remote log sources, and normalize raw log source events to format them for use by QRadar. The Event Collector bundles or coalesces identical events to conserve system usage and send the data to the Event Processor.
- The Event Collector can use bandwidth limiters and schedules to send events to the Event Processor to overcome WAN limitations such as intermittent connectivity.
  
  **Event Processor:**
- The Event Processor processes events that are collected from one or more Event Collector components.
- Processes events by using the Custom Rules Engine (CRE).

### **Flows**
  
  **Flow Collector:**
- The flow collector generates flow data from raw packets that are collected from monitor ports such as SPANS, TAPS, and monitor sessions, or from external flow sources such as netflow, sflow, jflow.
- This data is then converted to QRadar flow format and sent down the pipeline for processing.
  
  **Flow Processor:**
- Flow deduplication: is a process that removes duplicate flows when multiple Flow Collectors provide data to Flow Processors appliances.
- Asymmetric recombination: Responsible for combining two sides of each flow when data is provided asymmetrically. This process can recognize flows from each side and combine them in to one record. However, sometimes only one side of the flow exists.
- License throttling: Monitors the number of incoming flows to the system to manage input queues and licensing.
- Forwarding: Applies routing rules for the system, such as sending flow data to offsite targets, external Syslog systems, JSON systems, other SIEMs.

#### Reasons to add event or flow collectors to an All-in-One deployment

- Your data collection requirements exceed the collection capability of your processor.
- You must collect events and flows at a different location than where your processor is installed.
- You are monitoring packet-based flow sources.
- As your deployment grows, the workload exceeds the processing capacity of the All-in-One appliance.
- Your security operations center employs more analytics who do more concurrent searches.
- The types of monitored data, and the retention period for that data, increases, which increases processing and storage requirements.
- As your security analyst team grows, you require better search performance.

### Security Operations Center (SOC)
  
  **Triad of Security Operations: People, Process and Technology.**
  
![SIEM Platforms](/notes/SIEM%20Platforms-2.png)

### SOC Data Collection
  
![SIEM Platforms](/notes/SIEM%20Platforms-3.png)

## **SIEM Solutions – Vendors**
  
  “The security information and event management (SIEM) market is defined by customers’ need to analyze security event data in real-time, which supports the early detection of attacks and breaches. SIEM systems collect, store, investigate, support mitigation and report on security data for incident response, forensics and regulatory compliance. The vendors included in this Magic Quadrant have products designed for this purpose, which they actively market and sell to the security buying center.”

#### Deployments
  
  **Small:**
  Gartner defines a small deployment as one with around 300 log sources and 1500 EPS.
  
  **Medium:**
  A midsize deployment is considered to have up to 1000 log sources and 7000 EPS.
  
  **Large:**
  A large deployment generally covers more than 1000 log sources with approximately 15000 EPS.

### **Important Concepts**
  
![SIEM Platforms](/notes/SIEM%20Platforms-4.png)

![SIEM Platforms](/notes/SIEM%20Platforms-5.png)

#### IBM QRadar

![SIEM Platforms](/notes/SIEM%20Platforms-6.png)

**IBM QRadar Components**

![SIEM Platforms](/notes/SIEM%20Platforms-7.png)

#### ArcSight ESM

![SIEM Platforms](/notes/SIEM%20Platforms-8.png)

#### Splunk

![SIEM Platforms](/notes/SIEM%20Platforms-9.png)

**Friendly Representation**

![SIEM Platforms](/notes/SIEM%20Platforms-10.png)

#### LogRythm’s Security Intelligence Platform

![SIEM Platforms](/notes/SIEM%20Platforms-11.png)

## **User Behavior Analytics**

### Security Ecosystem

- Detecting insider threats requires a 360 degree view of both logs and flows.

![SIEM Platforms](/notes/SIEM%20Platforms-12.png)

### Advantages of an integrated UBA Solution

- Complete visibility across end point, network and cloud infrastructure with both log and flow data.
- Avoids reloading and curating data faster time to insights, lowers opex, frees valuable resources.
- Out-of-the-box analytics models that leverage and extend the security operations platform.
- Single Security operation processes with integration of workflow system and other security solutions.
- Easily extend to third-party analytic models, including existing insider threats use cases already implemented.
- Leverage UBA insights in other integrated security analytics solutions.
- Get more from your QRadar ecosystem.
  
  **IBM QRadar UBA**
  
  160+ rules and ML driven use cases addressing 3 major insider threat vectors:
  1. Compromised or Stolen Credentials
  2. Careless or Malicious Insiders
  3. Malware takeover of user accounts
  
  **Detecting Compromised Credentials**
- 70% of phishing attacks are to steal credentials.
- 81% of breaches are with stolen credentials.
- $4M average cost of a data breach.
  
![SIEM Platforms](/notes/SIEM%20Platforms-13.png)

**Malicious behavior comes in many forms**

![SIEM Platforms](/notes/SIEM%20Platforms-14.png)

**Maturing into User Behavioral Analytics**

![SIEM Platforms](/notes/SIEM%20Platforms-15.png)

**QRadar UBA delivers value to the SOC**

![SIEM Platforms](/notes/SIEM%20Platforms-16.png)

## AI and SIEM
  
**Your goals as a security operations team are fundamental to your business.**

![SIEM Platforms](/notes/SIEM%20Platforms-17.png)

**Pressures today make it difficult to achieve your business goals.**

![SIEM Platforms](/notes/SIEM%20Platforms-18.png)

**Challenge #1: Unaddressed threats**

![SIEM Platforms](/notes/SIEM%20Platforms-19.png)

**Challenge #2: Insights Overload**

![SIEM Platforms](/notes/SIEM%20Platforms-20.png)

**Challenge #3: Dwell times are getting worse**

Lack of consistent, high-quality and context-rich investigations lead to a breakdown of existing processes and high probability of missing crucial insights – exposing your organization to risk.

**Challenge #4: Lack of cybersecurity talent and job fatigue**
- Overworked
- Understaffed
- Overwhelmed

**Investigating an Incident without AI:**

![SIEM Platforms](/notes/SIEM%20Platforms-21.png)

**Unlock a new partnership between analysts and their technology:**

![SIEM Platforms](/notes/SIEM%20Platforms-22.png)

### AI and SIEM – An industry Example
  
**QRadar Advisor with Watson:**
Built with AI for the front-line Security Analyst.

QRadar Advisor empowers security analysts to drive consistent investigations and make quicker and more decisive incident escalations, resulting in **reduced dwell** times, and **increased analyst efficiency**.

**Benefits of adopting QRadar Advisor:**

![SIEM Platforms](/notes/SIEM%20Platforms-23.png)

**How it works – An app that takes QRadar to the next level:**

![SIEM Platforms](/notes/SIEM%20Platforms-24.png)

**How it works – Building the knowledge (internal and external)**

![SIEM Platforms](/notes/SIEM%20Platforms-25.png)

**How it works – Aligning incidents to the ATT&CK chain:**

![SIEM Platforms](/notes/SIEM%20Platforms-26.png)

**How it works – Cross-investigation analytics**

![SIEM Platforms](/notes/SIEM%20Platforms-27.png)

**How it works – Using analyst feedback to drive better decisions**

![SIEM Platforms](/notes/SIEM%20Platforms-28.png)

**How it works – QRadar Assistant**

![SIEM Platforms](/notes/SIEM%20Platforms-29.png)
