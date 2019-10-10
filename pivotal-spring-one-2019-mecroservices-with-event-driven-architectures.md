Getting Microservices and Legacy to play nicely together with event-driven architectures
===
* Dustin Muse - Accenture
* Ryan Johnson - Accenture

Digital Dedubling

WHy is modernation hard? Tech Debt.

Accenture did a study in 2018 about tech debt

How do we modernize?
* Code Generation tools - Quick and Dirty leaves you still pretty far in Tech Debt
* Build a new system to replace the old system - Costly, can take a long time
* Containerize it - Quick and Dirty - Frees you from legacy hardware and physical infrastructure. 
* We can use microservices in the cloud - Allows you to replace only parts of the legacy, which can stall out.
* Strangler Pattern - "Vertical Decomposition of BPEL" APIgee

Digital Decoupling
---- 
Changing the Business while the business is running

APIgee and Kafka can allow old and new to co-exist peacefully. 

4 Fundamenta things to do:
---
1) Isolate legacy systems, wrap them up
2) Unlock the data -> broadcast it
3) Deliver new business value -> If the business doesn't get anything out of it, they don't want to pay
4) Hollow out and replace 

Digital Decoupling Pattern
---

See the photo

* Transformers, 
* Change Data Capture for old systems
* Event Hubs
* modern microservices
* Data Lake 

Similar to what we've done with Parcel Service

Begin the way to Digital decoupling

1) Use Domain Driven Design and buiild microservices
2) Build a proof of Architecture
3) Performance Test it
4) Keep it simple
5) Be mindful of where the data is.


