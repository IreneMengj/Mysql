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
### v-bind.  
```
<div id="app">
        <img v-bind:src="imgSrc" alt="">
        <img :src="imgSrc" alt="" :title="imgTitle+'!!!'" :class="{active:isActive}" @click="togleActive">
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            el:"#app",
            data:{
               imgSrc:"http://www.itheima.com/images/logo.png",
               imgTitle:"heima programer",
               isActive:false
            },
            methods:{
                togleActive:function(){
                    this.isActive= !this.isActive
                }
            }

        })
    </script>
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
### v-on. 
```
<div id="app" class="app1">
        <input type="button" value="binding events" @click="doIT">
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            // el:"#app",
            el:".app1",
            methods: {
                doIT:function(){
                    alert("haha")
                }
            }
        })
    </script>
```    
```
   <div id="app" class="app1">
        <input type="button" value="binding events" @click="doIT">
        <input type="button" value="double click" @dblclick="doIT">
        <h2 @click="changeFood">{{food}}</h2>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            // el:"#app",
            el:".app1",
            data:{
                food:"tomato eggs"
            },
            methods: {
                doIT:function(){
                    alert("haha")
                },
                changeFood:function(){
                    this.food+=" so delicious!!!"
                }
            }
        })
    </script>
```    
### calculator. 
```
<div class="inputnum">
        <button @click="subtraction">-</button>
        <span>{{number}}</span>
        <button @click="addition">+</button>
    
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            el:".inputnum",
            data:{
                number:0
            },
            methods: {
                subtraction:function(){
                    if(this.number==0){
                        alert("number can't be less than 0");
                    }else{
                        this.number-=1;
                    }
                   
                },
                addition:function(){
                    if(this.number==9){
                        alert("number can't be over 10");
                    }else{
                        this.number+=1;
                    }
                }
            }
        })
    </script>
```
### v-show
```
<div id="app">
        <input type="button" value="click me" @click="changeIsShow">
        <img v-show="isShow" src="/Users/mengjiayu/Desktop/1.jpeg" alt="">
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            el:"#app",
            data:{
                isShow:ture
            },
            methods:{
                changeIsShow:function(){
                    this.isShow = !this.isShow;
                }
            },

        })
```
### v-if   
```
 <div id="app">
        <p v-if="true">heihei</p>
        <input type="button" value="clickme" @click="change"></input>
        <p v-if="isShow" >haha</p>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app= new Vue({
            el:"#app",
            data:{
                isShow:true
            },
            methods:{
                change:function(){
                    
                    this.isShow= !this.isShow
                    
                }
            }

        })
    </script>
```    
