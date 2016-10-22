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
