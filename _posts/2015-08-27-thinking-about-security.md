---
layout: post
title: Thinking About Security
tag: lecture
date: 2015-08-27 11:34:07
---
Instead of going through another past project, I decided to change the lecture plan so that I can address something that I observe during the work sessions so far.  __There is a lack of consideration about security when you capture the software requirements__

I mentioned passing penetration test as a verifiable non-function requirements.  But including security consideration is more than meeting non-functional requirements.   Some functionalities have to be included into the system to ensure that the security of the system.  Security is not a feature.  It is a property that emerges after sufficient security-related mechanism is implemented.

Here are the outline for lecture today:

+ CIA: Three key properties of security:
    + Confidentiality
    + Integrity
    + Avaialbility
+ Security can often be included as a constraint (e.g., "precondition: user must be authenticated" for a "transfer money" use case)
+ Another way security can be specified is by saying what users should _not_ do.  
+ How to think about security:
     + Adding anti-behavior: misuse cases and abuser stories
     + Categories of threats:
         + **S**poofing: can the user pretend to be someone else?
         + **T**ampering: can the user temper with the data?
         + **R**epudiation: can the user deny ever performing an action?
         + **I**nformation disclosure: can the user see something he/she is not supposed to see? 
         + **D**enial of service: can the user overload or crash the system?
         + **E**levation of privilege: can the user gain more privilege than intended?
+ We can counter these with added constraints or functions.

### Example User Stories

1. As a customer I want to login with my username and password so that I access my
bank account online 
2. As a customer I want to transfer money to another account after I login
3. As a customer I want to be able to logout after I login
4.  As a costumer I want to reset my password so that if I forgot what my password is I will not loose access to my account.

+ What could be the abuser stories?
+ What can we add to the user stories to counter these abuser stories?

### Additional Readings
+ Johan Peeters's article on [Agile Security Requirement Engineering](http://www.johanpeeters.com/papers/abuser%20stories.pdf)
+ Guttorm Sindre & Andreas L. Opdahl's article on [Eliciting Security Requirements with Misuse Cases](http://www.researchgate.net/profile/Andreas_Opdahl/publication/226177413_Eliciting_security_requirements_with_misuse_cases/links/09e4150cbe4e161dbf000000.pdf)
+ MSDN article on [STRIDE](https://msdn.microsoft.com/en-us/library/ee823878(v=cs.20).aspx)
