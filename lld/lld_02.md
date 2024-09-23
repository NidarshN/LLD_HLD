# 2. SOLID Principles

5 Concepts created Robert C. Martin to facilitate more concise, understandable and modular codes aimed to reduce complexity.

## 1. Single Responsibility

A class should be  associated with only one responsibility and should have only a single reason to change

**Advantages**:  

* Easier and Isolated Testing  
* Weak Coupling due to low dependencies
* Modular Approach allows for easier management of services

## 2. Open / Closed  Principles

Class should be open for extension but should closed for modification

**Advantages**:

* Robustness - Confidence that the code works as intended
* Limits the possibilities of new bugs which arises due to modification

## 3. Liskov Substitution

Sub Class / Child class objects should behave in similar fashion to that of the parent class. The return type and signature of inherited methods should comply with that of it's parent methods.

**Advantages**:

* Code Reusability
* Modularity
* Easier Code Maintenance
* Increased Code Quality

## 4. Interface Segregation

Ability to breakdown large interfaces into modular independent interfaces to avoid strong dependencies.

**Advantages**:

* Modularity
* Reduced Coupling
* Scalability
* Reusability

## 5. Dependency Inversion

High Level Modules should not depend on low level modules, rather both should depend on abstraction (abstract classes and interfaces). This allows us to decouple high level and low level modules.

**Advantages**:

1. Loose Coupling
2. Improved Testability
3. Easier Code Maintenance