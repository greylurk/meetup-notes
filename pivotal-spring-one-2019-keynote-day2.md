Josh Long - Spring developer advocate
---

All about developers - Day 2

ONly the customer knows whether a product is good.  

Production is a beautiful place, we all want to be there. 

Continuous Deliver is the way to get to prod.  We like prod, we want to be in prod. 

CloudFoundry is the dev oriented place to run stuff. 

RabbitMQ is the cloud native message borker

Project Reactor

Steeltoe is .Net version of Spring Cloud

Apache Geode - In memory database

Spinnaker - Multicloud continous deliver platform

Spring - Everyone loves it, it's a beautiful, everyone loves its ASCII Art. 

[A Bootiful Podcast](https://soundcloud.com/a-bootiful-podcast)

Start.spring.io is the second best place on the interent, behind prod. 

Barbara Sanders - VP tech and Cheif Architect @ Home Depot.
---

Austin Resident. 

Home Depot is founded in 1978 - 2200 stores in Canada, USA, and Mexico. 

More than 400k employees. 

* Over 3500 Engineers - 6000 git commits a day. 
* 91% of the software is made in house

4 years ago, committed 11B dollars, 1000+ new engineers, Products and expiernces instead of projects

Culture Values, Central to the company

Corporate "HEadquarters" is named the Store Support Center. 

Orange Method - ongoing  education and onboarding. Internal software boot camp. 

Uses Agile & XP

Wearing orange aprons while coding makes them better.

Product-based approach means that the products endure, and terminating a product is a lot more of a business comittment than killing a project.

Remove Constraints: Let your devs deploy easier.

Provide the tools the Devs want. 

Encourage Collaboration (6-8 person squads, etc.)

Make the easy thing and the right thing the same thing.

500+ prod changes per week. 

Higher Quality software

Creating an environment attractive to over 1000 engineers

Used to have 50+ Sev 1 incidents per year, now have zero so far this year. 


Transforming your thinking
----
 * Mark Fisher - Senior Staff Engineer
 * Cornelia Davis - VP Tech

Complexity has increased in the last 30 years. 

John Von Neumann - Originally began applying computing to weather. Thought that we would eventually be able to 100% model the weather.  Turns out he underestimated computing, but massively underestimated the complexity of weather. 

New Approaches and new Tools for much more complex problems than we ever thought computers could solve. 

CLoud Native software is hightly distributed and subject to constant change. 

CLoud Native Principles
 * Immutability
 * Reactive
 * Reconciliation
 * Composition

kpack - Foundation of Pivotal Build Service
 - Watches for changes in your code, 

Event Streams are a great location to put your immutable objects. 

Spring Cloud Sloth

Reactor provides the Flux model.

Riff is a lambda deployer for kubernetes

Back to Josh Long
---
Welcoming Netflix Engineers

Netflix + Spring = where it's going to be in the future. 

Taylor Wicksel - Senior Software Engineer @ Netflix
---

Java Platform Team at Netflix

Own the dev experience for Java

Bould application generators and support Java Devs. 

Maintain shared libraries. Originally in-house, but now building a lot of Spring Boot plugins.

2018 - 8 Billion on new content. Netflix needed to support more than just customers, but also movie production stuff (capturing pitches, video streaming for directors on site)

Deliver to desktops, phones, embedded workstations. 

Developers choose
 * Rest, GRPC, 
 * RabbitMQ, Whatever. 

Benefits to the developers: 
Google and Stack Overflow
* Good Documentation
* Huge Ecosystem

Production Ready Features
* Metrics
* Deploy 
* Discoverability

Over 350 spring apps deployed to prod in Netflix today. 

Lessons Learned
* Stick with Spring Absractions
* Empower users to find their own solutions

Tom Gianos - SSE @ Netflix
---

Big Data Platform 

200PB of data on S3

Computer Cluster does Spark, Haddop, Presto

Genie - Big Data Orchestration service

Jobs run a variety of dimentions
 * Long Running
 * Ad Hoc vs Schedules
 * Local exec vs Cluster

[Open Source](https://netflix.github.io/genie)

A lot fo spring inside of Genie

Spring Deploy OSS internally

Stephan Maldini - Principal Software Engineer
---

Reactive was first discussed at Spring One in 2016

Write new features faster. 

Concurrency is a pain.

* Reactor 3.3
* Spring 5.2
* Spring Boot 2.2

Reactive Foundation
 - Promote Ractive Practices

RSocket and R2DBC are core to the Reactive story, need to be everywhere.

Kotlin Coroutine support
Improved Micrometer and Netty metrics

Violeta Georgieva
---

[Blockhound finds blocking code in reactive paths](https://github.com/reactor/BlockHound)
[RSocket](http://rsocket.io/)
[R2DBC](https://r2dbc.io/)

GM Guy
---
Speed is good, velocity is better.  That direction vector is important.

This whole session went on too long, and was too filled with management speak to be interesting.  
