---
title: "Strategies for Secure Interaction Design: authority, guidelines for interface design"
linkTitle: "Strategies for Secure Interaction Design"
date: 2022-08-24 16:20:00 +0500
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
collapsibleMenu: true
alwaysOpen: false
weight: 4
---

## **Strategies for Secure Interaction Design: authority, guidelines for interface design**

- It's the user who is making security decision, so, keep user in mind when designing security systems.

### Authority Guidelines

- Match the easiest way to do a task with the least granting of authority.
  + What are typical user tasks?
  + What is the easiest way for the user to accomplish each task?
  + What authority is granted to software and other people when the user takes the easiest route to completing the task?
  + How can the safest ways of accomplishing the task be made easier and vice versa?
- Grant authority to others in accordance with user actions indicating consent.
  + When does the system give access to the user's resources?
  + What user action grants that access?
  + Does the user understand that the action grants access?
- Offer the user ways to reduce other's authority to access the user's resources.
  + What kind of access does the user grant to software and other users?
  + Which types of access can be revoked?
  + How can the interface help the user find and revoke access?

### Authorization and Communication Guidelines

- Users should know what authority other's have.
  + What kind of authority can software and other users hold?
  + What kind of authority impact user decisions with security consequences?
  + How can the interface provide timely access to information about these authorities?
- User should know what authority they themselves have.
  + What kind of authority does the user hold?
  + How does the user know they have that authority?
  + What might the user decide based on their expectation of authority?
- Make sure the user trust the software acting on their behalf.
  + What agents manipulate authority on the user's behalf?
  + How can users be sure they are communicating with the intended agent?
  + How might the agent be impersonated?
  + How might the user's communication with the agent be corrupted/intercepted?

### Interface Guidelines for Usable Security

- Enable the user to express safe security policies that fit the user's task.
  + What are some examples of security policies that users might want enforced for typical tasks?
  + How can the user express these policies?
  + How can the expression of policy be brought closer to the task?
- Draw distinction among objects and actions along boundaries relevant to the task.
  + At what level of details does the interface allow objects and actions to be separately manipulated?
  + What distinction between affected objects and unaffected objects does the user care about?
- Present objects and actions using distinguishable, truthful appearances.
  + How does the user identify and distinguish different objects and actions?
  + In what ways can the means of identification be controlled by other parties?
  + What aspects of an object's appearances are under system control?
  + How can those aspects be chosen to best prevent deception?
