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
2. class name: Obtained through the class attribute of the class name
3. getClass(): The getClass() method is defined in the object class

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





