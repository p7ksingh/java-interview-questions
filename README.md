# Java Interview Questions

2,466 questions with detailed answers. Covers Core Java through System Design.

Free. No signup. No paywall.

**Website:** [javabypankaj.live](https://www.javabypankaj.live)

## What's different about this

Most interview resources give one-paragraph answers. Real interviews don't work that way. The interviewer asks a follow-up, then another, and the textbook answer falls apart.

Every answer here includes production code, edge cases, and the follow-up questions interviewers actually ask. Written from 15 years of conducting and taking Java interviews at banks and fintech companies.

## Topics

| Chapter | Questions | Link |
|---------|-----------|------|
| Core Java | 194 | [Start here](https://www.javabypankaj.live/interview/core-java/jdk-jre-jvm/) |
| OOP | 32 | [Start here](https://www.javabypankaj.live/interview/oop/oops-fundamentals/) |
| Collections | 167 | [Start here](https://www.javabypankaj.live/interview/collections/collections-overview/) |
| Exception Handling | 31 | [Start here](https://www.javabypankaj.live/interview/exception-handling/exception-fundamentals/) |
| Concurrency | 317 | [Start here](https://www.javabypankaj.live/interview/concurrency-multithreading/thread-basics/) |
| Streams and Lambda | 94 | [Start here](https://www.javabypankaj.live/interview/java-streams-lambda-functional/lambda-expressions/) |
| Spring Boot | 230 | [Start here](https://www.javabypankaj.live/interview/spring-spring-boot/ioc-and-bean-lifecycle/) |
| JPA and Hibernate | 121 | [Start here](https://www.javabypankaj.live/interview/jpa-hibernate/jpa-fundamentals/) |
| Microservices | 194 | [Start here](https://www.javabypankaj.live/interview/microservices/fundamentals/) |
| Kafka | 77 | [Start here](https://www.javabypankaj.live/interview/kafka-messaging/kafka-fundamentals/) |
| Design Patterns | 133 | [Start here](https://www.javabypankaj.live/interview/design-patterns-lld/solid/) |
| System Design | 35 | [Start here](https://www.javabypankaj.live/interview/system-design/approach/) |
| DSA and Coding | 358 | [Start here](https://www.javabypankaj.live/interview/dsa-coding/beginner/) |
| DevOps and CI/CD | 133 | [Start here](https://www.javabypankaj.live/interview/devops-cicd-tooling/git/) |
| Database and SQL | 108 | [Start here](https://www.javabypankaj.live/interview/database-sql/sql-basics/) |
| REST API | 73 | [Start here](https://www.javabypankaj.live/interview/rest-api/rest-fundamentals/) |
| AWS and Cloud | 41 | [Start here](https://www.javabypankaj.live/interview/aws-cloud/aws-overview/) |
| Security | 32 | [Start here](https://www.javabypankaj.live/interview/security/auth-basics/) |

---

## Sample Questions

Here are 45 questions from across the chapters. Each one links to the full answer with code on the site.


### Core Java

**1. What is the difference between the JDK, the JRE, and the JVM, and who needs which one?**

- JVM is the engine that executes bytecode (handles class loading, memory, GC, JIT)
- JRE is the JVM bundled with standard libraries your program needs to run
- JDK is the JRE bundled with developer tools like javac, jar, and jlink

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/jdk-jre-jvm/jdk-jre-jvm-difference-needs/)

---

**2. What are the rules for declaring, initializing, accessing, and scoping instance variables in Java?**

- An instance variable is a non-static field declared inside a class but outside any method – each object gets its own copy
- Default values are assigned automatically: 0 for numbers, false for boolean, null for references
- Three places to initialize: at declaration, in an instance initializer block, or in a constructor

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/variables-scope-var/rules-declaring-initializing-accessing-scoping-instance/)

---

**3. What are the eight primitive data types in Java?**

- Eight primitives: byte (8-bit), short (16), int (32), long (64), float (32), double (64), char (16), boolean
- Primitives hold raw values directly, not references to objects on the heap
- Each has a fixed size defined by the Java spec, unlike C where sizes are platform-dependent

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/primitive-types-wrappers/eight-primitive-data-types/)

---

**4. What is the difference between == and .equals() in Java?**

- == compares values for primitives (int, double, boolean) and references (memory address) for objects
- .equals() compares logical content – overridden in String, Integer, BigDecimal to compare values
- Two different String objects with same text: == is false, .equals() is true

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/operators-expressions/equals-difference/)

---

**5. Why is the main method public, static, and void?**

- public: the JVM must access it from outside the class – if it were private, the JVM could not call it
- static: the JVM calls it without creating an object – no constructor runs before main
- void: there is no caller to return a value to – the JVM uses System.exit(code) for exit status

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/main-method/static-main-public-void/)

---

**6. What are the four access modifiers in Java and their exact visibility?**

- public: visible everywhere, to any class in any package
- protected: visible in the same package + subclasses in other packages
- default (no keyword): visible only within the same package (package-private)

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/access-modifiers/access-modifiers-exact-visibility/)

---

**7. What does the final keyword mean on a class, method, variable, and parameter?**

- final variable: assigned once, cannot be reassigned. Reference is fixed, but the object's internal state can change
- final method: cannot be overridden by subclasses
- final class: cannot be extended (no subclasses). String, Integer, Math are all final

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/keywords-final/final-keyword-mean-variable-parameter/)

---

**8. What is the static keyword and where can it be used?**

- static means "belongs to the class, not to any object" – one shared copy for all instances
- static field: one copy shared by all objects (e.g., a bank-wide interest rate or a counter)
- static method: called on the class, not on an object – cannot access instance fields or this

[Read the full answer with code](https://www.javabypankaj.live/interview/core-java/keywords-static/static-keyword-main/)

---


### Collections

**9. What is the Java Collections Framework: main interfaces, implementations, and algorithms?**

- JCF has three pillars: interfaces (List, Set, Queue, Map), implementations (ArrayList, HashSet, HashMap), and algorithms (Collections.sort, binarySearch, shuffle)
- Collection is the root interface for List, Set, and Queue; Map is a separate hierarchy and does not extend Collection
- ArrayList gives O(1) random access, LinkedList gives O(1) insertion at ends, HashSet gives O(1) contains, TreeSet gives O(log n) sorted iteration

[Read the full answer with code](https://www.javabypankaj.live/interview/collections/collections-overview/collections-framework-main-interfaces-implementations/)

---

**10. ArrayList vs LinkedList: when to use each**

- ArrayList is backed by a dynamic array with O(1) random access and excellent CPU cache locality; it is the default choice for 95% of use cases
- LinkedList is a doubly-linked list with O(1) add/remove at head and tail but O(n) random access due to node traversal
- ArrayList uses ~4 bytes per element (object reference); LinkedList uses ~40 bytes per node (object header + item + prev + next)

[Read the full answer with code](https://www.javabypankaj.live/interview/collections/list-arraylist-linkedlist/arraylist-linkedlist/)

---

**11. ArrayDeque vs LinkedList vs Stack: when to use each**

- ArrayDeque is the fastest general-purpose Deque, Stack, and Queue implementation; it is backed by a resizable circular array with O(1) amortized operations at both ends
- ArrayDeque beats LinkedList for Deque operations because contiguous memory gives excellent CPU cache locality
- ArrayDeque beats Stack because Stack extends Vector, which synchronizes every method even in single-threaded code

[Read the full answer with code](https://www.javabypankaj.live/interview/collections/queue-deque-stack/linkedlist-stack-arraydeque/)

---

**12. HashMap vs Hashtable vs ConcurrentHashMap**

- HashMap is not thread-safe, allows one null key and multiple null values, and is the fastest map for single-threaded use
- Hashtable is legacy (Java 1.0), synchronizes every method on a single lock, does not allow null keys or values, and should never be used in new code
- ConcurrentHashMap (Java 5+) uses per-bucket locking (Java 8+), provides lock-free reads via volatile, and does not allow null keys or values

[Read the full answer with code](https://www.javabypankaj.live/interview/collections/hashmap-internals/hashmap-hashtable-concurrenthashmap-difference/)

---

**13. HashMap vs LinkedHashMap vs TreeMap: ordering, performance, cache use case**

- HashMap is unordered with O(1) get/put and is the default choice when ordering does not matter
- LinkedHashMap maintains insertion order (default) or access order (LRU mode) with O(1) get/put and slight memory overhead
- TreeMap maintains keys in sorted order using a Red-Black tree with O(log n) get/put and provides NavigableMap range queries

[Read the full answer with code](https://www.javabypankaj.live/interview/collections/linkedhashmap-treemap/hashmap-linkedhashmap-treemap-cache-ordering-performance/)

---


### Concurrency & Multithreading

**14. Process vs Thread: memory space, stack, overhead**

- A process has its own isolated memory space; a thread shares the process heap but has its own stack.
- Thread creation is lightweight (about 1ms and 1MB stack) compared to process creation (about 100ms and 100MB).
- Context switching between threads in the same process is cheaper than between processes because threads share the address space.

[Read the full answer with code](https://www.javabypankaj.live/interview/concurrency/thread-basics/thread-stack-process-memory-space-overhead-difference/)

---

**15. Synchronized method vs synchronized block: scope, lock object, granularity**

- A synchronized method locks on this (instance) or ClassName.class (static) for the entire method body.
- A synchronized block locks on any specified object for only the critical section, providing finer granularity.
- Synchronized blocks are preferred because they minimize lock hold time and allow different locks for different data.

[Read the full answer with code](https://www.javabypankaj.live/interview/concurrency/synchronization/synchronized-block-scope-lock-object-granularity/)

---

**16. volatile keyword: visibility guarantee, no atomicity, happens-before**

- volatile guarantees visibility: every read comes from main memory, every write goes to main memory.
- Without volatile, the JIT compiler may cache a variable in a CPU register, and other threads never see updates.
- volatile does NOT guarantee atomicity: counter++ on a volatile int is still a race condition.

[Read the full answer with code](https://www.javabypankaj.live/interview/concurrency/volatile/volatile-keyword-visibility-guarantee-atomicity/)

---

**17. Race condition: concrete example, check-then-act, read-modify-write, fixes**

- A race condition occurs when program correctness depends on the timing of thread execution.
- Check-then-act: the condition is checked in one step and acted on in another, with a gap where another thread can change state.
- Read-modify-write: a value is read, modified, and written back as three separate operations, allowing interleaving.

[Read the full answer with code](https://www.javabypankaj.live/interview/concurrency/race-conditions/race-condition-concrete-check-then-act-read-modify-write/)

---

**18. Deadlock: what it is, code example, detection, and prevention strategies**

- A deadlock occurs when two or more threads permanently block each other, each holding a lock the other needs.
- Four Coffman conditions must all hold: mutual exclusion, hold-and-wait, no preemption, and circular wait.
- The most practical prevention is consistent lock ordering: always acquire locks in the same deterministic order.

[Read the full answer with code](https://www.javabypankaj.live/interview/concurrency/deadlock/deadlock-detection-prevention-strategies/)

---


### Spring & Spring Boot

**19. Explain the Spring IoC container, the difference between BeanFactory and ApplicationContext, Inversion of Control, and Dependency Injection vs Dependency Lookup.**

- IoC is a design principle where the framework controls object creation and dependency wiring instead of your code doing it with the new keyword.
- BeanFactory is the basic lazy-loading container interface that creates beans only when first requested.
- ApplicationContext extends BeanFactory with eager initialization, event publishing, AOP integration, annotation scanning, and i18n support.

[Read the full answer with code](https://www.javabypankaj.live/interview/spring-boot/ioc-and-bean-lifecycle/spring-ioc-container-difference-beanfactory/)

---

**20. What are all mechanisms to resolve multiple beans of the same type (@Primary, @Qualifier, variable name, List/Map injection, @Profile, custom qualifier)? When does NoUniqueBeanDefinitionException occur? What is the difference between @Primary and @Qualifier?**

- NoUniqueBeanDefinitionException occurs when Spring finds multiple beans of the same type and cannot decide which one to inject.
- @Qualifier on the injection point explicitly names the bean to inject and has the highest priority.
- @Primary on the bean definition marks it as the default when no qualifier is specified.

[Read the full answer with code](https://www.javabypankaj.live/interview/spring-boot/dependency-injection/list-map-mechanisms-resolve-multiple-beans-type-primary/)

---

**21. What is the difference between a Spring bean and a normal object? What is the difference between @Component, @Service, @Repository, @Controller? How does @Repository enable exception translation? What is the difference between @Bean and @Component?**

- A Spring bean is container-managed: it gets DI, AOP proxying, lifecycle callbacks (@PostConstruct, @PreDestroy), and scope management.
- An object created with new bypasses the container: @Transactional does nothing, @Autowired fields are null, @PostConstruct never runs.
- @Component is the generic stereotype; @Service, @Repository, and @Controller are specialized @Component annotations.

[Read the full answer with code](https://www.javabypankaj.live/interview/spring-boot/bean-types-and-stereotypes/spring-bean-component-service-repository-controller/)

---

**22. How does the Servlet model handle concurrent requests, why doesn't one slow request block others, and why is storing per-request state in a singleton bean a bug?**

- Spring MVC uses Tomcat's thread-per-request model with a default pool of 200 threads.
- Each HTTP request gets one exclusive thread from the pool for its entire lifecycle.
- Singleton beans are shared across ALL threads simultaneously, so they must be stateless or use thread-safe structures.

[Read the full answer with code](https://www.javabypankaj.live/interview/spring-boot/web-layer/state-singleton-bean-spring-servlet-model-handle-concurrent/)

---

**23. How does Spring Boot initialize? What is DispatcherServlet? How do you create, build, run, deploy? How do you avoid dropping requests during deployment (graceful shutdown)?**

- SpringApplication.run() creates the ApplicationContext, triggers auto-configuration, instantiates beans, and starts the embedded server
- DispatcherServlet is the front controller that routes every HTTP request to the matching controller method
- Bean creation follows dependency order: constructor injection first, then @PostConstruct lifecycle callbacks

[Read the full answer with code](https://www.javabypankaj.live/interview/spring-boot/configuration-and-profiles/spring-boot-initialize-dispatcherservlet-create-build-run/)

---


### Design Patterns & LLD

**24. Explain each SOLID principle with violations and fixes, how SRP and DIP can clash during refactoring, and whether SOLID can lead to over-engineering.**

- SRP violation: a class that validates, transfers, emails, and logs changes for four reasons – split into focused services.
- OCP violation: a growing if-else chain on account type – replace with an InterestStrategy interface and one class per type.
- LSP violation: a SavingsAccount subclass that throws on withdraw breaks callers written for Account – redesign the hierarchy.

[Read the full answer with code](https://www.javabypankaj.live/interview/design-patterns-lld/solid/solid-principle-violations-fixes-srp-dip-clash-refactoring/)

---

**25. What is the DRY ("Don't Repeat Yourself") principle, how do you follow it, and how should it be applied carefully in microservices?**

- DRY: every piece of knowledge should live in exactly one place, so a change is a single safe edit.
- DRY is about duplicated knowledge, not duplicated characters that happen to look alike.
- Techniques: extract method, extract class, composition, generics, constants, configuration.

[Read the full answer with code](https://www.javabypankaj.live/interview/design-patterns-lld/principles/microservices-dry-don-repeat-yourself-principle-follow/)

---

**26. Explain the Singleton pattern and the thread-safe ways to implement it in Java: eager initialization (simple, not lazy), lazy with a synchronized getter (lazy but locks on every call), double-checked locking (needs a volatile instance to avoid returning a partially-constructed object), the Bill Pugh initialization-on-demand holder idiom (lazy + thread-safe via class loading, no synchronization), and an enum singleton (concise, with free serialization-/reflection-safety): and which are preferred (Bill Pugh or enum)?**

- Singleton ensures one instance for the whole app with a single global access point.
- Eager initialization is thread-safe via class loading but not lazy; wastes resources if never used.
- Synchronized getter is lazy and correct but locks on every call, hurting performance.

[Read the full answer with code](https://www.javabypankaj.live/interview/design-patterns-lld/creational/singleton-pattern-synchronized-volatile-enum-thread-safe/)

---

**27. Explain the Proxy pattern types (Virtual/lazy, Protection/access-control, Caching, Dynamic/JDK, Remote) and how Spring AOP uses dynamic proxies.**

- A Proxy implements the same interface as the real object and controls access by adding lazy creation, security, caching, or remote communication.
- Virtual proxy defers expensive object creation until first use; protection proxy enforces access control before delegating.
- Caching proxy returns cached results on repeat calls; remote proxy hides network communication behind a local interface.

[Read the full answer with code](https://www.javabypankaj.live/interview/design-patterns-lld/structural/proxy-pattern-caching-dynamic-jdk-spring-types-virtual-lazy/)

---


### Microservices

**28. What is a "distributed monolith" (services that deploy/fail/scale together via shared libraries, shared DBs, synchronous chains), and how do you avoid it?**

- A distributed monolith has the complexity of distribution with none of the independence of microservices.
- Symptom 1: shared database -- schema changes force coordinated simultaneous redeploys.
- Symptom 2: shared libraries with business logic -- changing the library forces rebuilding every consumer.

[Read the full answer with code](https://www.javabypankaj.live/interview/microservices/fundamentals/distributed-monolith-services-deploy-fail-scale-together-via/)

---

**29. Explain Bounded Context in microservices (DDD), its principles, advantages, and disadvantages.**

- A Bounded Context is an explicit boundary where one domain model and one ubiquitous language are consistent and unambiguous.
- Inside the boundary every term has exactly one meaning; outside it the same word may mean something different.
- In microservices each bounded context typically maps to one service with its own model and private database.

[Read the full answer with code](https://www.javabypankaj.live/interview/microservices/decomposition-ddd/microservices-bounded-context-ddd-principles-advantages/)

---

**30. How do microservices communicate (synchronous REST/Feign/gRPC vs asynchronous Kafka/RabbitMQ), and when do you use each?**

- Synchronous communication uses REST, Feign, or gRPC where the caller blocks until it receives a response from the target service.
- Asynchronous communication uses a broker like Kafka or RabbitMQ where the producer publishes and continues without waiting.
- Choose synchronous when the caller genuinely needs the answer to proceed, such as a funds check before a transfer.

[Read the full answer with code](https://www.javabypankaj.live/interview/microservices/communication/microservices-rest-feign-grpc-kafka-rabbitmq-communicate/)

---

**31. What is the difference between a Load Balancer (L4 vs L7), a Reverse Proxy, and an API Gateway, and why are they complementary rather than alternatives?**

- L4 load balancer routes by IP and port without inspecting the payload; extremely fast, protocol-agnostic.
- L7 load balancer inspects HTTP request (path, headers, cookies) and routes by content; can do sticky sessions.
- A reverse proxy fronts and shields backends: TLS termination, caching, compression, path routing.

[Read the full answer with code](https://www.javabypankaj.live/interview/microservices/api-gateway/load-balancer-proxy-api-gateway-difference-l4-l7-reverse/)

---


### System Design

**32. How to do back-of-envelope estimation: estimate QPS (queries per second), storage needs, bandwidth, and number of servers needed for a given scenario?**

- Back-of-envelope estimation turns vague scale requirements into concrete numbers using round figures and simple arithmetic.
- QPS is computed by dividing daily volume by 86,400 seconds and multiplying by a peak factor of 2 to 10.
- Storage is record size multiplied by records per day multiplied by retention period.

[Read the full answer with code](https://www.javabypankaj.live/interview/system-design/approach/back-of-envelope-estimation-estimate-qps-queries-per-second/)

---

**33. CDN (Content Delivery Network): caches static content (images, CSS, JS, video) at edge servers close to users, reduces latency and origin server load.**

- A CDN is a geographically distributed network of edge servers that cache static content close to users for low-latency delivery.
- On a cache miss the edge fetches from the origin once, stores it, and serves all subsequent requests until the TTL expires.
- The cache key (usually the URL) decides what counts as the same object; incorrect keys can leak personalized content.

[Read the full answer with code](https://www.javabypankaj.live/interview/system-design/concepts/static-load-cdn-content-delivery-network-caches-images-css/)

---

**34. Design a Chat/Messaging System (like WhatsApp): WebSocket for real-time, message storage, delivery status (sent/delivered/read), group chat, end-to-end encryption, offline message queuing.**

- WebSocket connections provide bidirectional, real-time message delivery; a presence registry maps users to their server.
- Persist every message before attempting delivery so a server crash never loses it (persist-first rule).
- Delivery status is a state machine: sent (persisted) -> delivered (device ack) -> read (user opens chat).

[Read the full answer with code](https://www.javabypankaj.live/interview/system-design/design-problems/design-system-websocket-chat-messaging-whatsapp-real-time/)

---


### Coding Problems: DSA

**35. Find the average of all elements in an array (sum / length).**

- Average is the sum of all elements divided by the count, computed in a single O(n) pass with O(1) extra space.
- For money always use BigDecimal to accumulate the sum, never double, because binary floating point cannot represent decimal fractions exactly.
- BigDecimal division without a scale and RoundingMode throws ArithmeticException on non-terminating decimals such as 10 divided by 3.

[Read the full answer with code](https://www.javabypankaj.live/interview/dsa-coding/beginner/array-average-elements-sum-length/)

---

**36. Reverse a string (convert to char array, swap from both ends, or use StringBuilder.reverse()).**

- Strings in Java are immutable, so reversing requires creating a new character sequence.
- The cleanest production approach is new StringBuilder(s).reverse().toString(), which also handles surrogate pairs correctly.
- The manual approach converts to a char array and uses two-pointer swaps, mirroring the array reversal pattern.

[Read the full answer with code](https://www.javabypankaj.live/interview/dsa-coding/arrays/string-char-array-stringbuilder-reverse-convert-swap-ends/)

---

**37. What is a String in Java: a sequence of characters, immutable (cannot be changed after creation).**

- A String in Java is an immutable object that wraps a sequence of characters and cannot be modified after creation.
- Every operation like concat, substring, or toUpperCase returns a new String and leaves the original unchanged.
- String literals are interned in the String pool so identical literals share a single object in memory.

[Read the full answer with code](https://www.javabypankaj.live/interview/dsa-coding/strings/string-immutable-sequence-characters-cannot-changed-creation/)

---


### Database & SQL

**38. What is an UPSERT (insert-or-update in one atomic statement): `INSERT ... ON CONFLICT DO UPDATE` (PostgreSQL), `INSERT ... ON DUPLICATE KEY UPDATE` (MySQL), or the SQL-standard `MERGE`: and why is it safer than a separate SELECT-then-INSERT/UPDATE (race condition under concurrency)?**

- An UPSERT inserts a row if it does not exist and updates it if it does, all in one atomic statement.
- PostgreSQL uses `INSERT ... ON CONFLICT (key) DO UPDATE SET ...` with the `EXCLUDED` alias for proposed values.
- MySQL uses `INSERT ... ON DUPLICATE KEY UPDATE` to achieve the same single-statement upsert.

[Read the full answer with code](https://www.javabypankaj.live/interview/database-sql/sql-basics/atomic-postgresql-mysql-merge-race-condition-upsert/)

---

**39. Why do SQL JOINs become prohibitively expensive at very large scale (data sharded across nodes → cross-shard scatter-gather, deep index trees + disk reads per level, large intermediate result sets over the network, and per-user results that cannot be cached), and why does normalized design optimize for write correctness rather than read speed?**

- At small scale a JOIN is cheap because indexes and the buffer cache serve matching rows from memory.
- At large scale, data sharded across nodes forces cross-shard scatter-gather, bounded by the slowest shard.
- A B-tree with billions of rows is many levels deep, with a potential disk read per level per lookup.

[Read the full answer with code](https://www.javabypankaj.live/interview/database-sql/joins/sql-index-design-joins-become-prohibitively-expensive-large/)

---

**40. How do you write a custom method/query in MongoDB (shell, aggregation framework, Spring Data custom repository)?**

- The mongo shell uses `find` with a JSON filter document and `aggregate` with a pipeline of stages for custom queries.
- The aggregation framework chains stages like `$match`, `$group`, `$sort`, and `$lookup` to filter, group, and compute on the server.
- Spring Data MongoDB offers derived query methods where the method name is parsed into a query automatically.

[Read the full answer with code](https://www.javabypankaj.live/interview/database-sql/aggregation/mongodb-spring-repository-custom-query-shell-aggregation/)

---


### JPA & Hibernate

**41. What is JPA vs Hibernate? Advantages of JPA? Advantages/disadvantages of Hibernate? Core Hibernate interfaces? EntityManager vs Session? What is a dialect?**

- JPA is a specification (interfaces and annotations) that defines how Java objects map to database tables
- Hibernate is the most popular JPA implementation that generates SQL, manages the persistence context, and performs dirty checking
- EntityManager (JPA) and Session (Hibernate) are the core interfaces for CRUD operations on entities

[Read the full answer with code](https://www.javabypankaj.live/interview/jpa-hibernate/jpa-fundamentals/jpa-hibernate-advantages-disadvantages-core-interfaces/)

---

**42. What is N+1? How to detect? Fix strategies (JOIN FETCH, EntityGraph, @BatchSize)? Why is JOIN FETCH not a cure-all (Cartesian product, MultipleBagFetchException)? How to optimize Hibernate queries?**

- N+1 means 1 query loads N parents, then N additional queries load each parent's lazy collection – devastating at scale
- Detection: enable spring.jpa.show-sql=true and count queries per request, or use Hibernate statistics or p6spy
- JOIN FETCH loads parent and collection in one SQL query with a JOIN

[Read the full answer with code](https://www.javabypankaj.live/interview/jpa-hibernate/n-plus-1-and-fetching/join-hibernate-detect-fix-strategies-fetch-entitygraph/)

---


### Kafka & Messaging

**43. When would you deliberately choose NOT to use Kafka?**

- Skip Kafka for synchronous request-reply where a direct REST or gRPC call is simpler and faster.
- Low-volume workloads are better served by a managed queue like SQS with near-zero operational cost.
- Per-message priority and complex routing are native in RabbitMQ or ActiveMQ but awkward in Kafka.

[Read the full answer with code](https://www.javabypankaj.live/interview/kafka-messaging/kafka-fundamentals/kafka-deliberately-choose/)

---

**44. A rolling deployment triggers a rebalance for every pod restart: why does it hurt more than expected and how do you fix it?**

- Eager rebalancing causes 2N stop-the-world pauses for a rolling deploy of N pods.
- Cooperative sticky assignor pauses only the partitions that need to move, not the entire group.
- Static group membership with group.instance.id lets the coordinator skip rebalance on quick restarts.

[Read the full answer with code](https://www.javabypankaj.live/interview/kafka-messaging/consumer-groups/rolling-deployment-triggers-rebalance-pod-restart-hurt-fix/)

---


### Exception Handling

**45. What is exception handling, why do we need it, and what are the keywords involved (try/catch/finally/throw/throws)?**

- Exception handling is Java's mechanism for dealing with runtime errors gracefully instead of crashing the program
- Five keywords: try (risky code), catch (handle specific exceptions), finally (cleanup that always runs), throw (raise an exception), throws (declare in signature)
- Without exception handling a failed credit step leaves money debited but never credited and the connection leaked

[Read the full answer with code](https://www.javabypankaj.live/interview/exception-handling/exception-fundamentals/exception-try-catch-finally-throw-throws-handling-keywords/)

---


## How to use this

If you are a fresher, start with Core Java, OOP, and Collections. If you have a few years of experience, focus on Spring Boot, JPA, and Microservices. For senior and lead roles, go through System Design, Concurrency, and Design Patterns.

The full site has all 2,466 questions with progress tracking, search, and dark mode.

[javabypankaj.live](https://www.javabypankaj.live)

## About

Built by [Pankaj Singh](https://www.linkedin.com/in/p7ksingh/). 15 years in Java development, mostly in banking and fintech.

If this is useful, star the repo so others can find it.
