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

Bulkheads - Isolate parts of the system.

Hystrix Bulkheads are to isolate thread-pools and stop thread-exhaustion in
one method from running away with all of the threads in other sections of the
application.

"Load Shedding" - Rejecting requests when we don't have the resources to work 
on them.

Hystrix allows Thread Pool or Semaphore isolation strategies. Thread Pool is 
default.

Thread pool isolation uses command pattern, queues and futures to achieve 
transparency. 

Semaphores
 * Commands run on originating threads, so thread-local (session) data is
   preserved
 * Logical isolation via Semaphores that track concurrent command requests
 * (Bad) Cannot walk away from timed-out requests. Blocking requests
   still block the thread.

Hystrix fall back methods *must* have exact same signature of the original
method.  Naive example: 

```java
  @HystrixCommand(fallbackMethod="getProjectFromCache")
  public ProjectInfo getProject(long projectId) {
    ...
    projectClientCache.put(projectId, projectInfo);
    return projectInfo;
  }

  public ProjectInfo getProjectFromCache(long projectId) {
    return projectClientCache.get(projectId);
  }
```

Circuit Breaker Lifecycle
 Closed -> Open -> Half-Open
 Self Healing, attempt to reset occasionally.


