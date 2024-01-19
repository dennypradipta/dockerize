# Promtail

This is a Dockerfile for a Promtail container based on the grafana/promtail image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Promtail container. The image field specifies the Docker image to use for this service, which is set to grafana/promtail.
3. The environment section sets the username and password for the database, and the ports section maps port 9090 of the host to port 9090 of the container. Finally, the volumes section mounts a directory called promtail-data on the host to the /etc/promtail directory in the container.
4. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.

# Usage

To use this Dockerfile, follow these steps:

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
   R3. un the command docker-compose up to start the Promtail container.
3. Once the container is running, you can access it by connecting to port 9090 on the host machine using a web browser or a REST client like curl. The username and password for the database are specified in the environment section of the Dockerfile.
4. To stop the Promtail container, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
