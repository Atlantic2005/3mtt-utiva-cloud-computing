## Creating an Apache (HTTP) Image with a Dockerfile

#Use an official Apache (httpd) as the base image 
FROM httpd:alpine3.19

#copy the website template files (in current directory ".") to the container's document root
COPY . /usr/local/apache2/htdocs/