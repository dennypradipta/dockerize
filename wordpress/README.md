# WordPress

This is a Docker Compose file for running a WordPress container using the wordpress:latest image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a WordPress container. The image field specifies the Docker image to use for this service, which is set to wordpress:latest.
3. The ports section maps port 8000 of the host to port 80 of the container, allowing you to access the WordPress server through a web browser or REST client like curl.
4. The restart field is set to always. This means that if the container is stopped, it will automatically start again.
5. The volumes section mounts a directory called wordpress on the host to the /var/www/html directory in the container. This allows data to persist even if the container is stopped and restarted.
6. The environment section sets the credentials for the WordPress database, including the host, user, password, and name. You can modify these values according to your needs.

# Usage

1. Save the Docker Compose file to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Docker Compose file.
3. Run the command docker-compose up to start the WordPress container.
4. Once the container is running, you can access it by connecting to port 8000 on the host machine using a web browser or a REST client like curl. The username and password for the database are specified in the environment section of the Docker Compose file.
5. To stop the WordPress container, run the command docker-compose down.

Note that this Docker Compose assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
