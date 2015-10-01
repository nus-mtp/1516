---
layout: post
title: 5 Common Issues with Architecture Diagrams
tag: announcement
date: 2015-09-22 14:36:41
---

After a few rounds of discussions with most of the teams about the software architecture and design, a few common issues have emerged.  Let me document it here so that everyone is on the same page on what the common issues are. 

#### 1. The software architecture depicts high-level components that is responsible for many unrelated tasks.

To increase the cohesion of your design, a component should perform a small number of highly related tasks.  Try this: write down, as detail as you can, what each component in your architecture is supposed to do.  For instance, just saying "contains logic for DB" or "relay messages between UI and logic" is not detailed enough.  You should write down what type of logic is there, and what messages are relayed, etc.  

If you find that you have to write down many unrelated tasks, then this is a sign that you should further partition the component into smaller components.   As an example, if your component performs the tasks: (i) searching for the interested users in the database, and (ii) checking for users access right to the database, then instead of one "logic for DB" component, you can partition it into two, one called "User Finder", the other called "User Access Controller."

#### 2. The architecture diagrams depict arrows without labels.

The meaning of the arrows in the diagram should be clear.  Are they depicting dependencies? Data flows?  Sequence of invocations? Or something else?

You should decide what the arrows mean, then properly label them if it refers to the data flow between the components.

Similar to Item 1 above, if you find that you arrows capture too many types of data flowing between two components, then you should split the components and/or arrows.

One should be able to evaluate the amount of coupling between the components (and what resulted in the coupling) by looking at the architecture diagram.  If the components and arrows are too high level, then the coupling might not be visible, and this gets into the way of improving your design to remove the coupling.

#### 3. Pay attention to your domain logic and application logic.

I noticed that many of the proposed software architectures focus on the CRUD operations of the data.  To me, this portion of the software architecture, in a large part, is determined by the framework/platform chosen. 

What is more interesting and harder to decide, is how to fit your application/domain logic with the rest of the components, how to decompose the logic into smaller components with low coupling and high cohesion.  Most teams did not pay sufficient attention to this in the beginning.

#### 4. Choose meaningful names.

It is tempting to name your components "Something Manager," "Something Controller," "Something Logic," etc.  These are generic names that do not reflect what each component is doing.  It is a sign that the responsibility of the component is either not well thought out, or it has too many "rojak" responsibilities that you can find a good name.

Writing down the responsibilities of each component explicitly, as in Item 1 above, will help you to find the right _agent noun_ to call the component.  

#### 5. Overuse of the Facade pattern.

Some teams have used the facade pattern to communicate between client/server, or different layers of the architecture.

The facade pattern is useful to hide the complexity of the underlying components.  It is most useful when we do not have access to, or ability to modify, the underlying components (e.g., we use an external library).  

Most of the usage scenarios of the facade pattern in your design, however, does not fit into the use cases, and the facade could be removed to expose the underlying components directly.  If indeed the exposed components are too complex, then you should consider redesigning and simplifying the components first, before slabbing a facade over them to "sweep the complexity under the rug".
