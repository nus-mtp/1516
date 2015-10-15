---
layout: post
title: Let's Code
tag: lecture
date: 2015-10-07 15:37:00 
---

Several team is now ready to start the coding sprints, so I am moving this lecture forward by a week.


### Code sprint

* Getting a usable prototype out every sprint
* Timeboxed effect: whatever gets done during the sprint, ship it.
* Make sure high impact, important features are implemented first.
* Ideal sprint length for CS3283/4: 2-3 weeks
* End of sprint: **integrated, tested, potentially shippable**
* Use tools (such as Kanban) to visualize the state of the project

<!--more-->

### Task prioritization

* Plan what to achieve at the end of every sprint
* Prioritize task based on dependencies, importance of features, effort estimation.
* Plan one sprint at a time
* Each task must fit into a sprint (if not, break it down into smaller tasks).
* Agile lingo: Tasks are called _work items_.  _Product backlog_ is a sorted list of work items, in decreasing order of priority.

### Software development estimation techinique
 * Estimate the time/effort needed to complete a task, as a team.
* "Despite decades of research, there is no consensus on which software effort estimation methods produce the most accurate models." -- Ekrem Kocaguneli, Tim Menzies, and Jacky Keung. "On the value of ensemble effort estimation", TSE 2011.
* The effort-accuracy curve of software estimation ([Cohn, Figure 6.1](http://www.mountaingoatsoftware.com/system/asset/file/15/aep_sample.pdf)) 
* Two methods used: 
    * [Use Case Points](http://en.wikipedia.org/wiki/Use_Case_Points)
	    * What is the UCP of your project?  
	* [COCOMO (Constructive Cost Model)](https://en.wikipedia.org/wiki/COCOMO)
		* Check out [COCOMO II online estimator](http://csse.usc.edu/tools/COCOMOII.php)
    * Story Points:
		* Estimate *complexity*, not time needed to implement a story (or feature, or use case, or component)
		* Story point/Time is the velocity.  Estimate velocity based on how many story points you get to finish in the past iterations.
		* A task with k points takes k times as long to complete than a task with 1 point.  
		* Benchmark yourself with a task that is a 2 and another task that is a 5.
		* Estimate the rest.  
		* Ideal Time: How long would it take for you to implement the story, if (i) there is no interruption, (ii) you know what needs to be done, and (iii) you have everything you need.
		* Elapsed Time = (1 + overhead)*Ideal Time
		* [Planning Poker](https://www.mountaingoatsoftware.com/agile/planning-poker) is a technique to estimate story points.  It should be fun and educational to try out -- your milage on accuracy may vary.

### Writing professional quality code
* Coding is not just about writing code.  It is about **communicating with other developers** using code, comments, commit messages, API documentations, developers' guide etc.  Getting the code to compile and run correctly is just a small part of the process.  Take time to communicate properly.
* Your reputation as a software engineer depends on your code (extreme case: github is your resume).
* Review your CS2103's Handouts/Slides on _Good Code, Bad Code_.
* Properties of Good Code:
    * Correct
	* Cheanglable 
	* Readable (by human)
	* Extensible
	* Maintainable (Boehm's curve; common to have a cost of 100:1 after delivery)
* [Check out Page 1-2 of the _Clean Code Cheat Sheet_](http://www.planetgeek.ch/2013/06/05/clean-code-cheat-sheet/) for the dos and don'ts for writing clean code.
* Advices:
	* Don't try to be clever or terse 
	* Make your code self-explanatory (write as little comment as possible)
	* Comments are for high-level descriptions (what and why)
	* Use English
	* Don't be afraid of long names (thanks to autocomplete) (e.g., ``StudentViewController *studentViewController = [storyboard instantiateViewControllerWithIdentifier:@"StudentViewControllerID"]``)
	* Use tools to indent/format your code
	* Don't underestimate the importance of indentation ([see Apple's goto fail bug](http://www.wired.com/2014/02/gotofail/))
* Learning to write good code
	* practice: write and rewrite
	* read good code from others
													    
### Code review
* "Rigorous inspections can remove up to 90% of errors from a software product before the first test case is run." -- “Facts and Fallacies of Software Engineering,” Robert Glass.
* "The average defect detection rate is only 25% for unit testing, 35% for function testing, and 45% for integration testing. In contrast, the average effectiveness of design and code inspections are 55 and 60%." -- - “Code Complete,” Steve McConnell.
* Best practices [by SmartBear](http://smartbear.com/SmartBear/media/pdfs/WP-CC-11-Best-Practices-of-Peer-Code-Review.pdf)
    * review small chunk (<400 lines) at a time
	* take you time
	* author should make sure code is ready before review (self-review, tested, make code readable)
	* keep a checklist of common errors
	* be positive (finding bugs is a good thing)
	
### Good Practices Using Git
* [Gitflow Workflow](http://nvie.com/posts/a-successful-git-branching-model/)
* Commit often and [write good commit message](https://github.com/erlang/otp/wiki/Writing-good-commit-messages)
* [Good practices](http://www.slideshare.net/TarinGamberini/commit-messages-goodpractices) by Tarin Gamberini
* Describe specifically what has changed and **why**
* [Humor](http://i.imgur.com/3POtveC.jpg) 

### Test-driven development
* We will adopt TDD-redux in CS3283/4
    * Automate testing process
	* Write test cases for every sprint
	* Testing concurrently with development
* Goal: to have a peace of mind that your changes did not break anything.

### Continuous integration
* Integrate your code with the rest and test as soon as you push
* Why?
    * Everyone can see everything
	* You know what is broken immediately and can fix immediately
	* Contrast to: intergrate at the end (usually crunch time) and you don't know whether it will work!  (e.g., HealthCare.gov launch disaster).
* Good habit for CI
    * Keep the build/test process fast
    * Commit often, push often (to the main branch)
* Read [Martin Fowler's excellent article on CI](http://www.martinfowler.com/articles/continuousIntegration.html)

### Putting Everything Together
* Every sprint
    * Clean up code as needed
	* Have code written reviewed by another peer
	* Merge code into the main branch
	* Tested (with CI where applicable)

### Further readings: 
* [The failure of HealthCare.gov, one of the most disastrous software rollout in history and how it is saved.] (http://rust-class.org/static/classes/class12/healthcaregov.html)  Lessons: 
   * Continous integration and testing is important
   * Pay attention to scalability and performance
* Chapter on ["Techniques for Estimating"](http://www.mountaingoatsoftware.com/system/asset/file/15/aep_sample.pdf) in the Book "Agile Estimating and Planning" by Mike Cohn.  The book is [summarized here](http://www.mountaingoatsoftware.com/uploads/presentations/Agile-Estimating-Planning-Agile-Development-Practices-2008.pdf).
* [What We Do and Don't Know about Software Development Effort Estimation](http://www.infoq.com/articles/software-development-effort-estimation)
