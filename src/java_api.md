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

