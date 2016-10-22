## Inheritance and Polymorphism

#### Superclass and Subclass
* superclass and subclass
* **inheritance tree**
* the **lowest** method in the **inheritance tree** will be called
* ``super.someMethod()`` to call overriden method of the superclass (1 level higher)

#### Access Control
access level | access modifier | Class | Package | Sub-Class | World
-------------|-----------------|-------|---------|-----------|------
private | ``private`` | Y | N | N | N
default | N/A | Y | Y | N | N 
protected | ``protected`` | Y | Y | Y | N
public | ``public`` | Y | Y | Y | Y

#### Inheritance Design
* IS-A test
* common behavior for superclass
* specilization for subclass

#### Method Overriding
* **same argument list** (while overload has different argument list)
* **copatible return type**
* **equal or higher access level**
