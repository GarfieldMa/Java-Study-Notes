## The Ultimate Superclass: Object

#### Object
* every class in Java ``extends`` **Object** class
* **Object** class is the **superclass** of everything
* avaliable methods:
	* ``public boolean equals(Object obj)``
		* true if both reference variables refer to the same object
		* override both this method and ``hashCode()`` if you want to test whether they contain smae information
	* ``public final Class getClass()``
	* ``public int hashCode()``
		* if two objects are equal then they have the same result of ``hashCode()``
	* ``public String toString()``
		* class name + '@' + hash code (E.g. ``Dog@7852e922``)
#### Cast
* **cast** can also be applied to object reference:
```Java
Dog dog = new Dog();
Object o = dog;	//ISA
Dog sameDog = (Dog) o; //cast
```
* ``instance of``: check if an object is an instance of a certain class
```Java
Object o = new Dog();
if (o instanceof Dog) {
	System.out.println("It is a Dog");
}
```
