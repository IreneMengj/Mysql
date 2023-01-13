## Mysql master-slave replication
<img src="https://devopscube.com/wp-content/uploads/2019/09/unnamed-2048x1024.png.webp">
1.master records data changes to binary log
2.slave copies binary log to its own relay log
3.slave replays events in relay log and applies changes in its own database

## How to realize master-slave replication using docker on mac
I have been stuck for three days. Finally it works out&#x1F600;<br>
https://blog.csdn.net/qq_55022037/article/details/116140174<br>
I followed steps as this blog said! It finally succeeded!!<br>
During the first time, I used mysql 8.0+version. Slave_IO_Running showed "no" or "connecting".
This time I changed mysql version to 5.7 and set static IP address. I think this point plays a role. 
~~~
docker network create --subnet=172.172.0.0/16 docker-static
~~~

Then I started to perform read-write separation.Here I met a proble saying:Communications link failure. I searched through google and found one article might be useful:https://blog.csdn.net/izibeike/article/details/79366607
I changed mysql configuration as this artical said. It didn't work. So I think the reason why my read-write separation didn't work is probably caused by the conflict of mysql version. local version:8+ but docker version 5.7


