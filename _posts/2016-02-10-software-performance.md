---
layout: post
title: Softwre Performance
tag: announcement
date: 2016-02-10 12:57:03
---

## Importance 
* "“People will visit a Web site less often if it is slower than a close competitor by more than 250 ms.”" [from NY TImes](http://www.nytimes.com/2012/03/01/technology/impatient-web-users-flee-slow-loading-sites.html?pagewanted=all&_r=0)
* "the Apple iPhone 5 still has a dual core processor and 1 GB DDR2 RAM. But the magic is iPhone 5 is performing as good as any latest muscle Android phone" [Silicon Station](http://siliconstation.com/the-story-android-lag-ios/)


## Rules of Optimization
* Don Knuth says, "Premature optimization is the root of all evil."
* Ken Beck says, "Make it run, make it right, then, make it fast."

## Latency Numbers
* What every programmer should know (http://www.eecs.berkeley.edu/~rcs/research/interactive_latency.html)

## Examples of Performance Issues
* Unnecessary disk I/O
* Unnecessary memory copies
* Unnecessary SQL / database access
* Unnecessary network communication
* Unnecessary locking
* Unnecessary format conversion
* Too many indirections
* Unexpected interactions between system components
* Compiler options
* Bad data structures or algorithms
* Memory leaks / garbage collection

## Common Tricks for Performance Improvement
* Pre-computation
* Caching
* Prefetching
* Pipelining / Parallelizing
* Make things feel faster

Here is a [sample section from CS3281/2 Team Polaris, AY 14/15](images/polaris-proj-report-6.1.pdf)

