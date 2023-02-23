<b>What is JavaWeb?</b><br>
Use JAVA to complete the server-side program development<br>

<b>Testing type</b><br>
Black box testing: No need to write code, give the input value, see if the program can output the expected value<br>
White box testing: You need to write code and focus on how the program executes, such as JUNIT<br>

<b>1. Junit</b>.  
Steps:  
1. Define a test class (test case)  
Suggestion: 
- Test class name: Name of the class+Test <b>ComputerTest</b>.  
- Package name: xxx.xxx.xx.test <b>cn.itcast.test</b>. 
2. Define test methods: They can be run independently  
Suggestion:   
- Method name: test + Method name  <b>testAdd()</b>
- Return value: void
- Parameter list: empty parameter
3. add @Test. 
4. import junit dependency. 

Simple version: install JunitGenerator in Idea and press command+N in the class to generate test class. 

```
//computer class with two methods
public class Computer {
    public Integer add(int a, int b){
        return a+b;
    }
    public Integer reduce(int a,int b){
        return a-b;
    }
}
//    Initialization method:
//    For resource requests, all test methods execute this method before execution
@Before
public void before(){
}

//    Methods of resource release:
//    After all test methods have been executed, the method is automatically executed
@After
public void after(){
} 
@Test
public void testAdd(){
    //1.create object
    Computer computer = new Computer();
    //2.call add method
    int sum = computer.add(1, 2);
    //System.out.println(sum);
    Assert.assertEquals(3,sum);
} 
```
- Judgment result:  
Red: Failure  
Green: Success  
Typically we use assertion operations to process the result  

<b>2. Reflection</b>: Soul of frame design  
Framework: work-in-progress software. Can carry out software development on the basis of framework again, simplify coding  
Reflection: Encapsulating parts of a class as other objects is the reflection mechanism  
Advantages:  
1. These objects can be operated in the program operation project;
2. Can decouple, improve the program scalability.  

> JAVA code goes through three phases in a computer
- source code stage(hard disk). 
Person.java --(javac compile)----> Person.class. 
- class object stage. 
ClassLoader will load Person.class to (memory).   
- runtime stage  
Person p; This is created by class object.   

![image](https://user-images.githubusercontent.com/88880169/220913648-ba494b88-7caf-4289-964a-0fb707488af8.png)

> To get the Class object:
1. Class.forname (" full Class name "): Loads the bytecode file into memory and returns the Class object
* Most commonly used in configuration files, where the class name is defined. Read the file and load the class
2. class name: Obtained through the class attribute of the class name
* Most used for parameter passing
3. getClass(): The getClass() method is defined in the object class. 
* Most often used as a way of obtaining bytecode for objects
<b>4. conclusion:</b> The same bytecode file (*.class) is loaded only once during a program run, and the CLASS object is the same either way

```
//1.Class.forname
        Class cls1=Class.forName("JavaWeb.Computer");
        System.out.println(cls1);
        //2. class name
        Class<Computer> cls2 = Computer.class;
        System.out.println(cls2);
        //3. getClass()
        Computer computer=new Computer();
        Class<? extends Computer> cls3 = computer.getClass();
        System.out.println(cls3);
```        

<b>Class object function</b>:  
- Access function:  
1. Get member variables;  
- Field[] getFields(); Gets the public modified member variable
- Field getField(String name)Gets the public modified member variable
- Field[] getDeclaredFields() Gets all member variables, regardless of modifiers
- Field[] getDeclaredField(String name) Gets all member variables, regardless of modifiers
2. Get constructors;   
- Constructor<?>[]	getConstructors()
- Constructor<T>	getConstructor(Class<?>... parameterTypes)
- Constructor<?>[]	getDeclaredConstructors()
- Constructor<T>	getDeclaredConstructor(Class<?>... parameterTypes)
3. Access to member methods;   
- Method[]	getMethods()
- Method	getMethod(String name, Class<?>... parameterTypes)
- Method[]	getDeclaredMethods()
- Method	getDeclaredMethod(String name, Class<?>... parameterTypes)
4. Obtain the class name.  
- Class<?>[]	getClasses()
- Class<?>[]	getDeclaredClasses()
- Class<?>	getDeclaringClass()  


```
 Field[] fields = computerClass.getFields();
        for(Field field:fields){
            System.out.println(field);
        }
        Field name = computerClass.getField("name");
        System.out.println(name);
        Computer c = new Computer();
        Object o = name.get(c);
        System.out.println(o);
        name.set(c,"mac");
        System.out.println(c.name);
        System.out.println("==================");
        computerClass.getDeclaredFields();
        Field name1 = computerClass.getDeclaredField("name");
        //Ignore security checks for access modifiers
        name1.setAccessible(true);//reflection attack
        name1.get(c);
```
<p>In Java programming, "暴力反射" can be translated to "reflection" or "reflection attack". It refers to a type of attack where an attacker uses Java reflection to access and manipulate private or protected fields and methods of a class, which are not intended to be accessed or modified by external code. This can be a security vulnerability if the class is not designed to handle external access in a secure manner.</p>
> Case:
- Requirements: Requirements: Write a framework that can help us create objects of any class and execute any method without changing any code in that class  
- Implementation:
1. Configure the file
2: Reflection
- Steps:
1. Define the class name of the object to be created and the method to be executed in the configuration file
2. Load and read the configuration file in the program
3. Use reflection technology to load class files into memory
4. Create objects
5. Execution method   

```
className=JavaWeb.Computer
methodName=eat



  public static void main(String[] args) throws Exception {
        //load properties
        //1.1 create pro object
        Properties pro = new Properties();
        //1.2load properties and convert to a collection
        //1.2.1 get configuration under class catalog
        ClassLoader classLoader = ReflectTest.class.getClassLoader();
        InputStream resourceAsStream = classLoader.getResourceAsStream("pro.properties");
        pro.load(resourceAsStream);
        //2.get data defined in configuration
        String className = pro.getProperty("className");
        String methodName = pro.getProperty("methodName");
        //3.Load the class into memory
        Class<?> aClass = Class.forName(className);
        //4.create object
        Object o = aClass.newInstance();
        //5.get method objects
        Method method = aClass.getMethod(methodName);
        //6.execute method
        method.invoke(o);
    }
```    

