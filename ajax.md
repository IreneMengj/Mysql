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
