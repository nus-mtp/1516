---
layout: post
title: Software Tools/Library
tag: lecture
date: 2016-03-18 01:53:10 +0800
---

In this lecture, I will share with you some tools that might be useful for your project.  Not all tools apply to all projects, but it should give you an idea to look for similar tools that suit the programming language or operating system you are using.  This list is not exhaustive, and I don't have first hand experience with many of them.  

## Message Passing Formats

Almost all teams passes information around between client and server in JSON format.  JSON is human readable so it is great for debugging, but it is bloated in size since it is encoded in plain text.  

To address this problem, there are several frameworks that provide binary serialization of JSON data. [messagepack](http://msgpack.org/index.html) is one of them.  If it turns out that transferring JSON data is a bottleneck for your project, you may want to consider this library.

## Linting Tools
A linting tool perform static analysis on your code to check for style inconsistency, ensure good and professional coding habits, and identify potential bugs.  Think of it as a _computer-assisted code review_.

* [```eslint```](http://eslint.org) for Javascript
* [```swiftlint```](https://github.com/realm/SwiftLint) and [```oclint```](http://oclint.org) for iOS projects.  XCode has built-in code analyzer (Product -> Analyze)
* [```prospector```](https://github.com/landscapeio/prospector) for Django
* Android Studio comes with its own ```lint```
* [```phpcs```](http://pear.php.net/package/PHP_CodeSniffer/redirected) and [others](http://phpqatools.org)

Most of these tools allow configuration of rules -- what do you want to, or do not want to, detect.

## Virtual Development Environments

[Vagrant](https://www.vagrantup.com) is a really cool and simple way of creating a virtual development environment.  It allows a developer to easily setup and teardown an environment when switching between different projects, ensures different developers on the same team work on the same environment (even if they run different OSes), and simulate deployment environment locally.  

You can choose from a large catalogue of [boxes](https://atlas.hashicorp.com/boxes/search), which are basically pre-configured virtual development environments (e.g., [here is one](https://atlas.hashicorp.com/ncaro/boxes/php7-debian8-apache-nginx-mysql) with MySQL 5.5/PHP 5.4/Apache 2.2, and [another one](https://atlas.hashicorp.com/cbumgard/boxes/nodejs) with Node.js, MongoDB, Redis, Heroku and Travis-CI).

## OWASP Zed Attack Proxy (ZAP)

[```ZAP```](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project) is a security tool that helps you find security vulnerability.  __DO NOT USE ZAP ON ANY WEBSITE OTHER THAN YOUR OWN !!__  ZAP runs as a proxy between your browser (some browser configuration needed) and your server.  ZAP can launch an attack on your server to find any common vulnerability.

## Network Traffic Controller

Most of you runs your client and your server on the same host, or on two hosts belonging to the same network.  Such setup is convenient for development, but does not provide realistic network conditions to test your client and server.  You might find that your application is fast and responsive on your laptops, only for it to crawl when you deployed it onto a cloud server.  

Traffic controllers are tool that change your laptop network conditions so that it simulates a more realistic network condition (limited bandwidth, higher delay, packet losses, etc.).  So that you can run your client and server under more relistic network conditions.

Mac users can [download](https://developer.apple.com/downloads/?name=for%20Xcode) ```Network Link Conditioner``` as a developer's tool from Apple.  This tool is provided as part of the Hardware IO Tools.  Note that it does not work on localhost/127.0.0.1.  Adventurous students can check out ```dnctl```.

Linux users can use [```tc```](http://www.tldp.org/HOWTO/html_single/Traffic-Control-HOWTO/), which is usually bundled together.  The command line arguments, however, are pretty complex.

Chrome has a built-in [throttling mode](https://developer.chrome.com/devtools/docs/device-mode#network-conditions) but it works only for traffic from/to Chrome only.

## Server load testing

[```ab```](https://httpd.apache.org/docs/2.4/programs/ab.html)  is a web server benchmarking tool that allows developers to generate multiple requests to the server.  This is a very useful tool to stress test the system, as well as to help with profiling the server.

## Code Beautifier

To ensure consistent coding style, use a beaufitier, which can automatically reindent and reformat your code following a given configuration (e.g., use spaces or tab, how much to indent, etc.)

The following might be useful:

* [```js-beautify```](https://www.npmjs.com/package/js-beautify)
* [```ruby-beautify```](https://github.com/erniebrodeur/ruby-beautify)
* [```autopep8```](https://pypi.python.org/pypi/autopep8) formats Python code according to PEP8 recommended style
* [```jalopy```](https://github.com/lukespragg/jalopy) is for Java

XCode and Android Studio comes with built-in indenter, but I find them less configurable than CLI tools in general.

## Profiling

Profiling a code involves running the code and collect usage statistics during run-time.  This typically gives you the time taken to call a function (or to execute a line) plus the number of times a function/a line has been executed.  Looking at the data, we might identify bottleneck within our code.

* Django comes with pretty good [profiling support](https://code.djangoproject.com/wiki/ProfilingDjango).  There is also [```silk```](https://github.com/django-silk/silk).
* For Ruby, see [here](http://guides.rubyonrails.org/v3.2.13/performance_testing.html)
* ```node``` has built-in profiler.  First run ```node``` with ```--prof``` to create a profiler's output, then run with ```--prof-process``` to produce human readable results.

XCode and Android Studio comes with built-in profiler to instrument your code.
