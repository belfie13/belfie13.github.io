# Creational patterns 

provide the capability to create objects based on a required criteria and in a controlled way. 


## Dependency injection

one object supplies the dependencies (objects that can be used) of another object.
It separates the creation of a client's dependencies from the client's behavior.

It allows program designs to:
- be *loosely coupled*
- follow the *dependency inversion* principles
- follow the *single responsibility* principles.

It involves four roles:
* **service** object(s) to be used
* **client** object that is depending on the service(s) it uses
* **interfaces** that define how the client may use the services
* **injector**, which is responsible for constructing the services and injecting them into the client

Types of dependency injection:
* **constructor injection** The dependencies are provided through a client's *class constructor*.
* **setter injection** The client exposes a *setter method* that the injector uses to inject the dependency.
* **interface injection** The dependency's interface provides an injector method that will inject the dependency into any client passed to it. Clients must implement an interface that exposes a *setter method* that accepts the dependency.


# Structural patterns 

are about organizing different classes and objects to form larger structures and provide new functionality. 


# behavioral patterns 

are about identifying common communication patterns between objects and realize these patterns. 
