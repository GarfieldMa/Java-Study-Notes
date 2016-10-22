#COMP2396 OOP in Java

##Introduction

#### OOP v.s. PP
Procdedural Programming | Objec-Oriented Programming
------------------------|--------------------------- 
task | data
top-down design | bottom-up design
functions | classes

#### Trade Off:
* Security(Access Control)
* maintain&extend
* Code reusability

#### Objects in OOP
* Instances of the same class
	* have same  instance variables that represent their states to represent their **state**
	* actual values stored may be different
	* have same set of methods to represent their **behaviour**
	* actual behaviors **depend** their own states
 
#### Four Fundamental OOP Concepts
* **Abstraction**: representing essential features withour including backgroud details.
	* **WHAT** an object is
	* necessary and common properties
	* essential in **design**
* **Encapsulation**: wrapping data and operations into a single unit
	* information and implementation hiding
	* objects interact through public methods
	* essential in **implementation**
* **Inheritance**: objects of one class acquire the properties of objects of another class
	* a **subclass** can be derived from its **superclass**
	* **ISA TEST**: a subclass **is a** specialization of its superclass (inherit all its properties)(E.g. Cat is Animal)
* **Polymorphism**: able to take more than one form
	* making a call to the same method may results in different behaviors depending on the actual subclass object being called
	
#### Java
* Object-oriented
* Platform independent
* Architectural-neutral (Runing under Java Virtual Machine)
* Java application
	* at least one class
	* **at least one** main() method
* **strong type**
* variable: primitive type and reference
* Loops: iterator is avaliable in Java
```Java
String[] names = { "Amanda", "Jessica", "Jacky" };
for ( String name : names ){
	System.out.println( name );
}
```

## Classes and Objects

#### Advantages of OOP
* **Modularity**
* **Information hiding**
* **Code re-use**
* **Pluggability**

#### Class
* Blueprint of an object 
	* class tells virtual machine how to make an object of that type
* abstract both **state** and **behavior** of the objects created from the class

#### Object
* An instance of class
* Instance vairable: 
	* things an object **know** about itself
	* **state/data** of an object
	* differ from object to object
* Method:
	* thins an object **does**
	* **behavior** of an object
	* **operate on data** of an object
* Define a Class:
```Java
class Dog{
	//instance variable 
	
	//methods' definition
}
```
* Inherit from superclass:
```Java
class Poodle extends Dog
```
* **main()** Method:
	* **create** an object
	* **Call a method** of the object
	* name of the program is not included in the ``args``
```Java
public static void main(String[] args)
```
#### Garbage Collection
* objects live on **heap** 
* an object become eligible for **garbage collection** when it will never be used
* when system memory is low, **Garbage Collector** will run

## Primitives and References

#### Varibale Declaration
* Declare before use
* type and name

#### Primitive Types
* 8 primitive types: boolean, char, byte, short, int, long, float, double 
```Java
double PI = 3.14159;
float PI_F = 3.14159f; //Java treats number with floating point as double 'f' specify them as a float
```
* Type conversion: 
	* compiler doesn't allow cast wider range to narrower range (as this might result in information loss)
	* we must explicitly tell the compiler we want to cast
	
#### References
* **object reference variables** instead of **object variables**
* holds **way to access** a specific object
* doesn't hold **actual value**
```Java
Book b = new Book();
Book c = new Book();
Book d = c; //d refers to the same object as c, so we haven't create any new object
```

#### Array
* holds primitive types or reference variable
```Java
int[] nums = {6, 19, 44, 42};\\or
int[] arrs = new int[4];
```

## State and Behaviour of an object

* Instances of the same class have **same instance variables** and **same methods** but actual value may be different

#### Parameters

* **pass-by-value**

#### Methods

* Getters and setters (**Encapsulation**)
* Constructor
	* called automatically when an object is created
	* **same name** as the class
	* **no** return type
	* can be overloaded
	* **default constructor** will only be defined for a class when there is no other constructor
	* **Inheritance**
		* constructors are **not inherited**
		* **constructor chaining** to the **no no-argument constructor** of its superclass
		
#### Static 
* **Static Method**: methods doesn't depend on the value of instance variable
	* can run withtour any instance of the class
```Java
	Math.round( 3.14 ); //Math is class name and round() is a static method
``` 
	* can't use any **non-static** instance variables
	* can't use other **non-static** methods
* **Static Variable**: 
	* **shared** by all instances of a class
	* **initialized** when the class loaded for the first time
	* can be accessed using **class name**
	* can be used in **static methods** 
	
#### Final
* **no default value**
* can not be changed
```Java
public final int volume = 330;
```
* to define a constant
```Java
public static final double PI = 3.141592653589793;
```
* **static initializer**: run after the class is loaded and any static method can be used
```Java
public class Foo2 {
	public static final int FOO_X;
	static {
		FOO_X = 25;
	}
}
```
* **final method** cannot be overridden
* **final class** cannot be extended
	
#### Variable Initialization
* Instance variable get default value if not assigned:  

 type | default value
 ------|--------------
 number primitive | 0
 boolean | false
 object references | null
 
* Local variable: **must be initialized** before used

#### Comparison 
* `==`: check whether L.H.S and R.H.S's bit patterns are the same and extra bits will be ignored

## Java API

#### Packages
* advantages:
	* organization
	* name-scoping
	* security
* class' full name:
	* package name + class name
	* **must be specified** when class in a package other than ``java.lang`` is used
	* imprt all classes in a package (E.g. ``java,util``) to avoding typing the full name:
```Java
import java.util.*;
```

#### ArrayList
```Java
// create an ArrayList
ArrayList<Egg> myList = new ArrayList<Egg>();
// put something into it
Egg a = new Egg();
myList.add(a);
// put another thing into it
Egg b = new Egg();
myList.add(b);
int theSize = myList.size();
// find out if it contains something
boolean isIn = myList.contains(a);
for (Egg egg : myList) {
// egg.xxxx
}
```
* avaliable methods:
	* ``add(Object elem)``
	* ``remove(int index)``
	* ``remove(Object elem)``
	* ``contains(Object elem)``
	* ``isEmpty()``
	* ``indexOf(Object elem)``
	* ``size()``
	* ``get(int index)``

#### Wrapper Class

* classes correspond to primitive types: as ``ArrayList`` only supports class

primitive  type | wrapper class
----------------|--------------
boolean | Boolean
char | **Character**
byte | Byte
short | Short
int | **Integer**
long | Long
float | Float
double | Double

* wrap and un wrap:
```Java
boolean b = true;
Boolean bWrap = new Boolean(b);
boolean bUnWrap = bWrap.booleanValue();
```

* **autoboxing**: automatically conversion between primitive types and wrapper classes
	* works in assigning value, method arguments, return values, arithmetics, boolean expression
* static method to parse a string to a primitive:
	
```Java
double d = Double.parseDouble("420.24");
boolean b = Boolean.parseBoolean("True");
```

* static method to parse a primitive to a string:
```Java
double d = 42.5;
String doubleString = "" + d; // concatenating
String anotherDoubleString = Double.toString(d);//static method
```

#### Number Formatting
```Java
float a = 4.333;
String s = String.format("This cat weights %.2fkg", a );
```
foramt | meaning
-------|--------
%,d| insert **commas**, format as integer
%.2f| float with precision of **2** decimal places
%,.2f|  
%,5.2f | 5 means at least 5 characters wide, padding spaces and zeros
%h | hexadecimal
%c | character

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

## Abstract Classes and Interfaces

#### abstract class
class that can not be instantiated

* a class must be **abstract** if it has at least one **abstract method**

```Java
abstract class Canine extends Animal {
	public void roam() { ... }
}
```
#### abstract method
method has **no method body** and hence must be **extended** 
```Java
public abstract void eat();
```
* a **concrete class** must implements all the **abstract method** it inherits
* an **abstract class** may not need to do so

#### Interface
solve the problem of restriction of **multiple inheirtance**


	
	 





















