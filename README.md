# AngularSolidPrinciple


# What is SOLID principle in Angular

SOLID is a set of design principles that can be used to develop maintainable and scalable software applications. It stands for Single Responsibility Principle (SRP), Open-Closed Principle (OCP), Liskov Substitution Principle (LSP), Interface Segregation Principle (ISP), and Dependency Inversion Principle (DIP). Angular is a popular open-source framework for building web applications, and it can be used to implement SOLID design patterns.

# 1. S - Single Responsibility Principle (SRP):

The SRP states that a class should have only one reason to change. In Angular, this can be implemented by creating small, focused components that do one thing well. For example, a component that displays a list of items should only be responsible for displaying the list, and not for fetching the data or updating the items.


![image](https://github.com/user-attachments/assets/643f9ad9-3064-401b-81ba-36692881c6eb)


# 2. Open/Closed Principle (OCP):

The OCP states that a class should be open for extension but closed for modification. In Angular, this can be implemented by using interfaces and abstract classes to define behavior, and then implementing those interfaces or extending those classes in concrete classes. For example, if we have a service that fetches data from a backend API, we can define an interface for the service and then create concrete implementations of that interface for each backend API we need to support.

![image](https://github.com/user-attachments/assets/004282a6-8dad-4a37-8685-bb08d12675b1)



# 3. Liskov Substitution Principle (LSP):

The LSP states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program. In Angular, this can be implemented by using inheritance to create subclasses that inherit behavior and properties from a superclass. For example, if we have a base component that displays a list of items, we can create a child component that extends the base component and adds additional behavior or styling.

![image](https://github.com/user-attachments/assets/304f385b-9b7e-4d27-8880-2ec2a9664144)

# 4. Interface Segregation Principle (ISP):

The ISP states that a class should not be forced to depend on methods it does not use. In Angular, this can be implemented by creating small, focused interfaces that define behavior for a specific use case. For example, if we have a service that manages user authentication, we can create separate interfaces for login, logout, and user information retrieval.

![image](https://github.com/user-attachments/assets/01d2c88b-ef39-4078-981b-277caa612a3e)


# 5. Dependency Inversion Principle (DIP):

The DIP states that high-level modules should not depend on low-level modules, but should depend on abstractions. In Angular, this can be implemented by using dependency injection to provide dependencies to a class or component. For example, if we have a component that needs to make HTTP requests, we can inject an HTTP service into that component instead of creating a new instance of the service inside the component.

![image](https://github.com/user-attachments/assets/7078f868-fe01-437e-8e4a-1a80cb737279)
