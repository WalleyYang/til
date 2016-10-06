### OOP Concepts
**ABSTRACTION:** Abstraction is a process of hiding the implementation details and showing only functionality to the user. Abstraction lets you focus on what the object does instead of how it does it. You can achieve abstraction in Java through abstract classes and interfaces.

**Abstract Class:** 
 - Contain mixed methods declared with or without implementation
 - Declare fields that are not static and final
 - Define access modifiers public, protected, and private for concrete methods.

**Interfaces:**
 - All fields are automatically public, static, final
 - All methods are public

**Abstract Classes vs Interfaces:** Extending an abstract class is saying your class IS something. Implementing an interface is saying your class DOES something. Tacoma extends Toyota implements Drivable.

**POLYMORPHISM:** Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. Method overriding is considered polymorphic.

**INHERITANCE:** Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another.

**ENCAPSULATION:** Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.
 - Declare the variables of a class as private.
 - Provide public setter and getter methods to modify and view the variables values.
