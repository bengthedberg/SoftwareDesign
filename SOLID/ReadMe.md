# The S.O.L.I.D. design principles
The S.O.L.I.D. design principles are a collection of best practices for object-oriented design. The acronym was introduced by Michael Feathers for five principles that were defined in the book Agile Principles, Patterns, and Practices in C# by Robert C. Martin.
All of the Gang of Four design patterns adhere to these principles in one form or another. 

The following sections look at each one in turn:

## Single Responsibility Principle (SRP) 
It states that every object should only have one reason to change and a single focus of responsibility. The single focus of responsibility alignes to the Separation of Concern (SoC) principle. The end result should be a codebase with loosely coupled isolated parts.

## Open-Closed Principle (OCP) 
The OCP states that classes should be open for extension and closed for modification, in that you should be able to add new features and extend a class without changing its internal behavior. The principle strives to design of a codebase with clear extension ports, usually done by segregating dependencies using interfaces or inheretance. See 
[Dependency Inversion Principle](#DIP)

## Liskov Substitution Principle (LSP) 
The LSP dictates that you should be able to use any derived class in place of a parent class and have it behave in the same manner without modification. This principle is in line with OCP in that it ensures that a derived class does not affect the behavior of a parent class, or, put another way, derived classes must be substitutable for their base classes. When this principle is violated, it tends to result in a lot of extra conditional logic scattered throughout the application, checking to see the specific type of an object. This duplicate, scattered code becomes a breeding ground for bugs as the application grows.

## Interface Segregation Principle (ISP) 
The ISP is all about splitting the methods of a contract into groups of responsibility and assigning interfaces to these groups to prevent a client from needing to implement one large interface and a host of methods that they do not use. The purpose behind this is so that classes wanting to use the same interfaces only need to implement a specific set of methods as opposed to a monolithic interface of methods.

## Dependency Inversion Principle[](#DIP) (DIP) 
The DIP is all about isolating your classes from concrete implementations and having them depend on abstract classes or interfaces. It promotes the mantra of coding to an interface rather than an implementation, which increases flexibility within a system by ensuring you are not tightly coupled to one implementation.

## Dependency injection (Di) and inversion of Control (ioC) 
Closely linked to the DIP are the DI principle and the IOC principle. DI is the act of supplying a low level or dependent class via a constructor, method, or property. Used in conjunction with DI, these dependent classes can be inverted to interfaces or abstract classes that will lead to loosely coupled systems that are highly testable and easy to change. In IoC, a system’s flow of control is inverted compared to procedural programming. An example of this is an IoC container, whose purpose is to inject services into client code without having the client code specifying the concrete implementation. The control in this instance that is being inverted is the act of the client obtaining the service