# Docker DevServices

> This is derived from the [Confluent cp-all-in-one](https://github.com/confluentinc/cp-all-in-one) repository.

DevServices is a Docker compose project for quick local setup of local development services such as Kafka, AKHQ, MinIO S3, and various databases.

*Services:*

- Kafka in KRaft mode
- Schema Registry
- AKHQ
- Kafka Topology Builder / JulieOps
- Kafka Connect
- ksqlDB Server
- ksql Datagen
- Kafka REST Proxy
- MinIO S3 bucket storage
- Postgres Database
- MSSQL Database

## Usage

### Running DevServices

```bash
docker compose up -d
```

This command will run the default services.
See [Profiles](#profiles) for information on how to run additional services.

*Default Services:*

- Kafka in KRaft mode
- Schema Registry
- AKHQ

### Profiles

If you want to run other services in addition to the default ones, simply add the respective profile.

| Profile           | Containers                |
|-------------------|---------------------------|
| ktb               | Kafka Topology Builder    |
| kafka-extended    | Additional Kafka Services |
| s3                | MinIO S3 bucket storage   |
| postgres          | Postgres Database         |
| mssql             | MSSQL Database            |

Example:

```bash
docker compose --profile mssql up -d
```

To run multiple profiles use multiple `--profile` flags:

```bash
docker compose --profile s3 --profile mssql up -d
```

### Stopping DevServices

```bash
docker compose down -v
```

Remember to also add the profiles used in the `up` command to your `down` command, e.g. `docker compose --profile mssql down -v`

> :warning: Adding the `-v` flag will delete all volumes created by DevServices.
If you want to persist the data in the databases and MinIO S3 buckets, remove the `-v` flag from the command.

## Services

### Kafka in KRaft mode

Bootstrap server: `localhost:9092`

### Schema Registry

Schema registry URL: `http://localhost:8081`

### AKHQ

URL: `locahost:8084`

### Kafka Topology Builder / JulieOps

The topology file is located in `ktb/topology.yml`.

> Feel free to change it to match your desired topology.

### Kafka Connect

### ksqlDB Server

### ksql Datagen

### Kafka REST Proxy

### MinIO S3 bucket storage

Username: `local-user`

Password: `local-password`

> Feel free to change these in the `docker-compose.yml` file.

### Postgres Database

Username: `postgres`

Password: `local-password`

> Feel free to change these in the `docker-compose.yml` file.

### MSSQL Database

Username: `sa`

Password: `local-password123`

> Feel free to change these in the `docker-compose.yml` file.
