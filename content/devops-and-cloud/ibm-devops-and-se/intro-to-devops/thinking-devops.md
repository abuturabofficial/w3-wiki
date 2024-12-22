---
title: "Thinking DevOps"
date: 2023-05-09 11:36:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 2
---

## **Social Coding Principles**
  
  **What is social coding?**
- Open source practice
- All repos are public
- Everyone is encouraged to contribute
- Anarchy is controlled via Pull Requests
  
  **Code reuse dilemma:**
- Code has 80% of what you need, but 20% is missing
- How do you add 20% missing features?
	- Make a feature request and depend on another team?
	- Rebuild 100% of what you need (no dependencies)

**Social Coding Solution:**
- Discuss with the repo owner
- Agree to develop it
- Open an **Issue** and assign it to yourself
- **Fork** the code and make your changes
- Issue a **Pull Request** to review and merge back
  
  **Pair Programming:**
- Two programmers on one workstation
- The driver is typing
- The navigator is reviewing
- Every 20 minutes they switch roles
  
  **Pair programming benefits:**
- Higher code quality
- Defects found earlier
- Lower maintenance costs
- Skills transfer
- Two set of eyes on every line of codebase

## **Git Repository Guidelines**

- Create a separate Git repository for every component
- Create a new branch for every Issue
- Use PRs to merge to master
- Every PR is an opportunity for a code review
  
  **Git feature branch workflow:**
  
![Thinking DevOps](/notes/Thinking%20DevOps.png)

## **Working in Small Batches**

- Concept from Lean Manufacturing
- Faster feedback
- Supports experimentation
- Minimize waste
- Deliver faster
  
  **Small batch example:**
  
  You need to mail 1000 brochures:
- Step 1: Fold brochures
- Step 2: Insert brochures into envelopes
- Step 3: Seal the envelopes
- Step 4: Stamp the envelopes with postage
  
**Batch of 50 brochures:**

![Thinking DevOps](/notes/Thinking%20DevOps-1.png)

**Single Piece Flow:**

![Thinking DevOps](/notes/Thinking%20DevOps-2.png)

### Measuring the size of batches

- Feature size supports frequent releases
- Features should be completed in a sprint
- Features are a step toward a goal, so keep them small

## **Minimum Viable Product (MVP)**

- MVP is not “Phase 1” of a project
- MVP is an experiment to test your value hypothesis and learn
- MVP is focused on learning, not delivery
- At the end of each MVP, you decide whether to pivot or persevere
  
**Minimum Viable Product Example:**

![Thinking DevOps](/notes/Thinking%20DevOps-3.png)

### Gaining an understanding

- MVP is a tool for learning
- The experiment may fail and that’s okay
- Failure leads to understanding
- What did you learn from it?
- What will you do differently?

## **Test Driven Development (TDD)**
  
**The importance of testing:**

> “If it’s worth building, it’s worth testing. If it’s not worth testing, why are you wasting your time working on it?”
— Scott Ambler

### **What is test driven development?**

- Test cases drive the design
- You write the tests first then you write the code to make the test pass
- This keeps you focused on the purpose of the code
- Code is of no use if your client can’t call it
  
  **Why devs don’t test:**
- I already know my code works
- I don’t write broken code
- I have no time

#### Basic TDD workflow
  
![Thinking DevOps](/notes/Thinking%20DevOps-4.png)
  
**Why is TDD important for DevOps?**
- It saves time when developing
- You can code faster and with more confidence
- It ensures the code is working as expected
- It ensures that future changes don’t break your code
- In order to create a DevOps CI/CD pipeline, all testing must be automated

## **Behavior Driven Development (BDD)**

- Describes the behavior of the system from the outside
- Great for integration testing
- Uses a syntax both devs and stakeholders can easily understand
  
**BDD vs. TDD:**
- BDD ensures that you’re building the “**right thing**”
- TDD ensures that you are building the “**thing right**”
  
![Thinking DevOps](/notes/Thinking%20DevOps-5.png)

### BDD workflow

- Explore the problem domain and describe the behavior
- Document the behavior using Gherkin syntax
- Use BDD tools to run those scenarios
- One document that’s both the specification and the tests
  
  **Gherkin:**
- An easy-to-read natural language syntax
- Given … When… Then…
- Understandable by everyone
  
  **Gherkin Syntax:**
- Given (some context)
- When (some event happens)
- Then (some testable outcome)
- And (more context, events, or outcomes)

**Retail BDD example**

![Thinking DevOps](/notes/Thinking%20DevOps-6.png)

**Gherkin for acceptance criteria:**
- Add acceptance criteria to every user story
- Use Gherkin to do that
- Indisputable definition of “done”

### Expected benefits of BDD

- Improves communication
- More precise guidance
- Provides a common syntax
- Self-documenting
- Higher code quality
- Acceptance criteria for user stories

## **Cloud Native Microservices**
  
**Think differently about application design:**

![Thinking DevOps](/notes/Thinking%20DevOps-7.png)

**Think cloud native:**
- The Twelve-Factor App
- A collection of stateless microservices
- Each service maintains its own database
- Resilience through horizontal scaling
- Failing instances are killed and respawned
- Continuous Delivery of services

**Think microservices:**

>“The microservices architectural style is an approach to developing a single application as a **suit of small services**, each **running in its own process** and communicating with lightweight mechanisms, often an HTTP resource API. These services are **built around business capabilities** and **independently deployable** by fully automated deployment machinery.”
— Martin Fowler and James Lewis

### Monolith vs. Microservices
  
![Thinking DevOps](/notes/Thinking%20DevOps-8.png)

## **Designing for Failure**
  
**Failure happens:**
- Embrace failures – they will happen!
- How to avoid –> How to identify and what to do about it
- Operational concern –> developer concern
- Plan to be throttled
- Plan to retry (with exponential back off)
- Degrade gracefully
- Cache when appropriate
  
**Retry pattern:**

![Thinking DevOps](/notes/Thinking%20DevOps-9.png)

**Circuit Breaker pattern:**

![Thinking DevOps](/notes/Thinking%20DevOps-10.png)

**Bulkhead pattern:**

![Thinking DevOps](/notes/Thinking%20DevOps-11.png)
  
**Chaos engineering:**
- Also known as monkey testing
- You deliberately kill services
- Netflix created The Simian Army tools
- You cannot know how something will respond to a failure until it actually fails
