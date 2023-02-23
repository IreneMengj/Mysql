
<b>1.What is a JVM?</b><br>
Java Virtual Machine - Runtime environment for java programs (runtime environment for java binary bytecode)<br>
<b>Benefit:</b><br>
<li>Write once, run everywhere</li>
<li>Automatic memory management, garbage collection function</li>
<li>Array subscript out of bounds check</li>
<li>polymorphism</li>
<b>compare: jvm,jre,jdk</b><br>
1. JRE (Java Runtime Environment): It includes the JVM along with other libraries and components required to run Java applications. The JRE doesn't include any development tools, and it's meant for end-users who want to run Java programs on their machines.<br>
2. JDK (Java Development Kit): It's a software development kit that includes the JRE and additional tools for developing Java applications. The JDK includes a compiler for converting Java source code into bytecode, along with other tools for debugging, testing, and documentation.<br>
3. To summarize, the JVM is the runtime environment that executes Java code, the JRE is the environment that allows end-users to run Java applications, and the JDK is the software development kit that includes tools for building and debugging Java applications.<br>

<h3>Memory structure</h3><br>
1. Program counter 2. Virtual machine stack 3. Local method stack 4. Heap 5. Method area <br>

<b>1.Program Counter Register</b>:<br>
To remember the execution address of the next jvm instruction
<b>characteristic</b>
<li>It's thread private</li>是线程私有的
<li>There is no memory overflow</li>

<b>2.Java Virtual Machine Stacks</b>:<br>
The amount of memory that each thread needs to run is called the virtual machine stack. Each stack is made up of multiple stack frames, which corresponds to the amount of memory used for each method call. Each thread can only have one active stack Frame, which corresponds to the method that is currently executing<br>

1. Does garbage collection involve stack memory?<br>
2. Is larger stack memory allocation better?<br>
3. Are local variables within methods thread-safe?<br>
Local variables within a method are thread-safe if they are not accessed from the action of the method<br>
If a local variable references an object and escapes the scope of the method, you need to consider thread safety<br>

Stack Memory Overflow <br>
1.Excessive stack frames cause stack memory overflow<br>
2.Too large stack frame causes stack memory overflow<br>

<b>4.Heap</b>:<br>
<b>4.1. definition</b>: With the new keyword, objects are created using heap memory<br>
<b>characteristic</b><br>
It is thread-shared, and the objects in the heap need to be thread-safe<br>
There is a garbage collection mechanism<br>
<b>4.2. Heap memory overflow</b><br>
In the context of the Java Virtual Machine (JVM), heap memory overflow refers to the situation when a Java program tries to allocate more memory on the heap than is available.

The heap is the portion of memory used by the JVM to store Java objects created by a program at runtime. When a Java program requests memory allocation on the heap using the "new" keyword or through other object creation mechanisms, the JVM will try to allocate memory from the heap space.

If the JVM cannot find enough contiguous free space in the heap to satisfy the allocation request, it will throw an OutOfMemoryError. This can happen if the program has a memory leak or if it simply allocates more memory than the available heap space.

Heap memory overflow in the JVM can cause the program to crash or behave unpredictably. To prevent this error, developers can optimize their code to minimize memory usage and use tools like profilers and memory analyzers to detect and fix memory leaks. The JVM also provides several command-line options that can be used to adjust the heap size and allocation parameters to better suit the needs of the program.






