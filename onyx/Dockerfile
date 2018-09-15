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

# Setup supervisord
CMD /usr/bin/supervisord -c /etc/supervisor/conf.d/supervisord.conf
