# Kafka Connect + JDBC Connector + Heroku Data

## Getting Started

### Prerequisites

**Addons**
* Heroku Postgres Addon
* Heroku Kafka Addon

**Kafka Topics**
For each Postgres Table that is being sync'd, you will need to create an associated
Kafka topic using the naming scheme `pg-<table_name>`.

**Kafka Consumer Group**
You will also need to create the Consumer Group `kafka-connect`

### Config Vars

* `KAFKA_ADDON`
* `POSTGRES_ADDON`
* `TRUSTSTORE_PASSWORD`
* `KEYSTORE_PASSWORD`

### Buildpacks

* Apt: `https://github.com/heroku/heroku-buildpack-apt`
* JVM: `heroku/jvm`

### Setup

heroku buildpacks:add --index 1 heroku-community/apt
heroku buildpacks:add heroku/jvm