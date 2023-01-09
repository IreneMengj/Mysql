# Mysql master-slave replication
<img src="https://devopscube.com/wp-content/uploads/2019/09/unnamed-2048x1024.png.webp">
1.master records data changes to binary log
2.slave copies binary log to its own relay log
3.slave replays events in relay log and applies changes in its own database
