Introduction
===

* Bill Kable - Spring Cloud Trainer
* Alexi - Spring Cloud Services Team
* Bella - Spring Cloud Services Team
* Anand Rao - Spring Cloud Architect

9-5 every day.
12-1:30 Lunch

Morning and Afternoon break as schedule allows.

Room Logistics: 7am - 7pm building

Might be a bit heavy on Spring internals for my current skill level

Agenda:
 * Intro to Spring Cloud
 * Service Discovery and Client Load Balancing
 * External Config
 * Distributed Trace
 * Fault Tolerance

Resillience 4J - Netrflix Hystrix and Ribbon are in Maintenance Mode
* [Spring cloud circuit breaker](https://github.com/spring-cloud/spring-cloud-circuit-breaker)
* [Ressilience 4j](https://youtube.com/watch?v=CcL8wrguhhsM)

This is a 3 day course compressed into 2 days

Hold Q&A for breaks

https://github.com/pivotal-bill-kable/s1-spring-cloud-course-errata

Suggested Sessions 
* [How to live in a post-spring cloud netflix world](https://springoneplatform.io/2019/sessions/how-to-live-in-a-post-spring-cloud-netflix-world)
* [Building Robust](https://springoneplatform.io/2019/sessions/building-robust-and-resilient-apps-using-spring-boot-and-resilience4j)

Spring Cloud project is huge
Main focus will be:
 * Cloud Native RESTful Applications over HTTP
 * Service Discovery and Service Registry
 * Client Load Balancing
 * Transient Failure Retry
 * Others.

IaaS - Infrastructure as a service
CaaS - Containers as a service
FaaS - Functions as a service
PaaS - Platform as a service

This whole talk is assuming a very weird world where people haven't figured out monitoring and logging except by cating log files.

"Pick whatever build tool you want, as long as it's Gradle or Maven" - Bill K.


Discoverability
---

spring cloud consul 

Eureka is another discovery platform - Netflix based

Eureka runs in-process in Java VM, opens three endpoints:
  * Register (and DeRegister)
  * Renew Registration
  * Fetch Registry

Caches and can replicate across multiple servers/clients

State is held in memory in Eureka, no backing file/database

Load Balancing
---

Ribbon - Runs in process and works with Discovery Client to enable provider.
Ribbon isn't going to be maintained, but there will be a load-balancing clientin future releases (Hoxton)

Server list is inside of Ribbon, independent from Discovery 

Load Balancing Rules are configurable:
  * RoundRobinRule
  * Weighted ResponseTimeRule
  * RandomRule
  * BestAvailableRule
  * AvailableFilteringRule

See: [https://github.com/Netflix/ribbon/wiki/Working-with-load-balancers]

[Load Balancing Lab](https://courses.education.pivotal.io/c/349803331/spring-cloud/service-discovery-client-load-balancing/client-load-balancing.html)

Configuration
---

Use case: Feature Toggles
[Different types of Feature Toggles](https://martinfowler.com/articles/feature-toggles.html)

Can get config from:
  * Github
  * SVN
  * Hashicorp Vault

Spring cloud config  - HTTP Service Endpoints

Config goes in a heirarchy: 
  * application.yml
    * application-{profile}.yml
      * {spring.app.name}.yml
        * {spring.app.name}-{profile}.yml
    

Config happens at boot or on pull model
Spring boot actuator endpoint: /refresh


