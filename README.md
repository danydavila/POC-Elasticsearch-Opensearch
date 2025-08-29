## Opensearch or Elasticsearch POC

This proof-of-concept runs a standalone **OpenSearch** or **Elasticsearch** instance in Docker
without Dashboard (Kibana).
It is intended for **local development only**.

---

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running.
  Make sure the Docker Engine is available before starting the containers.


1. **Build** the container images

```bash
docker compose build
```

2. **Start** the container (detached, stays running):
```bash
docker compose up -d
```

### Test with curl

```bash
curl -u 'elastic:My!awesomePassword@2025' http://localhost:9207
```

Expected:

```json
{
  "name" : "es-standalone",
  "cluster_name" : "es-standalone",
  "cluster_uuid" : "8SucZWoPQpKTrCWgkKwt1g",
  "version" : {
    "number" : "8.15.0",
    "build_flavor" : "default",
    "build_type" : "docker",
    "build_date" : "2024-08-05T10:05:34.233336849Z",
    "build_snapshot" : false,
    "lucene_version" : "9.11.1",
    "minimum_wire_compatibility_version" : "7.17.0",
    "minimum_index_compatibility_version" : "7.0.0"
  },
  "tagline" : "You Know, for Search"
}
```