---
title: "Working DevOps"
date: 2023-05-15 08:31:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: thesajid@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 3
---

## **Taylorism and Working in Silos**
  
  **Working DevOps:**
- Culture of teaming and collaboration
- Agile development as a shared discipline
- Automate relentlessly
- Push smaller releases faster
  
  **Taylorism:**
- Adoption of command and control management
- Organizations divided into functional silos
- Decision-making is separated from work
  
**Impact of Taylorism on IT:**

![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps.webp)
  
  **Software development is bespoke:**
- Software development is **NOT** like assembling automobiles
- Most of the parts don’t exist, yet
- Software development is craft work
- Taylorism is not appropriate for craft work
  
  **Abandon Command and Control:**
- Command and control is not Agile
- Stop working in silos
- Let your people amaze you

## **Software Engineering vs. Civil Engineering**
  
  **Software engineering is organic:**
- Software stack is constantly updated
- New features are being added
- System behavior changes over time
- Yet we treat software engineering like a civil engineering project
  
  **The project model is flawed:**
- The project model doesn’t work for software development
- Treat software development like product development
- Encourage ownership and understanding
- Software engineering is not civil engineering
- Maintain stable, lasting teams

## **Required DevOps Behaviors**
  
  **Diametrically opposed views:**
- Enterprises see “new” as complex and time-consuming
- DevOps delivers a continual series of small changes
- These cannot survive traditional overheads
  
**A clash of work culture:**

![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-1.webp)

  **The no-win scenario:**
- Development wants innovation
- Operations wants stability
  
![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-2.webp)
  
  **Operations view of development:**
- Development teams throw dead cats over the wall
- Manually implemented changes
- Lack of back-out plans
- Lack of testing
- Environments that don’t look like production
  
  **Development view of operations:**
- All-or-nothing changes
- Change windows in the dead of night
- Implemented by people furthest away from the application
- Ops just cuts and pastes from “runbooks”
  
  **No-win scenario:**
- If the website works, the developers get the praise!
- If the website is down, operations gets the blame!
  
  **Required DevOps behaviors:**
  
![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-3.webp)

## **Infrastructure as Code**

- Described an executable textual format
- Configure using that description
- Configuration Management Systems to make this possible (Ansible, puppet etc.)
- Never perform configurations manually
- Use version control
  
  **Ephemeral immutable infrastructure:**
- Server drift is a major source of failure
- Servers are cattle not pets
- Infrastructure is transient
- Build through parallel infrastructure
  
  **Immutable delivery via containers:**
- Applications are packaged in containers
- Same container that runs in production can be run locally
- Dependencies are contained
- No variance limits side effects
- Rolling updates with immediate roll-back
  
  **Immutable way of working:**
- You never make changes to a running container
- You make changes to the image
- Then redeploy a new container
- Keep images up-to-date

## **Continuous Integration (CI)**
  
  **CI vs. CD:**
- CI/CD is not one thing
- Continuous Integration (CI):
	- Continuously building, testing, and merging to master
- Continuous Delivery (CD):
	- Continuously deploying to a production-like environment
	  
	  **Traditional Development:**
- Devs work in long-lived development branches
- Branches are periodically merged into a release
- Builds are run periodically
- Devs continue to add to the development branch
  
![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-4.webp)

### Continuous Integration

- Devs integrate code often
- Devs work in short-lived feature branches
- Each check-in is verified by an automated build
  
![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-5.webp)
  
  **Changes are kept small:**
- Working in small batches
- Committing regularly
- Using pull requests
- Committing all changes daily
  
  **CI automation:**
- Build and test every pull request
- Use CI tools that monitor version control
- Test should run after each build
- Never merge a PR with failing tests
  
  **Benefits of CI:**
- Faster reaction times to changes
- Reduced code integration risk
- Higher code quality
- The code in version control works
- Master branch is always deployable

## **Continuous Delivery**
  
  > “Continuous Delivery is a software development discipline where you build software in such a way that the software can be released to production at any time.” — Martin Fowler
  
  **Release to production at any time:**
- The master branch should always be ready to deploy
- You need a way to know if something will “break the build”
- Deliver every change to a production-like environment

### CI/CD pipeline:

- Automated gates that create a pipeline of checks:
  - Unit testing
  - Code quality checks
  - Integration testing
  - Security testing
  - Vulnerability scanning
  - Package signing
 
**A CI/CD pipeline needs:**
- A code repository
- A build server
- An integration server
- An artifact repository
- Automatic configuration and deployment
  
**Continuous integration and delivery:**

![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-6.webp)

**Five key principles:**

1. Build quality in
2. Work in small batches
3. Computers perform repetitive tasks, people solve problems
4. Relentlessly pursue continuous improvement
5. Everyone is responsible

**CI/CD + Continuous deployment:**

![Working DevOps](/notes/ibm-devops-and-se/Working%20DevOps-7.webp)

**How DevOps manages risk:**
- Deployment is king
- Deployment is decoupled from activation
- Deployment is not “one size fits all”
