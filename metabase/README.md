# Metabase

This is a Dockerfile for a Metabase application based on the official Metabase image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Metabase container. The image field specifies the Docker image to use for this service, which is set to metabase/metabase:latest.
3. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.
4. The ports section maps port 3000 of the host to port 3000 of the container.
5. The environment section sets various environment variables for connecting to a Postgres database, such as MB_DB_TYPE, MB_DB_DBNAME, MB_DB_PORT, MB_DB_USER, and MB_DB_PASS.
6. The volumes section mounts a directory called metabase on the host to the /metabase-data directory in the container.

# Postgres

This is a Dockerfile for a Postgres database based on the official PostgreSQL image. The following instructions are included:

1. Use the version directive to specify the version of the Docker Compose file format that this file uses. In this case, we use version 3.
2. Define a service for a Postgres container. The image field specifies the Docker image to use for this service, which is set to postgres.
3. The restart field is set to unless-stopped. This means that if the container is stopped, it will not be restarted unless it is manually started or the Docker daemon is restarted.
4. The ports section maps port 5432 of the host to port 5432 of the container.
5. The environment section sets various environment variables for configuring the Postgres database, such as POSTGRES_DB, POSTGRES_USER, and POSTGRES_PASSWORD.
6. The volumes section mounts a directory called postgres on the host to the /var/lib/postgresql/data directory in the container.

# Usage

1. Save the Dockerfile to a file named docker-compose.yml.
2. Open a terminal window and navigate to the directory where you saved the Dockerfile.
3. Run the command docker-compose up to start both Metabase and Postgres containers.
4. Once the containers are running, you can access the Metabase application by connecting to port 3000 of the host machine using a web browser or a REST client like curl.
5. To stop both containers, run the command docker-compose down.

Note that this Dockerfile assumes that you have already installed Docker on your system. If you haven't, you can download it from https://docs.docker.com/get-docker/.
