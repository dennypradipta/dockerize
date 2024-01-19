# Vite React

This is a Dockerfile for building and deploying a web application using React and Nginx. The following instructions are included:

1. Use the FROM directive to specify the base image for the builder stage. In this case, we use node:18-alpine.
2. Set the work directory to /usr/src using the WORKDIR directive. This is where all the files will be copied and built.
3. Define build time variables, reading from build-args. The BASE_URL variable specifies the base URL for the application, and the NODE_ENV variable specifies the environment in which the application is being built.
4. Set the build time environment variables by using the ENV directive. This ensures that the values of the BASE_URL and NODE_ENV variables are available during the build process.
5. Copy all files from the current directory to the work directory using the COPY directive. This includes both the source code and any other necessary files.
6. Install frontend dependencies and build the application by running npm install --prefer-offline and npm run build in the builder stage. This builds the application into a production-ready state.
7. Use the FROM directive to specify the base image for the serving stage. In this case, we use nginx:alpine.
8. Set the work directory to /usr/src/app using the WORKDIR directive. This is where the built application will be deployed.
9. Copy the built files from the builder stage to the Nginx server directory using the COPY directive. This ensures that the built application is available for serving through Nginx.
10. Copy the nginx configuration file from the docker/nginx directory to the appropriate location in the Nginx server's configuration directory using the COPY directive. This configures the Nginx server to serve the application correctly.
11. Expose port 80 for Nginx using the EXPOSE directive. This allows other containers or services to communicate with the application through this port.
12. Set the command for running Nginx by using the CMD directive. In this case, we use nginx -g daemon off; to start Nginx in standalone mode, which means it will not be managed by a process manager like systemd.

# Usage

1. Save the Dockerfile to a file named Dockerfile or any other name of your choice.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Build the Docker image by running the command docker build -t my-webapp . This will create a new Docker image named my-webapp based on the instructions in the Dockerfile.
4. Once the image is built, you can run it using docker run -p 80:80 my-webapp. This will start a new container of the web application and map port 80 of the host machine to port 80 of the container, allowing you to access the application through a web browser or REST client like curl.
5. To stop the running container, run the command docker stop my-webapp.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
