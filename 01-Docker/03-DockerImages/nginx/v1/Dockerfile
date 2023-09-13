# Base Image 
FROM ubuntu:jammy 

# MAINTAINER Info 
MAINTAINER Amit Vashist <amitvashist7@outlook.com>

# APT Repo Update
RUN  apt-get update 

# Install Nginx Packages 
RUN apt-get install nginx -y 

# Excute the following command whereever container created
CMD ["/usr/sbin/nginx", "-g", "daemon off;"] 
