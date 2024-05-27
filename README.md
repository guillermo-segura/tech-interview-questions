# tech-interview-questions
Tech interview questions I've faced throughout my career

## Agile

### What is Agile methodology?

The Agile methodology is a project management approach that involves breaking the project into phases and emphasizes continuous collaboration and improvement. Teams follow a cycle of planning, executing, and evaluating.

It has 4 values:

- Individuals and interactions over processes and tools
- Working software over comprehensive documentation
- Customer collaboration over contract negotiation
- Responding to change over following a plan

And 12 principles:

- Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
- Welcome changing requirements, even late in development. Agile processes harness change for the customer's competitive advantage.
- Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
- Business people and developers must work together daily throughout the project.
- Build projects around motivated individuals. Give them the environment and support they need and trust them to get the job done.
- The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
- Working software is the primary measure of progress.
- Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
- Continuous attention to technical excellence and good design enhances agility.
- Simplicity--the art of maximizing the amount of work not done--is essential.
- The best architectures, requirements, and designs emerge from self-organizing teams.
- At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behaviour accordingly.

### What project management frameworks are you familiar with? Can you explain them?
Scrum: Much like a rugby team (where it gets its name) training for the big game, scrum encourages teams to learn through experiences, self-organize while working on a problem, and reflect on their wins and losses to continuously improve.

- Sprint planning
- Daily stand-ups
- Sprint review
- Sprint retrospective

Kanban: Work items are represented visually on a kanban board, allowing team members to see the state of every piece of work at any time. A kanban board is an agile project management tool designed to help visualize work, limit work-in-progress, and maximize efficiency (or flow).

Kanban VS Scrum
Kanban is a project management framework that relies on visual tasks to manage workflows, limit work-in-progress and move quickly things from “In progress” to “Done”, while Scrum is a project management framework that helps teams structure and manage their work through a set of values, principles, and practices.

With Scrum, your team promises to ship some valuable increment of work by the end of each sprint. Scrum is built on empiricism, focusing on small increments of work that will help you learn from your customers and better inform what you do next. 

Kanban is great for teams that have lots of incoming requests that vary in priority and size. Whereas scrum processes require high control over what is in scope, kanban let’s you go with the flow.

## Architecture Patterns
---

### Circuit Breaker
The circuit breaker pattern minimizes the effects of a hazard by rerouting traffic to another service. While it helps make systems more fault tolerant to prevent accidents, it also requires sophisticated testing and using an infrastructure-management technology like service mesh.

### Client-server
The client-server pattern is a peer-to-peer architecture that is comprised of a client, which requests a service, and a server, which provides the service. Examples include banking, file sharing, email, and the World Wide Web. One advantage of this pattern is that data and network peripherals are centrally managed, however, the server is expensive. Furthermore, the server continues to listen to client requests.

### Command Query Responsibility Segregation
The command query responsibility segregation (CQRS) pattern handles the situation where database queries happen more often than data changes. It separates read and write activities to provide greater stability, scalability, and performance, but it requires more database technologies and therefore may increase costs.

### Controller-responder (Master-slave)
The controller-responder pattern divides the architecture into two components: The controller handles the data and distributes workloads, and the responder replicates data from the controller and generates results. One advantage is that you can read data from the responder without affecting the data in the controller, but if the controller fails, you may lose data and need to restart the application.

### Layered
The layered pattern is good for e-commerce, desktop, and other applications that include groups of subtasks that execute in a specific order. The layered pattern makes it easy to write applications quickly, but a disadvantage is that it can be hard to split up the layers later.

The most commonly found 4 layers of a general information system are as follows:
- Presentation layer (also known as UI layer)
- Application layer (also known as service layer)
- Business logic layer (also known as domain layer)
- Data access layer (also known as persistence layer)

### Microservices
The microservices pattern combines design patterns to create multiple services that work interdependently to create a larger application. Because each application is small, it's easier to update them when needed, but the complexity means you need greater architectural expertise to make everything work correctly.

### Model-view-controller ❗
The model-view-controller (MVC) pattern divides an application into three components. The model contains the application's data and main functionality; the view displays data and interacts with the user; and the controller handles user input and acts as the mediator between the model and the view. This pattern enables the application to generate various views, but its layers of abstraction increase complexity.

### Pub-sub
The pub-sub pattern sends (publishes) relevant messages to places that have subscribed to a topic. It's easy to configure but more challenging to test because interactions between the publisher and the subscriber are asynchronous.

### Saga
The saga pattern is used for transactions with multiple steps, such as travel reservation services. A "saga" includes the various steps that must happen for the transaction to complete. This pattern enables transactions (ideally with five or fewer steps) to happen in loosely coupled, message-driven environments, but it requires a lot of programming and can be complex to manage.

### Sharding
The sharding pattern segments data in a database to speed commands or queries. It ensures storage is consumed equally across instances but demands a skilled and experienced database administrator to manage sharding effectively. There’s horizontal sharding and vertical sharding.

S### tatic content hosting
The static content hosting pattern is used to optimize webpage loading time. It stores static content (information that doesn't change often, like an author's bio or an MP3 file) separately from dynamic content (like stock prices). It's very efficient for delivering content and media that doesn't change often, but downsides include data consistency and higher storage costs.

### Strangler
The strangler pattern is used when you're making incremental changes to a system. It places the old system behind an intermediary (strangler facade or interface) to support incremental transformation, which reduces risk compared to making larger changes. However, you need to pay close attention to routing and network management and make sure you have a rollback plan in place in case things go wrong.

### Throttling
The throttling (or rate-limiting) pattern controls how fast data flows into a target. It's often used to prevent failure during a distributed denial of service attack or to manage cloud infrastructure costs. To use this pattern successfully, you need good redundancy mechanisms in place, and it's often used alongside the circuit breaker pattern to maintain service performance.

### Pipe-filter
This pattern can be used to structure systems which produce and process a stream of data. Each processing step is enclosed within a filter component. Data to be processed is passed through pipes. These pipes can be used for buffering or synchronization purposes. E.g.: compilers; the consecutive filters perform lexical analysis, parsing, semantic analysis, and code generation.

### Broker
This pattern is used to structure distributed systems with decoupled components. These components can interact with each other by remote service invocations. A broker component is responsible for the coordination of communication among components.

Servers publish their capabilities (services and characteristics) to a broker. Clients request a service from the broker, and the broker then redirects the client to a suitable service from its registry.

- Usage: message broker software such as Apache ActiveMQ, Apache Kafka, RabbitMQ and JBoss Messaging.

### P2P
In this pattern, individual components are known as peers. Peers may function both as a client, requesting services from other peers, and as a server, providing services to other peers. A peer may act as a client, as a server or as both, and it can change its role dynamically with time.

- Used in file-sharing networks such as Gnutella and G2, multimedia protocols such as P2PTV and PDTP, or cryptocurrency-based products such as Bitcoin and Blockchain.

### Event-bus or Event-driven
This pattern primarily deals with events and has 4 major components; event source, event listener, channel and event bus. Sources publish messages to particular channels on an event bus. Listeners subscribe to particular channels. Listeners are notified of messages that are published to a channel to which they have subscribed before. This pattern is very popular in notification services.

### Blackboard
This pattern is useful for problems for which no deterministic solution strategies are known. The blackboard pattern consists of 3 main components.

- Blackboard — a structured global memory containing objects from the solution space
- Knowledge source — specialized modules with their own representation
- Control component — selects, configures and executes modules.

All the components have access to the blackboard. Components may produce new data objects that are added to the blackboard. Components look for particular kinds of data on the blackboard and may find these by pattern matching with the existing knowledge source.

- Usage: speech recognition, vehicle identification and tracking, protein structure identification, sonar signals interpretation.

### Interpreter
This pattern is used for designing a component that interprets programs written in a dedicated language. It mainly specifies how to evaluate lines of programs, known as sentences or expressions written in a particular language. The basic idea is to have a class for each symbol of the language.

- Usage: database query languages such as SQL and languages used to describe communication protocols.

### Space-Based
The concept of tuple space – the idea of distributed shared memory is the basis of the name of this architecture. The space-based pattern comprises two primary components – a processing unit and a virtualized middleware. 

The processing unit contains portions of application components, including web-based components and backend business logic. While smaller web applications could be deployed in a single processing unit, the larger applications could split the application functionality into multiple processing units to avoid functional collapse. Furthermore, the virtualized-middleware component contains elements that control various aspects of data synchronization and request handling. They can be custom-written or can be purchased as third-party products. 

A bidding auction site can be considered a fitting example of this architecture pattern. It functions as the site receives bids from internet users through a browser request. On receiving the request, the site records that bid with a timestamp, updates the information of the latest bid, and sends the data back to the browser.

- Usage
  - Applications and software systems that function with a large user base and a constant load of requests.
  - Applications that are supposed to address scalability and concurrency issues.

- Shortcoming:
  - It is a complex task to cache the data for speed without disturbing multiple copies. 

- Non-blocking (Asynchronous) ❗
Asynchronous is a non-blocking architecture that enables the execution of tasks independently: one task execution does not depend on another; tasks can run simultaneously. The differences between asynchronous and synchronous include

| Sync | Async |
| single-thread - one operation or program will run at a time. | multi-thread - operations or programs can run in parallel. |
| blocking — it will only send the server one request at a time and wait for that request to be answered by the server. | non-blocking - it will send multiple requests to a server. |
| Slower and more methodical. | Increases throughput because multiple operations can run at the same time. |

Asynchronous programming enhances the user experience by decreasing the lag time between when a function is called and when the value of that function is returned. Async programming translates to a faster, more seamless flow in the real world. For example, users want their apps to run fast, but fetching data from an API takes time. In these cases, asynchronous programming helps the app screen load more quickly, improving the user experience.

## JavaScript
---

### What is Hoisting?
Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function).

Variables defined with let and const are hoisted to the top of the block, but not initialized:
- Using a let variable before it is declared will result in a ReferenceError
- Using a const variable before it is declared, is a syntax error, so the code will simply not run.
JavaScript only hoists declarations, not initializations. Hoisting is (to many developers) an unknown or overlooked behavior of JavaScript. If a developer doesn't understand hoisting, programs may contain bugs. To avoid this, always declare all variables at the beginning of every scope.

## React
---

### What is React? What is the role of React in software development?

React is an open-source library used for building user interfaces. It simplifies the creation of Single-Page Applications (SPAs) by using reusable components.

### What are the key features of React?

- **Virtual DOM**: React utilizes a virtual representation of the DOM, allowing efficient updates by minimizing direct manipulation of the actual DOM, resulting in improved performance.
- **Component-Based Architecture**: React structures user interfaces as modular, reusable components, promoting a more maintainable and scalable approach to building applications.
- **Reusability & Composition**: React enables the creation of reusable components that can be composed together, fostering a modular and efficient development process.
- **JSX (JavaScript XML)**: JSX is a syntax extension for JavaScript used in React, allowing developers to write HTML-like code within JavaScript, enhancing readability and maintainability.
- **Declarative Syntax**: React has a declarative programming style (JSX), where developers focus on "what" the UI should look like and React handles the "how" behind the scenes.
- **Community & Ecosystem**: React benefits from a vibrant and extensive community, contributing to a rich ecosystem of libraries, tools, and resources, fostering collaborative development and innovation.
- **React Hooks**: Hooks are functions that enable functional components to manage state and lifecycle features, providing a more concise and expressive way to handle component logic.

### What is the DOM? What is the difference between HTML and DOM?

DOM stands for Document Object Model. It's a tree-like structure that represents the elements and structure of a web page. HTML is the language used to create the structure and content of your webpage, while the DOM is a programming interface that allows you to interact with and manipulate that structure using languages like JavaScript. HTML is the static blueprint, and DOM is the dynamic, interactive version browsers use to render and update web pages based on user interactions or scripting.

### What is Virtual DOM? Difference between DOM and Virtual DOM?

- **DOM**: Represents the structure and content of a website in the form of a tree. It allows scripts and webpages to manipulate, modify, and identify the components of a website. DOM can be slow for modern websites, which require frequent updates and dynamic content rendering.
- **Virtual DOM**: A copy of the DOM that doesn't display the page of a website in a browser. When there are changes in a web page, updates are first made to the Virtual DOM, which then compares itself to the real DOM to identify specific updates needed, minimizing the number of changes that must be made in the actual DOM. This optimization improves overall web page speed.

### What are React Components? What are the main uses of them?

React components are reusable and self-contained pieces of code that represent different parts of a webpage. They help organize and manage the user interface. Think of them as Lego pieces that can be combined to construct a webpage. Each component has its functionality and can be easily combined with other components to create an interactive user interface. For example, you can have a "Button" component for handling user clicks, a "Header" component for displaying the title of your page, and a "Form" component for collecting user input.

### What is SPA (Single-Page Application)?

A Single-Page Application (SPA) is a type of web application that loads and interacts with content on a single web page without needing to reload the entire page for each action. SPAs use modern web technologies like JavaScript to dynamically update the content on the same page, providing a smoother and faster user experience. SPAs often use frameworks like React, Angular, or Vue.js to manage the dynamic content and enhance user interactivity.

### What are the five advantages of React?

1. Simple to build Single Page Applications by reusing components.
2. React is cross-platform and open-source, making it free to use.
3. Lightweight and swift, thanks to the Virtual DOM.
4. Large community and ecosystem.
5. Easy to test.

### What are the Disadvantages of React?

- React introduces new concepts like JSX, component-based architecture, and virtual DOM, which can be challenging for junior developers to grasp.
- Managing state and props within React components may be confusing for junior developers, especially when dealing with complex applications.

### What is the role of JSX in React?

In React, JSX (JavaScript XML) allows developers to write HTML-like code within JavaScript. Instead of using plain JavaScript to create elements, JSX lets you write HTML-like code. JSX gets transformed into regular JavaScript by a transpilation process before it's rendered in the browser, helping React understand and efficiently update the user interface based on the underlying JavaScript logic.

### What is the difference between Declarative & Imperative syntax?

- **Imperative Syntax**: Gives step-by-step instructions, micromanaging every detail.
  - Example: Instructing a robot to make a sandwich by specifying each action.
- **Declarative Syntax**: Focuses on the result you want to achieve, letting the system figure out how to do it.
  - Example: Instructing a robot to make a sandwich without specifying each action.

Declarative syntax is more focused on what you want to achieve, letting the computer figure out how to do it.

### What is the difference between Component and PureComponent? Give an example where it might break an application.

- **Component**: Renders any time its render function is called, regardless of whether its state or props changed.
- **PureComponent**: Renders only if the state or props differ, using a shallow comparison between the previous state and the new state. Complex objects might still trigger a render due to a possible change in the memory reference.

Example:
If a child component extending from Component receives a huge array of objects and renders a long list of data, it will re-render any time the parent updates, even if the data is the same, causing performance issues. Extending from PureComponent might seem to fix the problem, but if the array memory reference changes, the PureComponent will still re-render.

### Why combining Context with ShouldComponentUpdate might be dangerous?

A component whose `ShouldComponentUpdate` function prevents updates also prevents anything below it in the DOM tree from updating, even if another component should update because it’s consuming data from Context. This is no longer a problem in the newer `createContext` API.

### Describe 3 ways to pass information from a component to its parent

1. A child can send data to its parent using a callback function.
2. Using Context.
3. Using a state manager such as Redux.

### Describe 2 ways to prevent components from re-rendering

1. Using `React.memo` or `shouldComponentUpdate` to prevent any component from re-rendering if its props have not changed, by doing a shallow comparison between the previous props and state and the new ones. This is not always effective if the props are functions, objects, or arrays.
2. Making good use of props by passing primitive types when possible and memoized objects, arrays, and functions using `React.useMemo` or `React.useCallback`.

### What is React.Fragment?

`Fragment` is a tool to wrap children components in an element without adding an extra element to the DOM tree.

### What are the differences between Promises, callbacks, and Async/Await functions?

- **Callbacks**: Use the error-first pattern where the callback’s first argument is always the error object.
- **Promises**: Objects that provide methods to handle the different states of an asynchronous function. Handle errors using the `.catch()` method.
- **Async/Await**: Syntactic sugar built on top of promises that help write async code in a sync way, using `try/catch` blocks to handle exceptions.

### How many arguments does setState take and why is it async?

`setState` accepts two parameters:
1. The new state or a callback to update the new state.
2. A callback function that is triggered when the state update is completed.

It is asynchronous because state updates are queued into the JS event loop to allow for synchronous operations to be completed before the state is updated.

### List a few ways to style components

- **Inline styling**: Pass a CSS property object to a component style attribute.
- **CSS Modules**: Define classes in a module and export them into your component, passing those classes to the component’s `className` attribute.
- **CSS-in-JS libraries**: Such as `styled-components`, allowing you to style components directly and more dynamically.
- **CSS frameworks**: Such as Tailwind or Bootstrap, providing predefined styles and classes that can be used across your application.

### How can I render an HTML string?

You can render an HTML string by setting the `innerHTML` attribute of an element to the string. To get the element, you either query it using JavaScript or set the prop `dangerouslySetInnerHTML={{ __html: <html_string> }}`

## Node.js
---

### Can you explain what Node.js is and its advantages for backend development?

Node.js is an event-driven JavaScript runtime environment oriented to server-side applications; an infrastructure to build and run JavaScript applications. 

- **Event Loop**: Node.js runs on a single-thread of execution called event loop. It listens continuously for events and dispatches them to event handlers or callbacks.
- **Event Emitters**: Node.js components are designed as event emitters. They emit named events when certain actions occur.
- **Event Handler/Callbacks**: Logic registered to handle specific events emitted by Node.js components. When the event occurs, the callback or handler is invoked, performing an asynchronous task or responding to user actions.
- **Asynchronous Programming**: Node.js uses event-driven programming to handle async operations efficiently. Instead of blocking execution while waiting for operations to complete, it continues executing other tasks. Once the operation finishes, the associated callback is invoked allowing the program to continue.

**Advantages:**
- **JavaScript Everywhere**: Reduce context switching for full-stack developers.
- **Asynchronous and Non-blocking I/O**: Efficient for handling concurrent operations. Large number of connections with minimal resources.
- **Rich Ecosystem**: Access to a vast array of libraries and tools via npm.
- **Performant**: Due to its asynchronous, non-blocking nature, it excels in handling network requests, file operations, and database queries.
- **Scalable**: Vertically by leveraging the event loop and async programming, and horizontally by deploying multiple instances or using clustering.
- **Cross-platform Compatible**: Runs on various operating systems.
- **Well-suited for Microservices Architecture**: Due to its lightweight, modularity, and async communications between services.

**Competitors**: Deno (Node.js V2?), Python, PHP, Ruby, Java, Go

### What is NPM? How do you use it?

NPM stands for Node Package Manager, and it’s the default package manager for Node.js used to install, manage, and share packages. It also serves as a registry where packages can be published for other developers to use.

**How to use:**
1. Install Node.js
2. Initialize npm: `npm init -y`
3. Install packages: `npm install express`

Overall, NPM is a powerful tool for managing dependencies, sharing code, and collaborating on Node.js projects.

### What is asynchronous programming, and how does it work in Node.js?

Asynchronous programming is a paradigm that allows tasks to be executed concurrently, without blocking the execution of other tasks. These tasks are executed independently of the main program flow, and their results are handled asynchronously once available.

### Can you explain the event loop in Node.js?

The event loop is a single-threaded mechanism that continuously checks for pending events and dispatches them to their respective event handlers or callback functions. This allows Node.js to handle multiple concurrent operations without blocking the execution of other tasks.

### How do you handle errors in Node.js applications?

Common approaches include:
- **Try-catch blocks**
- **Error-first callback pattern**: The error is passed as the first parameter in the callback.
- **Promises**: Errors are handled using the `.catch()` method.
- **Event Emitters**: Emit error events that can be listened to and handled accordingly.

### What is middleware in Express.js, and how is it used?

Middleware are functions that intercept and process incoming requests before they reach the route handlers. They have access to the request and response object and the next middleware function in the request-response cycle. They are usually passed as a second parameter in the app route handler or applied to every request through the `app.use()` method.

### Explain the difference between `require` and `import` in Node.js.

- **`require`**: Traditional way of importing modules in Node.js. Modules are loaded synchronously and it returns the `module.exports` object which contains the exported members of the module.
- **`import`**: ES6 module syntax introduced in ECMAScript 2015. Modules are loaded asynchronously, allowing for named or default imports and namespace imports, and it returns bindings to the exported members of the module.

### How do you secure a Node.js application?

- **Keeping dependencies updated**
- **Using secure dependencies**
- **Implementing a strong authentication mechanism**
- **Validating and sanitizing user input**
- **Enabling HTTPS**
- **Implementing role-based access control**
- **Avoiding hardcoding sensitive information**
- **Implementing rate limiting and throttling mechanisms**
- **Good monitoring and logging**

### What is RESTful API, and how do you design one in Node.js?

A Representational State Transfer API, or RESTful API, is an architectural style for designing networked applications. It is based on a set of principles that define how resources are identified and addressed using HTTP methods.

**Key principles:**
- Client-server architecture
- Statelessness
- Uniform interface
- Resource-based
- Representation

In Node.js, you’d define the resources, set the URI and the HTTP method, and implement CRUD operations.

### How do you handle database operations in a Node.js application?

Database operations are usually handled by using database drivers or Object-Relational Mappers (ORMs) to interact with a database management system such as MySQL, MongoDB, or others.

### Can you explain the difference between callbacks, promises, and async/await in Node.js?

- **Callbacks**: Traditional way of handling asynchronous operations in Node.js. They involve passing a function as an argument to another function that will be executed once the async operation completes.
- **Promises**: Objects that represent the eventual completion or failure of an async operation, providing methods for handling success and failure. They support chaining, allowing for multiple async operations to be sequenced and executed in a more readable and manageable manner.
- **Async/Await**: Syntactic sugar built on top of promises. Async functions return a promise and allow async code to be written in a synchronous style, making it easier to read and reason. Inside these functions, the `await` keyword is used to pause execution until a promise is resolved, allowing the sequential execution of async code. This simplifies error handling by allowing try-catch blocks to catch errors within async code.

### What are streams in Node.js, and how do you use them?

Node.js streams are a powerful feature that allows you to sequentially read from or write to data sources without loading the entire data into memory at once. They allow processing large amounts of data without consuming excessive memory or causing delays due to processing bottlenecks.

**Types of streams in Node.js:**
- Readable streams
- Writable streams
- Duplex streams
- Transform streams

**Benefits of streams:**
- **Memory efficiency**: Process data in chunks, reducing memory usage.
- **Performance**: Improve the performance of I/O-bound operations.
- **Flexibility**: Easily compose and pipe streams together to perform complex data processing tasks.

### Explain the concept of clustering in Node.js and when you would use it.

Clustering in Node.js refers to the capability of spawning multiple Node.js processes (workers) to efficiently utilize multi-core systems. By distributing the workload across multiple CPU cores, clustering allows Node.js applications to handle more concurrent requests and improve overall performance and scalability.

**How clustering works:**
- **Master-Worker Architecture**: The master process manages the worker processes and distributes incoming connections or tasks among them.
- **Creating Worker Processes**: The master process creates one or more workers using the `cluster` module. Each worker runs its own instance of the Node.js event loop.
- **Load Balancing**: The master process acts as a load balancer and distributes the workload among the worker processes.
- **Fault Tolerance**: Clustering provides fault tolerance by isolating worker processes from each other. The master process can monitor the health of worker processes and automatically restart them if necessary.
- **Scalability**: Clustering enables horizontal scalability by allowing Node.js applications to scale out across multiple CPU cores or even multiple servers.

### How do you handle concurrent requests in a Node.js application?

**Approaches to handle concurrent requests:**
- **Non-blocking I/O Operations**: Perform I/O operations asynchronously.
- **Promises and Async/Await**: Provide a more readable and maintainable way to work with asynchronous code.
- **Clustering**: Create multiple worker processes to handle a higher volume of concurrent requests.
- **Connection Pooling**: Improve performance and scalability by reusing existing connections.
- **Caching**: Reduce the need for repeated I/O operations and improve response times.
- **Optimized Code**: Write efficient code by minimizing synchronous operations and avoiding blocking I/O calls.
- **Use of Streams**: Process data incrementally and asynchronously.

### Can you discuss the differences between Express.js and other Node.js frameworks?

**Key differences:**
- **Minimalism vs. Opinionated**: Express.js is known for its minimalist approach, providing a lightweight and unopinionated framework. Other frameworks, like Sails.js or Nest.js, may be more opinionated with predefined structures and built-in features.
- **Community and Ecosystem**: Express.js has a large and vibrant community with a vast ecosystem of middleware, plugins, and extensions. Other frameworks may have smaller or more specialized communities and ecosystems.
- **Performance**: Express.js is often praised for its speed and efficiency due to its minimalist design. Performance impact may vary for other frameworks depending on their architecture and bundled features.

In summary, Express.js stands out for its minimalism, flexibility, and middleware architecture, making it a popular choice for building a wide range of web applications and APIs. Other Node.js frameworks may offer different approaches and features catering to diverse use cases and preferences.

### How do you deploy and scale a Node.js application in a production environment?

**Steps to deploy a Node.js application:**
1. **Choose a Hosting Provider**: Options include AWS, Google Cloud Platform, Microsoft Azure, DigitalOcean, Heroku, and Vercel.
2. **Set up your environment**: Configure your hosting environment for your Node.js application.
3. **Deploy your application**: Use deployment tools and services to deploy your Node.js application.

**Scaling a Node.js application:**
- **Load Balancer**: Distribute incoming traffic across multiple instances of your Node.js application.
- **Horizontal Scaling**: Add more instances of your Node.js application to handle increased traffic and workload.
- **Monitoring and Logging**: Track performance, health, and behavior of your Node.js application in real-time using tools like Prometheus, Grafana, Datadog, or New Relic.
- **Performance Optimization**: Implement best practices such as caching, compression, code optimization, and database query optimization to enhance performance.

## WEB3
---

### What can you tell me about Verifiable Credential Workflow?

There are four elements in this workflow:
1. **Issuer**: Creates the credential and issues it to the holder.
2. **Holder**: Owns the credential and controls whom they share these credentials with.
3. **Verifier**: Receives the credential information and confirms the information stored is true without the intervention of the issuer.
4. **Verifiable Data Registry**: Stores identifiers and schemas.

### What do you know of decentralized identity?

Decentralized Identity is a digital identity management system where individuals have complete control over their personal information. It uses cryptography to allow individuals to create and control their unique identifiers (DIDs). They can use these identifiers to obtain Verifiable Credentials from trusted organizations and present parts of these credentials as proof of claims about themselves. Individuals can take ownership of their identity, rendering a centralized service provider unnecessary.

**Benefits:**
- Empowers individuals with control over their data.
- Simplifies processes for organizations.
- Saves administrative time and costs.
- Improves audit trails.

### Identification VS Authentication

- **Identification**: The things used to prove an identity.
- **Authentication**: The validation process used to identify yourself to other entities.

### What is a Trust Framework?

A Trust Framework is a group of practices and principles set for the diverse stakeholders that make up a network or ecosystem. It includes the rules of the road: policies, criteria for interoperability, and technical specifications.

### What do you know about Web3?

Web3 is the third version of the World Wide Web, which involves giving users control of their data and the use of blockchain technologies. Overall, it is a vision of a decentralized web.

### What are digital twins?

Digital twins are digital representations of physical entities or processes.

### What is eKYC?

eKYC stands for electronic Know Your Customer. It is a process where authorized organizations and agents verify a customer's identity and address digitally.

### What is a white-label product?

A white-label product is a brandless product that will be sold to a company, which will then brand and sell the product as its own.

### What is digital identity?

Digital identity is a 1-1 relationship between an entity, usually a human, and its digital presence. In the context of Web3, it would be a Decentralized Identifier (DID).

## GIT
---

### What is Git and why is it used?

Git is a distributed version control system used for tracking changes in files and coordinating work among multiple developers. It is commonly used for managing source code during software development.

### What are the basic Git commands for initializing a repository, adding files, committing changes, and pushing to a remote repository?

Basic Git commands include:
- `git init`: Initialize a new Git repository.
- `git add`: Add files to the staging area.
- `git commit`: Record changes to the repository.
- `git push`: Push committed changes to a remote repository.

### Explain the difference between git pull and git fetch.

- `git pull` fetches changes from the remote repository and merges them into the local branch.
- `git fetch` only retrieves changes from the remote repository without merging them.

### What is a merge conflict and how do you resolve it?

A merge conflict occurs when Git is unable to automatically resolve differences between two branches during a merge operation. It requires manual intervention to resolve conflicts before the merge can be completed.

### Describe the difference between Git rebase and Git merge.

- `git rebase` integrates changes from one branch into another by reapplying commits from one branch on top of another.
- `git merge` combines the changes from two branches into a new commit.

### What is a Git branch and why would you use one?

A Git branch is a pointer to a specific commit in the repository's history. Branches allow developers to work on separate features or fixes independently and merge changes back into the main codebase when ready.

### How do you revert a commit in Git?

To revert a commit in Git, you can use the `git revert` command followed by the commit hash of the commit you want to revert. You can also use `git reset` if it’s a local commit.

### Explain what a Git repository is.

A Git repository is a storage location where Git stores the history and metadata for a project, including all files and directories, commit objects, branches, and configuration settings.

### How do you undo the last commit in Git?

To undo the last commit in Git, you can use the `git reset --soft HEAD~1` command to reset the HEAD pointer to the previous commit, keeping the changes staged for commit due to the `--soft` flag.

### Can you explain the concept of Git hooks and provide examples of when they might be useful?

Git hooks are custom scripts that Git executes at certain points during the version control process, such as before or after a commit, push, or merge. They can be used to enforce coding standards, run tests, or trigger automated deployments.

### Describe Git submodules and when you might use them.

Git submodules are repositories embedded within another repository. They allow you to include external repositories as dependencies in your project and track their versions independently.

### What is Git cherry-pick and in what situations would you use it?

Git cherry-pick is a command used to apply a specific commit from one branch to another. It's useful for selectively applying changes without merging entire branches.

### Explain the difference between Git reset, Git revert, and Git checkout.

- `git reset` is used to move the HEAD and branch pointers to a specific commit, potentially discarding changes.
- `git revert` creates a new commit that undoes the changes introduced by a specific commit.
- `git checkout` is used to switch between different branches or restore files from a specific commit.

### What is the purpose of Git reflog and when would you use it?

Git reflog records the history of HEAD movements and other changes to the repository's pointers. It's useful for recovering lost commits or branches that have been accidentally deleted.

### Can you describe the Git object model and how Git stores data internally?

The Git object model consists of four main object types: blobs (file content), trees (directory structure), commits (pointers to a snapshot of the repository), and tags (references to specific commits). Git stores these objects in a compressed form in the repository's `.git` directory.

### What are some best practices for collaborating with others using Git?

Best practices for collaborating with others using Git include:
- Using descriptive commit messages.
- Creating feature branches for new development.
- Rebasing local changes before merging.
- Regularly pulling changes from remote repositories to stay up to date.

### Describe a scenario where you would use Git rebase interactively and what benefits it provides over regular rebase.

`git rebase -i` allows you to selectively edit, reorder, or squash commits before applying them to the target branch. It provides more control over the commit history and can help maintain a clean and organized repository history.

### What are conventional commits?

Conventional Commits are a specification for structuring commit messages in a standardized format. It aims to provide a clear and consistent way to communicate about changes in a repository's history, turning commits into machine-readable messages which can be leveraged for automation, release notes generation, and semantic versioning.

**Structure:**
`type(scope): subject`

**Types:**
- `feat`: A new feature.
- `fix`: A bug fix.
- `docs`: Documentation changes.
- `style`: Changes that do not affect the meaning of the code (e.g., formatting, missing semi-colons).
- `refactor`: Code refactorings or restructuring that do not change its behavior.
- `test`: Adding or modifying tests.
- `chore`: Other changes that don't modify `src` or `test` files (e.g., updating build tasks, package manager configurations).

**Scope (optional):** Provides additional context about the part of the codebase that is affected by the commit.

**Subject:** Briefly describes the change in imperative tense (e.g., "Add feature" instead of "Added feature"). It should be clear and concise, typically limited to 50 characters.

Conventional Commits promote standardized and semantic commit messages, making it easier for developers to understand the purpose of changes, automate release processes, and generate accurate release notes.

## Express.js
---

### What is Express.js and why is it popular?

Express.js is a web application framework for Node.js that simplifies the process of building web applications and APIs. It is popular because it provides a minimalist and flexible approach to web development, allowing developers to create scalable and maintainable applications with ease.

### How does Express.js handle routing?

Express.js provides a routing mechanism to define routes for handling incoming HTTP requests. Routes are defined using methods like `app.get()`, `app.post()`, `app.put()`, and `app.delete()`, specifying the HTTP method and the route path. Each route can have one or more middleware functions that are executed when the route is matched.

### What are middleware functions in Express.js and how are they used?

Middleware functions in Express.js are functions that have access to the request, response, and the next middleware function in the application's request-response cycle. They can modify the request and response objects, terminate the request-response cycle, or call the next middleware function using the `next()` function.

### Explain the concept of request and response objects in Express.js.

- The request object (`req`) represents the HTTP request sent by the client to the server, containing information about the request such as URL, HTTP headers, query parameters, and body data.
- The response object (`res`) represents the HTTP response that the server sends back to the client, containing methods to set HTTP headers, status code, and send data back to the client.

### What is a templating engine and which templating engines are commonly used with Express.js?

A templating engine is a tool that allows you to generate dynamic HTML content by mixing static HTML markup with dynamic data. Commonly used templating engines with Express.js include Pug (formerly Jade), EJS (Embedded JavaScript), Handlebars, and Mustache.

### What are route parameters in Express.js and how are they used?

Route parameters in Express.js are placeholders in route paths that capture values from incoming URL segments. They are specified in route paths using colon syntax (e.g., `:id`). Route parameters are accessible in route handlers via the `req.params` object.

### Describe the difference between app.get() and app.use() in Express.js.

- `app.get()` is used to define a route handler for HTTP GET requests with a specific route path.
- `app.use()` is used to register middleware functions that are executed for all HTTP requests, regardless of the HTTP method and route path.

### What is the purpose of app.listen() in Express.js?

`app.listen()` is used to start a web server and listen for incoming connections on a specified port. It binds the Express application to a network address and port number, allowing it to handle incoming HTTP requests.

### How do you serve static files (e.g., CSS, JavaScript) in Express.js?

Express.js provides the `express.static()` middleware to serve static files such as CSS, JavaScript, images, and other resources. It is typically used to specify a directory from which to serve static files.

### What is the purpose of next() in Express.js middleware?

`next()` is a function provided by Express.js to pass control to the next middleware function in the request-response cycle. It is typically called within middleware functions to delegate control to subsequent middleware functions.

### How can you handle form data in Express.js?

Form data can be handled in Express.js using middleware such as `body-parser` or `multer`. `body-parser` is used to parse incoming request bodies in URL-encoded or JSON format.

### Explain the difference between req.query and req.params in Express.js.

- `req.query` contains the query parameters parsed from the URL's query string.
- `req.params` contains route parameters captured from the URL's route path.

### What is middleware stacking in Express.js and how is it useful?

Middleware stacking refers to the practice of stacking multiple middleware functions together using `app.use()` or `router.use()`. This allows you to apply middleware functions to multiple routes or to create reusable sets of middleware for specific purposes.

### Can you implement authentication using middleware in Express.js?

Yes, authentication can be implemented using middleware in Express.js. Middleware functions can be used to verify user credentials, check session data, and enforce authentication requirements for protected routes.

### How can you handle file uploads in Express.js?

File uploads can be handled in Express.js using middleware such as `multer`. `multer` is used to parse `multipart/form-data` and handle file uploads, providing options for specifying file upload limits, file storage destinations, and more.

### Describe the role of the express.Router() middleware in Express.js routing.

`express.Router()` is used to create modular, mountable route handlers in Express.js. It allows you to define groups of routes and middleware in separate files or modules, improving code organization and maintainability.

### How do you handle CORS (Cross-Origin Resource Sharing) in Express.js applications?

CORS in Express.js can be handled using the `cors` middleware or by implementing custom middleware to set the necessary CORS headers (e.g., `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers`) in the response to allow cross-origin requests from specific origins or methods.

Online Courses
React Native
Tracking App
Plan the navigation structure to follow. E.g.:

The Coding Interview: Algorithms & Data Structures
Types
Take-home assignments
Pair programming
Whiteboarding ⚠️
Notes
Consider multiple solutions for every exercise
Solutions don’t need to be perfect, but you need to be able to explain and acknowledge improvements in presented solutions
parseInt removes any symbol after the number (5- → 5)
Recursion: Functions call themselves.
Draw and verbalise your thoughts and solutions
Runtime complexity: the power or time a given algorithm costs to run
Constant (1) → Regardless of the elements, the cost stays the same
Linear (N) → Iterations over a collection of data (single for loop)
Logarithmic (log(N)) → Happens when doubling the elements doesn’t double the cost required. Common in search operations
Quasilinear (N * log(N)) → Happens when doubling the elements doesn’t double the cost required. Common in sorting operations
Quadratic (N2)→ Every element compares to every other element
(Exponential 2N) → Adding a single element duplicates the cost required
Runtime complexity is commonly used as O(type) and means an algorithm's worst-case complexity.
Single for loop over a collection? O(N)
Over half a collection? Still O(N)
Two separate loops over the same collection? O(2 * N)
And different collections? O(N + M)
Two nested loops over the same collection? O(N2)
Over different collections? O(N * M)
Sorting a collection? O(N * log(N))
Searching a collection? O(log(N))
Space complexity: the memory a given algorithm costs to run. Less common than runtime complexity in interviews
Memoisation can be useful to reduce the runtime complexity
How would you design X product? E.g. Twitter, Uber, Google: follow these rules
No right answer
Each interviewer expects a different answer
Focus on the data structure
Don’t mention specific technologies
Draw stuff
Talk
Data Structures
Queue: container of records where they enter (enqueue) and leave (dequeue) in FIFO order
Stack: container of records where we add or remove records in FILO (LIFO) order
Linked List: list of linked nodes that contains a value and the reference of the next node. When no further node is available, it returns null—also known as the chain.
Head - first node
Data - value within the node
Tail - last node
Generators and iterators are a thing. Similar structure to async functions
Slow & Fast variables help with moving through a linked list.
Trees: linked lists with multiple nodes. Two ways of navigating through them:
Traverse Breadth-First - horizontally
Traverse Depth-First - vertically
Binary Search Trees: Trees with only two children where the left child has a value lower than the parent node and the right child has a greater value.
Sorting
Bubble (O(N2)):

Selection (O(N2)): 

Merge (O(N * log(N)): 

Microfrontends with React
All the code in one single code base → Monolithic Single Page Application
Main features split into different SPAs → Microfrontend
Avoid direct communication between SPAs. Handle data through API

Integration: How and when the container accesses the source code in each MFE. Many solutions for this, with their pros and cons.
Built-time (Compile-time): Container gets access to MFE before it’s loaded into the browser.
Run-time (Client side): Container gets access to MFE after it’s loaded into the browser.
Server side

Webpack: Combines all our JS files into a single file
Module Federation Plugin: Allows a build to provide or consume modules with other independent builds at runtime.
Use bootstrap.js to prevent issues when sharing modules. It helps when loading other libraries asynchronously.
If different versions of modules are used, all should be loaded. No version enforcement should happen
Certain libraries will not work with multiple copies (e.g. React). singleton should be used in those cases. Copies should be mayor version-compatible (e.g. ^5.0.0 and 5.1.0).
⚠️ if an ID matches the name of the imported module, the page may crash as the element with said ID will overwrite the imported module variable.
Good rules to follow:
Zero coupling between children
Zero or near-zero coupling between container and children
CSS changes on project A should not affect other projects
Version control should not affect projects (matter of preference). Either monorepo or separated repos are fine
Container should be able to decide whether to use latest version of child or specific version
Deployment challenges:
Modules should be deployable independently. Including the container module.
Module URLs should be known at build time. They can be set on the webpack.prod.js file.
Services usually handle single project deployments. We need a service that handles multiple different projects deployments separately.
CI/CD.
remoteEntry.js needs a dynamic name as there could be caching issues with a fixed name.
AWS
Policy: What allows multiple AWS services to talk to each other and access their different features
Distribution: Allows us to distribute different files from our S3 bucket
[CloudFront] Invalidation: Fix caching issues and make sure we use the right version of our static page
Styling
Classnames clashes across multiple modules
Prefixes help sort this out
Css-in-JS helps too but CSS-in-JS libraries need extra setup to prevent generic classnames clash
Check library docs when required!
Navigation within MFApps
Container and subapps need routing features
Subapps might need new routes. This shouldn’t require a container deployment
Should be able to display multiple subapps at the same time
Better to use existing routing solutions. No need to reinvent the wheel.
Navigation should work both inside the container and in isolation
⚠️ Issues with routing handled through error management in CloudFront
Authentication
Not for enforcing permissions
Only to signin or signup
Either each subapp is aware of auth (leads to code duplication)
OR auth is centralized in container app
Summary
Important to understand the requirements. They drive the architecture
Always ask if changing something in the future will require a change on another app
Everyone will eventually forget React/Vue/[Library X]
Scope CSS
MFE might cause issues in production not reproducible in development
Notes
Framework VS Library: Libraries are called by the code but frameworks call our code. This is an Inversion of Control (IoC) as the framework maintains control of the application.
Load balancer: Invisible facilitator between the user and a group of servers, ensuring the server resources are distributed equally across the requests. Related to horizontal scalability.
❗Promise (JS): Object that will produce a single value sometime in the future. If the promise is successful, it will produce a resolved value, but if something goes wrong then it will produce a reason why the promise failed. 
Pending: This is the default state of a defined promise
Fulfilled:  This is the state of a successful promise
Rejected: This is the state of a failed promise
Elasticsearch: Search engine based on the Lucene library. It provides a distributed, multitenant-capable full-text search engine with an HTTP web interface and schema-free JSON documents. Elasticsearch is developed in Java and its official clients are available in Java, .NET (C#), PHP, Python, Ruby and many other languages. According to the DB-Engines ranking, Elasticsearch is the most popular enterprise search engine. Wiki
Security: Security refers to the practice of protecting software systems and data from unauthorized access, use, disclosure, disruption, modification, or destruction. It involves implementing various measures such as authentication, authorization, encryption, and secure coding practices to mitigate potential security threats and vulnerabilities.
Reliability: It refers to the ability of a software system to perform consistently and in a predictable manner even in the presence of failures or unexpected events. It encompasses aspects such as fault tolerance, error handling, and infrastructure robustness and is achieved through thorough testing, monitoring, and implementation of redundancy or failover mechanisms to minimize downtime and ensure continuous operation.
Scalability: The capability of a software system to handle increasing workload or user demand by efficiently expanding its resources or infrastructure without compromising performance or responsiveness. It is essential for accommodating growing user bases, increasing data volumes, or handling spikes in traffic without experiencing degradation in system performance.
Platform Management: Platform management involves overseeing the infrastructure, environment, and tools used to support software development, deployment, and operation. This includes managing hardware resources, operating systems, middleware, development frameworks, and other software components required to host and run applications effectively. Platform management also encompasses tasks such as provisioning, configuration, monitoring, and optimization of the development and production environments to ensure their reliability, security, and performance.
Development Evangelism: Development evangelism is the practice of promoting and advocating for software development platforms, technologies, frameworks, or best practices within the developer community. It involves engaging with developers through various channels such as conferences, workshops, forums, social media, and developer communities to educate, inspire, and encourage the adoption of specific technologies or methodologies. Development evangelists often collaborate with product teams, contribute to documentation and tutorials, and provide support and guidance to developers to help them succeed with the adopted technologies.
Developer Advocate Experience: Developer advocate experience focuses on enhancing the experience and satisfaction of developers who use a particular platform, tool, or technology. It involves understanding the needs, challenges, and preferences of developers and advocating for improvements, enhancements, or features that can enhance their productivity, usability, and overall satisfaction. Developer advocate experience encompasses aspects such as documentation quality, API design, developer tooling, community support, and responsiveness to feedback, aiming to create a positive and empowering experience for developers using the platform.
CDN: A Content Delivery Network is a geographically distributed group of servers that caches content close to end users. A CDN allows for the quick transfer of assets needed for loading Internet content, including HTML pages, JavaScript files, stylesheets, images, and videos. The popularity of CDN services continues to grow, and today the majority of web traffic is served through CDNs, including traffic from major sites like Facebook, Netflix, and Amazon. A properly configured CDN may also help protect websites against some common malicious attacks, such as Distributed Denial of Service (DDOS) attacks. While a CDN does not host content and can’t replace the need for proper web hosting, it does help cache content at the network edge, which improves website performance. Many websites struggle to have their performance needs met by traditional hosting services, which is why they opt for CDNs.

