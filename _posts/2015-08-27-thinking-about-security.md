---
layout: post
title: Thinking About Security
tag: lecture
date: 2015-08-27 11:34:07
---
Instead of going through another past project, I decided to change the lecture plan so that I can address something that I observe during the work sessions so far.  __There is a lack of consideration on security when you capture the software requirements__

I mentioned passing penetration tests as a verifiable non-functional requirement.  But building a secure system is more than meeting non-functional requirements.   Some functionalities have to be included into the system to ensure the security of the system.  Security is not a feature.  It is a property that emerges after sufficient number security-related mechanisms are implemented.

Here are the outline for lecture today:

+ CIA: Three key properties of security:
    + Confidentiality
    + Integrity
    + Availability
+ Security can often be included as a constraint (e.g., "precondition: user must be authenticated" for a "transfer money" use case)
+ Another way security can be specified is by saying what users should _not_ do.  
+ How to think about security:
     + Adding anti-behavior: misuse cases and abuser stories
     + Categories of threats:
         + **S**poofing: can the user pretend to be someone else?
         + **T**ampering: can the user tamper with the data?
         + **R**epudiation: can the user deny ever performing an action?
         + **I**nformation disclosure: can the user see something he/she is not supposed to see? 
         + **D**enial of service: can the user overload or crash the system?
         + **E**levation of privilege: can the user gain more privilege than intended?
+ We can counter these anti-behavior with added constraints or functional requirements.

### Example User Stories

1. As a __customer__ I want to __login with my username and password__ so that __I can access my bank account online__ 
2. As a __customer__ I want to __transfer money to another account after I login__
3. As a __customer__ I want to __be able to logout after I login__
4.  As a __costumer__ I want to __reset my password when I forgot what my password is__ so that __I will not lose access to my account__.

+ What could be the abuser stories?
+ What can we add to the user stories to counter these abuser stories?

### Additional Readings
+ Johan Peeters's article on [Agile Security Requirement Engineering](http://www.johanpeeters.com/papers/abuser%20stories.pdf)
+ Guttorm Sindre & Andreas L. Opdahl's article on [Eliciting Security Requirements with Misuse Cases](http://www.researchgate.net/profile/Andreas_Opdahl/publication/226177413_Eliciting_security_requirements_with_misuse_cases/links/09e4150cbe4e161dbf000000.pdf)
+ MSDN article on [STRIDE](https://msdn.microsoft.com/en-us/library/ee823878(v=cs.20).aspx)