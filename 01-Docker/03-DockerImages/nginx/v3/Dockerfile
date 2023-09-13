# Base Image 
FROM ubuntu:jammy 

# MAINTAINER Info 
MAINTAINER Amit Vashist <amitvashist7@outlook.com>

# APT Repo Update
RUN  apt-get update 

# Install Nginx Packages 
RUN apt-get install nginx -y 

# Deploy a custom webpage
COPY info.html /var/www/html/info.html

# Expos 
EXPOSE 80 

# Excute the following command whenever container created
CMD ["/usr/sbin/nginx", "-g", "daemon off;"] 
