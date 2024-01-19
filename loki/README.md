# Loki

This is a Dockerfile for a Loki application based on the official Grafana image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Loki container. The image field specifies the Docker image to use for this service, which is set to grafana/loki.
3. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.
4. The ports section maps port 3100 of the host to port 3100 of the container.
5. The command field is set to -config.file=/etc/loki/local-config.yaml, which specifies that the Loki configuration file should be loaded from /etc/loki/local-config.yaml within the container.
6. The volumes section mounts a directory called loki-config.yaml on the host to the /etc/loki/local-config.yaml directory in the container and another directory called loki on the host to the /loki directory in the container.
7. The networks section connects the Loki container to the loki network.
8. The logging section is configured to send logs to the Loki server running on the host machine using the specified Loki-url and log size limits.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start the Loki container.
4. Once the container is running, you can access it by connecting to port 3100 of the host machine using a web browser or a REST client like curl.
5. To stop the Loki container, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
