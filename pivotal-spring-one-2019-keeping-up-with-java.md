Java After 8
===

@giltene - CEO of Azul.com

- Java 6 - 2006 (December)
- Java 7 - 2011 (July)
- Java 8 - 2014 (March)
- Java 9 - 2017 (September)
- Java 10 - 2018 (march)
- Java 11 - 2018 (September) (LTS)
- Java 12 - 2019 (March)
- Java 13 - 2019 (September)

Feature Releases, Non-LTS is only 6 months of lifespan.

Java 17 is the next planned LTS, in 2021

Java the language (e.x Java 13)
  - Syntax changes

Java SE the platform (e.x. Java 13, JDK 13, Java SE 13)
  - specified APIs, Packages, behavior

OpenJDK: an implementation (OpenJDK 13)
  - Under the hood stuff,
  - garbage collectors, CDS

Java 9 was big: 86 changes
 - Linux S/390 port for example was a small OpenJDK change
 - Unicode 7.0
 - TLS

 JPMS ( Modules)
  - 75 platform models
    - 24 in Java SE
    - 2 aggegator modules
    - 1 smartcard
    - 48 JDK

  - Most internal APIs are now encapsulated
    - sun.misc.Unsafe
    - Some can be used with command line options

JLink - Java linker

```
$ jlink --module-path $JDKMODS:MYMODS \
   --admods com.azul.zapp --output myimage

$ myimage/bin/java --list-modules
java.base&9
java.sql&9
java.logging&9
java.xml@9
com.azul.zapp@1.0
com.azul.zoop@1.0
```

JDK 9: The Cleanup starts
 - JDK 9 was a big change for java. 
 - Deprecated APIs were removed for the first time
   - 6 methods, 1 class
   - JDK 10 removed 1 packages, 6 classses, 9 methods and 1 field.
 - Parts of the platform were removed for the first time
   - the entire java.see.ee aggregator odule ws "hidden" in jdk 9
   - completely removed in JDK 11
 - JDK 10, 11, 12, 13, 14... continues to work.
 - More features removed in the future
   
The Java.se.ee aggregator-module is gone
 - java.corba
 - java.transaction
 - java.activation
 - java.xml.bind
 - java.xml.ws
 - java.xml.ws.annotation

Compatibility isn't guaranteed
 - New version of java may include breaking changes
  - Anything for removal will be deprecated first
  - Minimum of one release warning
   - Could be only 6 months

JDK 10 
---
- Local type inference with the "var" keyword

```
var userList = new ArrayList<String>();
var stream = list.stream()
```

Clearer with some code.

var is a Reserved Type, not a keyword

- Applicaiton class -data sharing
- Expiermental GRAAL 
- Thread local handshakes
- Heap alocations on alternative devices
- parrallel full GC for G1

- 73 new APIS:
  - List, Set, Map.copyOf(collection)
  - Collectors
    - toUnmodifiableList
    - toUnmodifiableMap
    - toUnmodifiableSet
  - Optional.orElseThrow() - Exactly the same as Optional.get(), just included for readability

JDK 11
---
- Local-variable syntax for lambda parameters
```
list.stream()
  .map(s->s.toLowerCalse())

list.stream()
  .map(@Nonnul var s -> s.toLowerCase())
```


- Java shell scripts
```
#!$JAVA_HOME/java --source 11
.....
```

- HTTP client built in to the JVM
- Dynamic class file constants
- Transport Layer Security (TLS 1.3)
- Some Garbage Collectors
- Epsilon GC doesn't actually collect garbage ever.
- New IO Methods
  - InputStream nullInputStream()
  - OutputStream nullOutputStream()
  - Reader nullReader()
  - Writer nullWriter()
- Optional.isEmpty() // Opposite of Optional.isPresent()
- String.isBlank()
  - Stream lines()
  - String repeat(int)
  - String strip()
  - String stripLeading()
  - String stripTrailing()
- Predicate not(Predicate)

JDK 11 removed modules from the java.se.ee aggregator

JDK 12
----
- Switch expressions
  - Optional, requires enable at runtime

- More GC experiments and updates
- Constant API
- default CDS archive

- Streams - Teeing and joining with BiFictions

JDK 13
---
- Text Blocks: 
```
var a = """
        FOoo
        bar
        baz
        """;
```

- Switch Expressions are slightly different from 12, but still a preview feature

Project Valhalla
--- 
JDK 14?

- Value Types (so you don't need to box primitives)
- 

Project Loom
---
- Lightweight threads, 

OpenJDK
---
A source-only project

- Distros available, much like LInux
  - Adopt
  - Azul
  
Java Flight Recorder
---
JFR, go check it out.










