## What are design patterns?
- Design patterns are proven common solutions to solve common problem

## Why use design patterns?
- They're templates to follow when we face a common problem
- They're well tested and proven
- They provide transparency on the system designs

## What are the types of design patterns?
- Creation: about the creation of objects and hide the logic and data of those objects
- Structural: about how to design the structures of classes and services
- Behavioral: about how components should communicate with each other

## What is Decorator pattern?
- A decorator pattern is to use a class that wraps around some other classes. 
- This class has all the properties and methods of these classes but can also add more methods to communicate or manipulate the data of these classes. For example we have Java wrapper classes that provide more methods to the primitive data types.

## What is Singleton pattern?
- It's a pattern that instantiate only 1 object of a class during the whole program's life cycle.
- It does this by having a private static field of this class and a factory method that checks if this field already exists, if it does then it simply returns the field, else it instantiates it.

## What is Factory pattern?
- It's a pattern to instantiate objects of 1 or multiple classes based on the inputs and logic.
- By provide objects through a single factory class, it hides the creation logic of these classes.

## What is Observer pattern?
- It's when an object stores and maintains a list of dependencies (observers) and notifies these depedencies when the state changes.
- An object can become an observer of another by subscribing to it and being added to the list.
- An observer should implement an Observable interface so that it has a method to be called when the state changes.

## What is Adapter pattern?
- It's a pattern used when multiple components that have different interfaces want to communicate, then they should have adapters between them to translate the data.
- For example you're building a shopping website that allows users to pay using multiple payment provider like banks, credit cards, Paypal or phone bills. Upon checkout, the service calls pay() service to make the payment but each provider has a different API specification.
- The service should have adapters for each payment provider, ideally upon onboarding a new provider, this adapter helps translate the input data from upstream service and communicate with the provider's APIs.




















