<b>What is JavaWeb?</b><br>
Use JAVA to complete the server-side program development<br>

<b>Testing type</b><br>
Black box testing: No need to write code, give the input value, see if the program can output the expected value<br>
White box testing: You need to write code and focus on how the program executes, such as JUNIT<br>

<b>Junit</b>.  
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



