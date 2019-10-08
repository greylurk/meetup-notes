Keynote from Spring One 2019
===

SpringOne Platform
---
Enabling Cloud Native for Enterprise Devs

(Oh god, i'm an Enterprise dev? Ewww.)

Cloud Native Open Source

Continuous Delivery is hot (since 2000)

What's in vs Whats Out?
---
* In
  * Containerized
  * Dev Centric
  * CI/CD Friendly
  * Testable
  *  Just another Boot App
* Out
  * Slowing down developers
  * Proprietary or hosted only API Gateways
  * Proprietary integration/ESB
  * Proprietary ETL
  * ITIL

Cloud Native Infrastucture and Cloud Native App Infrastructure

* PCF - Pivotal Cloud Foundry - 

VMWare + Pivotal announcement

Tanzu - VMWare Product based around Kubernetes 
 - Any Cloud
 - Standard Kubernetes pitch, Devs first blah blah blag.

VMWare owns Bitnami, Pivotal and Heptio

Run - "Project Pacific" and VMWare PKS
Build - Bitnami, Spring, Pivotal
Manage - Tanzu & Heptio

Marketspeak: VMWare wants to open source... So much open source.  All the best open source. Kubernetes open source open source kubernetes. 

Pivotal was once part of VMWare anyhow, now VMWare sees why they were valuable, and Kubernetes has proven to them that Open Source is good.

Cornelia Davis
---

```bash
$ cf push # THIS IS IMPORTANT
```

Cloud Foundry was early into the Kubernetes/Container/Scheduler etc. world. Backing into the container world now.

Lots of cloudy stuff. K8s, Dynamic Routing, Load Balancing, Short tennancy, etc. 

Cloud Native Paterns 

[Spring Start](https://start.spring.io) - Growing at 64% a year, 15M projects per year (Probably mostly learning projects, but hey, that's like 2 a second)

Monolith -> Monolith + Microservices behind -> Microservices -> Event-Driven Microservices.  

Confluent Platform on PKS is now GA

Spring Gateway - API Gateway that's just Java Code. 

Break our AWS API Gateway dependency, and it's less confusing to configure. 

Microsoft + Pivotal 
---
A lot of Java is running on Azure, Microsoft sees which way the wind is blowing, wants to build windmills.

[Spring on Azure](cloud.spring.io/spring-cloud-azure)

Azure Spring Cloud - Introducing today.  
 * Built on K8s "Hyperscale" <- fun new buzzword
 * Zero code changes (ish)
 * Out of the box monitoring and tracing - Data Dog, New Relic, Dynatrace
 
Julien & Emily demo things - From a Mac. Go Microsoft.

 - Emily Wrote 4 microservices and a gateway, Julien is going to deploy it to Spring on Azure
 - GUI console and Azure CLI
```bash
$ az spring-cloud --help 
$ az spring-cloud app deployment create --app gateway --name green --jar-path ./gateway/target/gateway.jar
... Wait a few minutes ...
```

Spring boot Config server is running in azure, pointed at a git repo, and is accessible from the azure control panel, Neat. 

Managed distributed tracing (built in zipkin kind of stuff)

[Sign up](aks.foo/erg)

Jurgen Miller
---

"Modern software at the intersection of People and Technology" <- What does that mean?

What do we need to do to bring Java up to the standards of modern development?

Developer Experience - Java, Kotlin, Annotation-based and Imperative-based 
 - Reactive vs Spring Framework

Spring 5.2 and Spring Boot 2.2 are opening new possibilities. 

 * Developer Experience
 * Distrivuted Architectures
 * Runtime Efficiency

Spring 5.2 has lots of Kotlin Coroutine Support

Reactive Relational Database Access (R2DBC)
Reactive Messaging (SOCKET)

OpenJDK 11 LTS & 13 GA
GraalVM  - Next gen JIT & Mative Images

Ben Hale
---
JVM Runtime Support State

- Licensing Changes from Oracle have broken the market.
- Pivotal is a Platinum Sponsor of AdoptOpenJDK
  - AdoptOpenJDK applies zero patches of their own, it's just a distro
- Pivotal Spring Runtime - Pivotal supported OpenJDK, Spring, and Tomcat runtime
- 

AN: How meaningful are Download stats in the day of DockerHub and auto build and continuous delivery? 

Leah McGowen-Hare
---

* Bring others along for the ride - Teach others, because that's the way to build diverse teams
* Community is important to technology
* Business can be the leader
* [Trailhead](https://trailhead.salesforce.com/en/home)
* Write StackOverflow, Blogs, Present at conferences
* Make space for community involvement in deadlines - both as a dev and a manager
* Share knowledge, don't horde.
* Focus on Connecting not projecting
* Human Kind - Be both

Vijay Sankaran - TD Ameritrade
---
Early believer in Spring Boot/Microservices/etc. 

TD Ameritrade, Big company, does big things

- Uses SwaggerHub, Atlassian, all the real agile stuff. 
- Modern, streaming client
- 

Andrew Clay Schaeffer
---

Oh, *that's* who that guy is.  I've been following him on Twitter for a while, I couldn't remember who the heck he was.

Maslow's heirarchy now includes Wifi and Battery power.

Crossing the Chasm.

Swagless.



