# Common Design Principles

These are some more widely known design principles outside the SOLID group:

### Keep it simple stupid (Kiss) 
An all-too-common issue in software programming is the need to overcomplicate a solution. The goal of the KISS principle is concerned with the need to keep code simple but not simplistic, thus avoiding any unnecessary complexities.

### Don’t repeat Yourself (DrY) 
The DRY principle aims to avoiding repetition of any part of a system by abstracting out things that are common and placing those things in a single location. This principle is not only concerned with code but any logic that is duplicated in a system; ultimately there should only be one representation for every piece of knowledge in a system.

### Tell, Don’t ask 
The Tell, Don’t Ask principle is closely aligned with encapsulation and the assigning of responsibilities to their correct classes. The principle states that you should to tell objects what actions you want them to perform rather than asking questions about the state of the object and then making a decision yourself on what action you want to perform. This helps to align the responsibilities and avoid tight coupling between classes.

### You ain’t Gonna need it (YaGni)
The YAGNI principle refers to the need to only include functionality that is necessary for the application and put off any temptation to add other features that you may think you need. A design methodology that adheres to YAGNI is test-driven development (TDD). TDD is all about writing tests that prove the functionality of a system and then writing only the code to get the test to pass. TDD is discussed a little later in this chapter.

### separation of Concerns (soC) 
SoC is the process of dissecting a piece of software into distinct features that encapsulate unique behavior and data that can be used by other classes. Generally, a concern represents a feature or behavior of a class. The act of separating a program into discrete responsibilities significantly increases code reuse, maintenance, and testability.