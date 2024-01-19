# MariaDB

This is a Dockerfile for a MariaDB container based on the mariadb image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a MariaDB container. The image field specifies the Docker image to use for this service, which is set to mariadb.
3. The environment section sets the username and password for the database, and the ports section maps port 3306 of the host to port 3306 of the container. Finally, the volumes section mounts a directory called mariadb on the host to the /var/lib/mysql directory in the container.
4. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start the MariaDB container.
4. Once the container is running, you can access it by connecting to port 3306 on the host machine using a web browser or a REST client like curl. The username and password for the database are specified in the environment section of the Dockerfile.
5. To stop the MariaDB container, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
