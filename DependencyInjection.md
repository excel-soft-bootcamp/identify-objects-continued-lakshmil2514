# Dependency Injection

* Dependency Injection (DI) is a design pattern used to implement IoC

## Advantages

* Reduces class coupling
* Increases code reusing
* Improves code maintainability
* Improves application testing

## Types of Dependency Injection
1. Constructor Injection: In the constructor injection, the injector supplies the service (dependency) through the client class constructor.
2. Property Injection: In the property injection (aka the Setter Injection), the injector supplies the dependency through a public property of the client class.
3. Method Injection: In this type of injection, the client class implements an interface which declares the method(s) to supply the dependency and the injector uses this interface to supply the dependency to the client class.

