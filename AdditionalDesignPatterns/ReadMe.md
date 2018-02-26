# Additional Design Patterns

Additonal design patterns have been invented since the original GoF book. These are:

## null object Pattern 
Also known as the Special Case pattern, this acts as a return value rather than returning null to the calling code. The null object will share the same interface or inherit from the same base class as the expected result, which alleviates the need to check for null cases throughout the code base.

## Separated Interface 
The Separated Interface pattern is the act of keeping the interfaces in a separate assembly or namespace to the implementations. This ensures that the client is completely unaware of the concrete implementations and can promote programming to abstractions rather than implementations and the Dependency Inversion principle