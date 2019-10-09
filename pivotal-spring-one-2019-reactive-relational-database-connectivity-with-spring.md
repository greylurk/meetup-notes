Mark Paluch - Spring Data Project Lead
===

[@mp911de](https://twitter.com/mp911de)

[R2DBC](https://r2dbc.io) was released last year at spring 1

Depends on Java 8 and Reactive Streams, and that's it.

Reactive Streams dependency goes into Java 9+

So, if you're using Java 11, you've got it.

* R2DBC embraces reactive types and patterns, 

* non-blocking all the way to the database

* Shrink the driver SPI

* Enable multiple "humane" APIs

``` java
Publisher<Connection> create()

Publisher<Void> beginTransaction()
Publisher<Void> close()
Publisher<Void> commitTransaction()



```

* SPI = service Programming Interface, corresponds with API, but provided by the app.

Versions seem to be going back in time.  1.0.0 isn't right.  Going backwards to 0.8.0 that are more experimental

* Categorized Exceptions (Grammar, Integrity Violation, etc.)
* Driver discovery and connection URLs
* Connection Validation
* CLOB/BLOB support
* SPI Refinements 
* ConnectionPooling
* New Drivers: H2, MySQL, SQL Server, SAP Hana, Google Cloud Spanner

Spring Data R2DBC
---

```java

Flux<Person> rows = client
  .execute("SELECT * FROM PERSON where name=:name")
  .bind("name", name)
  .as(Person.class)
  .fetch()
  .all();
```

```java
interface CustomerRepository extends ReactiveCrudRepository<Customer, Long> {
  @Query("SELECT * FROM ... WHERE lastname=:lastname")
  Flux<Customer> findByName(String lastname);
}
```

Kotlin Coroutine extensions

Repositories

Named parameter support

Support for Transactions

Fluent API

Function-reactive declaration of data access

It's up on start.spring.io

Transactions are reasonably easy, there's a few syntaxes (Annotations, lambda, or other lambda)

Don't cancel things when you've got a transaction

OJDBC 20 with Reactive Extensions might support things nicely.

* R2DBC is proven 
* 0.8.0 RC2 is out
* 0.8.0 GA is later this year.
* 0.9.0 Will support Stored Procs, Extended Transactions, EventProvider

