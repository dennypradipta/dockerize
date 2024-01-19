# TimescaleDB

This is a Docker Compose file for a TimescaleDB container based on the timescaledb image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a TimescaleDB container. The image field specifies the Docker image to use for this service, which is set to timescaledb
3. The container_name field specifies a name for the container, which in this case is set to symon-sass-timescaledb.
4. The ports section maps port 5432 of the host to port 5432 of the container, allowing you to access the TimescaleDB server through a web browser or REST client like curl.
5. The environment section sets the credentials for the database, including the password and username. You can modify these values according to your needs.
6. The volumes section mounts a directory called timescale on the host to the /var/lib/postgresql/data directory in the container. This allows data to persist even if the container is stopped and restarted.
7. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.

# Usage

1. Save the Docker Compose file to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Docker Compose file.
3. Run the command docker-compose up to start the TimescaleDB container.
4. Once the container is running, you can access it by connecting to port 5432 on the host machine using a web browser or a REST client like curl. The username and password for the database are specified in the environment section of the Docker Compose file.
5. To stop the TimescaleDB container, run the command docker-compose down.

Note that this Docker Compose assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
