
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

Program Counter Register:
To remember the execution address of the next jvm instruction
<b>characteristic</b>
<li>It's thread private</li>是线程私有的
<li>There is no memory overflow</li>

Java Virtual Machine Stacks:<br>
The amount of memory that each thread needs to run is called the virtual machine stack. Each stack is made up of multiple stack frames, which corresponds to the amount of memory used for each method call. Each thread can only have one active stack Frame, which corresponds to the method that is currently executing<br>






