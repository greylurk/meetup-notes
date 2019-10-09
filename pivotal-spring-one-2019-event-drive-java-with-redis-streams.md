Event-Driven Java Applications with Redis Streams
===

Mark Paluch Again!

See my other one for his contact info [pivotal-spring-one-2019-reactive-relational-database-connectivity-with-spring.md]

Redis Streams is a new feature in Redis 5.0

Use cases:
 * Messaging
 * Activity Tracking
 * Metrics and Logging
 * Commit Log
 * Stream Processing

Stream Structure: 

Has a Key, acts like a container
  * Identifier, then a key:value tuple 
  * Unlike Kafka, this data is inherently key:value tuple, not binary
  * Identifier is timestamp followed by a counter, (15269858-0, 15269858-1)
  * Append Only
  * Body is like a hash (really a list of tuples)
  * Consumer Groups

OPERATIONS:
 * XADD - ADD AN ENTRY
 * XREAD - 
 * XLEN -
 * XRANGE

1. Create a stream by XADD
2. Read from the stream by XREAD STREAMS my_stream <starting offset>
3. Result includes the id for the next streams
4. xread can use blocking with a timeout.
5. XADD adds a unique ID, but you can insert manually



