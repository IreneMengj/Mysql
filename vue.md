```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Vue</title>
</head> 
<body>
    <div id="app" class="app1">
        <!-- {{message}}
        {{school.name}}{{school.mobile}}
        {{campus}}{{campus[0]}} -->
        
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            // el:"#app",
            el:".app1",
            data:{
                message:"hello",
                school:{
                    "name":"haha",
                    "location":"beijing",
                    "mobile":5432
                },
                campus:["hefdsa","fwef","fewfer"]
            }
        })
    </script>
</body>   
</html>
```
### v-text.  
```
<body>
    <div id="app" class="app1">
        <h2>shenzhen{{message+"!"}}</h2>
        <h2 v-text="message"></h2>
        
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            // el:"#app",
            el:".app1",
            data:{
                message:"hello",
                
            }
        })
    </script>
</body>   
```
### v-html
```
<body>
    <div id="app" class="app1">
        <p v-html="content"></p>
        <p v-text="content"></p>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            // el:"#app",
            el:".app1",
            data:{
                content:"<a href='http://www.baidu.com'>heima</a>",
            }
        })
    </script>
</body>   
```
