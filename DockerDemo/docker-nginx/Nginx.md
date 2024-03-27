# How to Create an Nginx Docker Image With a Dockerfile

1. Install nginx on your linux, ubuntu, cestos, etc. machine or server
2. Create a new project folder or directory and change into it.
3. Download any web template of your choice and place in the project directory
4. Create a Dockerfile in the project directory where the web templates files are located. If the web template files are downloaded as a folder, your Dockerfile must be placed insde the folder. Below command can be used to create a the Dockerfile

        $ sudo touch Dockerfile

5. Configure the Dockerfile as shown below using an nginx base image from the docker official website. In this exercise, an alpine base image was selected due to its small size.

        # Using an official nginx as base image 
        
        FROM nginx:stable-alpine3.17-slim

        # Copying the website template files (in current directory ".") to the container's document root
        
        COPY . /usr/share/nginx/html

        # (Optional) Exposing port 8080 for HTTP traffic
        
        EXPOSE 8080

6. To build the nginx docker image, use this commands

        $ docker build -t my-nginx-img:v1 .

7. To view or print on the screen the list of all docker images, use this command
        
        $ docker images

### Output       
![alt text](my-nginx-img-cont-list.png)

7. To run the docker container for the apache2 image, use this command

$ sudo docker run -d --name my-nginx-cont -p 8080:80 my-nginx-img:v1

8. To view the list of docker containers currently running, use this command

        $ sudo docker ps

### Output
![alt text](my-nginx-img-cont-list.png)

### Viewing the nginx website on firefox browser on ubuntu linux machine
![Apache Website Dockerization](my-wedding-app.png)

9. To view the list of all docker images (running and stopped, use this command)

        $ sudo docker ps -a

10. To start [stop] a containers from running, use this command

        $ sudo docker start [stop] [container_ID or container_name]

11. To remove a docker image, use

        $ sudo docker rmi [image_name:tag]
        
12. To remove a docker container, use

        $ sudo docker rm [container_ID or container_name]


### END