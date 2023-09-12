# Base Image 
FROM ubuntu

# Update the APT Repo.
RUN apt-get update 

# Install Apache Packages 
RUN apt-get install apache2 -y 

# Bring up my apache app.
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"] 