# Next.js Docker Image

This is a Dockerfile for a Next.js application based on the official Next.js image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Next.js container. The image field specifies the Docker image to use for this service, which is set to nextjs/node:18-alpine as the base image and nextjs/base as the builder image.
3. The environment section sets the NEXT_TELEMETRY_DISABLED environment variable to 1 to disable telemetry during runtime.
4. The volumes section mounts a directory called nextjs on the host to the /app directory in the container, and another directory called public to the /public directory.
5. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start the Next.js container.
4. Once the container is running, you can access it by connecting to port 3000 of the host machine using a web browser or a REST client like curl.
5. To stop the Next.js container, run the command docker-compose down.
   Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
