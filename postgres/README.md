# PostgreSQL

This is a Dockerfile for a PostgreSQL container. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a PostgreSQL container. The image field specifies the Docker image to use for this service, which is set to postgres.
3. Set the container_name field to "postgres", allowing you to easily reference this container in other parts of your Docker Compose file or scripts.
4. Map port 5432 of the host to port 5432 of the container, allowing you to access the PostgreSQL server from your host machine.
5. Set the environment variables for the PostgreSQL server credentials, including the password, username, and database name. You can customize these credentials to your preferences.
6. Mount a directory called data on the host to the /var/lib/postgresql/data directory in the container, allowing you to persist data between container runs.
7. Set the restart policy for this container to "unless-stopped", ensuring that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.

# Usage

1. Save the docker-compose.yml file to your project's root directory.
2. Open a terminal window and navigate to the directory where you saved the docker-compose.yml file.
3. Run the command `docker-compose up` to start the PostgreSQL container.
4. Once the container is running, you can access the PostgreSQL server by connecting to port 5432 on the host machine using a web browser or a REST client like curl. The username and password for the PostgreSQL server are specified in the environment section of the docker-compose.yml file.
5. To stop the PostgreSQL container, run the command `docker-compose down`. This will stop and remove the containers created by the Docker Compose file.

Note that this Docker Compose file assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
