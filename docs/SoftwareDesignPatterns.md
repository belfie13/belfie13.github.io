# 🇭🇷 Croational patterns 🇭🇷

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

```PHP
<?php

/**
 * Defines how a client may use the services.
 */
interface ServiceInterface
 {
    public function performOperation($onThis);
    public function doCalculation($withThis, $andThis):string;
    public function executeAlgorithm($configuration, $options);
    public function validateData($data):bool;
 }

/**
 * Objects that depend on a service(s) they use.
 */
class Client
 {
    /**
     * setter injection example.
     */
    public function setService(ServiceInterface $service)
     {
        $this->service = $service;
     }
     
    /**
     * constructor injection example.
     */
    public function __constructor(ServiceInterface $service)
     {
        $this->service = $service;
     }
 }

/**
 * Responsible for creating service objects needed and configuring clients with them.
 */
class Injector
 {
    /**
     * setter injection example.
     */
    public function conditionWasMet(Client $client)
     {
        if ($_POST['key'] == 'this one!')
         {
            $service = $this->factory->createThisOneService();
            $client->setService($service);
         }
     }
     
    /**
     * constructor injection example.
     */
    public function createClientWithThatService():Client
     {
        $service = $this->createThatService();
        $client = new Client($service);
        return $client;
     }
 }
```


# Structural patterns 

are about organizing different classes and objects to form larger structures and provide new functionality. 


# behavioral patterns 

are about identifying common communication patterns between objects and realize these patterns. 
