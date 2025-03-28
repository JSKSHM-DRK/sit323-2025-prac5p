# Dockerized Web Application

This repository demonstrates how to dockerize a simple Node.js web application using Docker and Docker Compose. It includes step-by-step instructions for setting up and running the application inside a Docker container.

## Steps to Get Started

### Step 1: Install Docker

1. Install Docker from the [official Docker website](https://www.docker.com/get-started) based on your OS.
2. Verify the installation by running the following command:

   - bash
   - docker --version

### Step 2: Clone the Sample Web Application
- git clone https://github.com/your-repo/sample-web-app.git
- cd sample-web-app

### Step 3: Create a Dockerfile
```
# Use Node.js base image
FROM node:latest

# Set the working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy the application code
COPY . .

# Expose the application port
EXPOSE 3000

# Command to run the app
CMD ["node", "server.js"]
```

### Step 4: Build the Docker Image
- docker build -t my-web-app .

### Step 5: Test the Application
- docker ps
- docker logs <container_id>

### Step 6: Push the Docker Image to a Registry
#### login into docker hub
- docker login
#### tag the image
- docker tag my-web-app your-dockerhub-username/my-web-app
#### push respo into docker hub
- docker push your-dockerhub-username/my-web-app





