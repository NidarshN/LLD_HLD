# 1. Basic Object Oriented Programming Concepts

Object Oriented Programming (OOP) is a programming paradigm which facilitates the creation of clean, concise and modular code. It primarily revolves around the concept of classes and objects.

## Classes

Classes are often referred to as a blueprint which defines the behaviour and properties associated with an object.

**Example:**

    class Vehicle:
        def __init__(self, brand, model, year):
            self.brand = brand
            self.model = model
            self.year = year

        def display_vehicle_info(self):
            print(f"The {brand} has created the {model} in the year {year}.")

## Objects

Objects are real world instances of classes.

**Example:**

    civic_vehicle = Vehicle('Honda', 'Civic', 2023)
    civic_vehicle.display_vehicle_info()

## OOPS Concepts

### 1. **Encapsulation**

Encapsulation is the ability to conceal the private data of an object from the external world, exposing only necessary information via public methods for usage.

**Example:**

    class User:
        def __init__(self, username, name, password):
            self.username = username
            self.name = name
            self.__password = password

        def get_password(self):
            return self.__password

        def set_password(self, new_password):
            self.__password = new_password

In the above example, password is a private field of class User. Since the provate fields cannot be accessed outside the scope of the class, we utilise methods such as get_password and set_password to fetch and set the value to / from the class object respectively.

### 2. **Inheritence**

Inheritance is the ability to inherit properties from another class. While the class from which the property is being inherited from is called super class / base class / parent class, the class innheriting such properties is called the child class.

**Example:**

Using the above example of Vehicle class as parent class:

    class Car(Vehicle):
        def __init__(self, brand, model, year, color, price):
            super().__init__(brand, model, year):
            self.color = color
            self.price = price

        def get_price(self):
            return self.price

    new_car = Car('Honda', 'Civic', 2023, 'silver', 25000)
    new_car.display_vehicle_info()
    new_car.display_price()

### 3. **Polymorphism**

Polymorphism is the ability to have multiple forms for a given function.

#### **Method Overloading**  

Method overloading is not directly supported in Python like it is in languages such as Java or C++. However, Python can achieve a similar effect using default parameters or variable-length argument lists (*args and **kwargs).

#### **Method Overriding**  

In terms of inheritance, inherited functions for the child can override the definitions given by the parent class.

| **Method Overloading** | **Method Overriding** |
| :---        |    :----   |
| Not natively supported in Python. You can simulate it using default arguments or *args/**kwargs. | Fully supported in Python. A child class can override a method from its parent class. |
| Occurs within the same class. | Occurs between a parent class and its child class. |
| Involves methods with the same name but different signatures (different parameters). | Involves methods with the same name and same signature (same parameters). |
| Helps in adding flexibility by allowing a method to accept varying numbers or types of parameters. | Allows a subclass to provide a specific implementation for a method defined in its superclass. |

**Example:**

Using the above example of Car class

    class Sedan(Car):
        def __init__(self, brand, model, year, color, price, features):
            super().__init__(brand, model, year, color, price)
            self.features = features

        # Method Overloading
        def run(self, speed=None):
            if(speed is not None):
                print(f"The car is in motion at a speed of {speed} km/hr")
            else:
                print(f"The car is in motion!")            

        # Method Overriding
        def get_price(self):
            return self.price * 10

### 4. **Abstraction**

Abstraction is the ability to hide the actual implementation details, exposing only the required features of the object

Python provides a module for abstraction called the abc module (Abstract Base Classes)

#### **Abstract Class**  

A class that cannot be instantiated and is meant to be inherited by subclasses that implement the abstract methods.

### **Abstract Method**

A method that is declared, but contains no implementation. Any subclass inheriting the abstract class must implement the abstract method.

**Example:**

    from abc import ABC, abstractmethod

    # Abstract Class
    class Car(ABC):
        def __init__(self, model, year):
            self.model = model
            self.year = year

        @abstractmethod
        def start_engine(self):
            pass

        @abstractmethod
        def fuel_type(self):
            pass

    class ElectricCar(Car):
        def start_engine(self):
            return f"{self.model} engine started silently."

        def fuel_type(self):
            return "Battery powered"

    class PetrolCar(Car):
        def start_engine(self):
            return f"{self.model} engine started with a roar."

        def fuel_type(self):
            return "Petrol powered"
            
