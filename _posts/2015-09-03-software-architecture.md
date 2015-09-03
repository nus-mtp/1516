---
layout: post
title: Software Architecture and Design
tag: lecture
date: 2015-09-03 13:09:42 
---

If your team already has sufficient ideas about __what__ to implement for your project, it is now time to think about __how__ to implement it.  This step is where you _plan_ your implementation details, from what are the major components of the system, what languages/libraries/frameworks/databases to use, what algorithms/data structures to use, what the UI would look like, what are the key classes in your system, etc.  You may even start a small prototype to explore the options you have.  

For your project, the design and architecture are expected to change over time.  You should, however, still have _sufficiently detailed and stable design_ to move on to the implementation phase. 

In this lecture, I will recap some principles of good software design and explain what you are expected to go through for your software design process for this module.  Here is the outline:

#### What is software architecture?

+ e.g., "mobile" -> "cloud" -> "database" ?
+ e.g., "UI" -> "logic" -> "storage"?
+ e.g., "AngularJS" + "node.js" + "express" + "MySQL"?
   
#### What makes a good software architecture design?

+ low coupling
+ high cohesion
+ testable
+ independent of framework/UI/library
+ components are reusable
+ allow delays in implementation decisions
+ with future changes in mind

+ Sanity check
     + If I replace X with Y (e.g., MySQL with Postgresql), how much code would I need to change?
     + If the requirement changes  (e.g., user can now do X), how much code would I need to change?
     + What is the simplest way to test? (e.g., can I test without UI and without DB?)
    
#### What type of diagrams to draw?
 + no fix rules here, just be simple, clear, and consistent
 + can have more than one
 + be very clear yourselves what boxes and arrows mean
 + common mistake: e.g., an arrow means inheritance in some parts of diagrams, means the sequence of flow in other parts, and means passing data from one component to the next in yet another part.
+ rules of thumb: if a diagram is not readable on 1-page A4 print out, it is not useful 

#### Example 1: MVC
+ Model: abstraction that the data in the system
+ View: abstraction for how the users see the data; a view _presents_ a model
+ Controller: abstraction for how the users control the data; a control _modifies_ a model

MVC is originally proposed in the context of Smalltalk, where every UI component (e.g., a button) is a view.  Now it is used as if the whole Web page is a view, and that makes it a bit awkward sometimes.

#### Example 2: The Clean Architecture
The Clean Architecture, proposed by Uncle Bob, basically separates a system into: 
+ domain logic 
+ application logic
+ implementation details (UI, DB, frameworks, libraries), and 
+ adaptors, which form a layer of indirection between the application logic and the implementation details.

#### Design Decisions
When you need to decide which framework/library/algorithms, etc., to use, consider the "QOC":

+ Q: what is the question? E.g., "how do I perform OCR on the input image?" "what algorithm should I use for image matching?"
+ O: what are the options available? E.g., (i) write my own OCR engine; (ii) use Tesseract, an open source library; (iii) use Aspire, a proprietary software, (iv)...
+ C: what are the criteria? E.g., (i) fast and small enough to run within the time limit on iPhone 5, (ii) accurate enough, (iii) cheap, (iv) able to get it done quickly, (v) availability of technical support, etc ..

#### CS3283 Requirements
+ Keep track of your architectural design evolution. Please explain how it evolves over time (and why).
+ Document your detailed design decision clearly. Starts with the QOC, then argue the pros and cons of each option according to the criteria.
