FROM ubuntu:16.04 

MAINTAINER Amit Vashist <amitvashist7@outlook.com>

RUN apt-get update

RUN apt-get install apache2 -y 

COPY sample.html /var/www/html/info.html

EXPOSE 80
EXPOSE 3306

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
