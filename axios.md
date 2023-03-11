### get and post
```
  <input type="button" value="get" class="get">
  <input type="button" value="post" class="post">
    <!-- <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script> -->
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <script>
       document.querySelector(".get").onclick=function(){
        axios.get("https://autumnfish.cn/api/joke/list?num=6").then(function(response){
          console.log(response);
        },function(err){
          console.log(err);
        })
       }
       document.querySelector(".post").onclick=function(){
        axios.post("https://autumnfish.cn/api/user/reg123123",{username:"brocolli"}).then(function(response){
          console.log(response);
        },function(err){console.log(err);})
       }
    </script>
```
