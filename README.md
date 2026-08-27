# Docker Compose PostgreSQL Setup

Ready-to-use Docker Compose setup for launching PostgreSQL database.

## Usage

### Setup

After cloning this repository, you must copy `env.example` to `.env` and customize it as needed. The file contains the following environment variables:

- `EXPOSE_DB`: The port on which PostgreSQL will be accessible
- `POSTGRES_DB`: The name of the PostgreSQL database to create
- `POSTGRES_MAX_CONNECTIONS`: The maximum number of connections for the PostgreSQL database
- `POSTGRES_PASSWORD`: The password for the PostgreSQL database
- `POSTGRES_USER`: The username for the PostgreSQL database
- `PROJECT_NAME`: The name of the project (used for naming the Docker containers)

### Startup

Once the secrets are generated and the `.env` file is configured, you can start the services by executing the following
command:

```bash
docker compose -f docker-compose.yml --env-file .env up -d
```

To stop the services, you can execute the following command:

```bash
docker compose -f docker-compose.yml --env-file .env down
```

To stop the services and remove the volumes, you can execute the following command:

```bash
docker compose -f docker-compose.yml --env-file .env down -v
```

To recreate the containers, you can execute the following command:

```bash
docker compose -f docker-compose.yml --env-file .env up -d --force-recreate
```

### Connexion

You can use a PostgreSQL client to connect to the database with the following parameters:

- Host: `localhost`
- Port: The value of `EXPOSE_DB` in the `.env` file
- Database: The value of `POSTGRES_DB` in the `.env` file
- Username: The value of `POSTGRES_USER` in the `.env` file
- Password: The value of `POSTGRES_PASSWORD` in the `.env` file
