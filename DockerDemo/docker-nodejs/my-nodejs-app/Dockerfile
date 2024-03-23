# Create a node image from an official node.js base image from the docker hub
FROM node:lts-alpine3.19
# Define a working directory inside the container
WORKDIR /app 
# Copy package.json and package-lock.json to the container
COPY . /app 
# Install application dependencies
RUN npm install
# Expose a port to see the port the application runs on
EXPOSE 3000
# Specify the command to run when the container starts
CMD node index.js 

