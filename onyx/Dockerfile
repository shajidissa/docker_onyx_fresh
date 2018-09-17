############################################################
# Dockerfile to build Onyx
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM java:8

MAINTAINER Saj Issa <saj.issa@gmail.com>

################## BEGIN INSTALLATION ######################


RUN apt-get update && \
    apt-get -y upgrade && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install curl wget git vim unzip mysql-server ntp cron supervisor ssmtp maven && \
    apt-get clean

RUN mkdir /usr/local/tomcat
RUN wget http://www-us.apache.org/dist/tomcat/tomcat-8/v8.5.34/bin/apache-tomcat-8.5.34.tar.gz -O /tmp/tomcat.tar.gz
RUN cd /tmp && tar xvfz tomcat.tar.gz
RUN cp -Rv /tmp/apache-tomcat-8.5.34/* /usr/local/tomcat/
RUN wget https://github.com/obiba/onyx-demo/archive/master.zip -O /tmp/master.zip

EXPOSE 8080
CMD /usr/local/tomcat/bin/catalina.sh run

# Setup supervisord
# CMD /usr/bin/supervisord -c /etc/supervisor/conf.d/supervisord.conf
