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

#### interface
* **interface** is a **pure abstract class** with all method being **abstract** 
* solve the problem of restriction of **multiple inheirtance**
```Java
public interface Pet {
	public abstract void beFriendly();
	public abstract void play();
}
```
* Interface methods are implicitly
**public** and **abstract**
* ``implement`` a **class** ``implements`` the ``interface`` must implement all the interface's methods
* a class may ``implements`` multiple interfaces

#### general design rule
* class
* subclass
* abstract class
* interface


