# Test-driven Development (TDD)

Contrary to the name, TDD is more of a design methodology than a testing strategy; the name simply just doesn’t do it justice. 

The main concept behind it is to allow your tests to shape the design of a system. When creating a software solution **you start by writing a failing test** to assert some business logic. Then you **write the code to get that test to pass**; last, you **clean up any code via refactoring**. This series of steps has been coined the red-green-refactor. The red and green refer to the colors that testing frameworks use to show tests passing and failing. 

By going through the process of TDD, you end up with a loosely coupled system with a suite of tests that confirm all behavior. 

A byproduct of TDD is that your tests provide a sort of living documentation that describes what your system can and can’t do. Because it is part of the system, the tests will never go out of date, unlike written documentation and code comments. 