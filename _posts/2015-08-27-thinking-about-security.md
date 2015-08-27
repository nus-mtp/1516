---
layout: post
title: Thinking About Security
tag: lecture
date: 2015-08-27 11:34:07
---
Instead of going through another past project, I decided to change the lecture plan so that I can address something that I observe during the work sessions so far.  __There is a lack of consideration on security when you capture the software requirements__

I mentioned passing penetration tests as a verifiable non-functional requirement.  But building a secure system is more than meeting non-functional requirements.   Some functionalities have to be included into the system to ensure the security of the system.  Security is not a feature.  It is a property that emerges after sufficient number security-related mechanisms are implemented.

<!--more-->

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

### Example: Initial User Stories

1. As a __customer__ I want to __login with my username and password__ so that __I can access my bank account online__ 
2. As a __customer__ I want to __transfer money to another account after I login__
3. As a __customer__ I want to __be able to logout after I login__
4.  As a __costumer__ I want to __reset my password when I forgot what my password is__ so that __I will not lose access to my account__.

### Example: Abuser Stories

To help us come up with requirements that improve the security of the system, we can come up with a list of abuser stories -- stories told from a malicious user point of view.  Here are what you came up with in the class.

1. As a thief, I want to try all possible passwords for a user so that I can login as that user.

2. As a thief, I want to install keylogger on a computer so that I can steal the passwords of users using that computer.

3. As a thief, I want to have physical access to the machine that the user is using so that I can access the user's account after he/she has logged in (but before he/she logged out).

4. As a thief, I want to sniff the packets between user and the bank so that I can steal the password of a user and login as that user later.

5. As a thief, I want to exploit a system vulnerability so that I can access a user account without logging in.

Note: you came up with other "creative" ways of stealing password that is outside of the system (e.g., beat the password out of the user) which I omitted here.
### Additional User Stories

With the abuser stories in mind, we need to think about what new requirements we can add to the system to prevent the abuser stories.  Here are what you came up with during the lecture.

1. As a system, I want to disable a user account after three failed login attempts by the user.
    + Mitigates Abuser Story 1

2. As a system, I want the user to solve a CAPTCHA when they login so that I know the password is submitted by a human. 
    + Mitigates Abuser Story 1

3. As a user, I want to have the option to enter my password using a software keyboard so that my password cannot be logged by a keylogger.
    + Mitigates Abuser Story 2

4. As a system, I want to automatically logged out a user that is inactive for 5 minutes.
    + Mitigates Abuser Story 3 

5. As a system, I want to encrypt all my customers' username and password before they are sent over the Internet.
     + Prevents Abuser Story 4

6. As a system administrator, I want to detect any intrusion into the system. 
     + Mitigates Abuse Story 5

7. As a system, I want to log all access to the system.

8. As a system, I want to log all transactions in the system.

9. As a system, I want to backup all my data and my logs.

10. As a system, I want the user to key in a one-time password when they login.

11. As a user, I want to set a limit to how much money I can transfer.

12. As a user, I want to be notified whenever there is a money transferred out of my account.

New user stories 7-12 strengthen the authentication process in general, allow restoration of user account, allow tracing back the thief, alert users of possible theft, and mitigate the lost of money in case of theft.  

### Additional Readings

+ Johan Peeters's article on [Agile Security Requirement Engineering](http://www.johanpeeters.com/papers/abuser%20stories.pdf)

+ Guttorm Sindre & Andreas L. Opdahl's article on [Eliciting Security Requirements with Misuse Cases](http://www.researchgate.net/profile/Andreas_Opdahl/publication/226177413_Eliciting_security_requirements_with_misuse_cases/links/09e4150cbe4e161dbf000000.pdf)
+ John Neil Ruck and Geraint Price's article on [Misuse Cases:Earlier and Smarter Information Security](http://media.techtarget.com/searchSecurityUK/downloads/RHUL_Ruck_final.pdf)

+ MSDN article on [STRIDE](https://msdn.microsoft.com/en-us/library/ee823878(v=cs.20).aspx)
