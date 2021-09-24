# Dependency Injection Lifetime Options

### Service Lifetimes
1. #### Transient : Services are created each time they are requested. It gets a new instance of the injected object, on each request of this object.For each time you inject this object is injected in the class, it will create a new instance.
2. #### Scoped — Services are created on each request (once per request). This is most recommended for WEB applications. So for example, if during a request you use the same dependency injection, in many places, you will use the same instance of that object, it will make reference to the same memory allocation.
3. #### Singleton — Services are created once for the lifetime of the application. It uses the same instance for the whole application.

- The dependency injection container keeps track of all instances of the created services, and they are disposed of or released for garbage collector once their lifetime has ended. This is how we can configure the DI in .NET core



