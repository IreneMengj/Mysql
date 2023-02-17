<b>1. Basic knowledge of Java</b>
1. Object class related methods<br>
<b>getClass</b>  Gets the Class object of the current runtime object.<br>
<b>hashCode</b> Returns the hash code of an object.<br>
<b>clone</b> copies the current object and must implement the <b>Cloneable</b> interface. <b>Shallow copy</b> copy the value of the basic type and copy the reference type. <b>Deep copy</b> copies the value of the basic type, and copies not only the reference of the object but also the properties and methods of the object. The difference is that deep copy creates a new object.<br>
<b>equals</b> compares two objects to each other by memory address. The String class overrides this method by using values to compare equality.<br>
<b>toString</b> returns the class name @ hash code in hexadecimal.<br>
<b>notify</b> Wakes up any thread of the current object monitor.<br>
<b>notifyAll</b> wakes up all threads on the current object monitor.<br>
<b>wait</b> 1. Pause the execution of the thread. 2. Three methods with different parameters (wait milliseconds; How many extra milliseconds to wait; 3. In contrast to Thread.sleep(long time), sleep puts the current Thread to sleep for a period of time without releasing the lock on the object. wait releases the lock.<br>
<b>finalize</b> The method to execute when a finalize object is collected by the garbage collector.<br>


<b>2、Basic data type</b>
Integral type：byte(8)、short(16)、int(32)、long(64)<br>
Floating point type：float(32)、double(64)<br>
boolean：boolean(8)<br>
char：char(16)<br>

