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


## GUI and Event-Handling

In Java GUI, y is the vertical axis and x is the horizontal one.

####``JFrame``
* ``import javax.swing``
* an **object** represents a **window** 
* host all the **Swing component**
* has **windowing icons** for **minimizing, mximizing* and **closing**
* ``JFrame()``: default constructor
* ``setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE)``: make program **quit** when window is closed
* ``add(someWidget)``: add wdiget to the frame
* ``add(someWidget, location)``: add ``someWidget`` into ``location``.$location\in\{BorderLayout.NORTH, BorderLayout.WEST, BorderLayout.CENTER, BorderLayout.EAST, BorderLayout.SOUTH\}$
* ``repaint()``: repaint the frame and therefore ``paintComponent()`` will be called
* ``setSize(width,height)``
* ``setVisible(isVisible)``: set the visibility of ``JFrame`` as ``isVisible`` 

####``Swing``
* the widget of the window
* ``import javax.swing``
* most of the common Swing components extend from ``javax.swing.JComponent``
* we classify components into __interactice__ and __backgroud__ components, however, this distinction is artificial
* we can usually add __interactive__ component into __background__ component
* ``JLabel``:
	* ``label.setText(str)``

####Create a GUI
1. Create a **JFrame**:``JFram frame = new JFrame()``
2. Create some widgets (Swing): ``JButton button = new JButton("click me")``
3. Add the widget to the frame: ``frame.add(button)``
4. Display:
```java
frame.setSize(300,300);
frame.setVisible(true);
```

####Event Handling
* ``import java.awt.event``
* Swing GUI components are **event source** turning **user actions** into **events**
* **Event Classes** represent certain type of events (e.g. ``ActionEvent``,``MouseEvent``) 
	* ``event.getSource()`` return the source of event
* **listener interface**: implement certain **listener interface** to handle certain events (e.g. ``ActionListener``, ``MouseListener``)
	* a **listener interface** may have more than one method 
* **listener**: the class the implement **listener interface**
	* **register**: a **listener** must register itself to **event source** to receive events.
	* **register method**: (e.g. ``addActionListener(someListener)``, ``addMouseListener(someListener)``)
	
####Display User Designed Graphic
* define a **subclass** of **JPanel**
* override ``paintComponent(Graphics g)`` method. However, we will never call this method by ourselves
* **Graphics**:
	* ``g.setColor(Color.CONST)`` set color as ``CONST``
		* ``Color color = new Color(red_c, green_c, blue_c )``, where ``red_c``,``green_c`` and ``blue_c`` are integer constant.
	* ``g.fillRect(x,y,width,height)``
	* ``g.fillOval(x,y,width,height)``
	* ``g.drawImage(image,width, height,this)``
* **Graphics2D**: a subclass of **Graphics**
	* the argument passed in ``paintComponent(Graphics g)`` actuallay references to a **Graphics2D** object so we can cast it
* **Image**:
	* ``Image image = new ImageIcon(file_path).getImage()``
	
####Inner class
* class defined within another class
* can access **all** the methods and instance variables of the **outer class** and vice-versa
* tied to **outer class objects** on the heap
* can't access other **outer class** except the one it is tied to

####Layout Manager
* **BorderLayout**: default layout for a frame with 5 regions. Nort and South Components will get prefered height and as wide as the frame. East and West Components will get prefered width and as high as remain. Center will get the space remained
* **FlowLayout**: default layout for a panel. Components are laid out left to right in the order that they are added. When a component doesn't fit horizontally, it drops to the next "line" in the layout.
* **BoxLayout**: like a ``FlowLayout`` but it can stack components either **vertically** or **horizontally**
	* ``setLayout(new BoxLayout(panel,BoxLayout.Y_AXIS))``
* **GridBagLayout**:
	* Components are placed in a
	* Rows can be of different heights
	* Columns can be of different widths 
	* Components can span multiple rows or columns
	* The size and placement of a component in the grid is specified by a GridBagConstraints object
	* **gridx** x-pos of cell containing leading column
	* **gridy** y-pos of cell containing leading row
	* **gridwidth** num of cells in a row
	* **gridheight** num of cells in a column
	* **weightx** specifies how to distribute extra horizontal space
	* **weighty** specifies how to distribute extra vertical space
```java
	    JFrame frame = new JFrame();
	    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	    
	    JPanel panel = new JPanel(); 
	    panel.setLayout(new GridBagLayout());
	    GridBagConstraints c = new GridBagConstraints();
	    c.gridx = 0;
	    c.gridy = 0;
	    c.gridwidth = 1; // default value
	    c.gridheight = 1; // default value
	    c.weightx = 0.0; // default value
	    c.weighty = 0.0; // default value
	    c.anchor = GridBagConstraints.CENTER; // default value
	    c.fill = GridBagConstraints.HORIZONTAL;
	    c.insets = new Insets(0, 0, 0, 0); // default value
	    c.ipadx = 0; // default value
	    c.ipady = 0; // default value
	    
	    JButton button = new JButton("Button 1");
	    c.weightx = 0.5;
	    panel.add(button, c);
	    
	    button = new JButton("Button 2");
	    c.gridx = 1; // 2nd column
	    panel.add(button, c);
	    
	    button = new JButton("Button 3");
	    c.gridx = 2; // 3rd column
	    panel.add(button, c);
	    
	    button = new JButton("Button 4");
	    c.gridx = 0; // 1st column
	    c.gridy = 1; // 2nd row
	    c.gridwidth = 3; // spans 3 columns
	    c.weightx = 0.0;
	    c.ipady = 40; // makes the button tall
	    panel.add(button, c);
	    
	    button = new JButton("Button 5");
	    c.gridx = 1; // 2nd column
	    c.gridy = 2; // 3rd row
	    c.gridwidth = 2; // spans 2 columns
	    c.weighty = 1.0; // takes up extra vertical space
	    c.anchor = GridBagConstraints.SOUTH;
	    c.insets = new Insets(10, 0, 0, 0); // top padding
	    c.ipady = 0;
	    panel.add(button, c);
	    
	    frame.add(panel);
	    frame.pack();
	    frame.setVisible(true);
```





	
	 





















