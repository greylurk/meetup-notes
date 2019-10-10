Sam Brannen
===

JUnit5 Core Committer, Pivotal Principal

* Junit5
* Jupiter
* What's coming up

JUnit5
---

14 jars.  Lots of different stuff. 

IDES/RUnners connect with the Platform, platform maintains the list of engines, which run tests.

Junit Jupiter - New model for JUnit 5 tests

Junit Legacy - Allows you to run Junit3/Junit4 tests. 

Third party TestEngines for Junit5
---
* Specsy
* Speck

JDK compatibility is 8+

IntelliJ, Eclipse, Netbeans, VSCode all support

Gradle 4.6+, Maven 2.22.0+, Ant 1.10.3+

Start.spring.io uses Junit5 as the default.

5.5.2 is current, good release cadence since 5.0 in 2017

Junit Jupiter (Jupiter is the 5th planet)

* Allows private stuff
* @DisplayName
* DisplayNameGenerator
* @Tag
* Tag expression Language
* Allows test messages to be provdier<String> lambdas
* assertThrows accepts a lambda, asserts that it throws the exception.
* assertTimeout accepts a lambda, see above.
* assertTimeoutPreemptively - threaded version of above.
* meta-annotations
  * Create your own custome composed annotations
  * Combine annotations from Spring and Junit
* Conditional test execution
* Dependency inejction for constructor 
* Interface default methods and testing traits
* @Nested test cases
* @RepeatedTest, @parameterizedTest, @TestFactory
* @TestInstance lifecycle management

Extensibility
---
* Extension interface is a marker
* org.junit.jupiter.api.extension
* @Disabled, @EnabledOnOS, @EnabledOnJRE
* TestWatcher
* TestTemplateInvocationContextProvider
* DisplayNameGenerator
  * 
* MethodOrderer - Change order that the tests are executed in
* InvocationInterceptor
* TestWatcher
  * Just watch the test, process the results of test execution
  * Supported for @Test and @TestTemplate methods
  * Fires, disabled, aborted, succeeded, failed
  * Could use for conditional exectuion of subsequent tasks

5.5
---

* Global tImeouts and @timeout for tests
* @EnabledIf adn @DisabledIf are deprecated
* @ValueSource supports booleans
* Invocation Intercapter API
* Explicity java module descripters


