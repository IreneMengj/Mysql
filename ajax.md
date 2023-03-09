### asynchronous Javascript and XML. 
- synchronization: The client must wait for a response from the server and cannot do anything else while waiting
- asynchronous: Instead of waiting for a response from the server, the client can perform other operations while the server is processing the request.  
- meaning a user's web browser doesn't need to reload an entire web page when only a small portion of content on the page needs to change. One of the most ubiquitous examples of asynchronous updating is Google's “Google Suggest” feature.   

```
<script src="js/jquery-3.2.1.min.js"></script>
    <script>
        function fun(){
            $.ajax({
                url:"ajaxServlet",//request url
                type:"POST",//request method
                //data:"username=jack&age=23",
                data:{
                    "username":"jack",
                    "age":23
                },//request parameters
                success:function (data) {
                    alert(data)
                },//callback
                error:function () {
                    alert("404 not found")
                },
                dataType:"text"
            });
        }
    </script>
```
```
$.get("ajaxServlet",{"username":"jack"},function () {
      alert("404 not found");
            },"text");
$.post("ajaxServlet",{"username":"jack"},function () {
       alert("404 not found");
       },"text");
```            
### JSON JavaScript object notation.  
- JSON is a syntax for storing and exchanging text information, similar to XML
- JSON is smaller, faster, and easier to parse than XML
```
var person={"name":"zhangsan","age":32};
      var persons={"persons":[{"name":"zhangs"},{"name":"Dsada"},{"name":"fadsgaf"}]};
      //alert(persons)
      var ps=[{"name":"zhangs"},{"name":"Dsada"},{"name":"fadsgaf"}];
```
```
 <script>
      var person={"name":"zhangsan","age":32};
      var name=person.name;
      alert(name);
      var persons={"persons":[{"name":"zhangs"},{"name":"Dsada"},{"name":"fadsgaf"}]};
      var name1=persons.persons[2].name;
      alert(name1);
      //alert(persons)
      var ps=[{"name":"zhangs"},{"name":"Dsada"},{"name":"fadsgaf"}];
      var name2=ps[1].name;
      alert(name2);
      alert(ps);
    </script>
```
```
for(var key in person){
   alert(key+":"+person[key]);
}
for(var i=0;i<ps.length;i++){
     var person=ps[i];
     for(var key in person){
     alert(key+":"+person[key]);
   }
}
```      
- JSON data and JAVA objects are converted to each other   
- jackson(The built-in parser for springmvc)
- Convert JAVA objects to JSON
  1. Import jackson jar packages
  2. Create the core jackson object objectmapper
  3. Invoke the related methods of the objectmapper for conversion
  4. @JsonIgnore || @JsonFormat(pattern="yyyy-MM-dd")
```
@Test
    public void test1() throws Exception {
       //create person object
       Person p = new Person("irene",40);
       //create jackson core object,ObjectMapper
        ObjectMapper mapper=new ObjectMapper();
        //conversion: convert object to string
        String s = mapper.writeValueAsString(p);
        System.out.println(s);
    }
```
```
public class Person {
    String name;
    int age;
    @JsonFormat(pattern = "yyyy-MM-dd")
    Date birthday;

    public Person(String name, int age,Date birthday) {
        this.name = name;
        this.age = age;
        this.birthday=birthday;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public Date getBirthday() {
        return birthday;
    }

    public void setBirthday(Date birthday) {
        this.birthday = birthday;
    }
}
@Test
    public void test1() throws Exception {
       //create person object
       Person p = new Person("irene",40,new Date());
       //create jackson core object,ObjectMapper
        ObjectMapper mapper=new ObjectMapper();
        //conversion: convert object to string
        String s = mapper.writeValueAsString(p);
        System.out.println(s);
    }
```
```
@Test//list converts to json
    public void test3() throws Exception {
        //create person object
        Person p = new Person("irene",40,new Date());
        Person p1 = new Person("irene1",40,new Date());
        Person p2 = new Person("irene2",40,new Date());
        List<Person> list=new ArrayList<>();
        list.add(p);
        list.add(p1);
        list.add(p2);
        //create jackson core object,ObjectMapper
        ObjectMapper mapper=new ObjectMapper();
        //conversion: convert object to string
        String s = mapper.writeValueAsString(list);
        System.out.println(s);
    }
    @Test//map converts to json
    public void test2() throws Exception {
        Map<String,Object> map = new HashMap<>();
        map.put("name","irene");
        map.put("age",20);
        //create jackson core object,ObjectMapper
        ObjectMapper mapper=new ObjectMapper();
        //conversion: convert object to string
        String s = mapper.writeValueAsString(map);
        System.out.println(s);
    }
```    
