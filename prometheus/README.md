# Prometheus

This is a Dockerfile for a Prometheus container based on the prom/prometheus image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Prometheus container. The image field specifies the Docker image to use for this service, which is set to prom/prometheus.
3. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.
4. The volumes field mounts a directory called prometheus-config from the host to /etc/prometheus in the container. This allows you to configure Prometheus using a custom configuration file located at ./prometheus-config/prometheus.yml.
5. The volumes field also mounts a directory called prometheus-data from the host to /prometheus in the container. This allows you to store Prometheus data files, such as alerts and rules, at ./prometheus-data/alertmanager.yml.
6. The ports field maps port 9090 of the host to port 9090 of the container, allowing you to access the Prometheus web interface at http://localhost:9090.
7. The command field specifies two arguments for the container: --config.file=/etc/prometheus/prometheus.yml and --web.config.file=/etc/prometheus/web.yml. These arguments instruct Prometheus to use the specified configuration files for its configuration and web interface settings.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start the Prometheus container.
4. Once the container is running, you can access it by connecting to port 9090 on the host machine using a web browser or a REST client like curl. The Prometheus web interface can be found at http://localhost:9090, where you can configure and manage the Prometheus instance.
5. To stop the Prometheus container, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
