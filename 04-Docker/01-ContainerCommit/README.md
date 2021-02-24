# Run following Command inside. 

## docker run -it --name apache-test-1 ubuntu:16.04

```
root@containerid# apt-get update
root@containerid# apt-get install apache2 -y 
root@containerid# echo "Welcome to Docker Apache Container" >> /var/www/html/info.html
root@containerid# which apache2ctl 
root@containerid# echo "/usr/sbin/apache2ctl start" >> /root/.bashrc
root@containerid# CTL + P + Q 
```

# Run the following Command on Host
```
docker commit -p -m "My First Apache Server" test-apache-1 myapache-ubuntu-16.04:v1
docker images
docker run -itd --name test-apache-3 myapache-ubuntu-16.04:v1
docker inspect test-apache-3
curl <IP>/info.html
```
