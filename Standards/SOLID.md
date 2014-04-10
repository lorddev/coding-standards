## SOLID principles

The mnemonic "SOLID" refers to a particular school of object-oriented software development best practices which is focused on increased clarity and maintainability. The five partitions of **SOLID** are 

* Single responsibility principle
* Open/Closed principle
* Liskov substitution principle
* Interface segregation principle
* Dependency inversion principle

### Single responsibility

Functions should do one thing. Classes should have one purpose, and only one reason to change.

### Open/closed principle (Meyer)

> The idea was that once completed, the implementation of a class could only be modified to correct errors; new or changed features would require that a different class be created. That class could reuse coding from the original class through inheritance. The derived subclass might or might not have the same interface as the original class. ([Wikipedia](http://en.wikipedia.org/wiki/Open/closed_principle))

When features are added, use a subclass instead of changing the original class. This helps ensure backwards compatibility, which is kind of awesome.

### Liskov substitution principle

A subtype ought to be able to be substituted for an object of its parent class without compromising the integrity and intent of the system. In C# inheritance, this is built in, unless an overridden function deliberately does the opposite of what the base class function does.

### Interface segregation principle

Interfaces should be small, and only reflect a single particular functionality. For example, if an object can read and write, use an `IReader` interface and an `IWriter` interface, rather than creating an `IReadWrite` interface.

### Dependency inversion principle

Depend on abstractions, not concretions. All your hooks to another tier should use interfaces.
