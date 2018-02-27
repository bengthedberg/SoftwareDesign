# Creational Patterns

Creational patterns deal with object construction and referencing. They abstract away the responsibility of instantiating instances of objects from the client, thus keeping code loosely coupled and the responsibility of creating complex objects in one place adhering to the Single Responsibility and Separation of Concerns principles. 

Following are the patterns in the Creational group: 

* **Abstract Factory**:  
Provides an interface to create families of related objects. 
* **Factory**:   
Enables a class to delegate the responsibility of creating a valid object. 
* **Builder**:   
Enables various versions of an object to be constructed by separating the construction for the object itself. 
* **Prototype**:   
Allows classes to be copied or cloned from a prototype instance rather than creating new instances. 
* **Singleton**:   
Enables a class to be instantiated once with a single global point of access to it.

The new operator is often considered harmful as it scatters objects all over the application. Over time it can become challenging to change an implementation because classes become tightly coupled.

Creational Design Patterns address this issue by decoupling the client entirely from the actual initialization process.

## Singleton Pattern 
Although the Singleton pattern was introduced by GoF, the original implementation is known to be problematic in multithreaded scenarios.

So here is an example in C# that ensures that only one instance is created and only when the instance is needed. Also, the variable is declared to be volatile to ensure that assignment to the instance variable completes before the instance variable can be accessed. Lastly, this approach uses a syncRoot instance to lock on, rather than locking on the type itself, to avoid deadlocks.

```c#
using System;

public sealed class Singleton
{
   private static volatile Singleton instance;
   private static object syncRoot = new Object();

   private Singleton() {}

   public static Singleton Instance
   {
      get 
      {
         if (instance == null) 
         {
            lock (syncRoot) 
            {
               if (instance == null) 
                  instance = new Singleton();
            }
         }

         return instance;
      }
   }
}
```
This double-check locking approach solves the thread concurrency problems while avoiding an exclusive lock in every call to the Instance property method. It also allows you to delay instantiation until the object is first accessed. In practice, an application rarely requires this type of implementation. In most cases, the static initialization approach is sufficient.

### When to Use Singleton Design Pattern
* For resources that are expensive to create (like database connection objects)
* It’s good practice to keep all loggers as Singletons which increases performance
* Classes which provide access to configuration settings for the application
* Classes that contain resources that are accessed in shared mode


## Factory Method Design Pattern

The Factory Design Pattern or Factory Method Design Pattern is one of the most used design patterns.

According to GoF, this pattern “defines an interface for creating an object, but let subclasses decide which class to instantiate. The Factory method lets a class defer instantiation to subclasses”.

This pattern delegates the responsibility of initializing a class from the client to a particular factory class by creating a type of virtual constructor.

To achieve this, we rely on a factory which provides us with the objects, hiding the actual implementation details. The created objects are accessed using a common interface.

### When to Use Factory Method Design Pattern
* When the implementation of an interface or an abstract class is expected to change frequently
* When the current implementation cannot comfortably accommodate new change
* When the initialization process is relatively simple, and the constructor only requires a handful of parameters

## Abstract Factory Design Pattern

The Factory Method design pattern could be used to create objects related to a single family.

By contrast, the Abstract Factory Design Pattern is used to create families of related or dependent objects. It’s also sometimes called a factory of factories.

The GoF definition states that an Abstract Factory “provides an interface for creating families of related or dependent objects without specifying their concrete classes”.

### When to Use Abstract Factory Pattern:
* The client should be independent of how the products are created and composed in the system
* The system consists of multiple families of products, and these families are designed to be used together
* We need a run-time value to construct a particular dependency

## Builder Design Pattern

The Builder Design Pattern is another creational pattern designed to deal with the construction of comparatively complex objects.

When the complexity of creating object increases, the Builder pattern can separate out the instantiation process by using another object (a builder) to construct the object.

This builder can then be used to create many other similar representations using a simple step-by-step approach.

### When to Use Builder Pattern
* When the process involved in creating an object is extremely complex, with lots of mandatory and optional parameters
* When an increase in the number of constructor parameters leads to a large list of constructors
* When client expects different representations for the object that’s constructed
