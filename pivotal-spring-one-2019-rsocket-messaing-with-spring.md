RSocketMessaging with Spring
===

 * Rob Winch - Spring SEcurity project Lead
 * Brian

AN - Inital expectation: Sounds like ZeroMQ rebranded.

Introducing RSocket Protocol 
---

Rsocket - Reactive Streams RPC Mechanisms

RSocket doesn't need Code Generation (I'm looking at you gRPC)

Based on Project Reactor

RSocket isn't tied to HTTP2 (I'm looking at you again gRPC)

RSocket is used by Facebook, Netflix, Netlifi, Pivotal

RSocket is supported in:
 * Spring Framework
 * SPring Security
 * Spring Boot

vs HTTP comparison comes up a lot.  HTTP is Lingua Franca, so comparisons are inevitable, but HTTP and RSocket aren't directly comparable. It's not a drop in replacement.  

RSocket is good for within the firewall, not great over load balanced public streams (Maybe)

An application protocol for Multiplex and Duplex communication between applications

RSocket is an application level protocol that can run on top of WebSocket, raw TCP, or raw UDP

Multiplex with 4 interaction models:
 * Request/Response - "Request Respone" Frame sent, receive back "Payload" frame
 * Request Stream - "Request Stream" Frame sent, receive back multiple "Payload" frames
   * Backpressure: Tell server to slow down or stop publishing payloads
 * Request Channel - "Request channel" frame sent, followed by sending several Payload frames in both directions.  
   * Remember this is multiplex, this isn't exclusive.
 * Fire and forget - Just give me some data, and don't tell me when you're done.
 
Request Stream can include a limit number : i.e. only give me three payloads (Backpressure)
 * Can subsequently request more over the same channel.

```bash
$ ./rsocket-cli -i@=/usr/share/dict/words --server --debug tcp://localhost:8765
....
```

Applicaiton to open Request Stream

Session resumes after reconnect.  Because of Backpressure, Caching isn't important, because we'll just stop producing until the reconnect happens.

Request Throttling with LEASE
 - Responder or Requester can send LEASE to throttle the requests.

Heartbeats

Metadata Mime Types
----
Routing Metadata
Composite Metadata

REQUEST_* frames contain the route, security, etc metadata.  Other frames can, but REQUEST are the important ones in general.

SETUP frame
---
Set up the connection


Brian
----
spring-boot-starter-rsocket dependency

```
spring.rsocket.server.transport=localhost
spring.roscket.server.port=8765
```

@MessageMapping annotation is on Controllers

Security
---

Add Spring-boot-starter-security and spring.security.rsocket

[Repo](https://github.com/bcozel/spring-flights)

AN: Summary - Sounds like ZeroMQ rebranded. a little friendlier for Java and load balancers. 
