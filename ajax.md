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
