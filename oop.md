## What are the main features of OOP?
- Inheritance
- Encapsulation
- Abstraction
- Polymorphism

## What is Inheritance ?
- It's the ability of a class to inherite properties and methods from another super class
- In Java it's only possible to inherit from a single class, this is to avoid the diamond problem when class A and B inherite from class C and both override the run() method. Then class D inherits from both class A and B and Java doesn't understand which implementation it inherits

## What is Encapsulation?
- It means bundle data and behaviors of an entity within a class.

## What is Abstraction?
- It means the ability to hide the internal structure of a class, including properties and methods from the outside.
- Only part of that data and methods is exposed.

## What is Polymorphism?
- It's the ability of data to have many forms based on how it's called
- For example, we have a class Animal with a makeSound() method, class Dog inherits from Animal ans override makeSound() to return "Woof", another class Cat inherits from Animal and return "Meow". Let's say we have a method that take Animal as a parameter then call the its makeSound() method. The result of this method is different, depends on how we create the Animal object, if it's a Dog object then it's "Woof", if it's a Cat object then it's "Meow", this is called polymorphism at runtime.
- Method overloading could also be considered as polymorphism at complile time, if we have 2 methods with the same return type and name but different parameters, the compiler will depend on the parameters passed into the method to decide which method is called

## Difference between overloading and overriding
- Overloading is to have multiple methods with the same name but different input parameters, it's not possible to have different return types though.
- Overriding is for a subclass to change the behavior of a method that it inherits from a superclass.

## What are the access modifiers?
- Default: accessed by other classes in the same package
- Private: accessed within the class only
- Protected: accessed by subclasses and other classes in the same package
- Public: accessed by anyone.

## What is the super keyword?
- It's to call the property or method implementation of the parent class

## What are the SOLID design principles?
- S: Single responsibility, a class or a method should have only 1 responsibility, it should not have any side effect
- O: Open for extension and closed for modification, meaning the design of a class should allow other classes to extend its behaviors but its original properties and behaviors should not be modifed, we can do this using access modififer.
- L: Liskov's substitution, by her own word, the author describes this as if class A is a subclass of class B then class A should be able to replace class B without any unexpected outcome.
- I: Interface segregation, this means a class should not implement a method of an interface if it doesn't use it. This usually happens when an interface has multiple methods but a class might not need them all, thus it's better to break it down into multiple specialized interfaces
- D: Dependency inversion means the high level modules which handles complex business logic should not be affected by low level utility modules when they change. To do this we should introduce an abstraction to decouple them.

## Use cases of Abstract class
- When you have multiple related classes that have some common properties and behavior implementations, instead of writing the same logic on each class, we can have an abstract super class that defines the methods and implementations so that these classes can inherit from and can modify later if needed.
- Abstract class is used in a hierachy design where some classes are related and need to inherit common behaviors.

## Use cases of Interface
- Interfaces declare the common behavior of classes that are not necessarily related.
- These behaviors although are not necessarily similar in implementation, they are known to have these implementation so can be called by other methods using the interface references instead of concrete classes.
- Let's say you have a method that take in an object as a parameter, you want this object to be able to fly(), you don't care if it's a bird or a plane, you can use Flyable interface to refer to the input, then any classes that implement Flyable interface can be used, it could be Airplane or Spaceship or Bird class.


























