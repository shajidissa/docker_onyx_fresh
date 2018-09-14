############################################################
# Dockerfile to build Redcap
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM java:7

MAINTAINER Saj Issa <saj.issa@gmail.com>

################## BEGIN INSTALLATION ######################


RUN apt-get update && \
    apt-get -y upgrade && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install apache2 php7.0  php7.2-mysql  php7.2-curl  php7.2-json libapache2-mod-php7.2  php7.2-zip php7.2-gd php-pear curl phpmyadmin libpcre3-dev wget git vim unzip mysql-server ntp cron supervisor ssmtp maven && \
    apt-get clean

# Setup supervisord
CMD /usr/bin/supervisord -c /etc/supervisor/conf.d/supervisord.conf
