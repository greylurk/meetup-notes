Training Day 2
===

Distributed logging and tracing
---
* [OpenTrace](https://opentracing.io)
* [Zipkin](https://zipkin.io/)
* [Jager](https://www.jaegertracing.io/)

Terminology:
* Span - Basic unit of work, a chunk of work (~Parcel)
* Trace - Whole flow (~Parcel tree)

Sping Cloud Sleuth

Zipkin - Running it 

For Traces through zipkin - Can send HTTP directly, but can cause issues.
Preferred messaging format is AMQP through RabbitMQ

Custom spans are available.
Traces can be established outside of the Spring Boot app by using the openTracing headers

Resilience
---

[Release It](https://www.amazon.com/Release-Design-Deploy-Production-Ready-Software-ebook/dp/B079YWMY2V/ref=sr_1_1?keywords=release+it&qid=1570461288&sr=8-1)

* Service Level Objective: Must respond within 1 second.. 
* Service Level indicator: Metric to measure SLO
* Correctness: Does the program behave as specified
* Liveness: Is it available when needed.

Problems (Anti-patterns)

  * Chain Reactions
  * Cascading Failures
  * Blocked Threads
  * Slow Responses
  * Dog Piles

Ribbon load balancing with failures can be tricky. Use IPing to make it a bit better.

[Hystrix](https://github.com/Netflix/Hystrix) - Does "Circuit Breaking"
methodology, and also retries and other fault tolerance stuff.

Hystrix Dashboard does some internal metrics, but is going away... :(

Spring Cloud Services Cloud Foundry Demo.  Neat stuff.  BDP-adjacent

Hystrix (his-tricks) is more than just a circuit breaker, also does auto-
retries on rest clients, and features bulkheads and other stuff.

Almost none of the retry/resiliency stuff in this class is things we haven't
already considered and "solved" in Workflow Orchestration. Also, mostly
applicable to blocking REST microservices.  Queues and async change things
drastically. 


