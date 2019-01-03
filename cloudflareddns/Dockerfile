# Builds a docker image for CloudlFlare DDNS
FROM phusion/baseimage:0.9.18
MAINTAINER Tom Eaton <tom@eaton.network>
# Based on the work of Marcus Hughes <hello@msh100.uk>
# Updated in 2019 to use the new CloudFlare URL's.

#########################################
##        ENVIRONMENTAL CONFIG         ##
#########################################
# Set correct environment variables
ENV HOME="/root" LC_ALL="C.UTF-8" LANG="en_US.UTF-8" LANGUAGE="en_US.UTF-8"

# Use baseimage-docker's init system
CMD ["/sbin/my_init"]

#########################################
##    RUN  ENVIORMENT INSTALL SCRIPT   ##
#########################################
COPY install.sh /tmp/
RUN chmod +x /tmp/install.sh && sleep 1 && /tmp/install.sh && rm /tmp/install.sh

#########################################
##      ADD CLOUDFLARE UPDATE API      ##
#########################################
ADD updateip.php /root/
