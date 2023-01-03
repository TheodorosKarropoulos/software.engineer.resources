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

#### Introduction
Software engineering and architecture are key disciplines in the field of computer science, concerned with the design, development, and maintenance of software systems. In this repository, you will find a variety of resources on these topics, ranging from general best practices to specific design patterns and real-world case studies.

#### Time Complexity
[Time complexity](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/TimeComplexity/TimeComplexityIntro.md) is a measure of how long an algorithm takes to run as a function of the size of its input.

#### Best Practices
- [Clean Code](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/BestPractices/CleanCode.md): A classic book on writing clean, maintainable code.
- [SOLID Principles](https://github.com/TheodorosKarropoulos/software.engineer.resources/tree/main/BestPractices/SOLID): A set of five principles for designing object-oriented software.
- [DRY](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/BestPractices/DRY.md): It is a way of designing software systems so that every piece of knowledge is expressed in a single, unambiguous way.
- [KISS](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/BestPractices/KISS.md): It is a way of designing software systems with a focus on simplicity and minimalism.
- [YAGNI](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/BestPractices/YAGNI.md): It is a software development principle that advises developers to avoid adding unnecessary features or functionality to a software system.
- [Agile Development](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/BestPractices/AgileDevelopment.md): A software development methodology that emphasizes flexibility, collaboration, and rapid iteration.

#### Design Patterns
[Design Patterns](https://github.com/TheodorosKarropoulos/software.engineer.resources/blob/main/DesignPatterns/Introduction.md) are established solutions to common problems that occur in software design. They provide a way for developers to reuse successful designs and avoid reinventing the wheel

#### Anti-patterns

- Spaghetti code: Code that is poorly structured, difficult to read, and hard to maintain.
- Golden hammer: Using a particular solution or tool for every problem, even when it may not be the best fit.
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
