# Software Engineering and Architecture Resources

Welcome to the Software Engineering and Architecture Resources repository! This repository contains a collection of resources on software engineering and architecture, including best practices, design patterns, and case studies.

### Table of Contents
- [Introduction](https://github.com/TheodorosKarropoulos/software.engineer.resources#introduction)
- [Time Complexity](https://github.com/TheodorosKarropoulos/software.engineer.resources#time-complexity)
- [Best Practices](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/README.md#best-practices)
- [Design Patterns](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/README.md#design-patterns)
- [Anti-patterns](https://github.com/TheodorosKarropoulos/software.engineer.resources#anti-patterns)
- [Refactoring Techniques](https://github.com/TheodorosKarropoulos/software.engineer.resources#refactoring-technics)
- [Code Smells](https://github.com/TheodorosKarropoulos/software.engineer.resources#code-smells)
- [Branching Strategies](https://github.com/TheodorosKarropoulos/software.engineer.resources#branching-strategies)
- [Architectural Patterns](https://github.com/TheodorosKarropoulos/software.engineer.resources#architectural-patterns)

#### Introduction
Software engineering and architecture are key disciplines in the field of computer science, concerned with the design, development, and maintenance of software systems. In this repository, you will find a variety of resources on these topics, ranging from general best practices to specific design patterns and real-world case studies.

#### Time Complexity
[Time complexity](TimeComplexity/TimeComplexityIntro.md) is a measure of how long an algorithm takes to run as a function of the size of its input.

#### Best Practices
- [Clean Code](BestPractices/CleanCode.md): A classic book on writing clean, maintainable code.
- [SOLID Principles](BestPractices/SOLID): A set of five principles for designing object-oriented software.
- [DRY](BestPractices/DRY.md): It is a way of designing software systems so that every piece of knowledge is expressed in a single, unambiguous way.
- [KISS](BestPractices/KISS.md): It is a way of designing software systems with a focus on simplicity and minimalism.
- [YAGNI](BestPractices/YAGNI.md): It is a software development principle that advises developers to avoid adding unnecessary features or functionality to a software system.
- [Agile Development](BestPractices/AgileDevelopment.md): A software development methodology that emphasizes flexibility, collaboration, and rapid iteration.

#### Design Patterns
[Design Patterns](DesignPatterns/Introduction.md) are established solutions to common problems that occur in software design. They provide a way for developers to reuse successful designs and avoid reinventing the wheel

#### Anti-patterns

- [Spaghetti code](anti-patterns/spaghetti-code.md): Code that is poorly structured, difficult to read, and hard to maintain.
- [Golden hammer](anti-patterns/golden-hammer.md): Using a particular solution or tool for every problem, even when it may not be the best fit.
- Copy-paste programming: Copying and pasting code without understanding how it works or modifying it to fit the specific context.
- God object: A class that has too many responsibilities and becomes difficult to maintain.
- Leaky abstractions: Abstractions that break down or "leak" implementation details, making the code harder to understand and maintain.
- Accidental complexity: Adding unnecessary complexity to the codebase, making it harder to understand and maintain.
- Premature optimization: Optimizing code without a clear understanding of the performance trade-offs and their impact on the overall system.
- Not invented here: Refusing to use external libraries or solutions, even when they would be more appropriate, because of a preference for in-house solutions.

#### Refactoring Technics

- Extract method: Move a block of code into a separate method with a descriptive name.
- Extract variable: Replace an expression with a descriptive variable name.
- Rename: Rename a class, method, or variable to make its purpose clearer.
- Inline: Replace a method call with the contents of the method.
- Replace conditional with polymorphism: Replace a conditional statement with polymorphism (using inheritance or interface implementation) to make the code more flexible and maintainable.
- Replace loop with pipeline: Replace a loop with a pipeline of functions to make the code more readable and easier to maintain.
- Extract class: Move a group of related methods and variables into a separate class.
- Replace inheritance with delegation: Replace inheritance with delegation (using composition) to improve the flexibility and maintainability of the code.
- Replace magic numbers with constants: Replace "magic numbers" (hard-coded values) with named constants to make the code more readable and maintainable.
- Consolidate duplicated code: Remove duplicated code by extracting common functionality into a separate method.

#### Code Smells

- Bloaters: Code smells that indicate areas of the code that are excessively large and complex, and may be difficult to understand and maintain. Examples include large classes, long methods, and large parameters.
- Object-oriented smells: Code smells that relate to the design of object-oriented code, and may indicate problems with the structure or relationships between classes. Examples include duplication, tight coupling, and inappropriate intimacy.
- Change prevention smells: Code smells that indicate areas of the code that are resistant to change, and may be difficult to modify or extend. Examples include code duplication, feature envy, and data clumps.
- Refactoring smells: Code smells that indicate areas of the code that may benefit from refactoring to improve its design and maintainability. Examples include long methods, primitive obsession, and long parameter lists.

#### Branching Strategies

- Gitflow: A branching strategy that involves using two main branches, called "develop" and "master," as well as additional supporting branches for features, hotfixes, and releases. The develop branch is used for ongoing development, and the master branch represents the latest stable release.
- Trunk-Based Development: A branching strategy in which all development is done in a single "trunk" branch, and developers are expected to commit their code frequently and resolve conflicts as they arise.
- Feature Branching: A branching strategy in which a separate branch is created for each new feature that is being developed. When the feature is complete, the branch is merged back into the main development branch.
- Release Branching: A branching strategy in which a separate branch is created for each new release that is being prepared. The release branch is used to stabilize the code and fix any final bugs before the release is deployed.
- Branch by Abstraction: A branching strategy in which a new abstraction layer is introduced into the codebase, allowing the old and new implementations to coexist until the new implementation is ready to be fully deployed.

#### Architectural Patterns

- Monolithic architecture: A monolithic architecture is a traditional approach in which the entire application is built as a single, self-contained unit. All components of the application, including the user interface, business logic, and data storage, are combined into a single codebase.
- Microservices architecture: A microservices architecture is a modern approach in which the application is broken down into small, independent components, or "microservices," that communicate with each other through APIs. Each microservice is responsible for a specific function, and they can be developed, deployed, and scaled independently.
- Layered architecture: A layered architecture is a design in which the application is divided into logical layers, such as a presentation layer, a business logic layer, and a data storage layer. Each layer has a specific responsibility, and they are separated by clear interfaces.
- Client-server architecture: A client-server architecture is a design in which the application is divided into two parts: a client, which is responsible for presenting data to the user and handling user input, and a server, which is responsible for processing requests and storing data.
- Event-driven architecture: An event-driven architecture is a design in which the application is built around a series of events that trigger certain actions. The application listens for events, and when an event occurs, it performs the appropriate action.
- Model-View-Controller (MVC): An MVC architecture is a design pattern in which the application is divided into three main components: the model, which represents the data and business logic; the view, which represents the user interface; and the controller, which handles user input and coordinates between the model and view.
- Pipe and Filter: A pipe and filter architecture is a design in which the application is divided into a series of independent filters that transform the data as it passes through them. Each filter performs a specific transformation, and the output of one filter becomes the input of the next.
- Event-Sourcing: An event-sourcing architecture is a design in which the application stores all changes to the system as a series of events, rather than storing the current state of the system. This allows the system to be reconstructed from the events at any point in time.
- Service-Oriented Architecture (SOA): A service-oriented architecture is a design in which the application is divided into a collection of independent services that communicate with each other through APIs. Each service is responsible for a specific function, and they can be developed, deployed, and scaled independently.
- Serverless Architecture: A serverless architecture is a design in which the application is built using cloud-based functions that are triggered by events. The cloud provider is responsible for scaling and managing the infrastructure, allowing the developer to focus on writing code.
- Object-Oriented Architecture: An object-oriented architecture is a design in which the application is built using objects, which are self-contained units that combine data and behavior. Objects can interact with each other through methods, and they can be organized into inheritance hierarchies.
- Data-Centric Architecture: A data-centric architecture is a design in which the application is built around a central data store, and the data is the primary focus of the system. The application uses various mechanisms, such as database queries and data transformation pipelines, to access and manipulate the data.
- Publish-Subscribe Architecture: A publish-subscribe architecture is a design in which the application is built around a message bus, and components of the system publish messages to the bus and subscribe to messages from the bus. This allows components to communicate with each other asynchronously, without needing to know about each other directly.
- Space-Based Architecture: A space-based architecture is a design in which the application is built around a shared memory space, and components of the system interact with the space by reading and writing data to it. This allows components to communicate with each other in a decoupled, asynchronous manner.
- Representational State Transfer (REST) Architecture: A REST architecture is a design for building web APIs that follows a set of principles for creating scalable, maintainable, and reusable APIs. REST APIs use HTTP methods and resources to expose data and functionality, and they are based on the idea of representing the state of a system through a set of resources that can be accessed and manipulated using HTTP requests.
- Hexagonal Architecture (Ports and Adapters): Separates an application into inner and outer layers. The core business logic (hexagon) is independent of external concerns (adapters), allowing for easy integration with different technologies or frameworks.
- CQRS (Command Query Responsibility Segregation): Separates read and write operations in a system. Commands handle updates and modifications, while queries handle data retrieval. This pattern can improve performance and scalability by optimizing for specific use cases.
- GraphQL Architecture: Provides a flexible and efficient alternative to traditional REST APIs. Clients can request only the data they need, reducing over-fetching and under-fetching of data. GraphQL allows clients to shape responses according to their requirements.
- Clean Architecture: Emphasizes separation of concerns by organizing code into concentric circles or layers, with the innermost layer containing the core business logic. Dependencies flow inward, promoting testability and maintainability.
