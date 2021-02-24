FROM ubuntu:16.04 

MAINTAINER Amit Vashist <amitvashist7@outlool.com>

RUN apt-get update

RUN apt-get install apache2 -y 

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
