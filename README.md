# PostgreSQL Docker Setup

This repository contains a Docker Compose configuration for setting up a PostgreSQL database using Docker.

## Prerequisites

- Docker installed on your machine
- Docker Compose installed on your machine

## Getting Started

### Clone the Repository

Clone this repository to your local machine:

```bash
git clone <repository-url>
cd <repository-directory>
```

### Docker Compose Configuration

The `docker-compose.yml` file is configured to set up a PostgreSQL container with the following details:

- **Container Name:** `db`
- **Image:** `postgres:13`
- **Restart Policy:** `always`
- **Environment Variables:**
  - `POSTGRES_USER: root`
  - `POSTGRES_PASSWORD: root`
- **Ports:** `5432:5432`
- **Volumes:** `pg-dataset:/var/lib/postgresql/data`

### Volumes

A Docker volume named `pg-dataset` is used to persist the PostgreSQL data.

### Starting the Container

To start the PostgreSQL container, navigate to the directory containing the `docker-compose.yml` file and run:

```bash
docker-compose up -d
```

This command will start the container in detached mode.

### Stopping the Container

To stop the PostgreSQL container, run:

```bash
docker-compose down
```

### Accessing PostgreSQL

Once the container is running, you can connect to the PostgreSQL database using a client of your choice (e.g., `psql`, DBeaver, PgAdmin) with the following credentials:

- **Host:** `localhost`
- **Port:** `5432`
- **Username:** `root`
- **Password:** `root`

### Persistent Data

The PostgreSQL data is stored in a Docker volume named `pg-dataset`, which ensures that the data persists even if the container is removed or recreated.

## Troubleshooting

- Ensure that Docker and Docker Compose are correctly installed and running.
- Check the container logs for any errors:

```bash
docker-compose logs db
```

- If the container fails to start, ensure that the specified ports are not in use by other services on your host machine.

## References

- [PostgreSQL Docker Image Documentation](https://hub.docker.com/_/postgres)

## License

This project is licensed under the MIT License.
```

This `README.md` file provides detailed instructions on how to set up and use the PostgreSQL Docker container, including prerequisites, starting and stopping the container, accessing the database, and troubleshooting.
