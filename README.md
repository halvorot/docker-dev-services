# DevServices

This is derived from the [Confluent cp-all-in-one](https://github.com/confluentinc/cp-all-in-one) repository.

*Services:*

- Kafka in KRaft mode
- Schema Registry
- AKHQ
- Kafka Topology Builder
- Kafka Connect
- ksqlDB Server
- ksql Datagen
- Kafka REST Proxy
- Oracle Database
- MSSQL Database
- MinIO S3 bucket storage

## Usage

### Running DevServices

```
docker compose up -d
```

This command will run the default services.
See [Profiles](#profiles) for information on how to run additional services.

*Default Services:*

- Kafka in KRaft mode
- Schema Registry
- AKHQ
- MinIO S3 bucket storage

### Profiles

Default: Kafka in KRaft mode, Schema Registry, AKHQ, and MinIO S3.

| Profile           | Containers                |
|-------------------|---------------------------|
| ktb               | Kafka Topology Builder    |
| kafka-extended    | Additional Kafka Services |
| oracle            | Oracle Database           |
| mssql             | MSSQL Database            |

Example:

```
docker compose --profile mssql up -d
```

### Stopping DevServices

```
docker compose down -v
```

Remember to also add the started profiles to your command, e.g. `docker compose --profile mssql down -v`

> :warning: Adding the `-v` flag will delete all volumes created by DevServices.
If you want to persist the data in the databases and MinIO S3 buckets, remove the `-v` flag from the command.