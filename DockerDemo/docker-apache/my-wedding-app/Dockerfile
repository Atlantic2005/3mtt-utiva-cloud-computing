## Creating an Apache HTTP Server Image withdocker pull httpd:alpine3.19docker pull httpd:alpine3.19 a Dockerfile

#Use an official Apache (httpd) image as the base image 
FROM httpd:alpine3.19

#copy the website template files (in current directory ".") to the container's document root
COPY . /usr/local/apache2/htdocs/

#Expose port 80 for HTTP traffic
EXPOSE 80
