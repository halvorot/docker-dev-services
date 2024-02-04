# DevServices

This is derived from the [Confluent cp-all-in-one](https://github.com/confluentinc/cp-all-in-one) repository.

## Usage

```
docker compose up -d
```

### Profiles

Default: Kafka in KRaft mode, Schema Registry, AKHQ, and MinIO S3.

| Profile           | Containers                |
|-------------------|---------------------------|
| ktb               | Kafka Topology Builder    |
| kafka-extended    | |
| oracle            | Oracle Database           |
| mssql             | MSSQL Database            |
