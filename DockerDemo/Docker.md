# What is Docker?
### Docker is an open source software for packaging software (developing, shipping and runnning) and ensure the application can run on any Operating system (OS). Docker enables a separation of applications from infrastructure to ensure software are delivered quickly. To understand how the process works, there are 3 things to know
1. Dockerfile: A Dockerfile (created with a capital "D" and without an extension) is a blueprint or configuration file for building a docker image. 
2. Image: A docker image is a temporary file for running a docker container.
Container: A docker container is a running process or a running environment for docker images.

#### A sample Dockerfile
A developer who creates a software can replace the build environment with a Dockerfile like the one below which is for a node.js application.
    
        FROM node:12
        WORKDIR /app
        COPY package*.jason ./
        RUN npm install
        COPY . .
        ENV PORT=8080
        EXPOSE 8080
        CMD [ "npm", "app.js" ]

Above Dockerfile configuration can be used to build a docker image.

# How to Build a Docker Image from a Dockerfile (A Single Stage Dockerfile)
1. Install a docker engine
2. Create a folder for your app or website and change into the folder
3. Create a Dockerfile in the newly created app folder. 
4. Configure the Dockerfile with commands and arguments as specified in the docker documentation
5. Transfer the web file or app into the app folder
6. Use below CLI commands to build a dcoker image

        $ docker build -t [image_name]:tag .
        * "-t" is for naming your image
        * "tag" is for the version reference
        * "." refers to current directory where    
        the Dockerfile is placed.
    
7. To view or print on the screen a list of all the docker images, use below command

        $ docker images OR  $ docker image ls

8. To run a docker container with any of the docker images, use below command

        $ docker run -d --name [container_name] -p 
          8080:80 [image_name]:tag
        * "-d" will ensure the container runs in a 
          detached mode and allow the terminal to 
          be used for other commands
        * "-p" is for defining port to open on the 
          host machine and the container port.

    If the container runs successfully, a unique hashes, called SHA, will be generated and printed on the screen.

9. To view running containers on the screen, use the command below

        $ docker ps

10. To view a list of all containers (runnind and stopped), use 

        $docker ps -a



## Reference for further reading:

https://hub.docker.com/



    




    
