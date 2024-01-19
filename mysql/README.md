# MySQL

This is a Docker Compose file for a MySQL container based on the mysql image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a MySQL container. The image field specifies the Docker image to use for this service, which is set to mysql.
3. The environment section sets the username and password for the MySQL server, along with the name of the database to be created. You can customize these credentials to your preferences.
4. The volumes section mounts a directory called mariadb on the host to the /var/lib/mysql directory in the container, allowing you to persist data between container runs.
5. The ports section maps port 3306 of the host to port 3306 of the container, allowing you to access the MySQL server from your host machine.

# Usage

1. Save the docker-compose.yml file to your project's root directory.
2. Open a terminal window and navigate to the directory where you saved the Docker Compose file.
3. Run the command `docker-compose up` to start the MySQL container.
4. Once the container is running, you can access the MySQL server by connecting to port 3306 on the host machine using a web browser or a REST client like curl. The username and password for the MySQL server are specified in the environment section of the Docker Compose file.
5. To stop the MySQL container, run the command `docker-compose down`. This will stop and remove the containers created by the Docker Compose file.

Note that this Docker Compose file assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
