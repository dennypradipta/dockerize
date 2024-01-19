# Prometheus Node Exporter

This is a Dockerfile for a Prometheus Node Exporter container based on the node-exporter image from quay.io/prometheus. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Prometheus Node Exporter container. The image field specifies the Docker image to use for this service, which is set to quay.io/prometheus/node-exporter:latest.
3. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.
4. The command field specifies a command to run on the container, which in this case sets the path.rootfs to /host using the --path.rootfs=/host flag.
5. The network_mode field is set to "host", which allows the container to communicate with the host system using the host's network stack.
6. The pid field is set to "host", which means that the container will use the host system's PID namespace.
7. The volumes field mounts the root filesystem of the host (/) to /host in the container with read-only access and read/write slave access.
8. The ports field maps port 9100 of the host to port 9100 of the container.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start the Prometheus Node Exporter container.
4. Once the container is running, you can access it by connecting to port 9100 on the host machine using a web browser or a REST client like curl.
5. To stop the Prometheus Node Exporter container, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
