# Explain the ... architecture pattern

## Circuit Breaker ⭐

The circuit breaker pattern minimizes the effects of a hazard by rerouting traffic to another service. While it helps make systems more fault tolerant to prevent accidents, it also requires sophisticated testing and using an infrastructure-management technology like service mesh.

## Client-server

The client-server pattern is a peer-to-peer architecture that is comprised of a client, which requests a service, and a server, which provides the service. Examples include banking, file sharing, email, and the World Wide Web. One advantage of this pattern is that data and network peripherals are centrally managed, however, the server is expensive. Furthermore, the server continues to listen to client requests.

## Command Query Responsibility Segregation

The command query responsibility segregation (CQRS) pattern handles the situation where database queries happen more often than data changes. It separates read and write activities to provide greater stability, scalability, and performance, but it requires more database technologies and therefore may increase costs.

## Controller-responder (Master-slave)

The controller-responder pattern divides the architecture into two components: The controller handles the data and distributes workloads, and the responder replicates data from the controller and generates results. One advantage is that you can read data from the responder without affecting the data in the controller, but if the controller fails, you may lose data and need to restart the application.

## Layered

The layered pattern is good for e-commerce, desktop, and other applications that include groups of subtasks that execute in a specific order. The layered pattern makes it easy to write applications quickly, but a disadvantage is that it can be hard to split up the layers later.

The most commonly found 4 layers of a general information system are as follows:

- Presentation layer (also known as UI layer)

- Application layer (also known as service layer)

- Business logic layer (also known as domain layer)

- Data access layer (also known as persistence layer)

## Microservices

The microservices pattern combines design patterns to create multiple services that work interdependently to create a larger application. Because each application is small, it's easier to update them when needed, but the complexity means you need greater architectural expertise to make everything work correctly.

## Model-view-controller ⭐

The model-view-controller (MVC) pattern divides an application into three components. The model contains the application's data and main functionality; the view displays data and interacts with the user; and the controller handles user input and acts as the mediator between the model and the view. This pattern enables the application to generate various views, but its layers of abstraction increase complexity.

## Pub-sub

The pub-sub pattern sends (publishes) relevant messages to places that have subscribed to a topic. It's easy to configure but more challenging to test because interactions between the publisher and the subscriber are asynchronous.

## Saga

The saga pattern is used for transactions with multiple steps, such as travel reservation services. A "saga" includes the various steps that must happen for the transaction to complete. This pattern enables transactions (ideally with five or fewer steps) to happen in loosely coupled, message-driven environments, but it requires a lot of programming and can be complex to manage.

## Sharding

The sharding pattern segments data in a database to speed commands or queries. It ensures storage is consumed equally across instances but demands a skilled and experienced database administrator to manage sharding effectively. There’s horizontal sharding and vertical sharding.

## Static content hosting

The static content hosting pattern is used to optimize webpage loading time. It stores static content (information that doesn't change often, like an author's bio or an MP3 file) separately from dynamic content (like stock prices). It's very efficient for delivering content and media that doesn't change often, but downsides include data consistency and higher storage costs.

## Strangler

The strangler pattern is used when you're making incremental changes to a system. It places the old system behind an intermediary (strangler facade or interface) to support incremental transformation, which reduces risk compared to making larger changes. However, you need to pay close attention to routing and network management and make sure you have a rollback plan in place in case things go wrong.

## Throttling

The throttling (or rate-limiting) pattern controls how fast data flows into a target. It's often used to prevent failure during a distributed denial of service attack or to manage cloud infrastructure costs. To use this pattern successfully, you need good redundancy mechanisms in place, and it's often used alongside the circuit breaker pattern to maintain service performance.

## Pipe-filter

This pattern can be used to structure systems which produce and process a stream of data. Each processing step is enclosed within a filter component. Data to be processed is passed through pipes. These pipes can be used for buffering or synchronization purposes. E.g.: compilers; the consecutive filters perform lexical analysis, parsing, semantic analysis, and code generation.

## Broker

This pattern is used to structure distributed systems with decoupled components. These components can interact with each other by remote service invocations. A broker component is responsible for the coordination of communication among components.

Servers publish their capabilities (services and characteristics) to a broker. Clients request a service from the broker, and the broker then redirects the client to a suitable service from its registry.

- Used in message broker software such as Apache ActiveMQ, Apache Kafka, RabbitMQ and JBoss Messaging.

## P2P

In this pattern, individual components are known as peers. Peers may function both as a client, requesting services from other peers, and as a server, providing services to other peers. A peer may act as a client, as a server or as both, and it can change its role dynamically with time.

- Used in file-sharing networks such as Gnutella and G2, multimedia protocols such as P2PTV and PDTP, or cryptocurrency-based products such as Bitcoin and Blockchain.

## Event-bus or Event-driven

This pattern primarily deals with events and has 4 major components; event source, event listener, channel and event bus. Sources publish messages to particular channels on an event bus. Listeners subscribe to particular channels. Listeners are notified of messages that are published to a channel to which they have subscribed before. This pattern is very popular in notification services.

## Blackboard

This pattern is useful for problems for which no deterministic solution strategies are known. The blackboard pattern consists of 3 main components.

- Blackboard — a structured global memory containing objects from the solution space
- Knowledge source — specialized modules with their own representation
- Control component — selects, configures and executes modules.

All the components have access to the blackboard. Components may produce new data objects that are added to the blackboard. Components look for particular kinds of data on the blackboard and may find these by pattern matching with the existing knowledge source.

- Used in speech recognition, vehicle identification and tracking, protein structure identification, sonar signals interpretation.

## Interpreter

This pattern is used for designing a component that interprets programs written in a dedicated language. It mainly specifies how to evaluate lines of programs, known as sentences or expressions written in a particular language. The basic idea is to have a class for each symbol of the language.

- Used in database query languages such as SQL and languages used to describe communication protocols.

## Space-Based

The concept of tuple space – the idea of distributed shared memory is the basis of the name of this architecture. The space-based pattern comprises two primary components – a processing unit and a virtualized middleware.

The processing unit contains portions of application components, including web-based components and backend business logic. While smaller web applications could be deployed in a single processing unit, the larger applications could split the application functionality into multiple processing units to avoid functional collapse. Furthermore, the virtualized-middleware component contains elements that control various aspects of data synchronization and request handling. They can be custom-written or can be purchased as third-party products.

A bidding auction site can be considered a fitting example of this architecture pattern. It functions as the site receives bids from internet users through a browser request. On receiving the request, the site records that bid with a timestamp, updates the information of the latest bid, and sends the data back to the browser.

- Usage

  - Applications and software systems that function with a large user base and a constant load of requests.
  - Applications that are supposed to address scalability and concurrency issues.

- Shortcoming:

  - It is a complex task to cache the data for speed without disturbing multiple copies.

## Non-blocking (Asynchronous) ⭐

Asynchronous is a non-blocking architecture that enables the execution of tasks independently: one task execution does not depend on another; tasks can run simultaneously. The differences between asynchronous and synchronous include

| Sync                                                                                                                  | Async                                                                      |
| --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| single-thread - one operation or program will run at a time.                                                          | multi-thread - operations or programs can run in parallel.                 |
| blocking — it will only send the server one request at a time and wait for that request to be answered by the server. | non-blocking - it will send multiple requests to a server.                 |
| Slower and more methodical.                                                                                           | Increases throughput because multiple operations can run at the same time. |

Asynchronous programming enhances the user experience by decreasing the lag time between when a function is called and when the value of that function is returned. Async programming translates to a faster, more seamless flow in the real world. For example, users want their apps to run fast, but fetching data from an API takes time. In these cases, asynchronous programming helps the app screen load more quickly, improving the user experience.
