---
title: "SDLC - The Software Development Lifecycle"
linkTitle: "SDLC"
date: 2023-05-20 08:45:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 1
---

## **What is Software Engineering?**

- Application of scientific principles for design and creation of software
- Systematic approach to software development
  - Design
  - Build
  - Test

**Software Crisis:**
- Began in mid-1960s
- Resulted from software development that ran over budget and behind schedule with unmanageable and buggy code
- By the time old software solutions were developed, the newer technologies got the traction, and code refactoring would become necessary
- Solutions didn’t scale well to large projects
  
  Engineering principles:
- Resolved as standardized methods in software engineering and computer-aided software engineering (CASE) tools were developed
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle.webp)
  
  **Software engineer vs. software developer:**
  
  | Engineer                          | Developer                                                                  |
  | --------------------------------- | -------------------------------------------------------------------------- |
  | Also developers                   | Narrower in scope than SE                                                  |
  | Broad, big picture knowledge base | Creative approaches                                                        |
  | Systematic development process    | Write code to implement specific functionality and solve specific problems |
  | Focus on structure                |                                                                            | 
  
  **SE responsibilities:**
- Design, build and maintain software systems
- Write and test code
- Consult with stakeholders, third party vendors' security specialists, and other team members
  
  **Software Development Life Cycle (SDLC):**
- Scientific approach to software development
- Guides the software development process
- Identifies discrete steps needed to develop software

## **Introduction to SDLC**

- Systematic process to develop high-quality software
- Aims to produce software that meets requirements
- Defined phases with their own processes and deliverables
- Cycle of planning, design, and development
- Minimizes development risks and costs
  
  **History of the SDLC:**
- Conceived of in the mid-1960s
- A deliberate approach needed to manage complex projects
- Initially used the waterfall method
- Adapted to use iterative methods
  
  **Advantages of the SDLC:**
- Improves efficiency and reduce risks
- Team members know what they should be working on and when
- Facilitates communication among stakeholders
- Team members know when development can move to the next phase
- Respond to changing requirements
- Solve problems early in the process
- Reduces overlapping responsibilities

## **Phases of the SDLC**

- Organizations may have different names for each stage
- Some organizations have more or fewer stages
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-1.webp)

### Phase 1: Planning
  
  Requirements;
- Gathered
- Analyzed
- Documented
- Prioritized
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-2.webp)
  
  **Prototyping:**
- Small-scale replica to clarify requirements
- Tests design ideas
- Can be developed at various stages of the SDLC
  
  **Software Requirements Specification:**
- Requirements are documented in the SRS
- All stakeholders must agree

### Phase 2: Design
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-3.webp)

### Phase 3: Development
  
Development starts when the design document is finalized and sent to the developers to write code for it.

### Phase 4: Testing

- Code is tested to ensure stability, security, and that it meets requirements from the SRS
- Bugs reported, tracked, fixed, and retested
  
  Some common tests:
- Unit testing
- Integration testing
- System testing
- Acceptance testing

### Phase 5: Deployment

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-4.webp)

### Phase 6: Maintenance
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-5.webp)

## **Building Quality Software**
  
  **Common software engineering processes:**
- Requirements gathering
- Design
- Coding for quality
- Testing
- Release
- Documenting

### Requirement Gathering

- The SRS encompasses the process of collecting and documenting the set of requirements that the software needs to adhere to
- It may include a set of use cases that describe the business needs and user flows that the software must implement
  
  Software requirements can be classified into four broad categories:
  1. Functionality
  2. External & user interface
  3. System features
  4. Non-functional

### Design

- Transforming requirements into code
- Breaking down requirements into sets of related components
- Communicating business rules and application logic

### Coding for quality
  
  It refers to characteristics of the code, including attributes:
- Maintainability
- Readability
- Testability
- Security
  
  Quality code must fulfill the intended requirements of the software without defects
- Clean and consistent
- Easy to read and maintain
- Well documented
- Efficient
  
  Coding for quality entails a following set of coding practices during development;
- Following coding standards
- Using linters to detect errors
- Commenting in the code itself to make it easy to understand and modify

### Testing
  
  The process of verifying that the software matches established requirements and is free of bugs
- Identify errors, gaps, or missing requirements
- Ensures reliability, security, performance, and efficiency
- Software testing can often be automated or done manually
  
  The types of testing are;
- Unit testing
- Integration testing
- System testing
- User acceptance testing (UAT) or Beta testing

### Releases
  
  | Alpha                          | Beta               | General Availability |
  | ------------------------------ | ------------------ | -------------------- |
  | Select stakeholders            | All stakeholders   | Stable               |
  | May contain errors             | User testing       | All users            |
  | Preview of functioning version | Meets requirements |                      |
  | Design changes may occur       |                    |                      |

### Documenting
  
**System documentation:**

README files, inline comments, architecture and design documents, verification information, and maintenance guides

**User documentation:**

User guides, instructional videos, manuals, online and inline help

## **Requirements**
  
  **Steps to gathering requirements:**
- Identifying stakeholders
- Establishing goals and objectives
- Eliciting requirements from the stakeholders
- Documenting the requirements
- Analyzing and confirming the requirements
- Prioritizing

### 1) Identifying stakeholders
  
  **Key personnel:**
- Decision-makers
- End-users
- System administrators
- Engineering Marketing
- Sales
- Customer support

### 2) Establishing goals and objectives
  
**Goals:** broad, long-term achievable outcomes
  
**Objectives:** actionable, measurable actions that achieve the goal

### 3) Eliciting, documenting, confirming
  
  **Elicit:**
- Surveys
- Questionnaires
- Interviews
  
  **Document:**
- Align with goals and objectives
- Easily understood
  
  **Confirm:**
- Consistency
- Clarity
- Completeness

### 4) Prioritizing

- Must-have
- Highly desired
- Nice to have

### Requirements documentation:

- Software requirements specification (SRS)
- User requirements specification (URS)
- System requirements specification (SysRS)
  
**1) Software requirements specification (SRS)**
- Captures functionalities the software should perform
- Establishes benchmarks / service-levels for performance
- Purpose and scope
  - Purpose
    - Who has access to the SRS
    - How it should be used
  - Scope
		- Software benefits
- Constraints, assumptions, dependencies
  - **Constraints:** how the software must operate under given conditions
  - **Assumptions:** required OS or hardware
  - **Dependencies:** on other software products
- Requirements
  - **Functional:** functions of the software
  - **External interface:** users and interactions with other hardware or software
  - **System features:** functions of the system
  - **Non-functional:** performance, safety, security, quality
	  
**2) User requirements specification (URS)**
- Describe business need and end-user expectations
- **User stories:**
  - Who is the user?
  - What is the function that need to be performed?
  - Why does the user want this functionality?
- Confirmed during user acceptance testing
- Often combined into the SRS
  
**3) System Requirements Specification (SysRS)**
- Outlines requirements of the system
- Broader than an SRS
- Contains;
  - System capabilities
  - Interface and user characteristics
  - Policy
  - Regulation
  - Personnel
  - Performance
  - Security
  - System acceptance criteria
  - Hardware expectations

# **The Software Building Process and Associated Roles**

## **Software Development Methodologies**
  
**Common development methodologies:**

A process is needed to clarify communication and facilitates information sharing among team members.

Some of these methodologies are:
- Waterfall

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-6.webp)

- V-shape model

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-7.webp)

- Agile

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-8.webp)

**Sequential vs. iterative:**

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-9.webp)

### Waterfall pros and cons
  
  ![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-10.webp)
### V-shape model pros and cons
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-11.webp)

### Agile pros and cons
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-12.webp)

## **Software Versions**

- Software versions are identified by version numbers,  indicate:
  - When the software was released
  - When it was updated
  - If any minor changes or fixes were made to the software
- Software developers use versioning to keep track of new software, updates, and patches
  
  **Version numbers:**
- Version numbers can be short or long, with 2, ,3, or 4 set
- Each number set is divided by a period
- An application with a 1.0 version number indicates the first release
- Software with many releases and updates will have a larger number
- Some use dates for versioning, such as Ubuntu Linux version **18.04.2** released in 2018 April, with a change shown in the third number set
  
  **What do version numbers mean?**
  
  Some version numbers follow the semantic numbering system, and have 4 parts separated by a period
- the first number indicates major changes to the software, such as a new release
- The second number indicates that minor changes were made to a piece of software
- The third number in the version number indicates patches or minor bug fixes
- The fourth number indicates build numbers, build dates, and less significant changes
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-13.webp)
  
  **Version compatibility:**
- Older versions may not work as well in newer versions
- Compatibility with old and new versions of software is a common problem
- Troubleshoot compatibility issues by viewing the software version
- Update software to a newer version that is compatible
- Backwards-compatible software functions properly with older versions of files, programs, and systems

## **Software Testing**

- Integrate quality checks throughout SDLC
- Purpose
  - Ensure software meets requirements
  - Error-free software
	  
**Test cases:**

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-14.webp)

### Three types of testing:
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-15.webp)

1) **Functional testing:**

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-16.webp)

The purpose of functional is to check:
- Usability
- Accessibility

2) **Non-functional testing**

Its attributes are:
- Performance
- Security
- Scalability
- Availability

Non-functional testing questions:
- How does the application behave under stress?
- What happens when many users log in at the same time?
- Are instructions consistent with behavior?
- How does the application behave under different OSs?
- How does the application handle disaster recovery?
- How secure is the application?

3) **Regression Testing**
- Confirms changes don’t break the application
- Occurs after fixes such as change in requirements or when defects are fixed

Choosing test cases for regression testing:

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-17.webp)

### Testing levels
  
Unit → Integration → System → Acceptance

1) **Unit testing**
- Test a module code
- Occurs during the build phase of the SDLC
- Eliminate errors before integration with other modules

2) **Integration testing**
- Identify errors introduced when two or more modules are combined
- Type of black-box test
- Occurs after modules are combined into larger application

Purpose of integration testing:

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-18.webp)

3) **System testing**
- Compliance with SRS
- Validate the system
- Functional and non-functional
- Staging environment

4) **Acceptance testing**

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-19.webp)

## **Software Documentation**

- Written assets
- Video assets
- Graphical assets
  
  **Product vs. process documentation:**
  
  | Product Documentation            | Process Documentation            |
  | -------------------------------- | -------------------------------- |
  | Relates to product functionality | Describes how to complete a task |

### Types of product documentation
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-20.webp)
  
1) **Requirements documentation**

Intended for the development team including developers, architects, and QA. Describes expected features and functionality.

It includes:
- SRS
- SysRS
- User acceptance specification

2) **Design documentation**

Written by architects and development team to explain how the software will be built to meet the requirements.
- Consists of both conceptual and technical documents

3) **Technical documentation**

Written in the code to help developers read the code:
- Comments embedded in code and working papers that explain how the code works, documents that record ideas and thoughts during implementation

4) **Quality Assurance documentation**

Pertains to the testing team’s strategy progress, and metrics:
- Test plans, test data, test scenarios, test cases, test strategies, and traceability matrices

5) **User documentation**

Intended for end-users to explain to operate software or help install and troubleshoot system:
- FAQs, installation and help guides, tutorials, and user manuals

### Standard operating procedures

- Accompanies process documentation
- Step-by-step instructions on how to accomplish common yet complex tasks
- Ex: organization specific instructions for check in code to a repository
- Types of SOPs
  - Flowcharts
  - Hierarchical
  - Step-by-step

### Updating documentation

- Must be kept up-to-date
- Documentation should be reviewed and updated periodically

## **Roles in Software Engineering Projects**

- Project manager / Scrum master
  
![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-21.webp)

- Stakeholders

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-22.webp)

- System / software architect

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-23.webp)

- UX Designer

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-24.webp)

- Developer

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-25.webp)

- Tester / QA engineer

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-26.webp)

- Site reliability / Ops engineer

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-27.webp)

- Product manager / Product owner

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-28.webp)

- Technical writer / Information developer

![The Software Development Lifecycle](/notes/ibm-devops-and-se/SDLC%20-%20The%20Software%20Development%20Lifecycle-29.webp)
